# DeleteUisNodeIp {#doc_api_Uis_DeleteUisNodeIp .reference}

调用DeleteUisNodeIp接口删除UIS节点上的IP。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=DeleteUisNodeIp)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteUisNodeIp|要执行的操作。 取值：**DeleteUisNodeIp**。

 |
|UisNodeId|String|是|UISNODE-xxx0gdclomnwvxs6m\*\*\*\*|指定Uis节点ID。

 |
|UisNodeIpAddress|String|是|192.168.XX.XX|指定需要删除的IP地址。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-0016e04\*\*\*\*|用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过 64 个 ASCII 字符。

 |
|RegionId|String|否|cn-hangzhou|Uis实例所在的地域。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|FD7BE99A-0402-4A6C-B3DA-353F230DD743|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteUisNodeIp
&UisNodeId=UISNODE-xxx0gdclomnwvxs6m****
&UisNodeIpAddress=192.168.XX.XX
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUisNodeIpResponse>
  <RequestId>FD7BE99A-0402-4A6C-B3DA-353F230DD743</RequestId>
</DeleteUisNodeIpResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"FD7BE99A-0402-4A6C-B3DA-353F230DD743"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidAddrsNum|The number of IP addresses must be in the range of 2 to 10.|IP地址数应为2-10个。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

