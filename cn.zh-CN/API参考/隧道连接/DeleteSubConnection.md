# DeleteSubConnection {#doc_api_Uis_DeleteSubConnection .reference}

调用DeleteSubConnection接口删除GRE的连接。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DeleteSubConnection&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteSubConnection|要执行的操作。取值：

 **DeleteSubConnection**。

 |
|UisSubConnectionId|String|是|UISSUBCONN-xxxn30i6x2orzj5vd\*\*\*\*|GRE连接ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DeleteSubConnection
&UisSubConnectionId=UISSUBCONN-xxxn30i6x2orzj5vd****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteSubConnectionResponse>
      <RequestId>8D9190A0-565D-4589-BE56-090EA10F3BFD</RequestId>
</DeleteSubConnectionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"8D9190A0-565D-4589-BE56-090EA10F3BFD"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|Uis.Configuring|The specified UIS instance is being configured.|该Uis实例正在配置中。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|400|InvalidUisConnectionId.NotFound|The specified UIS connection does not exist.|该Uis连接不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

