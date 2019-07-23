# DescribeUisNodes {#doc_api_Uis_DescribeUisNodes .reference}

调用DescribeUisNodes接口查询已创建的节点实例。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeUisNodes&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeUisNodes|要执行的操作。 取值：

 **DescribeUisNodes**。

 |
|RegionId|String|是|cn-hangzhou|节点实例所属的实例的地域。

 |
|UisId|String|是|UIS-xxxbtfk761c670ok9\*\*\*\*|要查询的节点所属的实例的ID。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|Name|String|否|node\_name1|节点实例的名称。

 |
|PageNumber|Integer|否|1|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|Status|String|否|active|节点实例的状态：

 -   **active**：可用
-   **creating**：创建中

 |
|UisNodeId|String|否|UISNODE-xxxc4dacp9wal2jx6\*\*\*\*|要查询的节点实例ID，如果不指定则查询指定实例关联的节点实例。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|PageNumber|Integer|1|当前页码。

 |
|PageSize|Integer|10|每页包含多少条目。

 |
|RequestId|String|0ECA995D-0D92-4507-919C-E5BF9A881834|请求ID。

 |
|TotalCount|Integer|1|列表条目数。

 |
|UisNodeList| | |Uis接入节点列表。

 |
|CreateTime|Long|1540536789000|节点实例的创建时间。

 |
|Description|String|node\_desc|节点实例的描述。

 |
|IpAddrsNum|Integer|2|节点包含的IP数量。

 |
|Name|String|node\_name1|节点实例的名称。

 |
|Status|String|active|节点实例的状态：

 -   **active**：可用
-   **creating**：创建中

 |
|UisEniIps|String|172.20.1.XX，172.20.XX|用户弹性网卡的私网IP，多个IP使用逗号分隔。

 |
|UisId|String|UIS-xxxbtfk761c670ok9\*\*\*\*|所属的实例的ID。

 |
|UisNodeActiveIp|String|47.100.14.XX，47.100.103.XX|当前可用的IP地址。

 |
|UisNodeAreaId|String|cn-shanghai|地域名称。

 |
|UisNodeBandwidth|Integer|29|带宽值。

 |
|UisNodeId|String|UISNODE-xxxc4dacp9wal2jx6\*\*\*\*|节点名称。

 |
|UisNodeIps|String|47.100.14.XX，47.100.103.XX|节点IP。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeUisNodes
&UisNodeId=UISNODE-xxxc4dacp9wal2jx6****
&UisId=UIS-xxxbtfk761c670ok9****
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUisNodesResponse>
      <PageNumber>1</PageNumber>
      <UisNodeList>
            <UisNode>
                  <Description>node_desc</Description>
                  <UisNodeIps>47.100.14.XX,47.100.103.XX</UisNodeIps>
                  <UisNodeAreaId>cn-shanghai</UisNodeAreaId>
                  <CreateTime>1540536789000</CreateTime>
                  <UisNodeActiveIp>47.100.14.XX,47.100.103.XX</UisNodeActiveIp>
                  <IpAddrsNum>2</IpAddrsNum>
                  <UisId>UIS-xxxbtfk761c670ok9****</UisId>
                  <UisNodeBandwidth>20</UisNodeBandwidth>
                  <UisNodeId>UISNODE-xxxc4dacp9wal2jx6****</UisNodeId>
            </UisNode>
      </UisNodeList>
      <TotalCount>1</TotalCount>
      <PageSize>10</PageSize>
      <RequestId>0ECA995D-0D92-4507-919C-E5BF9A881834</RequestId>
</DescribeUisNodesResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"totalCount":1,
	"requestId":"0ECA995D-0D92-4507-919C-E5BF9A881834",
	"uisNodeList":[
		{
			"createTime":1540536789000,
			"uisNodeAreaId":"cn-shanghai",
			"description":"node_desc",
			"uisNodeIps":"47.100.14.XX,47.100.103.XX",
			"uisNodeId":"UISNODE-xxxc4dacp9wal2jx6****",
			"uisNodeBandwidth":20,
			"ipAddrsNum":2,
			"uisNodeActiveIp":"47.100.14.XX,47.100.103.XX",
			"uisId":"UIS-xxxbtfk761c670ok9****"
		}
	],
	"pageSize":10,
	"pageNumber":1
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisId.NotFound|The specified UIS instance does not exist.|该Uis实例不存在。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

