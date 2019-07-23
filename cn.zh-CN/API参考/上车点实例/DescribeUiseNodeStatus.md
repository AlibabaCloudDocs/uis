# DescribeUiseNodeStatus {#doc_api_Uis_DescribeUiseNodeStatus .reference}

调用DescribeUiseNodeStatus接口查询UIS节点的状态信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeUiseNodeStatus&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisNodeId|String|是|UISNODE-xxxbink187cqsgfni\*\*\*\*|节点实例的ID。

 |
|Action|String|否|DescribeUiseNodeStatus|要执行的操作，取值：

 **DescribeUiseNodeStatus**。

 |
|Ip|String|否|140.206.225.xx|节点IP。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|IpStatusList| | |接入点IP的信息列表。

 |
|CurrentConnections|Integer|246|当前连接数量。

 |
|Ip|String|140.206.225.XXX|接入点IP。

 |
|MaxConnections|Integer|1000|最大连接数量。

 |
|RequestId|String|01DEA843-F116-4881-B356-6A492E60B36D|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeUiseNodeStatus
&UisNodeId=UISNODE-xxxbink187cqsgfni****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeUiseNodeStatusResponse>
      <IpStatusList>
		    <IpStatus>
			      <Ip>140.206.225.XXX</Ip>
			      <MaxConnections>1000</MaxConnections>
			      <CurrentConnections>246</CurrentConnections>
		    </IpStatus>
		    <IpStatus>
			      <Ip>180.163.202.XXX</Ip>
			      <MaxConnections>1000</MaxConnections>
			      <CurrentConnections>355</CurrentConnections>
		    </IpStatus>
	  </IpStatusList>
	  <RequestId>01DEA843-F116-4881-B356-6A492E60B36D</RequestId>
</DescribeUiseNodeStatusResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"IpStatusList":{
		"IpStatus":[
			{
				"Ip":"140.206.225.XXX",
				"MaxConnections":1000,
				"CurrentConnections":246
			},
			{
				"Ip":"180.163.202.XXX",
				"MaxConnections":1000,
				"CurrentConnections":355
			}
		]
	},
	"RequestId":"01DEA843-F116-4881-B356-6A492E60B36D"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidIpAddress.WrongFormat|The specified IP address is invalid.|指定的IP地址格式无效。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

