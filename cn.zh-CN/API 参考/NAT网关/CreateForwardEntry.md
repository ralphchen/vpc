# CreateForwardEntry {#reference_i4w_xmt_ndb .reference}

在DNAT列表中添加DNAT条目。

每条DNAT条目由五部分组成，包括ExternalIp、ExternalPort、protocol、InternalIp和InternalPort。添加DNAT条目后，NAT网关会将ExternalIp：ExternalPort上收到的指定协议的报文转发给InternalIp:InternalPort，并将回复消息原路返回。

调用本接口添加DNAT条目时，请注意：

-   所有DNAT条目的ExternalIp、ExternalPort和Protocol三个字段组成的组合必须互不重复。即不允许将同一个源IP、同一个端口、同一个协议的消息转发到多个目标。

-   所有DNAT条目的Protocol、InternalIp和InternalPort三个字段组成的组合也必须互不重复。

-   当DNAT表中有DNAT条目的状态处于Pending或Modifying状态时，无法添加DNAT条目。

-   DNAT条目中的公网IP（ExternalIp）需满足以下条件：
    -   对于2017年11月3日之前账户下存在NAT带宽包的用户，ExternalIp必须是该NAT网关的NAT带宽包中的公网IP地址。
    -   对于2017年11月3日之前账户下不存在NAT带宽包的用户，ExternalIp必须是绑定了该NAT网关的弹性公网IP。
    -   一个公网IP不能同时用于DNAT条目和SNAT条目。
-   DNAT条目中的内网IP（InternalIp）需满足以下条件：
    -   InternalIp必需属于NAT网关所在的VPC的网段。
    -   只有当InternalIp被一个ECS实例使用且该实例没有绑定EIP时，DNAT条目才生效。若该InternalIp被HAVIP、SLB或RDS等非ECS资源使用，DNAT条目无效，公网流量无法转发到该IP上。
    -   一个公网IP不能同时用于DNAT条目和SNAT条目。
-   一个DNAT表最多可添加40条DNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateForwardEntry

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ForwardTableId|String|是| DNAT列表的ID。

 |
|ExternalIp|String|是| 公网IP地址。

 |
|IpProtocol|String|是| 协议类型。取值：

-   TCP：转发TCP协议的报文。

-   UDP：转发UDP协议的报文。

-   Any：转发所有协议的报文。


 |
|ExternalPort|String|否|公网端口。取值范围：\[1,65535\]|
|InternalIp|String|是|目标私网IP。|
|InternalPort|String|否|目标私网端口。取值范围：\[1,65535\]|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ForwardEntryId|String|DNAT条目的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateForwardEntry
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
    <CreateForwardEntryResponse>
    	<ForwardEntryId>fwd-119smw5tk</ForwardEntryId>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </CreateForwardEntryResponse>
    ```

-   JSON格式

    ```
    {
      "ForwardEntryId": "fwd-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


