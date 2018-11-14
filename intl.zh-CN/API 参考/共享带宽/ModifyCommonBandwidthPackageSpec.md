# ModifyCommonBandwidthPackageSpec {#reference_i4w_xmt_ndb .reference}

更改共享带宽的带宽峰值。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCommonBandwidthPackageSpec

 |
|RegionId|String|是|共享带宽所在的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|Bandwidth|Integer|是| 共享带宽的带宽峰值，单位为Mbps。

 |
|BandwidthPackageId|String|是| 共享带宽的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyCommonBandwidthPackageSpec
&RegionID=cn-hangzhou
&Bandwidth=20
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId":"7F129000-F929-4AF5-BE8D-BAE434C795306"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<ModifyCommonBandwidthPackageSpecResponse>
    <RequestId>7F129000-F929-4AF5-BE8D-BAE434C79530</RequestId>
</ModifyCommonBandwidthPackageSpecResponse>
```

