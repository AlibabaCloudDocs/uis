# DescribeDnatEntries {#doc_api_Uis_DescribeDnatEntries .reference}

调用DescribeDnatEntries接口查询已创建的DNAT规则。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=DescribeDnatEntries)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeDnatEntries|要执行的操作。 取值：**DescribeDnatEntries**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|RegionId|String|否|cn-hangzhou|UIS实例所在的地域。

 |
|UisDnatId|String|否|UISDNAT-xxxxlpa9jojfuvvxt\*\*\*\*|DNAT规则ID。

 |
|UisNodeId|String|否|UISNODE-xxxpucur6tfhpzok5\*\*\*\*|UIS节点ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含多少条目。

 |
|RequestId|String|DD14A51E-B94A-487E-B0F0-3D413FBD1E1F|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |
|UisDnatEntries| | |DNAT规则列表。

 |
|DestinationIp|String|8.8.8.X|DNAT转换后的目标IP地址。

 |
|DestinationPort|Integer|1001|DNAT转换后的目标端口。

 |
|IpProtocol|String|tcp|DNAT的协议。

 |
|OriginalIp|String|9.9.9.X|源IP地址。

 |
|OriginalPort|Integer|2001|源端口。​​-1​​代表所有端口。

 |
|UisDnatId|String|UISDNAT-xxxxlpa9jojfuvvxt\*\*\*\*|DNAT规则ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeDnatEntries
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDnatEntriesResponse>
  <PageNumber>1</PageNumber>
  <UisDnatEntries>
    <UisDnatEntry>
      <IpProtocol>tcp</IpProtocol>
      <UisDnatId>UISDNAT-xxxxlpa9jojfuvvxt****</UisDnatId>
      <DestinationIp>8.8.8.X</DestinationIp>
      <OriginalPort>2001</OriginalPort>
      <DestinationPort>1001</DestinationPort>
      <OriginalIp>9.9.9.X</OriginalIp>
    </UisDnatEntry>
  </UisDnatEntries>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>DD14A51E-B94A-487E-B0F0-3D413FBD1E1F</RequestId>
</DescribeDnatEntriesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UisDnatEntries":{
		"UisDnatEntry":[
			{
				"IpProtocol":"tcp",
				"UisDnatId":"UISDNAT-xxxxlpa9jojfuvvxt****",
				"DestinationIp":"8.8.8.X",
				"OriginalPort":2001,
				"DestinationPort":1001,
				"OriginalIp":"9.9.9.X"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"DD14A51E-B94A-487E-B0F0-3D413FBD1E1F"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

