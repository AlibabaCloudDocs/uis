# CreateUisConnection {#reference_npg_wrw_pfb .reference}

创建隧道连接。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateUisConnection

 |
|UisNodeId|String|是| 节点实例ID。

 |
|UisProtocol|String|是| 软件端与服务端使用的协议名称，默认值OpenVPN。

 |
|Name|Integer|否|隧道连接的名称。|
|Description|Integer|否|隧道连接的描述。|
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|SslConfig|JSON String|否|Protocal指定为OpenVPN协议时：-   SSLConfig. Protocol：SSL-VPN服务端所使用的协议。取值：UDP（默认值） | TCP。
-   SSLConfig.Port：SSL-VPN服务端所使用的端口，默认值为1194。

不能用使用以下端口端口范围1025-10000，以及避开以下知名端口\[22, 2222, 22222, 9000, 9001, 9002, 7505, 80, 443, 53, 68, 123, 4510, 4560, 500, 4500\]。

-   SSLConfig.Cipher：SSL-VPN使用的加密算法。取值：AES-128-CBC（默认值） |AES-192-CBC | AES-256-CBC | none。

|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|UisConnectionId|String|VPN服务端的ID，此ID不区分协议。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUisConnection
&UisNodeId=UISNODE-xxxcp0zr5m2avmn2rw2p7
&UisProtocol=SSLVPN
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateUisConnectionResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <UisConnectionId>UISCONN-xxxblu51boe75a1ebj2y4</UisConnectionId>
    </CreateUisConnectionResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "uisConnectionId": "UISCONN-xxxblu51boe75a1ebj2y4"
    }
    ```


