# ModifyUisAttribute {#doc_api_Uis_ModifyUisAttribute .reference}

调用ModifyUisAttribute接口修改已创建的实例的配置。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Uis&api=ModifyUisAttribute)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisId|String|是|UIS-xxxk7k971za1h6gxk\*\*\*\*|实例的ID。

 |
|Action|String|否|ModifyUisAttribute|要执行的操作。 取值：

 **ModifyUisAttribute**。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|Description|String|否|test\_uis\_desc|实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|Name|String|否|new\_uis\_name|实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://`或`https://`开头。

 |
|RegionId|String|否|cn-hangzhou|实例的地域。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=ModifyUisAttribute
&RegionId=cn-hangzhou
&UisId=UIS-xxxk7k971za1h6gxk****
&Description=test_uis_desc
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyUisAttributeResponse>
  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyUisAttributeResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"ModifyUisAttributeResponse":{
		"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
	}
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

