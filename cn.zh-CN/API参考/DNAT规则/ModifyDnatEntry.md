# ModifyDnatEntry {#reference_opz_232_bhb .reference}

调用ModifyDnatEntry接口修改DNAT规则。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyDnatEntry

 |
|UisNodeId|String|是|UIS节点ID。|
|RegionId|String|否|UIS实例所属的地域ID。|
|UisDnatId|String|否|DNAT规则ID。|
|DestinationIp|String|否| DNAT转换后的目标IP地址。

 |
|DestinationPort|Integer|否| DNAT转换后的目标端口。

 -1代表所有端口。

 |
|IpProtocol|String|否| 指定DNAT的协议，支持tcp、udp、icmp、any。当协议为any时，指定端口无效。

 |
|Name|String|否|DNAT规则的名称。|
|OriginalIp|String|否|要转换的源IP地址。|
|OriginalPort|String|否|要转换的源端口。-1代表所有端口。

|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 请求示例 {#section_l4x_lr3_ygb .section}

```
http(s)://uis.cn-hangzhou.aliyuncs.com/?Action=ModifyDnatEntry
&DestinationIp=3.3.3.3
&DestinationPort=8080
&IpProtocol=tcp
&Name=dnatEntry1
&OriginalIp=2.2.2.2
&OriginalPort=80
&UisNodeId=UISNODE-xxxpucurxxx
&<公共请求参数>
```

## 返回示例 {#section_hcz_nr3_ygb .section}

```

{
  "RequestId": "FC6EAEDF-72BC-4028-A622-63320AD1DEEF"
}
```

