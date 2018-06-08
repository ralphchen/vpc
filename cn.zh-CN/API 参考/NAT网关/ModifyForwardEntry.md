# ModifyForwardEntry {#reference_i4w_xmt_ndb .reference}

修改指定的DNAT条目。

**说明：** 当DNAT表中有DNAT条目的状态为Pending或Modifying时，无法修改DNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyForwardEntry

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ForwardTableId|String|是| DNAT列表的ID。

 |
|ForwardEntryId|String|是| DNAT条目的ID。

 |
|ExternalIp|String|否| 公网IP地址。

 |
|IpProtocol|String|否| 协议类型。取值：

-   TCP：转发TCP协议的报文。

-   UDP：转发UDP协议的报文。

-   Any：转发所有协议的报文。


 |
|ExternalPort|String|否|公网端口。取值范围：\[1,65535\]|
|InternalIp|String|否|目标私网IP。|
|InternalPort|String|否|目标私网端口。取值范围：\[1,65535\]|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyForwardEntry
&ExternalIp=139.224.22.107
&RegionId=cn-shanghai
&ExternalPort=Any
&InternalIp=192.168.1.1
&ForwardTableId=ftb-11tc6xgmv
&IpProtocol=Any
&InternalPort=Any
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyForwardEntryResponse>
    	<ForwardEntryId>fwd-119smw5tk</ForwardEntryId>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyForwardEntryResponse>
    ```

-   JSON格式

    ```
    {
      "ForwardEntryId": "fwd-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


