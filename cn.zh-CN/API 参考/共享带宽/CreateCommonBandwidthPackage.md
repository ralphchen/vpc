# CreateCommonBandwidthPackage {#reference_i4w_xmt_ndb .reference}

创建共享带宽。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateCommonBandwidthPackage

 |
|RegionId|String|是| 共享带宽所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Bandwidth|Integer|是| 共享带宽的带宽峰值，单位为Mbps。

 |
|InternetChargeType|String|否| 共享带宽的计费方式，取值：

 PayByBandwidth（默认值）：按带宽计费

 PayBy95：按增强型95计费

 |
|Ratio|Integer|否|共享带宽的保底百分比，取值范围为\[10, 100\]，即保底百分比的范围是10%-100%，选择按增强型95计费时需指定该参数。|
|Name|String|否| 共享带宽的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 共享带宽的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|BandwidthPackageId|String|共享带宽的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateCommonBandwidthPackage
&RegionID=cn-hangzhou
&Bandwidth=10
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "CreateCommonBandwidthPackageResponse": {
        "BandwidthPackageId": "cbwp-bp1vevu8h3ieh5xkcdhdy", 
        "RequestId": "FF39F653-033E-4CD9-9EDF-3CCA5A71FBC3"
    }
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<CreateCommonBandwidthPackageResponse>
    <BandwidthPackageId>cbwp-bp1vevu8h3ieh5xkcdhdy</BandwidthPackageId>
    <RequestId>FF39F653-033E-4CD9-9EDF-3CCA5A71FBC3</RequestId>
</CreateCommonBandwidthPackageResponse>

```

