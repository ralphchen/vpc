# ModifyCommonBandwidthPackageSpec {#reference_i4w_xmt_ndb .reference}

Modify the peak bandwidth of an Internet Shared Bandwidth instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value: 

 ModifyCommonBandwidthPackageSpec

 |
|RegionId|String |Yes|The ID of the region where the Internet Shared Bandwidth instance is located.You can obtain the region ID by calling the DescribeRegions API.

|
|Bandwidth|Integer|Yes| The peak bandwidth in Mbps of the Internet Shared Bandwidth instance.

 |
|BandwidthPackageId|String |Yes| The ID of the Internet Shared Bandwidth instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyCommonBandwidthPackageSpec
&RegionID=cn-hangzhou
&Bandwidth=20
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&CommonParameters
```

**Response example**

JSON format

```
{
    "RequestId":"7F129000-F929-4AF5-BE8D-BAE434C795306"
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
<ModifyCommonBandwidthPackageSpecResponse>
    <RequestId>7F129000-F929-4AF5-BE8D-BAE434C79530</RequestId>
</ModifyCommonBandwidthPackageSpecResponse>
```

