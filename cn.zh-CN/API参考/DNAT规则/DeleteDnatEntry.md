# DeleteDnatEntry {#doc_api_Uis_DeleteDnatEntry .reference}

调用DeleteDnatEntry接口删除DNAT规则。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DeleteDnatEntry&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteDnatEntry|要执行的操作。 取值：**DeleteDnatEntry**。

 |
|UisDnatId|String|是|UISDNAT-xxx58s0dxe3418dqu\*\*\*\*|要删除的DNAT规则ID。

 |
|UisNodeId|String|是|UISNODE-xxxpucur6tfhpzok5\*\*\*\*|DNAT规则所属的UIS节点ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|5DF5D97F-DB1F-4602-935C-5A050DAD3E48|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteDnatEntry
&UisDnatId=UISDNAT-xxx58s0dxe3418dqu****
&UisNodeId=UISNODE-xxxpucur6tfhpzok5****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteDnatEntryResponse>
    <RequestId>5DF5D97F-DB1F-4602-935C-5A050DAD3E48</RequestId>
</DeleteDnatEntryResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"5DF5D97F-DB1F-4602-935C-5A050DAD3E48"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

