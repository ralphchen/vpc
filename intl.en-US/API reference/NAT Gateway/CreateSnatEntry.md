# CreateSnatEntry {#reference_i34w_xmt_ndb .reference}

Add an SNAT entry in an SNAT table.

Each SNAT entry consists of SourceVSwitchId and SnatIp.  After an SNAT entry is added, ECS instances under the specified VSwitch can access the Internet using the public IP \(SnatIp\).

Note the following before creating an SNAT entry:

-   The VSwitch must belong to the same VPC as the NAT gateway.

-   Each VSwitch can belong to only one SNAT entry.

-   The SNAT entry cannot be added if there is any HaVip instance under the VSwitch.

-   The public IP \(SnatIp\) in the SNAT entry must meet the following requirements:
    -   If your account has a NAT bandwidth package before 23:59, January 26, 2018, SnatIp must be a public IP address in the NAT bandwidth package of the NAT gateway.
    -   If your account does not have a NAT bandwidth package before 23:59, January 26, 2018, SnatIp must be an EIP bound to the NAT gateway.
    -   A public IP cannot be used by a DNAT entry and an SNAT entry at the same time.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 CreateSnatEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|SnatTableId|String|Yes|  The ID of the SNAT table.

 |
|SourceVSwitchId|String|No|The CIDR block of the VSwitch, such as 10.1.1.0/24.**Note:** This parameter and the SourceVSwitchId parameter cannot be specified at the same time.

|
|SourceCIDR|String|No| The protocol type. Valid value: 

-   TCP: forward TCP packets.

-   UDP: forward UDP packets.

-   Any: forward all packets.


 |
|SnatIp|String|No|The public IP address. Separate multiple EIPs by commas.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|SnatEntryId|String|The ID of the SNAT entry.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateSnatEntry
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&SnatIp=139.224.22.40
&SourceVSwitchId=vsw-yrv0winkw
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
                            <CreateSnatEntryResponse>
        <RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
        <SnatEntryId>snat-119smw5tk</ForwardEntryId>
                            </CreateSnatEntryResponse>
    ```

-   JSON format

    ```
    
      "SnatEntryId": "snat-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    
    ```


