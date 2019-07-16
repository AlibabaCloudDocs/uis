# GRE接入UIS {#task_1198721 .task}

本文介绍如何通过GRE协议实现终端接入UIS。

请确保满足以下条件：

-   您已经创建了UIS实例并添加了目标地址。详细信息，请参见[创建UIS实例](cn.zh-CN/用户指南/管理UIS实例/创建UIS实例.md#)和[添加目标地址](cn.zh-CN/用户指南/管理目标地址/添加目标地址.md#)。
-   您已经创建了节点并添加了节点IP地址。详细信息，请参见[创建节点](cn.zh-CN/用户指南/管理节点/创建节点.md#)和[添加节点IP地址](cn.zh-CN/用户指南/管理节点IP/添加节点IP地址.md#)。
-   您已经创建了连接。详细信息，请参见[创建连接](cn.zh-CN/用户指南/管理连接/创建连接.md#)。

本文以ECS实例（Ubuntu系统）搭建GRE网关为例，介绍私网IP 192.168.0.xx如何通过GRE网关接入阿里云UIS，访问公网47.254.87.xx。

![GRE接入UIS](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/908822/156328260751590_zh-CN.png)

1.  执行以下命令在ECS实例上搭建GRE网关。 

    ``` {#codeblock_iq5_lr5_1bj .lanuage-shell}
    modprobe ip_gre
    ip link add gre1 type gre local 172.16.254.xx remote 47.95.197.xx
    ip link set gre1 up
    ip addr add 10.0.1.xx/32 dev gre1
    ip addr add 192.168.0.xx/32 dev gre1
    ip route add 47.254.87.xx/32 dev gre1
    ```

    **说明：** 

    172.16.254.xx为云上ECS实例的弹性公网IP 39.106.5.208 对应的私网IP，线下IDC配置时需要根据设备是否在NAT设备后选择对应的IP。

2.  将GRE网关接入UIS服务（GO语言）。 

    **说明：** 需要将AK和KEY配置到环境变量ALICLOUD\_ACCESS\_KEY 和ALICLOUD\_SECRET\_KEY。

    ``` {#codeblock_sut_051_859 .lanuage-go}
    package main
    
    import (
        "encoding/json"
        "fmt"
        "log"
        "os"
        "strings"
    
        "github.com/aliyun/alibaba-cloud-sdk-go/sdk/requests"
        "github.com/aliyun/alibaba-cloud-sdk-go/services/uis"
    )
    
    //GreInfo struct
    type GreInfo struct {
        LocalIP          string `json:"localIp"`
        LocalTunnelIP    string `json:"localTunnelIp"`
        CustomerIP       string `json:"customerIp"`
        CustomerTunnelIP string `json:"customerTunnelIp"`
        CustomerSubnet   string `json:"customerSubnet"`
    }
    
    //DestinationInfo struct
    type DestinationInfo struct {
        Destination string `json:"destination"`
        AreaID      string `json:"areaId"`
    }
    
    const UisDomain = "uis.cn-hangzhou.aliyuncs.com"
    
    //CreateClient init client to operate all Api
    func CreateClient() (*uis.Client, error) {
        var accessKey string
        var secretKey string
        regionID := "cn-hangzhou"
        fmt.Printf("%s", os.Getenv("PATH"))
        if v := os.Getenv("ALICLOUD_ACCESS_KEY"); v != "" {
            accessKey = v
    
        }
        if v := os.Getenv("ALICLOUD_SECRET_KEY"); v != "" {
            secretKey = v
        }
    
        fmt.Printf("%s, %s, %s", accessKey, secretKey, regionID)
        client, err := uis.NewClientWithAccessKey(
            regionID,  // 地域ID
            accessKey, // 您的Access Key ID
            secretKey) // 您的Access Key Secret
        if err != nil {
            return nil, err
        }
        return client, nil
    }
    
    //CreateUis create Uis instance
    func CreateUis(client *uis.Client, name string, description string) (string, error) {
        request := uis.CreateCreateUisRequest()
        request.Domain = UisDomain
        request.Name = name
        request.Description = description
        request.RegionId = "cn-hangzhou"
    
        uisResponse, err := client.CreateUis(request)
        if err != nil {
            log.Println(err)
            return "", err
        }
        return uisResponse.UisId, nil
    }
    
    //CreateUisNode create uis node
    func CreateUisNode(client *uis.Client, uisID string, nodeAreaId string, bandwidth int) (string, error) {
        request := uis.CreateCreateUisNodeRequest()
        request.Domain = UisDomain
        request.UisNodeAreaId = nodeAreaId
        request.UisId = uisID
        if bandwidth != 0 {
            request.UisNodeBandwidth = requests.NewInteger(bandwidth)
        }
    
        response, err := client.CreateUisNode(request)
        if err != nil {
            fmt.Println("", err)
            return "", err
        }
        return response.UisNodeId, nil
    }
    
    //CreateUisConnection create uis connection
    func CreateUisConnection(client *uis.Client, uisNodeID string, protocol string, config string) (string, error) {
        request := uis.CreateCreateUisConnectionRequest()
        request.Domain = UisDomain
        request.UisNodeId = uisNodeID
        request.UisProtocol = protocol
    
        if request.UisProtocol == "GRE" {
            request.GreConfig = config
        }
        response, err := client.CreateUisConnection(request)
    
        if err != nil {
            log.Println(err)
            return "", err
        }
        return response.UisConnectionId, nil
    }
    
    //DescribeUisNodes Describe uis node
    func DescribeUisNodes(client *uis.Client, uisID string, uisNodeID string) (*uis.DescribeUisNodesResponse, error) {
        request := uis.CreateDescribeUisNodesRequest()
        request.Domain = UisDomain
        request.UisId = uisID
        request.UisNodeId = uisNodeID
    
        response, err := client.DescribeUisNodes(request)
        if err != nil {
            fmt.Println("DescribeUisNodes", err)
            return nil, err
        }
        return response, nil
    }
    
    ////AddHighPrioirtyIP  API
    func AddHighPrioirtyIP(client *uis.Client, uisID string, des []DestinationInfo) error {
        request := uis.CreateAddHighPriorityIpRequest()
        request.Domain = UisDomain
        request.RegionId = "cn-hangzhou"
        request.UisId = uisID
    
        highPrioriytIP, err := json.Marshal(des)
        if err != nil {
            log.Println(err)
            return err
        }
    
        request.HighPriorityIp = string(highPrioriytIP)
        _, err = client.AddHighPriorityIp(request)
    
        if err != nil {
            fmt.Println("AddHighPriorityIp", err)
            return err
        }
    
        return nil
    }
    
    //UisGreDemo Use the GRE type Uis connection
    func UisGreDemo() {
        client, err := CreateClient()
        if nil != err {
            return
        }
    
        uisID, err := CreateUis(client, "GRE_UIS", "GRE_UIS_DEMO")
        if err != nil {
            return
        }
        fmt.Println("uisID:", uisID)
    
        uisNodeID, err := CreateUisNode(client, uisID, "cn-hongkong", 50)
        if err != nil {
            return
        }
        fmt.Println("uisNodeID", uisNodeID)
    
        uisNodeList, err := DescribeUisNodes(client, uisID, uisNodeID)
        if err != nil {
            fmt.Println(err)
        }
        uisNode := uisNodeList.UisNodeList.UisNode[0]
    
        var greConfigs []GreInfo
        for _, item := range strings.Split(uisNode.UisNodeActiveIp, ",") {
            greConfig := GreInfo{
                LocalIP:          item,
                LocalTunnelIP:    "10.0.0.xx",
                CustomerIP:       "39.106.5.xx",
                CustomerTunnelIP: "10.0.1.xx",
                CustomerSubnet:   "192.168.0.0/24",
            }
            greConfigs = append(greConfigs, greConfig)
        }
        data, _ := json.Marshal(greConfigs)
    
        uisConnID, err := CreateUisConnection(client, uisNodeID, "GRE", string(data))
        fmt.Println(uisConnID)
    
        des := []DestinationInfo{
            DestinationInfo{
                Destination: "47.254.87.xx",
            },
        }
        err = AddHighPrioirtyIP(client, uisID, des)
        if err != nil {
            fmt.Println(err)
        }
    
        return
    }
    ```


