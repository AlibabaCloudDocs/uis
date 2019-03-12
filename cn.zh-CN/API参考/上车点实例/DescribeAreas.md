# DescribeAreas {#reference_vj3_tqd_bhb .reference}

调用DescribeAreas接口查看UIS节点支持的地域信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action |String|是| 要执行的操作。 取值：

  DescribeAreas 

 |
|RegionId |String|否|UIS实例所在的地域ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|
| Areas |List|UIS节点支持的地域列表，包含以下信息：-   AreaId：地域ID。
-   LocalName：地域名称。

|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DescribeAreas
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```


{
  "RequestId": "56D9219F-348F-43F5-9751-1E1560DCEE7F",
  "Areas": {
      "Area": [
          {
            "AreaId": "cn-beijing",
            "LocalName": "华北2（北京）"
          }
       ]
    }
}
```

