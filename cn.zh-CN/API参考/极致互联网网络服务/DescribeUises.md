# DescribeUises {#doc_api_Uis_DescribeUises .reference}

调用DescribeUises接口查询已创建的实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeUises&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|DescribeUises|要执行的操作。 取值：

 **DescribeUises**。

 |
|Name|String|否|test\_uis\_modify|实例的名称。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|UisId|String|否|UIS-xxxk7k971za1h6gx\*\*\*\*|查询指定实例的详细信息。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含多少条目。

 |
|RequestId|String|BE1D1ACC-63E6-4EE2-A159-5F63C3D8771B|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |
|Uises| | |UIS实例信息列表。

 |
|Bandwidth|Integer|10|UIS实例的带宽，单位是M。

 |
|BandwidthType|String|BGP|带宽类型。取值：

 -   BGP
-   ChinaTelecom
-   ChinaUnicom
-   ChinaMobile
-   BGP+CEN
-   ChinaTelecom+CEN
-   ChinaUnicom+CEN
-   ChinaMobile+CEN

 |
|BusinessStatus|String|Normal|UIS实例的业务状态。取值：**Normal**/**FinancialLocked\(欠费锁定\)**。

 |
|ChargeType|String|PREPAY|付费类型。取值：**PREPAY\(预付费\)**/**POSTPAY\(后付费\)**。

 |
|ConnectionBandwidth|Integer|100|指定每个连接的带宽，单位K。

 |
|ConnectionCount|Integer|500|付费方式为"按连接"时，购买的连接的数量。

 |
|ConnectionType|String|SSL|用户的连接类型。取值：**SSL**/**SDK**/**GRE**。

 |
|CreateTime|Long|1540535456000|实例创建的时间。

 |
|Description|String|test\_uis\_desc|实例的描述。

 |
|Name|String|test\_uis\_modify|实例的名称。

 |
|PayType|String|connection|付费方式。取值：**connection**/**bandwidth**。

 |
|ServiceRegion|String|Overseas|UIS实例的服务区域。取值：**国内\(China-mainland\)**/**海外\(Overseas\)**/**全球\(Global\)**。

 |
|SslClientCertUrl|String|http://example.com|客户端证书的下载连接。

 |
|Status|String|active|客户端证书的状态：

 -   **expiring-soon**：证书将在1周后过期。
-   **normal**：正常。
-   **expired**：已过期。

 |
|UisId|String|UIS-xxxk7k971za1h6gxk\*\*\*\*|实例的名称。

 |
|UisNodeIds| |\[ \]|该实例关联的节点列表。

 |
|UserInfo| | |管理VPN数据库的用户列表信息。

 |
|ClientInfoDB|String|test\_db29|管理用户数据的数据库链接地址。

 |
|ClientInfoDBAccount|String|test\_account1|此数据库的账号名称。

 |
|ClientInfoDBPassword|String|test\_password1|此数据库的密码。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUises
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeAansResponse>
	  <PageNumber>1</PageNumber>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
	  <RequestId>4E0234B3-9484-4E3D-BF5D-426DC951360C</RequestId>
		  <Uis>
			    <ChargeType>POSTPAY</ChargeType>
			    <ConnectionCount>500</ConnectionCount>
			    <ConnectionType>GRE</ConnectionType>
			    <Name>uis-test-00030</Name>
			    <BandwidthType>BGP</BandwidthType>
			    <Status>active</Status>
			    <ConnectionBandwidth>5</ConnectionBandwidth>
			    <ServiceRegion>China-mainland</ServiceRegion>
			    <BusinessStatus>Normal</BusinessStatus>
			    <UserInfo>
				      <ClientInfoDB>test1</ClientInfoDB>
				      <ClientInfoDBAccount>account1</ClientInfoDBAccount>
				      <ClientInfoDBPassword>password1</ClientInfoDBPassword>
			    </UserInfo>
			    <CreateTime>1561647417000</CreateTime>
			    <UisId>UIS-xxx81sig1kn0dhr1t****</UisId>
			    <SslClientCertUrl>"http://example.com"</SslClientCertUrl>
			    <PayType>connection</PayType>
		  </Uis>
</DescribeAansResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Uis":[
		{
			"ChargeType":"POSTPAY",
			"ConnectionCount":500,
			"ConnectionType":"GRE",
			"Name":"uis-test-00030",
			"BandwidthType":"BGP",
			"Status":"active",
			"ConnectionBandwidth":5,
			"ServiceRegion":"China-mainland",
			"BusinessStatus":"Normal",
			"UserInfo":{
				"ClientInfoDB":"test1",
				"ClientInfoDBAccount":"account1",
				"ClientInfoDBPassword":"password1"
			},
			"CreateTime":1561647417000,
			"UisId":"UIS-xxx81sig1kn0dhr1t****",
			"SslClientCertUrl":"http://example.com",
			"PayType":"connection"
		}
	],
	"PageNumber":1,
	"TotalCount":1,
	"PageSize":10,
	"RequestId":"4E0234B3-9484-4E3D-BF5D-426DC951360C"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisId.NotFound|The specified UIS instance does not exist.|该Uis实例不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

