# DescribeRegions {#doc_api_Uis_DescribeRegions .reference}

调用DescribeRegions接口查询可用地域。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeRegions&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeRegions|要执行的操作，取值：**DescribeRegions**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Regions| | |可用地域的集合。

 |
|LocalName|String|华东 1|地域名称。

 |
|RegionId|String|cn-hangzhou|地域ID。

 |
|RequestId|String|611CB80C-B6A9-43DB-9E38-0B0AC3D9B58F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeRegions
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeRegionsResponse> 
	  <RequestId>38EC7366-F5A9-46B1-BDB1-0FDC2E296397</RequestId>
	  <Regions>
		    <Region>
			      <RegionId>cn-hangzhou</RegionId>
			      <LocalName>China (hanghzou)</LocalName>
		    </Region>
	  </Regions>
</DescribeRegionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"38EC7366-F5A9-46B1-BDB1-0FDC2E296397",
	"Regions":{
		"Region":[
			{
				"RegionId":"cn-hangzhou",
				"LocalName":"China (hanghzou)"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

