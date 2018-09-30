# DeletePhysicalConnection {#reference_i214w_xmt_ndb .reference}

Delete a physical connection.

You can only delete a physical connection in the Rejected, Canceled, AllocationFailed, or Terminated status.

## Request parameters {#section_tgk_2pp_vdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DeletePhysicalConnection

 |
|RegionId|String|Yes| The region of the physical connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|PhysicalConnectionId|String|Yes| The ID of the physical connection.

 |

## Return Parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeletePhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeletePhysicalConnectionResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeletePhysicalConnectionResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


