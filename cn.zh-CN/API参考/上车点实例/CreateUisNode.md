# CreateUisNode {#doc_api_Uis_CreateUisNode .reference}

调用CreateUisNode接口为已创建的实例添加节点实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=CreateUisNode&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateUisNode|要执行的操作。 取值：

 **CreateUisNode**。

 |
|UisId|String|是|UIS-xxxbtfk761c670ok9\*\*\*\*|节点所属的实例ID。

 |
|UisNodeAreaId|String|是|cn-shanghai|指定节点的地域ID。您可通过DescribeRegions接口查询支持的地域。

 |
|UisNodeBandwidth|Integer|是|20|指定此节点的带宽值。默认值：**20Mbps**。

 |
|Description|String|否|node\_description|节点的描述信息。

 |
|IpAddrsNum|Integer|否|2|节点可用的IP数量。默认值为**2**，最大值为**10**。

 **说明：** 您如果需要更多配额，请提交工单。

 |
|Name|String|否|node\_name1|节点的名称。

 |
|RegionId|String|否|cn-hangzhou|该节点关联的实例的地域。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |
|UisNodeId|String|UISNODE-xxxc4dacp9wal2jx6\*\*\*\*|实例的节点ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUisNode
&RegionId=cn-hangzhou
&NodeBandwidth=20
&UisId=UIS-xxxbtfk761c670ok9****
&RegionId=cn-hangzhou
&UisNodeAreaId=cn-shanghai
&IpAddrsNum=2
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateUisNodeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
      <UisNodeId>UISNODE-xxxc4dacp9wal2jx6****</UisNodeId>
</CreateUisNodeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"UisNodeId":"UISNODE-xxxc4dacp9wal2jx6****",
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

