# DescribeCommonBandwidthPackages {#reference_amt_w2p_rdb .reference}

查询指定地域中共享带宽的列表。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCommonBandwidthPackages

 |
|RegionId|String|是| 共享带宽所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthPackageId|String|是| 共享带宽的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_hlq_4gp_rdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|CommonBandwidthPackages|List|共享带宽的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|BandwidthPackageId|String| 共享带宽的ID。

 |
|Name|String| 共享带宽的名称。

 |
|Description|String| 共享带宽的描述信息。

 |
|Bandwidth|Integer| 共享带宽的带宽峰值。

 |
|InternetChargeType|String| 共享带宽的计费方式。

 -   PayBy95：按增强型95计费

-   PayByBandwidth：按带宽计费


 |
|BusinessStatus |String| 共享带宽的付费状态。

 -   Normal：正常

-   FinancialLocked：欠费锁定


 |

|名称|类型|描述|
|--|--|--|
|IpAddress|String|EIP的地址。|
|AllocationId|String|EIP的实例ID。|

## 示例 {#section_dg4_y5r_rdb .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeCommonBandwidthPackages
&RegionID=cn-hangzhou
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "DescribeCommonBandwidthPackagesResponse": {
        "PageNumber": "1", 
        "TotalCount": "1", 
        "PageSize": "10", 
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
                    "PublicIpAddresse": {
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

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
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

