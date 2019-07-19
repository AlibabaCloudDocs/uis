# CreateUisNetworkInterface {#doc_api_Uis_CreateUisNetworkInterface .reference}

调用CreateUisNetworkInterface接口创建弹性网卡，并将已创建的弹性网卡绑定到UIS服务中。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=CreateUisNetworkInterface)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|SecurityGroupId|String|是|sg-m5eiigbzenfqcpdt\*\*\*\*|指定弹性网卡绑定的安全组ID。

 |
|UisNodeId|String|是|UISNODE-xxxdc9wyfmpf0tik5\*\*\*\*|指定弹性网卡绑定的UIS节点ID。

 |
|VswitchId|String|是|vsw-m5e1caexsmph0og6l\*\*\*\*|指定弹性网卡所在的VswitchID。

 |
|Action|String|否|CreateUisNetworkInterface|要执行的操作。 取值：**CreateUisNetworkInterface**。

 |
|Description|String|否|ENI for test|指定弹性网卡的描述。

 |
|IpAddress|String|否|192.168.XX.XX|指定弹性网卡的私网IP地址。

 |
|Name|String|否|TestUisENI|指定弹性网卡的名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|1736145F-B482-47E4-8BBF-7EEC38CC800B|请求ID。

 |
|UisEniId|String|cgw-bp1aw0a5nfff03xp1\*\*\*\*|弹性网卡的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateUisNetworkInterface
&SecurityGroupId=sg-m5eiigbzenfqcpdt****
&UisNodeId=UISNODE-xxxdc9wyfmpf0tik5****
&VswitchId=vsw-m5e1caexsmph0og6l****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateUisNetworkInterfaceResponse>
  <UisEniId>cgw-bp1aw0a5nfff03xp1****</UisEniId>
  <RequestId>1736145F-B482-47E4-8BBF-7EEC38CC800B</RequestId>
</CreateUisNetworkInterfaceResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UisEniId":"cgw-bp1aw0a5nfff03xp1****",
	"RequestId":"1736145F-B482-47E4-8BBF-7EEC38CC800B"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|400|Resource.QuotaFull|The resource quota is exceeded.|资源配额已满。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

