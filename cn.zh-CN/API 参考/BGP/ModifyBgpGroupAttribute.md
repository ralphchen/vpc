# ModifyBgpGroupAttribute {#reference_i4w_xmt_ndb .reference}

修改BGP组的配置。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyBgpGroupAttribute

 |
|RegionId|String|是| BGP组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PeerASN|String|是| BGP邻居的ASN，长度为2字节或4字节，不能与阿里云侧的ASN（45104）相同。

 |
|RouterId|String|否| VBR的ID。

 |
|Name|String|否| BGP组的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| BGP组的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyBgpGroupAttribute
&RegionId=cn-beijing
&BgpGroupId=2010
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyBgpGroupAttributeResponse>
        <RequestId>C1221A1F-2ACD-4592-8F27-474E02883159</RequestId>
    </ModifyBgpGroupAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "C1221A1F-2ACD-4592-8F27-474E02883159"
    }
    ```


