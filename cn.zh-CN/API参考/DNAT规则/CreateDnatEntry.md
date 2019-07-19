# CreateDnatEntry {#doc_api_Uis_CreateDnatEntry .reference}

调用CreateDnatEntry接口在指定的UIS Node上配置DNAT规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=CreateDnatEntry)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateDnatEntry|要执行的操作。 取值：**CreateDnatEntry**。

 |
|DestinationIp|String|是|3.3.3.X|DNAT转换后的目标IP地址。

 |
|DestinationPort|Integer|是|8080|DNAT转换后的目标端口。-1代表所有端口。

 |
|IpProtocol|String|是|tcp|指定DNAT的协议，支持tcp、udp、icmp、any。当协议为any时，指定端口无效。

 |
|Name|String|是|dnatEntry1|DNAT规则的名称。

 |
|OriginalIp|String|是|2.2.2.X|要转换的源IP地址。

 |
|OriginalPort|Integer|是|80|要转换的源端口。-1代表所有端口。

 |
|UisNodeId|String|是|UISNODE-xxxpucur6tfhpzok5\*\*\*\*|UIS的节点ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|FC6EAEDF-72BC-4028-A622-63320AD1DEEF|请求ID。

 |
|UisDnatId|String|cgw-bp1aw0a5nfff03xp1\*\*\*\*|DNAT规则ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateDnatEntry
&DestinationIp=3.3.3.X
&DestinationPort=8080
&IpProtocol=tcp
&Name=dnatEntry1
&OriginalIp=2.2.2.X
&OriginalPort=80
&UisNodeId=UISNODE-xxxpucur6tfhpzok5****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateDnatEntryResponse>
  <UisDnatId>cgw-bp1aw0a5nfff03xp1****</UisDnatId>
  <RequestId>FC6EAEDF-72BC-4028-A622-63320AD1DEEF</RequestId>
</CreateDnatEntryResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UisDnatId":"cgw-bp1aw0a5nfff03xp1****",
	"RequestId":"FC6EAEDF-72BC-4028-A622-63320AD1DEEF"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Resource.QuotaFull|The resource quota is exceeded.|资源配额已满。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|
|403|Invalid.DnatEntry|The specified DNAT entry \(source IP, source port, and protocol\) already exists.|该Dnat条目（源IP、源端口和协议）已经存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

