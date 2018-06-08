# AddCommonBandwidthPackageIp {#reference_i4w_xmt_ndb .reference}

添加EIP到共享带宽中。

调用本接口添加EIP时，请注意：

-   只支持添加后付费的EIP。

-   EIP和共享带宽的地域必须相同。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AddCommonBandwidthPackageIp

 |
|RegionId|String|是| 共享带宽所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthPackageId|String|是| 共享带宽的ID。

 |
|IpInstanceId|String|否| EIP实例的ID。

 您可以通过调用DescribeEipAddresses接口查询EIP实例的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AddCommonBandwidthPackageIp
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&IpInstanceId=eip-bp13e9i2qst4g6jzi35tc
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId": "01FDDD49-C4B7-4D2A-A8E5-A93915C450A6"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<AddCommonBandwidthPackageIpResponse>
    <RequestId>01FDDD49-C4B7-4D2A-A8E5-A93915C450A6</RequestId>
</AddCommonBandwidthPackageIpResponse>
```

