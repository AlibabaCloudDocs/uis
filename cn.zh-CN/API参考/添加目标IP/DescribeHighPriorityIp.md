# DescribeHighPriorityIp {#doc_api_Uis_DescribeHighPriorityIp .reference}

调用DescribeHighPriorityIp接口查询指定的实例中目标IP地址或域名列表，并返回指定地址的节点信息。

**说明：** 如果是指定的\{地址：RegionId\}，则标记为StaticAreaId，否则为DynamicAreaId。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeHighPriorityIp&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeHighPriorityIp|要执行的操作。 取值：**DescribeHighPriorityIp**。

 |
|HighPriorityIp|String|是|\[\{'Destination': '221.6.4.XX','AreaID':'cn-shanghai'\},\{'Destination': 'www.microsoft.com'\}\]|目标IP地址或域名，用逗号分隔。格式如下:

 `[{'Destination': 'IP','AreaID':'regionID'},{'Destination': 'domain'}]` |
|UisId|String|是|UIS-xxxsjkn8dtiej7bbb\*\*\*\*|要查询的目标地址信息的实例ID。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|RegionId|String|否|cn-hangzhou|地域，和UIS实例上的region保持一致。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|HighPriorityIps| | |目的信息列表。

 |
|BoardAreaId|String|cn-hangzhou|对应目的地址的接入点的地域。

 |
|Domain|String|www.google.com|目的域名。

 |
|DynamicOffAreaId|String|us-west-1|根据用户输入的域名动态探测的目的地域。

 |
|Ip|String|61.19.1.XXX|用户输入的目的IP。

 |
|State|String|active|状态：

 -   **active**：正常状态
-   **probing**：探测中

 |
|StaticOffAreaId|String|us-west-1|用户输入的静态目的地地域。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页数量。

 |
|RequestId|String|A35AEC0B-1820-4969-9A2E-6BFC1ADC9936|请求ID。

 |
|TotalCount|Integer|1|总数量。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeHighPriorityIp
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeHighPriorityIpResponse>
      <PageNumber>1</PageNumber>
	  <TotalCount>1</TotalCount>
	  <HighPriorityIps>
		    <HighPriorityIp>
			      <Ip>10.45.3.X</Ip>
			      <State>probing</State>
			      <DynamicOffAreaId></DynamicOffAreaId>
			      <StaticOffAreaId>cn-beijing</StaticOffAreaId>
			      <BoardAreaId>cn-shanghai</BoardAreaId>
		    </HighPriorityIp>
	  </HighPriorityIps>
	  <PageSize>10</PageSize>
	  <RequestId>A35AEC0B-1820-4969-9A2E-6BFC1ADC9936</RequestId>
</DescribeHighPriorityIpResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"HighPriorityIps":{
		"HighPriorityIp":[
			{
				"Ip":"10.45.3.X",
				"State":"probing",
				"DynamicOffAreaId":"",
				"StaticOffAreaId":"cn-beijing",
				"BoardAreaId":"cn-shanghai"
			}
		]
	},
	"PageSize":10,
	"RequestId":"A35AEC0B-1820-4969-9A2E-6BFC1ADC9936"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

