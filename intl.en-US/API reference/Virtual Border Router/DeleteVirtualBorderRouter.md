# DeleteVirtualBorderRouter {#referen5ce_i4w_xmt_ndb .reference}

Delete a VBR.

Note the following before deleting a VBR:

-   Before deleting a VBR, you must delete all router interfaces on the VBR.
-   You can only delete a VBR in the Unconfirmed, Enabled, or Terminated status.
-   If the owner of a physical connection wants to delete a VBR under another account, the VBR must be in the Unconfirmed status.


## Request parameters {#section_fpn_kpp_vdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteVirtualBorderRouter

 |
|RegionId|String|Yes|  The region of the VBR.

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
https://vpc.aliyuncs.com/?Action=DeleteVirtualBorderRouter
&VbrId=pc-2zeoaxkq3xxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeleteVirtualBorderRouterResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeleteVirtualBorderRouterResponse>
    ```

-   JSON format

    ```
     
        "Requestid": "maid"
    
    ```


