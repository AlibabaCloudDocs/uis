# DeleteUisNode {#doc_api_Uis_DeleteUisNode .reference}

调用DeleteUisNode接口删除节点实例。

**说明：** 如果节点实例正处于配置中，或节点实例已经添加到了隧道连接中，则无法删除节点实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DeleteUisNode&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DeleteUisNode|要执行的操作。 取值：

 **DeleteUisNode**。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|UisId|String|否|UIS-xxxbtfk761c670ok9\*\*\*\*|节点所属的实例ID。

 |
|UisNodeId|String|否|UISNODE-xxxc4dacp9wal2jx6\*\*\*\*|要删除的节点实例的ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteUisNode
&UisNodeId=UISNODE-xxxc4dacp9wal2jx6****
&UisId=UIS-xxxbtfk761c670ok9****
&RegionId=cn-hangzhou
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DeleteUisNodeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</DeleteUisNodeResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码 { .section}

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

