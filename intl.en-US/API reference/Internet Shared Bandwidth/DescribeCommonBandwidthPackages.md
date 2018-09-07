# DescribeCommonBandwidthPackages {#reference_amt_w2p_rdb .reference}

Query Internet Shared Bandwidth instances in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes| The action to perform. Valid value: 

 DescribeCommonBandwidthPackages

 |
|RegionId|String |Yes| The ID of the region where the Internet Shared Bandwidth instance is located.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BandwidthPackageId|String |Yes| The ID of the Internet Shared Bandwidth instance.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize |Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_hlq_4gp_rdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of rows per page.|
|CommonBandwidthPackages|List|A list of Internet Shared Bandwidth instances.|

|Name|Type|Description|
|:---|:---|:----------|
|BandwidthPackageId|String| The ID of the Internet Shared Bandwidth instance.

 |
|Name|String| The name of the Internet Shared Bandwidth instance.

 |
|Description|String| The description of the Internet Shared Bandwidth instance.

 |
|Bandwidth|Integer| The peak bandwidth of the Internet Shared Bandwidth instance.

 |
|InternetChargeType|String| The billing method of the Internet Shared Bandwidth instance.

 -   PayBy95: Pay by classic 95th percentile pricing.

-   PayByBandwidth: Pay by bandwidth.


 |
|BusinessStatus |String| The business status of the Internet Shared Bandwidth instance.

 -   Normal: normal

-   FinancialLocked: Locked because the instance is overdue


 |

|Name|Type|Description|
|----|----|-----------|
|IpAddress|String|The address of the EIP.|
|AllocationId|String|The ID of the EIP instance.|

## Examples {#section_dg4_y5r_rdb .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeCommonBandwidthPackages
&RegionId=cn-hangzhou
&CommonParameters
```

**Response example**

JSON format

```
{
    "DescribeCommonBandwidthPackagesResponse": {
        "PageNumber": 1, 
        "TotalCount": "1", 
        "PageSize": 10, 
        "RequestId": "20E6FD1C-7321-4DAD-BDFD-EC8769E4AA33", 
        "CommonBandwidthPackages": {
            "CommonBandwidthPackage": {
                "ZoneId": "cn-hangzhou-d", 
                "InternetChargeType": "PayByBandwidth", 
                "Name": "abc", 
                "CreationTime": "2017-06-28T06:39:20Z", 
                "Status": "Available", 
                "BandwidthPackageId": "cbwp-bp1vevu8h3ieh5xkcdhdy", 
                "BusinessStatus": "Normal", 
                "RegionId": "cn-hangzhou", 
                "Ratio": "100", 
                "InstanceChargeType": "PostPaid", 
                "PublicIpAddresses": {
                    "PublicIpAddresse": [
                        "IpAddress": "116.62.129.250", 
                        "AllocationId": "eip-bp13e9i2qst4g6jzi35tc"
                    }
                }, 
                "Bandwidth": "20"
            }
        }
    }
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
<DescribeCommonBandwidthPackagesResponse>
    <PageNumber>1</PageNumber>
    <TotalCount>1</TotalCount>
    <PageSize>10</PageSize>
    <RequestId>20E6FD1C-7321-4DAD-BDFD-EC8769E4AA33</RequestId>
    <CommonBandwidthPackages>
        <CommonBandwidthPackage>
            <Description/>
            <ZoneId>cn-hangzhou-d</ZoneId>
            <InternetChargeType>PayByBandwidth</InternetChargeType>
            <Name>abc</Name>
            <CreationTime>2017-06-28T06:39:20Z</CreationTime>
            <Status>Available</Status>
            <BandwidthPackageId>cbwp-bp1vevu8h3ieh5xkcdhdy</BandwidthPackageId>
            <BusinessStatus>Normal</BusinessStatus>
            <RegionId>cn-hangzhou</RegionId>
            <Ratio>100</Ratio>
            <InstanceChargeType>PostPaid</InstanceChargeType>
            <PublicIpAddresses>
                <PublicIpAddresse>
                    <IpAddress>116.62.129.250</IpAddress>
                    <AllocationId>eip-bp13e9i2qst4g6jzi35tc</AllocationId>
                </PublicIpAddresse>
            </PublicIpAddresses>
            <Bandwidth>20</Bandwidth>
        </CommonBandwidthPackage>
    </CommonBandwidthPackages>
</DescribeCommonBandwidthPackagesResponse>
```

