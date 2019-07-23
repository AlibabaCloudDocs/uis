# ModifyWhiteList {#doc_api_Uis_ModifyWhiteList .reference}

调用ModifyWhiteList接口修改访问认证数据库的白名单。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=ModifyWhiteList&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyWhiteList|要执行的操作。取值：

 **ModifyWhiteList**。

 |
|RegionId|String|是|cn-hangzhou|地域ID，和uis实例的region保持一致。

 |
|UisId|String|是|UIS-xxxvb2gnqbvgrqsd9\*\*\*\*|UIS实例ID。

 |
|Whitelist|String|是|10.23.12.XX/24|该实例的IP白名单，多个IP地址请以英文逗号（,）隔开，不可重复，最多1000个。

 格式：CIDR形式。例如：10.23.12.XX/24（无类域间路由，24表示了地址中前缀的长度，范围为1~32）

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|ModifyMode|String|否|Append|修改方式，默认值为**Cover**。取值：

 -   **Cover**：覆盖原IP白名单，第一次创建的时候要使用Cover模式。
-   **Append**：追加IP。
-   **Delete**：删除IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyWhiteList
&RegionId=cn-hangzhou
&UisId=UIS-xxxvb2gnqbvgrqsd9****
&Whitelist=10.23.12.XX/24
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyWhiteListResponse>
      <RequestId>8D9190A0-565D-4589-BE56-090EA10F3BFD</RequestId>
</ModifyWhiteListResponse>
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
|400|InvalidUisId.NotFound|The specified UIS instance does not exist.|该Uis实例不存在。|
|400|InvalidIpAddress.WrongFormat|The specified IP address is invalid.|指定的IP地址格式无效。|
|400|Resource.QuotaFull|The resource quota is exceeded.|资源配额已满。|
|400|InvalidIpAddress.NotFound|The specified IP address does not exist.|白名单地址不存在。|
|400|Whitelist.Conflict|The specified IP address already exists.|指定的地址已经存在。|
|400|InvalidProtocol|The specified protocol type is invalid.|无效的协议类型。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

