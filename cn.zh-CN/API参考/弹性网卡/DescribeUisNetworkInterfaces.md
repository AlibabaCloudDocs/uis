# DescribeUisNetworkInterfaces {#doc_api_Uis_DescribeUisNetworkInterfaces .reference}

调用DescribeUisNetworkInterfaces接口查询已创建的弹性网卡。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=DescribeUisNetworkInterfaces)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeUisNetworkInterfaces|要执行的操作。 取值：**DescribeUisNetworkInterfaces**。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|RegionId|String|否|cn-hangzhou|UIS实例所在的地域。

 |
|UisEniId|String|否|UISENI-xxxfunml63xpaz0tz\*\*\*\*|UIS弹性网卡ID。

 |
|UisNodeId|String|否|UISNODE-xxxccvrtiviatdroh\*\*\*\*|UIS节点ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|NetworkInterfaces| | |弹性网卡列表。

 |
|Description|String|TestCreateEni|弹性网卡的描述信息。

 |
|IpAddress|String|192.168.XX.XX|弹性网卡的私网IP地址。

 |
|Log|String|ok|弹性网卡创建失败的日志信息。

 |
|Name|String|TestCreateEni|弹性网卡的名称。

 |
|NetworkInterfaceId|String|eni-m5e0hoi1xi93raq\*\*\*\*|弹性网卡的ID。

 |
|SecurityGroupID|String|sg-m5eiigbzenfqcpd\*\*\*\*|弹性网卡绑定的安全组ID。

 |
|State|String|active|active正常状态。

 |
|UisEniId|String|UISENI-xxxfunml63xpaz0t\*\*\*\*|UIS弹性网卡的ID。

 |
|UisNodeId|String|UISNODE-xxxccvrtiviatdroh\*\*\*\*|绑定的UIS节点ID。

 |
|VswitchId|String|vsw-m5e1caexsmph0og6l\*\*\*\*|弹性网卡所属的交换机ID。

 |
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含多少条目。

 |
|RequestId|String|5B877E24-48C5-48F4-B3A6-43B61AC4FCBA|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUisNetworkInterfaces
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUisNetworkInterfacesResponse>
  <PageNumber>1</PageNumber>
  <NetworkInterfaces>
    <NetworkInterface>
      <Name>TestCreateEni</Name>
      <Description>TestCreateEni</Description>
      <UisEniId>UISENI-xxxfunml63xpaz0tz****</UisEniId>
      <UisNodeId>UISNODE-xxxccvrtiviatdroh****</UisNodeId>
      <SecurityGroupID>sg-m5eiigbzenfqcpdt****</SecurityGroupID>
      <State>active</State>
      <VswitchId>vsw-m5e1caexsmph0og6l****</VswitchId>
      <IpAddress>192.168.XX.XX</IpAddress>
      <NetworkInterfaceId>eni-m5e0hoi1xi93raqg****</NetworkInterfaceId>
    </NetworkInterface>
  </NetworkInterfaces>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>5B877E24-48C5-48F4-B3A6-43B61AC4FCBA</RequestId>
</DescribeUisNetworkInterfacesResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"5B877E24-48C5-48F4-B3A6-43B61AC4FCBA",
	"NetworkInterfaces":{
		"NetworkInterface":[
			{
				"Name":"TestCreateEni",
				"UisNodeId":"UISNODE-xxxccvrtiviatdroh****",
				"UisEniId":"UISENI-xxxfunml63xpaz0tz****",
				"Description":"TestCreateEni",
				"SecurityGroupID":"sg-m5eiigbzenfqcpdt****",
				"State":"active",
				"VswitchId":"vsw-m5e1caexsmph0og6l****",
				"IpAddress":"192.168.XX.XX",
				"NetworkInterfaceId":"eni-m5e0hoi1xi93raqg****"
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

