# DescribeHighPriorityIps {#doc_api_Uis_DescribeHighPriorityIps .reference}

调用DescribeHighPriorityIps接口查询uis实例中的目的地址（ip或者URL）列表。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeHighPriorityIps&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeHighPriorityIps|要执行的操作。取值：

 DescribeHighPriorityIps。

 |
|UisId|String|是|UIS-xxxsjkn8dtiej7bbb\*\*\*\*|UIS实例ID。

 |
|PageNumber|Integer|否|1|分页查询时的页码。

 |
|PageSize|Integer|否|10|分页查询时的每页数量。

 |
|RegionId|String|否|cn-hangzhou|地域，和UIS实例上的region保持一致。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|HighPriorityIps| | |目的地址列表。

 |
|AreaId|String|cn-shanghai|IP或者域名所在的地域。

 |
|Destination|String|www.microsoft.com|域名或者IP。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页数量。

 |
|RequestId|String|B00CFE04-4E81-4225-8FD8-A0DDBBB28835|请求ID。

 |
|TotalCount|Integer|15|总数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeHighPriorityIps
&UisId=UIS-xxxsjkn8dtiej7bbb****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeHighPriorityIpsResponse>
	  <HighPriorityIps>
		    <HighPriorityIp>
			      <AreaId>us-west-1</AreaId>
			      <Destination>www.microsfot.com</Destination>
		    </HighPriorityIp>
		    <HighPriorityIp>
			      <AreaId>cn-hongkong</AreaId>
			      <Destination>10.45.67.X</Destination>
		    </HighPriorityIp>
	  </HighPriorityIps>
	  <RequestId>3B2B675D-17AB-499D-9070-CE8A891CD3AD</RequestId>
</DescribeHighPriorityIpsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"HighPriorityIps":{
		"HighPriorityIp":[
			{
				"AreaId":"us-west-1",
				"Destination":"www.microsfot.com"
			},
			{
				"AreaId":"cn-hongkong",
				"Destination":"10.45.67.X"
			}
		]
	},
	"RequestId":"3B2B675D-17AB-499D-9070-CE8A891CD3AD"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisId.NotFound|The specified UIS instance does not exist.|该Uis实例不存在。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

