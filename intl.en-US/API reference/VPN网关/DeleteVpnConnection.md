# DeleteVpnConnection {#reference_i4w_xmt_ndb .reference}

Delete an IPsec connection.

**Note:** After an IPsec connection is deleted, the VPC and the local data center is disconnected.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteVpnConnection

 |
|RegionId|String|Yes| The region of the IPsec connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpnConnectionId|String|Yes| The ID of the IPsec connection.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteVpnConnection
&RegionId=cn-hangzhou
&VpnConnectionId=vco-bp10lz7aejumd2vxoqgev
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteVpnConnection>
        <RequestId>606998F0-B94D-48FE-8316-ACA81BB230DA</RequestId>
    </DeleteVpnConnection>
    ```

-   JSON format

    ```
    {
      "RequestId":"606998F0-B94D-48FE-8316-ACA81BB230DA"
    }
    ```


