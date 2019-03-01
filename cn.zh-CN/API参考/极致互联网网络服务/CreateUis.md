# CreateUis {#reference_i4w_xmt_ndb .reference}

创建一个实例。实例创建后会指定隧道协议并生成VPN数据库的管理口令。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateUis

 |
|RegionId|String|否| 实例的地域。默认值是cn-hangzhou。

 |
|Name|String|否| 实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|UisId|String|实例的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://uis.cn-hangzhou.aliyuncs.com/?Action=CreateUis
&RegionId=cn-hangzhou
&Name=test_uis
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateUisResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <uisId>UIS-xxxk7k971za1h6gxkli5n</uisId>
    </CreateUisResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "uisId":"UIS-xxxk7k971za1h6gxkli5n"
    }
    ```


