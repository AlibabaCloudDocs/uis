# ModifyUisNodeAttribute {#doc_api_Uis_ModifyUisNodeAttribute .reference}

调用ModifyUisNodeAttribute接口修改已创建的节点实例配置。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=ModifyUisNodeAttribute&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisId|String|是|UIS-xxxbtfk761c670ok9\*\*\*\*|要修改的节点所属的极致互联网网络服务实例ID。

 |
|UisNodeId|String|是|UISNODE-xxxc4dacp9wal2jx6\*\*\*\*|要修改的节点实例的ID。

 |
|Action|String|否|ModifyUisNodeAttribute|要执行的操作。 取值：

 **ModifyUisNodeAttribute**。

 |
|Description|String|否|node\_desc|节点实例的描述信息。

 |
|Name|String|否|new\_node\_name|节点实例的名称。

 |
|RegionId|String|否|cn-hangzhou|极致互联网网络服务实例的地域。

 |
|UisNodeBandwidth|Integer|否|20|指定此节点的带宽值，默认值：**20Mbps**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=ModifyUisNodeAttribute
&UisNodeId=UISNODE-xxxc4dacp9wal2jx6****
&UisNodeBandwidth=20
&Description=node_desc
&UisId=UIS-xxxbtfk761c670ok9****
&RegionId=cn-hangzhou
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyUisNodeAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyUisNodeAttributeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidBandwidth|The specified bandwidth is invalid.|带宽值非法|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

