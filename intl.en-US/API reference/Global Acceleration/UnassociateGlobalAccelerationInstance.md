# UnassociateGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

Unbind a Global Acceleration instance from the associated backend server.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 UnassociateGlobalAccelerationInstance

 |
|RegionId|String|Yes| The region of the Global Acceleration instance.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the Global Acceleration instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=UnassociateGlobalAccelerationInstance
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-t4nluhu6n417xxxxxxxx
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
<UnassociateGlobalAccelerationInstanceResponse>
    <RequestId>BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX</RequestId>
</UnassociateGlobalAccelerationInstanceResponse>
```

