# AddUisNodeIp {#reference_l5s_jdt_pfb .reference}

调用AddUisNodeIp为UisNode增加IP。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AddUisNodeIp

 |
|IpAddrsNum|Integer|是| 指定增加上车点IP地址的个数。受整体地址个数的限制（默认不超过10个）。

 |
|UisNodeId|String|是| UIS节点ID。

 |
|ClientToken|String|否| 用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大不值过 64 个 ASCII 字符，具体参见如何保证幂等性。

 |
|RegionId|String|否|UIS实例的地域。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=AddUisNodeIp
&IpAddrsNum=2
&UisNodeId=UISNODE-xxx4i1kged5xd3dk8hnum
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```
{
    "RequestId": "47D882C2-AE83-4B6D-90DD-F32B135AEBD8"
}
```

