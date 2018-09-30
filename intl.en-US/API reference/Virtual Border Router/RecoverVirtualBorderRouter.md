# RecoverVirtualBorderRouter {#refere1nce_i4w_xmt_ndb .reference}

Recover a terminated VBR.

After the API is called, the VBR status will be changed from the Terminated status to the Recovering status. When the operation is completed, the status of the VBR is Enabled. Note the following before recovering a VBR:

-   Only the owner of the physical connection can call this API.

-   The physical connection that the VBR connects to must be in the Enabled status.

-   The recovery fails if the VLAN ID is used by other VBR after the VBR is terminated after 7 days. If the VLAN ID is occupied, the recovery operation fails.


## Request parameters {#section_qjj_tpp_vdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 RecoverVirtualBorderRouter

 |
|RegionId|String|Yes| The region of the VBR.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VbrId|String|Yes| The ID of the VBR.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=RecoverVirtualBorderRouter
&VbrId=pc-2zeoaxkq3xxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <RecoverVirtualBorderRouterResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </RecoverVirtualBorderRouterResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


