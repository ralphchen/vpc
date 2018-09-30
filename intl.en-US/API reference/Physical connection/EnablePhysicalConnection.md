# EnablePhysicalConnection {#reference_i4124w_xmt_ndb .reference}

Enable the physical connection in the Confirmed status. After enabled, the physical connection changes to the Enabled status.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required |Description|
|:---|:---|:--------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 EnablePhysicalConnection

 |
|RegionId|String|Yes| The region of the physical connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|PhysicalConnectionId|String|Yes| The ID of the physical connection.

 |
|ClientToken|String|No| A client token used to guarantee the idempotence of requests.

 This parameter value is generated by the client and must be unique. It cannot exceed 64 ASCII characters.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=EnablePhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <EnablePhysicalConnectionResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </EnablePhysicalConnectionResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```

