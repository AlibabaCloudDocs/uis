# ModifyUisConnectionAttribute {#doc_api_Uis_ModifyUisConnectionAttribute .reference}

调用ModifyUisConnectionAttribute接口修改隧道连接的配置信息。

 **** 

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=ModifyUisConnectionAttribute&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisConnectionId|String|是|UISCONN-xxxblu51boe75a1eb\*\*\*\*|要修改的隧道连接ID。

 |
|Action|String|否|ModifyUisConnectionAttribute|要执行的操作。 取值：**ModifyUisConnectionAttribute**。

 |
|Description|String|否|conn\_desc|隧道连接的描述。

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
|Name|String|否|test\_conn|隧道连接的名称。

 |
|RegionId|String|否|cn-hangzhou|地域ID。

 |
|SslConfig|String|否|\{\\”Port\\":1194,\\"Protocol\\":\\"UDP\\",\\"Cipher\\":\\"AES-256-CBC\\”\}|Protocal指定为OpenVPN协议时：

 -   SSLConfig. Proto：SSL-VPN服务端所使用的协议。取值：**UDP（默认值） | TCP**。
-   SSLConfig.Port：SSL-VPN服务端所使用的端口，默认值为1194。端口范围1025-10000，以及避开以下知名端口[22, 2222, 22222, 9000, 9001, 9002, 7505, 80, 443, 53, 68, 123, 4510, 4560, 500, 4500](url)。
-   SSLConfig.Cipher：SSL-VPN使用的加密算法。取值：**AES-128-CBC（默认值） |AES-192-CBC | AES-256-CBC | none**。

 |
|UisNodeId|String|否|UISNODE-xxxcp0zr5m2avmn2r\*\*\*\*|节点实例ID。

 |
|UisProtocol|String|否|SSLVPN|UIS实例软件端与服务端使用的协议名称。取值：**SSLVPN/GRE/SDK**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=ModifyUisConnectionAttribute
&UisConnectionId=UISCONN-xxxblu51boe75a1eb****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyUisConnectionAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyUisConnectionAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidProtocol|The specified protocol type is invalid.|无效的协议类型。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

