# DescribeUisNetworkInterfaces {#reference_dc3_z5d_bhb .reference}

调用DescribeUisNetworkInterfaces接口查询已创建的弹性网卡。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  DescribeUisNetworkInterfaces 

 |
|RegionId |String|否|UIS实例所在的地域ID。|
|UisNodeId |String|否|UIS节点ID。|
|UisEniId |String|否|UIS弹性网卡ID。|
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|
|TotalCount|String|列表条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
| NetworkInterfaces |List|查询到的弹性网卡列表，包含以下信息：-   Description：弹性网卡的描述信息。
-   IpAddress：弹性网卡的私网IP地址。
-   Log：弹性网卡创建失败的日志信息。
-   Name：弹性网卡的名称。
-   NetworkInterfaceId：弹性网卡的ID。
-   SecurityGroupID：弹性网卡绑定的安全组ID。
-   UisEniId：UIS弹性网卡的ID。
-   UisNodeId：绑定的UIS节点ID。
-   VswitchId：弹性网卡所属的交换机ID。

|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUisNetworkInterfaces
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```
{
    "PageNumber": 1,
    "TotalCount": 1,
    "PageSize": 10,
    "NetworkInterfaces": {
        "NetworkInterface": [
            {
                "Name": "TestCreateEni",
                "Description": "TestCreateEni",
                "UisEniId": "UISENI-xxxfunml63xpaz0tzbev0",
                "UisNodeId": "UISNODE-xxxccvrtiviatdroh92pm",
                "SecurityGroupID": "sg-m5eiigbzenfqcpdxxx",
                "State": "active",
                "VswitchId": "vsw-m5e1caexsmph0og6lis8h",
                "IpAddress": "192.168.XXX.XXX",
                "NetworkInterfaceId": "eni-m5e0hoi1xi93xxxxxx"
            }
        ]
    },
    "RequestId": "5B877E24-48C5-48F4-B3A6-43B61AC4FCBA"
}
```

