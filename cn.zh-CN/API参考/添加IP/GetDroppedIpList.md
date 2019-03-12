# GetDroppedIpList {#reference_a1z_4wd_bhb .reference}

调用GetDroppedIpList接口查询报文丢失的IP列表。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  GetDroppedIpList 

 |
|UisId |String|是|UIS实例ID。|
|ChartDate|String|否|数据日期，例如2019-02-27。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|
| DroppedIpListUrl |String|查询到的IP，以URL展示。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=GetDroppedIpList
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```
{
    "DroppedIpListUrl": "http://14434xxxxx-nfv-jiasu-cn-hangzhou.oss-cn-hangzhou.aliyuncs.com/customer_data/UIS-xxx88h4csbc6j8kkkxpf6/block_ip_2019-02-27",
    "RequestId": "DEC4B8B2-E73A-47A5-9169-547ECB115205"
}
```

