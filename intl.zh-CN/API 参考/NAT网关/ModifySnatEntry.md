# ModifySnatEntry {#reference_i4w_xmt_ndb .reference}

修改指定的SNAT条目。

**说明：** 当SNAT表中有SNAT条目的状态为Pending或Modifying时，无法修改SNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifySnatEntry

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SnatTableId|String|是| SNAT表ID。

 |
|SnatEntryId|String|是| SNAT条目ID。

 |
|SnatIp|String|否|公网IP地址。多个IP之间逗号隔开。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifySnatEntry
&SnatEntryId=snat-bs5bezbme
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&SnatIp=139.224.36.107
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifySnatEntryResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifySnatEntryResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


