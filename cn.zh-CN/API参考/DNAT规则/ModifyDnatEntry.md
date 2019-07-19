# ModifyDnatEntry {#doc_api_Uis_ModifyDnatEntry .reference}

调用ModifyDnatEntry接口修改DNAT规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=ModifyDnatEntry)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisNodeId|String|是|UISNODE-xxxi9zyyd8seh8udp\*\*\*\*|UIS节点ID。

 |
|Action|String|否|ModifyDnatEntry|要执行的操作。 取值：**ModifyDnatEntry**。

 |
|DestinationIp|String|否|3.3.3.X|DNAT转换后的目标IP地址。

 |
|DestinationPort|Integer|否|8080|DNAT转换后的目标端口。-1代表所有端口。

 |
|IpProtocol|String|否|tcp|指定DNAT的协议，支持tcp、udp、icmp、any。当协议为any时，指定端口无效。

 |
|Name|String|否|TestModifyDnat|DNAT规则的名称。

 |
|OriginalIp|String|否|2.2.2.X|要转换的源IP地址。

 |
|OriginalPort|Integer|否|80|要转换的源端口。-1代表所有端口。

 |
|RegionId|String|否|cn-hangzhou|UIS实例所属的地域ID。

 |
|UisDnatId|String|否|UISDNAT-xxxs1yb3gtpxrfbbz\*\*\*\*|DNAT规则ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|AFCE5064-FD94-44E1-AD9E-BE1E23765CE6|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyDnatEntry
&UisNodeId=UISNODE-xxxi9zyyd8seh8udp****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyDnatEntryResponse>
  <RequestId>AFCE5064-FD94-44E1-AD9E-BE1E23765CE6</RequestId>
</ModifyDnatEntryResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"AFCE5064-FD94-44E1-AD9E-BE1E23765CE6"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

