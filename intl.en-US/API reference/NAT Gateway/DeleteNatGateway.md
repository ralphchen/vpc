# DeleteNatGateway {#reference_i4w1_xmt_ndb .reference}

Delete a NAT gateway.

## Request parameters {#section_cch_pjg_mdb .section}

|Delete

Name|Type|Required |Description|
|:-----------|:---|:--------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteNatGateway

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|NatGatewayId|String|Yes| The ID of the NAT gateway.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteNatGateway
&RegionId=cn-beijing
&NatGatewayId=ngw-112za33e4
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteNatGatewayResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteNatGatewayResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


