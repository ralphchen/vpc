# ConnectRouterInterface {#reference_1i4w_xmt_ndb .reference}

The initiator router interface initiates a connection to the receiver router interface.

After this API is called, the router interface changes to the Connecting status. When the connection is established, the router interface changes to the Active status and the two VPCs are interconnected through the intranet.

Note the following before initiating a connection:

-   Only an initiator router interface in the Idle status can initiate a connection.

-   Up to one pair of interconnected router interfaces can be created between any two routers.

-   If there is a delinquent router interface under the account, you cannot initiate a connection.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ConnectRouterInterface

 |
|RegionId|String|Yes| The region of the router interface.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouterInterfaceId|String|Yes| The ID of initiator router interface.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ConnectRouterInterface
&RegionId=cn-hangzhou
&RouterInterfaceId=ri-sf3rxsf
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <ConnectRouterInterfaceResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </ConnectRouterInterfaceResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


