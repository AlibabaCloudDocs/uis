# DeleteUisNetworkInterface {#reference_g3v_npd_bhb .reference}

调用DeleteUisNetworkInterface接口将弹性网卡从UIS服务中解绑，并删除该弹性网卡。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
| Action |String|是| 要执行的操作。 取值：

  DeleteUisNetworkInterface 

 |
| UisEniId |String|是|UIS弹性网卡的ID。|
| UisNodeId |String|是|弹性网卡绑定的UIS节点ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteUisNetworkInterface
&UisEniId=UISENI-xxxg3rqds52gz7sbxdhsc
&UisNodeId=UISNODE-xxxdc9wyfmpf0tik5eyik
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```

{
    "RequestId": "1736145F-B482-47E4-8BBF-7EEC38CC800B"
}
```

