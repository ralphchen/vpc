# ModifyGlobalAccelerationInstanceAttributes {#reference_i4w_xmt_ndb .reference}

Modify the name and description of a Global Acceleration instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ModifyGlobalAccelerationInstanceAttributes

 |
|RegionId|String|Yes| The region of the Global Acceleration instance.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the Global Acceleration instance.

 |
|Name|String|No| The name of the Global Acceleration instance.

 The name can contain 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://`  or `https://`.

 |
|Description|String|No| The description of the Global Acceleration instance.

 The description can contain 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Example {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyGlobalAccelerationInstanceAttributes 
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-t4nluhu6n4xxxxxxxxxx
&Name=AdjustName
&Description=ModifyDescription
&CommonParameters
```

**Response example**

JSON format

```
{
    "RequestId": "BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX"
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
<ModifyGlobalAccelerationInstanceAttributesResponse>
    <RequestId>185E81B1-3916-4667-B48F-C52409B33F2B</RequestId>
</ModifyGlobalAccelerationInstanceAttributesResponse>
```

