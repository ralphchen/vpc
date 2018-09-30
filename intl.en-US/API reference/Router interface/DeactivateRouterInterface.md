# DeactivateRouterInterface {#refe2rence_i4w_xmt_ndb .reference}

Deactivate a router interface.

After the API is called, the router interface changes to the Deactivating status. When the deactivation completes, the router interface changes to the Inactive status.

**Note:** A delinquent router interface cannot be deactivated.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DeactivateRouterInterface

 |
|RegionId|String|Yes| The region of the router interface.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouterInterfaceId|String|Yes| The ID of the router interface.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeactivateRouterInterface
&RegionId=cn-hangzhou
&RouterInterfaceId=ri-sf3rxsf
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <ActivateRouterInterfaceResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </ActivateRouterInterfaceResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


