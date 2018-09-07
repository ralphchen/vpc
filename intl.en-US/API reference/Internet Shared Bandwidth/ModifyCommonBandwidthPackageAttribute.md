# ModifyCommonBandwidthPackageAttribute {#reference_i4w_xmt_ndb .reference}

Modify the name and description of an Internet Shared Bandwidth instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description |
|:---|:---|:-------|:-----------|
|Action|String |Yes| The action to perform. Valid value:

 ModifyCommonBandwidthPackageAttribute

 |
|RegionId|String|Yes|The ID of the region where the Internet Shared Bandwidthinstance is located.You can obtain the region ID by calling the DescribeRegions API.

|
|BandwidthPackageId|String |Yes| The ID of the Internet Shared Bandwidth instance.

 |
|Name|String|No| The name of the Internet Shared Bandwidth instance.

 The name can contain 2-128 characters including a-z, A-Z, 0-9, periods, underlines, and hyphens. It must start with English letters, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the Internet Shared Bandwidth instance.

 The description can contain 2-256 characters. It must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name |Type|Description|
|:----|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyCommonBandwidthPackageAttribute
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&Name=abc
&CommonParameters
```

**Response example**

JSON format

```
{
    "RequestId":B450CAD8-50BC-4506-ADA7-35C6CE63E96B6"
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
<ModifyCommonBandwidthPackageAttributeResponse>
    <RequestId>B450CAD8-50BC-4506-ADA7-35C6CE63E96B</RequestId>
</ModifyCommonBandwidthPackageAttributeResponse>
```

