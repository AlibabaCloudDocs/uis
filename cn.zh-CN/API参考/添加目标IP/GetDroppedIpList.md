# GetDroppedIpList {#doc_api_Uis_GetDroppedIpList .reference}

调用GetDroppedIpList接口查询报文丢失的IP列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=GetDroppedIpList&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisId|String|是|UIS-xxx88h4csbc6j8kkk\*\*\*\*|UIS实例ID。

 |
|Action|String|否|GetDroppedIpList|要执行的操作。 取值：**GetDroppedIpList**。

 |
|ChartDate|String|否|2019-02-27|数据日期，例如2019-02-27。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|DroppedIpListUrl|String|http://1443427xxx-nfv-jiasu-cn-hangzhou.oss-cn-hangzhou.aliyuncs.com/customer\_data/UIS-xxx88h4csbc6j8kkkxpf6/block\_ip\_2019-02-27|查询到的IP，以URL展示。

 |
|RequestId|String|DEC4B8B2-E73A-47A5-9169-547ECB115205|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=GetDroppedIpList
&UisId=UIS-xxx88h4csbc6j8kkk****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<GetDroppedIpListResponse>
    <DroppedIpListUrl>http://1443427xxx-nfv-jiasu-cn-hangzhou.oss-cn-hangzhou.aliyuncs.com/customer_data/UIS-xxx88h4csbc6j8kkkxpf6/block_ip_2019-02-27</DroppedIpListUrl>
    <RequestId>DEC4B8B2-E73A-47A5-9169-547ECB115205</RequestId>
</GetDroppedIpListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"DroppedIpListUrl":"http://1443427xxx-nfv-jiasu-cn-hangzhou.oss-cn-hangzhou.aliyuncs.com/customer_data/UIS-xxx88h4csbc6j8kkkxpf6/block_ip_2019-02-27",
	"RequestId":"DEC4B8B2-E73A-47A5-9169-547ECB115205"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

