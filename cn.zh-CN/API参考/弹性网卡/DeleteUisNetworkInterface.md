# DeleteUisNetworkInterface {#doc_api_Uis_DeleteUisNetworkInterface .reference}

调用DeleteUisNetworkInterface接口将弹性网卡从UIS服务中解绑，并删除该弹性网卡。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=DeleteUisNetworkInterface)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisEniId|String|是|UISENI-xxxg3rqds52gz7sbx\*\*\*\*|UIS弹性网卡的ID。

 |
|UisNodeId|String|是|UISNODE-xxx2d6jni60ifs7tz\*\*\*\*|弹性网卡绑定的UIS节点ID。

 |
|Action|String|否|DeleteUisNetworkInterface|要执行的操作。 取值：**DeleteUisNetworkInterface**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C9C8125B-449F-4244-9815-DD9FCEF8F789|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteUisNetworkInterface
&UisEniId=UISENI-xxxg3rqds52gz7sbx****
&UisNodeId=UISNODE-xxx2d6jni60ifs7tz****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUisNetworkInterfaceResponse>
  <RequestId>C9C8125B-449F-4244-9815-DD9FCEF8F789</RequestId>
</DeleteUisNetworkInterfaceResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"C9C8125B-449F-4244-9815-DD9FCEF8F789"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

