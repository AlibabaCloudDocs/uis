# AddUisNodeIp {#doc_api_Uis_AddUisNodeIp .reference}

调用AddUisNodeIp接口为UisNode增加IP。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=AddUisNodeIp&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AddUisNodeIp|要执行的操作，取值：**AddUisNodeIp**。

 |
|IpAddrsNum|Integer|是|2|指定增加节点ip地址的个数。受整体地址个数的限制（默认不超过10个）。

 |
|UisNodeId|String|是|UISNODE-xxx4i1kged5xd3dk8\*\*\*\*|指定UIS节点的ID。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-001\*\*\*\*|用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过 64 个 ASCII 字符。

 |
|RegionId|String|否|cn-hangzhou|UIS实例所在地域。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|47D882C2-AE83-4B6D-90DD-F32B135AEBD8|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AddUisNodeIp
&IpAddrsNum=2
&UisNodeId=UISNODE-xxx4i1kged5xd3dk8****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AddUisNodeIpResponse>
    <RequestId>47D882C2-AE83-4B6D-90DD-F32B135AEBD8</RequestId>
</AddUisNodeIpResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"47D882C2-AE83-4B6D-90DD-F32B135AEBD8"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidAddrsNum|The number of IP addresses must be in the range of 2 to 10.|IP地址数应为2-10个。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

