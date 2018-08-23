# ModifyGlobalAccelerationInstanceSpec {#reference_i4w_xmt_ndb .reference}

Modify the bandwidth of a Global Acceleration instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ModifyGlobalAccelerationInstanceSpec

 |
|RegionId|String|Yes| The region of the Global Acceleration instance.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the Global Acceleration instance.

 |
|Bandwidth|Integer|Yes| The peak bandwidth in Mbps of the Global Acceleration instance. Valid values: \[10,20,30,40,50,60,70,80,90,100,200,300,400,500,600,700,800,900,1000\]

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyGlobalAccelerationInstanceSpec 
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-t4nluhu6n4xxxxxxxxxx
&Bandwidth=20
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
<ModifyGlobalAccelerationInstanceSpecResponse>
    <RequestId>BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX</RequestId>
</ModifyGlobalAccelerationInstanceSpecResponse>
```

