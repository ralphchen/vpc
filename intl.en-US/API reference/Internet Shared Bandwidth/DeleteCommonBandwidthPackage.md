# DeleteCommonBandwidthPackage {#reference_i4w_xmt_ndb .reference}

Delete an Internet Shared Bandwidth instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DeleteCommonBandwidthPackage

 |
|RegionId|String |Yes| The ID of the region where the Internet Shared Bandwidth instance is located.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BandwidthPackageId|String |Yes| The ID of the Internet Shared Bandwidth instance.

 |
|Force|Boolean|No| Specify whether to delete the Internet Shared Bandwidth instance by force. Valid value:

 -   false: Do not delete the Internet Shared Bandwidth instance if it contains EIP.
-   true: Remove all EIPs in the Internet Shared Bandwidth instance and then delete the Internet Shared Bandwidth instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteCommonBandwidthPackage
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&CommonParameters
```

**Response example**

JSON format

```
{
    "RequestId":"B400EF57-60E3-4D61-B8FB-7FA8F72DF5A6"
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8"? >
<DeleteCommonBandwidthPackageResponse>
    <RequestId>B400EF57-60E3-4D61-B8FB-7FA8F72DF5A6</RequestId>
</DeleteCommonBandwidthPackageResponse>
```

