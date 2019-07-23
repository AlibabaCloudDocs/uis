# DescribeSubConnections {#doc_api_Uis_DescribeSubConnections .reference}

调用DescribeSubConnections接口查询GRE的连接。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeSubConnections&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisNodeId|String|是|UISNODE-xxxbink187cqsgfn\*\*\*\*|接入点ID。

 |
|Action|String|否|DescribeSubConnections|要执行的操作。取值：

 **DescribeSubConnections**。

 |
|IP|String|否|140.206.225.XX|接入点IP。

 |
|PageNumber|Integer|否|1|当前页码。

 |
|PageSize|Integer|否|10|每页数量。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页数量。

 |
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |
|TotalCount|Integer|2|总数量。

 |
|UisSubConnections| | |连接列表。

 |
|CreateTime|Long|1563420951000|创建时间。

 |
|Description|String|subconnection description|描述信息。

 |
|Ip|String|140.206.225.XXX|接入点IP。

 |
|Name|String|subconnection001|名称。

 |
|UisSubConnectionId|String|UISSUBCONN-xxxxpsxkme91l6kz2\*\*\*\*|连接ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSubConnections
&UisNodeId=UISNODE-xxxbink187cqsgfn****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSubConnectionsResponse>
      <UisSubConnections>
            <UisSubConnection>
                  <Name>lianjie1</Name>
                  <Ip>140.206.225.XX</Ip>
                  <Description>1111</Description>
                  <CreateTime>1563420951000</CreateTime>
                  <UisSubConnectionId>UISSUBCONN-xxxxpsxkme91l6kz2dgff</UisSubConnectionId>
            </UisSubConnection>
            <UisSubConnection>
                  <Name>connection2</Name>
                  <Ip>180.163.202.XX</Ip>
                  <Description>annother connection</Description>
                  <CreateTime>1563781819000</CreateTime>
                  <UisSubConnectionId>UISSUBCONN-xxxn30i6x2orzj5vd5f79</UisSubConnectionId>
            </UisSubConnection>
      </UisSubConnections>
      <PageNumber>1</PageNumber>
      <TotalCount>2</TotalCount>
      <PageSize>10</PageSize>
</DescribeSubConnectionsResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UisSubConnections":{
		"UisSubConnection":[
			{
				"Name":"lianjie1",
				"Ip":"140.206.225.XX",
				"Description":"1111",
				"CreateTime":1563420951000,
				"UisSubConnectionId":"UISSUBCONN-xxxxpsxkme91l6kz2dgff"
			},
			{
				"Name":"connection2",
				"Ip":"180.163.202.XX",
				"Description":"annother connection",
				"CreateTime":1563781819000,
				"UisSubConnectionId":"UISSUBCONN-xxxn30i6x2orzj5vd5f79"
			}
		]
	},
	"PageNumber":1,
	"TotalCount":2,
	"PageSize":10
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|400|InvalidIpAddress.WrongFormat|The specified IP address is invalid.|指定的IP地址格式无效。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

