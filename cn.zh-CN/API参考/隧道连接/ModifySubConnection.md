# ModifySubConnection {#doc_api_Uis_ModifySubConnection .reference}

调用ModifySubConnection接口修改GRE的连接信息。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=ModifySubConnection&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|UisSubConnectionId|String|是|UISSUBCONN-xxxn30i6x2orzj5vd\*\*\*\*|连接ID。

 |
|Action|String|否|ModifySubConnection|要执行的操作。取值：

 **ModifySubConnection**。

 |
|Description|String|否|uis connection description|连接的描述信息。

 |
|GreConfig|String|否|\{"localTunnelIp": "10.0.0.1","customerIp": "39.106.5.208","customerTunnelIp": "10.0.0.2","customerSubnet": "192.168.0.0/24"\}|GRE的配置信息。

 -   localTunnelIp：UIS节点Tunnel设备的IP
-   customerIp：公网IP
-   customerTunnelIp：客户Tunnel设备的IP
-   customerSubnet：私网网段

 |
|Name|String|否|newUisSubConnName|连接名称。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifySubConnection
&UisSubConnectionId=UISSUBCONN-xxxn30i6x2orzj5vd****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifySubConnectionResponse>
      <RequestId>8D9190A0-565D-4589-BE56-090EA10F3BFD</RequestId>
</ModifySubConnectionResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"8D9190A0-565D-4589-BE56-090EA10F3BFD"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden.SubUser|You are not authorized to operate on the specified resource because your account was created by another user.|由于账号是其他用户创建的，并未授权访问指定资源。|
|403|Forbidden|The user is not authorized to operate on the specified resource.|用户并未授权操作指定资源。|
|400|InvalidName|The specified name is invalid.|无效的名字。|
|400|InvalidCustomerIp.Exists|The specified customer IP already exists.|指定的客户IP已经存在。|
|400|InvalidCustomerSubnet.Conflict|The specified customer subnet conflicts.|指定的客户子网段冲突。|
|400|InvalidUisSubConnectionId.NotFound|The specified UIS subconnection ID does not exist.|指定的UIS子连接不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

