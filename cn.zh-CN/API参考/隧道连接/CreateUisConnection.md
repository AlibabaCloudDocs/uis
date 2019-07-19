# CreateUisConnection {#doc_api_Uis_CreateUisConnection .reference}

调用CreateUisConnection接口创建隧道连接。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=CreateUisConnection)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateUisConnection|要执行的操作。 取值：**CreateUisConnection**。

 |
|UisNodeId|String|是|UISNODE-xxxcp0zr5m2avmn2r\*\*\*\*|节点实例ID。

 |
|UisProtocol|String|是|SSLVPN|UIS实例软件端与服务端使用的协议名称。取值：**SSLVPN**/**GRE**/**SDK**。

 |
|Description|String|否|connection description|隧道连接的描述。

 |
|GreConfig|String|否|\[\{'localIp':'47.95.197.XX','localTunnelIp':'10.0.0.X','customerIp':'39.106.5.XX','customerTunnelIp':'10.0.0.X','customerSubnet':'192.168.X.X/24'\},\{'localIp':'47.94.219.XX','localTunnelIp':'10.0.0.X','customerIp':'39.106.5.XX','customerTunnelIp':'10.0.0.X','customerSubnet':'192.168.X.X/24'\}\]|在创建UIS Connection时，Protocol参数的值指定为**GRE**。

 GreConfig参数为结构体数组转成的JSON String，可以通过LocalIP来为每个UisNode的IP配置不同的GRE tunnel。

 结构体中的参数包含：

 -   **LocalIP**：UisNode的IP
-   **LocalTunnelIP**：UisNode的GRE Tunnel设备的IP
-   **CustomerIP**：客户的公网IP
-   **CustomerTunnelIP**：客户的GRE Tunnel设备的IP
-   **CustomerSubnet**：客户GRE的私网网段

 |
|Name|String|否|connection\_name|隧道连接的名称。

 |
|RegionId|String|否|cn-hangzhou|地域ID。

 |
|SslConfig|String|否|TCP|Protocol指定为OpenVPN协议时：

 -   **SSLConfig. Protocol**：SSL-VPN服务端所使用的协议。取值：**UDP（默认值） | TCP**。
-   **SSLConfig.Port**：SSL-VPN服务端所使用的端口，默认值为1194。端口范围1025-10000，以及避开以下知名端口[22, 2222, 22222, 9000, 9001, 9002, 7505, 80, 443, 53, 68, 123, 4510, 4560, 500, 4500](url)。
-   **SSLConfig.Cipher**：SSL-VPN使用的加密算法。取值：**AES-128-CBC（默认值） |AES-192-CBC | AES-256-CBC | none**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |
|UisConnectionId|String|UISCONN-xxxblu51boe75a1eb\*\*\*\*|VPN服务端的ID，此ID不区分协议。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUisConnection
&UisNodeId=UISNODE-xxxcp0zr5m2avmn2****
&UisProtocol=SSLVPN
&RegionId=cn-hangzhou
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateUisConnectionResponse>
  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
  <UisConnectionId>UISCONN-xxxblu51boe75a1eb****</UisConnectionId>
</CreateUisConnectionResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0",
	"uisConnectionId":"UISCONN-xxxblu51boe75a1eb****"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

