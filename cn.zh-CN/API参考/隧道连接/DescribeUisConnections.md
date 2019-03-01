# DescribeUisConnections {#reference_ems_nyw_pfb .reference}

查看已创建的隧道连接信息。

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeUisConnections

 |
|UisConnectionId|String|是| 要查看的隧道连接ID。

 |
|UisNodeId|String|是| 要查询的节点实例ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|UisConnections|JSON String|隧道连接列表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|UisId|String|实例的ID。|
|UisNodeId|String|节点实例的名称。|
|UisConnectionId|String|隧道连接的ID。|
|UisProtocol|String|传入软件端与服务端使用的协议。|
|SslConfig|String|SSL （OpenVPN）的配置信息。|
|Name|String|隧道连接的名称。|
|Description|String|隧道连接的描述。|
|Status|Long|隧道连接的状态：-   init：初始化
-   configuring：配置中
-   deleted：已删除

|

|名称|类型|描述|
|:-|:-|:-|
|port|String|SSL-VPN服务端所使用的端口。|
|Proto|String|SSL-VPN服务端所使用的协议。|
|Cipher|String|使用的加密算法。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUisConnections
&UisNodeId=UISNODE-xxxcp0zr5m2avmn2rw2p7
&UisConnectionId=UISCONN-xxxblu51boe75a1ebj2y4
&Description=conn_desc
&Name=test_conn
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <DescribeUisConnectionsResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>485997B0-3EB4-40B7-82D8-4A404EBFDB20</RequestId>
        <UisConnections>
            <UisConnection>
                <Name>test_conn</Name>
                <UisConnectionId>UISCONN-xxxblu51boe75a1ebj2y4</UisConnectionId>
                <UisNodeId>UISNODE-xxxcp0zr5m2avmn2rw2p7</UisNodeId>
                <SslConfig>{\"cipher\":\"AES-128-CBC\",\"port\":1194,\"protocol\":\"udp\"}</SslConfig>
                <State>running</State>
                <UisProtocol>SSLVPN</UisProtocol>
                <UisId>UIS-xxxbtfk761c670ok94w1u</UisId>
                <GreConfig>null</GreConfig>
            </UisConnection>
        </UisConnections>
    </DescribeUisConnectionsResponse>
    ```

-   JSON格式

    ```
    {
        "pageNumber": 1, 
        "pageSize": 10, 
        "requestId": "485997B0-3EB4-40B7-82D8-4A404EBFDB20", 
        "totalCount": 1, 
        "uisConnections": [
            {
                "greConfig": "null", 
                "name": "test_conn", 
                "sslConfig": "{\"cipher\":\"AES-128-CBC\",\"port\":1194,\"protocol\":\"udp\"}", 
                "state": "running", 
                "uisConnectionId": "UISCONN-xxxblu51boe75a1ebj2y4", 
                "uisId": "UIS-xxxbtfk761c670ok94w1u", 
                "uisNodeId": "UISNODE-xxxcp0zr5m2avmn2rw2p7", 
                "uisProtocol": "SSLVPN"
            }
        ]
    }
    ```


