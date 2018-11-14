# ModifySnatEntry {#reference_i4w3_xmt_ndb .reference}

Modifies a specified SNAT entry.

**Note:** You cannot modify a SNAT entry if any SNAT entry in the SNAT table is in the Pending or Modifying status.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifySnatEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|SnatTableId|String|Yes| The ID of the SNAT table.

 |
|SnatEntryId|String|Yes| The ID of the SNAT entry.

 |
|SnatIp|String|No|The public IP address. Separate multiple IPs by comma.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifySnatEntry
&SnatEntryId=snat-bs5bezbme
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&SnatIp=139.224.36.107
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
                            <ModifySnatEntryResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    	</ModifySnatEntryResponse>
    ```

-   JSON format

    ```
    
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    
    ```


