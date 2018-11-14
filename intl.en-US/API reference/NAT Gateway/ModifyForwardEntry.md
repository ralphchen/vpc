# ModifyForwardEntry {#reference_i4w_xmt_ndb4 .reference}

Modify a DNAT entry.

**Note:** You cannot modify a DNAT entry if any DNAT entry in the DNAT table is in the Pending or Modifying status.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifyForwardEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|ForwardTableId|String|Yes| The ID of the DNAT table.

 |
|ForwardEntryId|String|Yes|  The ID of the DNAT entry.

 |
|ExternalIp|String|No| The public IP address.

 |
|IpProtocol|String|No| The protocol type. Valid value:

-   TCP: forward TCP packets.

-   UDP: forward UDP packets.

-   Any: forward all packets.


 |
|ExternalPort|String|No|The public port. Valid value: \[1, 65535\]|
|InternalIp|String|No|The target private IP.|
|InternalPort|String|No|The target private port. Valid value: \[1, 65535\]|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyForwardEntry
&ExternalIp=139.224.22.107
&RegionId=cn-shanghai
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
                            <ModifyForwardEntryResponse>
    	<ForwardEntryId>fwd-119smw5tk</ForwardEntryId>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    	</ModifyForwardEntryResponse>
    ```

-   JSON format

    ```
    
      "ForwardEntryId": "fwd-119smw5tk",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    
    ```


