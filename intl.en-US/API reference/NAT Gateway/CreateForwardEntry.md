# CreateForwardEntry {#reference_i4w_xmt_ndb5 .reference}

Add a DNAT entry in the DNAT table.

Each DNAT entry consists of five parts: ExternalIp, ExternalPort, Protocol, InternalIp, InternalPort. After a DNAT entry is added, the NAT gateway forwards the data of the specified protocol received from \[ExternalIp:ExternalPort\] to \[InternalIp:InternalPort\], and sends the response back by the same way.

Note:

-   The combination of ExternalIp, ExternalPort, and Protocol of all DNAT entries cannot duplicate,  that is, the message of the same IP, port, and protocol cannot be forwarded to multiple targets.

-   The combination of Protocol, InternalIp, and InternalPort of all DNAT entries cannot duplicate.

-   If any DNAT entry in the DNAT table is in the Pending or Modifying status, a new DNAT entry cannot be added.

-   ExternalIp must meet the following requirements:
    -   If your account has purchased a NAT bandwidth package before 23:59, January 26, 2018, ExternalIp must be a public IP in the NAT bandwidth package of the NAT gateway.
    -   A public IP cannot be used in both SNAT and DNAT entries at the same time.
-   InternalIp must meet the following requirements:
    -   InternalIp must belongs to the CIDR block of the VPC to which the NAT gateway belongs.
    -   The DNAT entry takes effect only when the InternalIP is used by an ECS instance and the instance is not bound with an EIP.  If the InternalIP is used by non-ECS resources such as HaVip, SLB, or RDS, the DNAT entry does not take effect and the Internet traffic cannot be forwarded to the IP.
    -   A public IP cannot be used in both SNAT and DNAT entries at the same time.
-   A maximum of 100 DNAT entries can be added to a DNAT table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 CreateForwardEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|ForwardTableId|String|Yes| The ID of the DNAT table.

 |
|ExternalIp|String|Yes| The public IP address.

 |
|IpProtocol|String|Yes| The protocol type. Valid value:

-   TCP: forward TCP packets.

-   UDP: forward UDP packets.

-   Any: forward all packets.


 |
|ExternalPort|String|No|The public port. Valid value: \[1, 65535\]|
|InternalIp|String|Yes| The target private IP address.|
|InternalPort|String|No|The target private port. Valid value: \[1, 65535\]|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|ForwardEntryId|String|The ID of the DNAT entry.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateForwardEntry
&ExternalIp=139.224.22.107
&Regionid = cn-shanghai
&ExternalPort=Any
&InternalIp=192.168.1.1
&ForwardTableId=ftb-11tc6xgmv
&IpProtocol=Any
&InternalPort=Any
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
    <CreateForwardEntryResponse>
        <ForwardEntryId>fwd-119smw5tk</ForwardEntryId>
        <RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </CreateForwardEntryResponse>
    ```

-   JSON format

    ```
    
      "ForwardEntryId": "fwd-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    
    ```


