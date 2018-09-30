# AddBgpNetwork {#reference_i4w_xmt_nd4b .reference}

Advertise a BGP network

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 AddBgpNetwork

 |
|RegionId|String|Yes| The region of the VBR group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|DstCidrBlock|String|Yes| The CIDR block of the VPC or VSwitch to be connected to the local data center.

 |
|RouterId|String|Yes| The ID of the VBR.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AddBgpNetwork
&RegionId=cn-beijing
&RouterId=vbr-2zeff11o2sqhnp1u7ci93
&DstCidrBlock=10.0.0.0/24
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <AddBgpNetworkResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </AddBgpNetworkResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


