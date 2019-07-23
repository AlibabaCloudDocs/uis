# CreateSubConnection {#doc_api_Uis_CreateSubConnection .reference}

调用CreateSubConnection接口创建GRE连接。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=CreateSubConnection&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|CreateSubConnection|要执行的操作，取值：

 **CreateSubConnection**。

 |
|Ip|String|是|10.34.43.xx|节点IP。

 每个节点IP只能创建一个连接。

 |
|UisNodeId|String|是|UISNODE-xxxbink187cqsgfni\*\*\*\*|UIS节点ID，节点必须与节点IP对应。

 |
|Description|String|否|a gre description|连接描述信息。

 |
|GreConfig|String|否|\{"localTunnelIp": "10.0.xx.1","customerIp": "39.106.5.xx","customerTunnelIp": "10.0.xx.2","customerSubnet": "192.168.0.0/24"\}|GRE的配置信息。

 **说明：** localTunnelIp为节点GRE Tunnel设备的IP，customerIp为终端GRE的公网IP，customerTunnelIp为终端GRE Tunnel设备的IP，customerSubnet为终端GRE的私网网段。

 |
|Name|String|否|gre-name|连接名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0baf3d5315637815389227509e5464|请求ID。

 |
|UisSubConnectionId|String|UISSUBCONN-xxxxpsxkme91l6kz2\*\*\*\*|GRE连接ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=CreateSubConnection
&Ip=10.34.43.xx
&UisNodeId=UISNODE-xxxbink187cqsgfni****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<CreateSubConnectionResponse>
      <UisSubConnectionId>UISSUBCONN-xxxn30i6x2orzj5vd****</UisSubConnectionId>
	  <RequestId>FC6EAEDF-72BC-4028-A622-63320AD1DEEF</RequestId>
</CreateSubConnectionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"FC6EAEDF-72BC-4028-A622-63320AD1DEEF",
	"UisSubConnectionId":"UISSUBCONN-xxxn30i6x2orzj5vd****"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|400|InvalidName|The specified name is invalid.|无效的名字。|
|400|InvalidUisNodeId.NotFound|The specified UIS node does not exist.|该Uis Node不存在。|
|400|Resource.QuotaFull|The resource quota is exceeded.|资源配额已满。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

