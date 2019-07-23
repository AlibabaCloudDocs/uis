# DescribeSubConnection {#doc_api_Uis_DescribeSubConnection .reference}

调用DescribeSubConnection接口查询GRE的连接详情。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeSubConnection&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisSubConnectionId|String|是|UISSUBCONN-xxxxpsxkme91l6kz2\*\*\*\*|GRE连接ID。

 |
|Action|String|否|DescribeSubConnection|要执行的操作。取值：

 **DescribeSubConnection**。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|CustomerIp|String|39.106.5.XX|公网IP。

 |
|CustomerSubnet|String|192.168.0.0/16|私网网段。

 |
|CustomerTunnelIp|String|10.0.0.X|客户Tunnel设备的IP。

 |
|Description|String|description info|描述信息。

 |
|Ip|String|180.163.202.XX|接入点的IP。

 |
|LocalTunnelIp|String|10.0.0.X|UIS节点Tunnel设备的IP。

 |
|Name|String|uisSubConn1|连接名称。

 |
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |
|UisId|String|UIS-xxxvb2gnqbvgrqsd9\*\*\*\*|uis实例ID。

 |
|UisNodeId|String|UISNODE-xxxbink187cqsgfni\*\*\*\*|接入点ID。

 |
|UisSubConnectionId|String|UISSUBCONN-xxxxpsxkme91l6kz2\*\*\*\*|连接ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeSubConnection
&UisSubConnectionId=UISSUBCONN-xxxxpsxkme91l6kz2****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeSubConnectionResponse>
      <CustomerSubnet>192.168.1.1/16</CustomerSubnet>
	  <Name>lianjie1</Name>
	  <Ip>140.206.225.XXX</Ip>
	  <Description>1111</Description>
	  <UisNodeId>UISNODE-xxxbink187cqsgfni****</UisNodeId>
	  <LocalTunnelIp>192.168.2.X</LocalTunnelIp>
	  <UisId>UIS-xxxvb2gnqbvgrqsd9****</UisId>
	  <CustomerTunnelIp>192.168.3.X</CustomerTunnelIp>
	  <UisSubConnectionId>UISSUBCONN-xxxxpsxkme91l6kz2****</UisSubConnectionId>
	  <CustomerIp>10.23.22.X</CustomerIp>
</DescribeSubConnectionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"Name":"lianjie1",
	"CustomerSubnet":"192.168.1.1/16",
	"Ip":"140.206.225.XXX",
	"UisNodeId":"UISNODE-xxxbink187cqsgfni****",
	"Description":"1111",
	"LocalTunnelIp":"192.168.2.X",
	"UisId":"UIS-xxxvb2gnqbvgrqsd9****",
	"CustomerTunnelIp":"192.168.3.X",
	"UisSubConnectionId":"UISSUBCONN-xxxxpsxkme91l6kz2****",
	"CustomerIp":"10.23.22.X"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|UnknownError|An error occurred while processing your request. Please try again. If the error persists, please submit a ticket.|未知错误。请重试该操作，若再出现该错误请提交工单。|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|400|InvalidUisSubConnectionId.NotFound|The specified UIS subconnection ID does not exist.|指定的UIS子连接不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

