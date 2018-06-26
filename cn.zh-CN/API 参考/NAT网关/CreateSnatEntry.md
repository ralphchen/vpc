# CreateSnatEntry {#reference_i4w_xmt_ndb .reference}

在SNAT列表中添加SNAT条目。

每个SNAT条目由SourceVSwitchId（交换机）和SnatIp（公网IP）组成。添加SNAT条目后，交换机下的ECS实例将通过SnatIp访问公网。

调用本接口添加DNAT条目时，请注意：

-   SNAT条目中的指定的交换机必须在NAT网关所属的VPC内。

-   每个交换机只能属于一个SNAT条目。

-   如果交换机中存在HAVIP实例，则无法添加SNAT条目。

-   SNAT条目中的公网IP（SnatIp）需满足以下条件：
    -   对于2017年11月3日之前账户下存在NAT带宽包的用户，SnatIp必须是该NAT网关的NAT带宽包中的公网IP地址。
    -   对于2017年11月3日之前账户下不存在NAT带宽包的用户，SnatIp必须是绑定了该NAT网关的弹性公网IP。
    -   一个公网IP不能同时用于DNAT条目和SNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateSnatEntry

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SnatTableId|String|是| SNAT表ID。

 |
|SourceVSwitchId|String|是|需要公网访问的交换机的ID。|
|SourceCIDR|String|否|指定交换机的网段。比如10.0.0.1/24**说明：** 此参数和SourceVSwtichId参数互斥，不能同时出现。如果指定了SourceVSwitchId，则不能指定SourceCIDR参数。如果指定了SourceCIDR参数，则不能指定SourceVSwitchId参数。

|
|SnatIp|String|否|公网IP地址。多个IP之间逗号隔开。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|SnatEntryId|String|SNAT条目ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateSnatEntry
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&SnatIp=139.224.22.40
&SourceVSwitchId=vsw-yrv0winkw
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateSnatEntryResponse>
        <RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
        <SnatEntryId>snat-119smw5tk</ForwardEntryId>
    </CreateSnatEntryResponse>
    ```

-   JSON格式

    ```
    {
      "SnatEntryId": "snat-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


