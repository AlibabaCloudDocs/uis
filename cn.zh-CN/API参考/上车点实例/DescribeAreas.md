# DescribeAreas {#doc_api_Uis_DescribeAreas .reference}

调用DescribeAreas接口查询UIS节点支持的地域信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=DescribeAreas)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeAreas|要执行的操作。 取值：

 **DescribeAreas**。

 |
|RegionId|String|否|cn-hangzhou|UIS实例所在的地域ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Areas| | |UIS节点支持的地域列表。

 |
|AreaId|String|cn-beijing|地域ID。

 |
|LocalName|String|华北2（北京）|地域名称。

 |
|RequestId|String|56D9219F-348F-43F5-9751-1E1560DCEE7F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeAreas
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAreasResponse>
  <RequestId>185E81B1-3916-4667-B48F-C52409B33F2B</RequestId>
  <Areas>
    <Area>
      <AreaId>cn-beijing</AreaId>
      <LocalName>华北2（北京）</LocalName>
    </Area>
  </Areas>
</DescribeAreasResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"56D9219F-348F-43F5-9751-1E1560DCEE7F",
	"Areas":{
		"Area":[
			{
				"AreaId":"cn-beijing",
				"LocalName":"华北2（北京）"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

