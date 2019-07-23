# ModifyHighPriorityIp {#doc_api_Uis_ModifyHighPriorityIp .reference}

调用ModifyHighPriorityIp接口修改指定实例的HighPriorityIp地址列表信息。可以用来修改路由的节点信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=ModifyHighPriorityIp&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyHighPriorityIp|要执行的操作。 取值：**ModifyHighPriorityIp**。

 |
|HighPriorityIp|String|是|\[\{'Destination': '221.6.4.XX','AreaID':'cn-shanghai'\},\{'Destination': 'www.microsoft.com'\}\]|目标IP地址或域名，用逗号分隔。格式如下:

 `[{'Destination': 'IP','AreaID':'regionID'},{'Destination': 'domain'}]`。

 |
|UisId|String|是|UIS-xxxsjkn8dtiej7bbb\*\*\*\*|要修改目标地址信息的实例ID。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符

 |
|RegionId|String|否|cn-hangzhou|地域ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A35AEC0B-1820-4969-9A2E-6BFC1ADC9936|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyHighPriorityIp
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyHighPriorityIpResponse>
      <RequestId>A35AEC0B-1820-4969-9A2E-6BFC1ADC9936</RequestId>
</ModifyHighPriorityIpResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A35AEC0B-1820-4969-9A2E-6BFC1ADC9936"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

