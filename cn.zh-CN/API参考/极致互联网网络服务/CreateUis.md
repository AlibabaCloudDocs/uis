# CreateUis {#doc_api_Uis_CreateUis .reference}

调用CreateUis接口创建一个Uis实例。实例创建后会指定隧道协议，并生成VPN数据库的管理口令。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=CreateUis&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|AccessType|String|是|GRE|接入类型，与UisProtocol有对应关系。

 -   接入**VPN**类型，对应的UisProtocol为**SSL、SDK**。
-   接入**IOT**类型，对应的UisProtocol为**GRE**。

 |
|Action|String|是|CreateUis|要执行的操作。 取值：

 **CreateUis**。

 |
|ServiceRegion|String|是|China-mainland|UIS实例服务的区域。

 取值：**中国大陆\(China-mainland\)**/**海外\(Overseas\)**/**全球\(Global\)**。

 |
|AutoPay|Boolean|否|true|是否支持自动支付。默认值是**false**。

 |
|Bandwidth|Integer|否|10|指定UIS实例的带宽，单位为M。

 |
|BandwidthType|String|否|BGP|带宽类型。取值：

 -   **BGP**
-   **ChinaTelecom**
-   **ChinaUnicom**
-   **ChinaMobile**
-   **BGP+CEN**
-   **ChinaTelecom+CEN**
-   **ChinaUnicom+CEN**
-   **ChinaMobile+CEN**

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|ConnectionBandwidth|Integer|否|20|指定每个连接的带宽。

 |
|ConnectionCount|Integer|否|500|指定连接的数量。

 |
|Description|String|否|uis description info|实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|Duration|Integer|否|1|预付费时，购买的周期数。

 |
|InstanceChargeType|String|否|PREPAY|付费方式。取值：**后付费\(POSTPAY\)**/**预付费\(PREPAY\)**。

 |
|InternetChargeType|String|否|Connection|计费方式。取值：**连接\(Connection\)**/**带宽\(Bandwidth\)**。

 |
|Name|String|否|test\_uis\_name|实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://`或`https://`开头。

 |
|PricingCycle|String|否|Year|预付费购买的周期数类型。取值：**Month**/**Year**。

 |
|RegionId|String|否|cn-hangzhou|实例的地域。

 **说明：** 目前仅支持cn-hangzhou。

 |
|UisProtocol|String|否|GRE|用户的连接类型。取值：**SSL**/**SDK**/**GRE**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|OrderId|String|2040684504905xx|生成的订单ID。

 |
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |
|UisId|String|UIS-xxxk7k971za1h6gxk\*\*\*\*|实例的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUis
&AccessType=GRE
&ServiceRegion=China-mainland
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateUisResponse>
      <OrderId>2040684504905xx</OrderId>
	  <RequestId>5C23D304-F0F9-4581-88B0-6E2123B23AC1</RequestId>
	  <UisId>UIS-xxxe61q5i00921m3w****</UisId>
</CreateUisResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"5C23D304-F0F9-4581-88B0-6E2123B23AC1",
	"OrderId":"2040684504905xx",
	"UisId":"UIS-xxxe61q5i00921m3w****"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

