# DeleteDnatEntry {#reference_rds_cpd_bhb .reference}

调用DeleteDnatEntry接口删除DNAT规则。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  DeleteDnatEntry 

 |
|UisDnatId |String|是|要删除的DNAT规则ID。|
|UisNodeId|String|是|DNAT规则所属的UIS节点ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteDnatEntry
&UisDnatId=UISDNAT-xxx58s0dxe3418dqua85o
&UisNodeId=UISNODE-xxxpucur6tfhpzok5u2mi
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```

{
    "RequestId": "1736145F-B482-47E4-8BBF-7EEC38CC800B"
}
```

