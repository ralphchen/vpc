# TerminateVirtualBorderRouter {#refe1rence_i4w_xmt_ndb .reference}

Terminate the virtual border router \(VBR \).

After the API is called, the VBR status will be changed from the Enabled status to the Terminated status. Note the following before terminating a VBR.

**Note:** Only the owner of the physical connection that the VBR connects to can call the API.

## Request parameters {#section_ulr_rpp_vdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 TerminateVirtualBorderRouter

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
https://vpc.aliyuncs.com/?Action=TerminateVirtualBorderRouter
&VbrId=pc-2zeoaxkq3xxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <TerminateVirtualBorderRouterResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </TerminateVirtualBorderRouterResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


