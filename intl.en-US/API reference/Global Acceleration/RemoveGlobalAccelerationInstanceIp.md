# RemoveGlobalAccelerationInstanceIp {#reference_i4w_xmt_ndb .reference}

Remove an EIP from a shared-bandwidth instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name |Type|Required|Description |
|:----|:---|:-------|:-----------|
|Action|String|Yes| The action to perform. Valid value: 

 RemoveGlobalAccelerationInstanceIp

 |
|RegionId|String|Yes| The ID of the region where the shared-bandwidth instance is located.

 Call the DescribeRegions API to obtain the region ID.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the shared-bandwidth instance.

 |
|IpInstanceId|String|Yes| The ID of the EIP to remove.

 Call the DescribeEipAddresses API to obtain the EIP ID.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=RemoveGlobalAccelerationInstanceIp
&RegionID=cn-hangzhou
&GlobalAccelerationInstanceId=ga-m5ex47zwya1sejynidhms
&IpInstanceId=eip-bp13e9i2qst4g6jzi35tc
&CommonRequestParameters
```

**Response example**

JSON format

```
{
    "RequestId": "01FDDD49-C4B7-4D2A-A8E5-A93915C450A6"
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
<RemoveGlobalAccelerationInstanceIpResponse>
    <RequestId>01FDDD49-C4B7-4D2A-A8E5-A93915C450A6</RequestId>
</RemoveGlobalAccelerationInstanceIpResponse>
```

