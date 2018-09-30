# ActivateRouterInterface {#reference_i94w_xmt_ndb .reference}

Activate a router interface in the Inactive status.

After the API is called, the router interface changes to the Activating status. When the activation completes, the router interface changes to the Active status.

**Note:** A delinquent router interface cannot be activated.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ActivateRouterInterface

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
https://vpc.aliyuncs.com/?Action=ActivateRouterInterface
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


