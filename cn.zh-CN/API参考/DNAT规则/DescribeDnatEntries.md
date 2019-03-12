# DescribeDnatEntries {#reference_zhy_5rd_bhb .reference}

调用DescribeDnatEntries接口查询已创建的DNAT规则。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  DescribeDnatEntries 

 |
|RegionId |String|否|UIS实例所在的地域ID。|
|UisNodeId |String|否|UIS节点ID。|
|UisDnatId |String|否|DNAT规则ID。|
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|
|TotalCount|String|列表条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
| UisDnatEntries |List|查询到的DNAT规则列表，包含以下信息：-   DestinationIp：DNAT转换后的目标IP地址。
-   DestinationPort：DNAT转换后的目标端口。
-   IpProtocol：DNAT的协议。
-   OriginalIp：源IP地址。
-   OriginalPort：源端口。​​-1​​代表所有端口。
-   UisDnatId：DNAT规则ID。

|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeDnatEntries
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```
{
    "UisDnatEntries": {
        "UisDnatEntry": [
            {
                "IpProtocol": "tcp",
                "UisDnatId": "UISDNAT-xxxxlpa9jojfuvvxtvob1",
                "DestinationIp": "8.8.8.1",
                "OriginalPort": 2001,
                "DestinationPort": 1001,
                "OriginalIp": "9.9.9.1"
            }
        ]
    },
    "PageNumber": 1,
    "TotalCount": 1,
    "PageSize": 10,
    "RequestId": "DD14A51E-B94A-487E-B0F0-3D413FBD1E1F"
}
```

