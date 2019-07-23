# DescribeUisConnections {#doc_api_Uis_DescribeUisConnections .reference}

调用DescribeUisConnections接口查看已创建的隧道连接信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeUisConnections&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUisConnections|要执行的操作。 取值：**DescribeUisConnections**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|RegionId|String|否|cn-hangzhou|地域ID。

 |
|UisConnectionId|String|否|UISCONN-xxxblu51boe75a1eb\*\*\*\*|要查看的隧道连接ID。

 |
|UisNodeId|String|否|UISNODE-xxxcp0zr5m2avmn2r\*\*\*\*|要查询的节点实例ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含多少条目。

 |
|RequestId|String|485997B0-3EB4-40B7-82D8-4A404EBFDB20|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |
|UisConnections| | |隧道连接列表的详细信息。

 |
|Description|String|connection description info|隧道连接的描述。

 |
|GreConfig|String|\[\{'localIp':'47.95.197.XX','localTunnelIp':'10.0.0.X','customerIp':'39.106.5.XX','customerTunnelIp':'10.0.0.X','customerSubnet':'192.168.X.X/24'\},\{'localIp':'47.94.219.XX','localTunnelIp':'10.0.0.X','customerIp':'39.106.5.XX','customerTunnelIp':'10.0.0.X','customerSubnet':'192.168.X.X/24'\}\]|在创建UIS Connection时，Protocol参数的值指定为**GRE**。

 GreConfig参数为结构体数组转成的JSON String，可以通过LocalIP来为每个UisNode的IP配置不同的GRE tunnel。

 结构体中的参数包含：

 -   **LocalIP**：UisNode的IP
-   **LocalTunnelIP**：UisNode的GRE Tunnel设备的IP
-   **CustomerIP**：客户的公网IP
-   **CustomerTunnelIP**：客户的GRE Tunnel设备的IP
-   **CustomerSubnet**：客户GRE的私网网段

 |
|Name|String|test\_conn|隧道连接的名称。

 |
|SslConfig|String|\{\\"cipher\\":\\"AES-128-CBC\\",\\"port\\":1194,\\"protocol\\":\\"udp\\"\}|SSL （OpenVPN）的配置信息。

 |
|State|String|running|隧道连接的状态：

 -   **init**：初始化
-   **configuring**：配置中
-   **deleted**：已删除

 |
|UisConnectionId|String|UISCONN-xxxblu51boe75a1eb\*\*\*\*|隧道连接的ID。

 |
|UisId|String|UIS-xxxbtfk761c670ok9\*\*\*\*|实例的ID。

 |
|UisNodeId|String|UISNODE-xxxcp0zr5m2avmn2r\*\*\*\*|节点实例的名称。

 |
|UisProtocol|String|SSLVPN|传入软件端与服务端使用的协议。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUisConnections
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUisConnectionsResponse>
      <PageNumber>1</PageNumber>
      <TotalCount>1</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>485997B0-3EB4-40B7-82D8-4A404EBFDB20</RequestId>
      <UisConnections>
            <UisConnection>
                  <Name>test_conn</Name>
                  <UisConnectionId>UISCONN-xxxblu51boe75a1eb****</UisConnectionId>
                  <UisNodeId>UISNODE-xxxcp0zr5m2avmn2r****</UisNodeId>
                  <SslConfig>{\"cipher\":\"AES-128-CBC\",\"port\":1194,\"protocol\":\"udp\"}</SslConfig>
                  <State>running</State>
                  <UisProtocol>SSLVPN</UisProtocol>
                  <UisId>UIS-xxxbtfk761c670ok9****</UisId>
                  <GreConfig>null</GreConfig>
            </UisConnection>
      </UisConnections>
</DescribeUisConnectionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"uisConnections":[
		{
			"uisProtocol":"SSLVPN",
			"greConfig":"null",
			"name":"test_conn",
			"uisNodeId":"UISNODE-xxxcp0zr5m2avmn2r****",
			"state":"running",
			"uisConnectionId":"UISCONN-xxxblu51boe75a1eb****",
			"uisId":"UIS-xxxbtfk761c670ok9****",
			"sslConfig":"{\"cipher\":\"AES-128-CBC\",\"port\":1194,\"protocol\":\"udp\"}"
		}
	],
	"totalCount":1,
	"requestId":"485997B0-3EB4-40B7-82D8-4A404EBFDB20",
	"pageSize":10,
	"pageNumber":1
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

