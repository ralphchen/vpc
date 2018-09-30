# DeleteForwardEntry {#reference_i4w_xmt_ndb .reference}

Delete a DNAT entry.

**Note:** You cannot delete a DNAT entry if there is any DNAT entry in the Pending or Modifying status.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DeleteForwardEntry

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|ForwardTableId|String|Yes| The ID of the DNAT table.

 |
|ForwardEntryId|String|Yes| The ID of the DNAT entry.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteForwardEntry
&RegionId=cn-shanghai
&ForwardEntryId=fwd-11iv34uj7
&ForwardTableId=ftb-11tc6xgmv
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeleteForwardEntryResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeleteForwardEntryResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


