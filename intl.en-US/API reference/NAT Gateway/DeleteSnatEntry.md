# DeleteSnatEntry {#reference_4i4w_xmt_ndb .reference}

Delete an SNAT entry.

**Note:** You cannot delete an SNAT entry if there is any SNAT entry in the Pending or Modifying status in the SNAT table.

## Request parameters {#section_cch_pjg_mdb .section}

|Delete

Name|Type|Required|Description|
|:-----------|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DeleteSnatEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|SnatTableId|String|Yes| The ID of the SNAT table.

 |
|SnatEntryId|String|Yes| The ID of the SNAT entry.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteSnatEntry
&SnatEntryId=snat-bs5bezbme
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeleteSnatEntryResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeleteSnatEntryResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


