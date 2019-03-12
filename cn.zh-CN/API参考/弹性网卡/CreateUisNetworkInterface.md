# CreateUisNetworkInterface {#reference_l5s_jdt_pfb .reference}

调用CreateUisNetworkInterface接口创建弹性网卡，并将已创建的弹性网卡绑定到UIS服务。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
| Action |String|是| 要执行的操作。 取值：

  CreateUisNetworkInterface 

 |
| SecurityGroupId |String|是|指定弹性网卡绑定的安全组ID。|
| UisNodeId |String|是|指定弹性网卡绑定的UIS节点ID。|
| VswitchId |String|是|指定弹性网卡所在的交换机ID。|
| IpAddress |String|否|指定弹性网卡的私网IP地址。|
| Name |String|否|指定弹性网卡的名称。|
| Description |String|否|指定弹性网卡的描述。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
| RequestId |String|请求ID。|
| UisEniId |String|弹性网卡的ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```

http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUisNetworkInterface
&SecurityGroupId=sg-m5eiigbzenfqcpdt6nvi
&UisNodeId=UISNODE-xxxdc9wyfmpf0tik5eyik
&VswitchId=vsw-m5e1caexsmph0og6lis8h
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```

{
    "UisEniId": "UISENI-xxxlcfij8zpkp17g1r9ry",
    "RequestId": "1736145F-B482-47E4-8BBF-7EEC38CC800B"
}
```

