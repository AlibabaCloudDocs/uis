# DescribeWhiteList {#doc_api_Uis_DescribeWhiteList .reference}

调用DescribeWhiteList接口查询访问认证数据库的白名单。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Uis&api=DescribeWhiteList&type=RPC&version=2018-08-21)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeWhiteList|要执行的操作，取值：

 **DescribeWhiteList**。

 |
|UisId|String|是|UIS-xxxvb2gnqbvgrqsd9\*\*\*\*|UIS实例ID。

 |
|ClientToken|String|否|d7d24a21-f4ba-4454-9173-b3828dae492b|客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|RegionId|String|否|cn-hangzhou|地域ID，必须与UIS实例的地域ID一致。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|8D9190A0-565D-4589-BE56-090EA10F3BFD|请求ID。

 |
|Whitelist|String|10.23.12.XX/24|该实例的IP白名单，多个IP地址请以英文逗号（,）隔开，不可重复，最多1000个。

 格式：CIDR形式。例如：10.23.12.XX/24（无类域间路由，24表示了地址中前缀的长度，范围为1~32）。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=DescribeWhiteList
&UisId=UIS-xxxvb2gnqbvgrqsd9****
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeWhiteListResponse>
      <RequestId>8D9190A0-565D-4589-BE56-090EA10F3BFD</RequestId>
	  <Whitelist>10.23.12.XX/24</Whitelist>
</DescribeWhiteListResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"8D9190A0-565D-4589-BE56-090EA10F3BFD",
	"Whitelist":"10.23.12.XX/24"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InvalidUisId.NotFound|The specified UIS instance does not exist.|该Uis实例不存在。|

访问[错误中心](https://error-center.aliyun.com/status/product/Uis)查看更多错误码。

