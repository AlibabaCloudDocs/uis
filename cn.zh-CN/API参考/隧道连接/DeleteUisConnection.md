# DeleteUisConnection {#reference_edn_hmx_pfb .reference}

删除隧道连接。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteUisConnection

 |
|UisNodeId|String|是| 要查询的节点ID，如果不指定则查询指定实例关联的所有节点。

 |
|UisNodeAreaId|String|是|隧道连接关联的节点实例的地域ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://uis.cn-hangzhou.aliyuncs.com/?Action=DeleteUisConnection
&UisNodeId=UISNODE-xxxcp0zr5m2avmn2rw2p7
&UisConnectionId=UISCONN-xxxblu51boe75a1ebj2y4
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <DeleteUisConnectionResponse>
    	<RequestId>A179AE8A-A7FE-4242-A830-641720CE2785</RequestId>
    </DeleteUisConnectionResponse>
    ```

-   JSON格式

    ```
    {
        "requestId":"A179AE8A-A7FE-4242-A830-641720CE2785"
    }
    ```


