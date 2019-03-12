# DeleteUisNodeIp {#reference_ssx_ypd_bhb .reference}

调用DeleteUisNodeIp接口删除UIS节点上的IP。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  DeleteUisNodeIp 

 |
|UisNodeIpAddress |String|是|UIS弹性网卡的ID。|
|UisNodeId|String|是|指定要删除的IP地址。|
|RegionId|String|否|UIS实例所在的地域。|
|ClientToken|String|否|客户端token，用于保证请求的幂等性。 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteUisNodeIp
&UisNodeIpAddress=43.98.xx.xx
&UisNodeId=UISNODE-xxxdc9wyfmpf0tik5eyik
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```

{
    "RequestId": "1736145F-B482-47E4-8BBF-7EEC38CC800B"
}
```

