# AddCommonBandwidthPackageIp {#reference_i4w_xmt_ndb .reference}

Add an EIP to an Internet Shared Bandwidth instance.

Note the following before calling this API to add an EIP:

-   You can only add a Pay-As-You-Go EIP.

-   The EIP and the Internet Shared Bandwidth instance must be in the same region.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 AddCommonBandwidthPackageIp

 |
|RegionId|String |Yes| The ID of the region where the Internet Shared Bandwidth instance is located.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BandwidthPackageId|String |Yes| The ID of the Internet Shared Bandwidth instance.

 |
|IpInstanceId|String|No| The ID of the EIP instance.

 You can obtain the ID of the EIP instance by calling the DescribeEipAddresses API.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AddCommonBandwidthPackageIp
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&IpInstanceId=eip-bp13e9i2qst4g6jzi35tc
&CommonParameters
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
<AddCommonBandwidthPackageIpResponse>
    <RequestId>01FDDD49-C4B7-4D2A-A8E5-A93915C450A6</RequestId>
</AddCommonBandwidthPackageIpResponse>
```

