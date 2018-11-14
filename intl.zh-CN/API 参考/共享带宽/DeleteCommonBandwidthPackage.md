# DeleteCommonBandwidthPackage {#reference_i4w_xmt_ndb .reference}

删除共享带宽包。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteCommonBandwidthPackage

 |
|RegionId|String|是| 共享带宽所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthPackageId|String|是| 共享带宽的ID。

 |
|Force|Boolean|否| 指定是否强制删除共享带宽。取值：

 -   false（默认值）：只删除不包含EIP的共享带宽。
-   true：将共享带宽内的EIP全部移出后，删除共享带宽。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteCommonBandwidthPackage
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId":"B400EF57-60E3-4D61-B8FB-7FA8F72DF5A6"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8"?>
<DeleteCommonBandwidthPackageResponse>
    <RequestId>B400EF57-60E3-4D61-B8FB-7FA8F72DF5A6</RequestId>
</DeleteCommonBandwidthPackageResponse>
```

