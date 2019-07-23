# DeleteUisConnection {#doc_api_Uis_DeleteUisConnection .reference}

调用DeleteUisConnection接口删除隧道连接。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DeleteUisConnection&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteUisConnection|要执行的操作。 取值：**DeleteUisConnection**。

 |
|UisConnectionId|String|是|UISCONN-xxxblu51boe75a1eb\*\*\*\*|要删除的隧道连接ID。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|UisNodeId|String|否|UISNODE-xxxcp0zr5m2avmn2r\*\*\*\*|节点ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A179AE8A-A7FE-4242-A830-641720CE2785|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteUisConnection
&UisNodeId=UISNODE-xxxcp0zr5m2avmn2r****
&UisConnectionId=UISCONN-xxxblu51boe75a1eb****
&RegionId=cn-hangzhou
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUisConnectionResponse>
	  <RequestId>A179AE8A-A7FE-4242-A830-641720CE2785</RequestId>
</DeleteUisConnectionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"requestId":"A179AE8A-A7FE-4242-A830-641720CE2785"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

