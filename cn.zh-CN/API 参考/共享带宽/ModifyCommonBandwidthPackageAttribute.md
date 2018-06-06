# ModifyCommonBandwidthPackageAttribute {#reference_i4w_xmt_ndb .reference}

修改共享带宽的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCommonBandwidthPackageAttribute

 |
|RegionId|String|是|共享带宽所在的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|BandwidthPackageId|String|是| 共享带宽的ID。

 |
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

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyCommonBandwidthPackageAttribute
&RegionID=cn-hangzhou
&BandwidthPackageId=cbwp-bp1vevu8h3ieh5xkcdhdy
&Name=abc
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId":B450CAD8-50BC-4506-ADA7-35C6CE63E96B6"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<ModifyCommonBandwidthPackageAttributeResponse>
    <RequestId>B450CAD8-50BC-4506-ADA7-35C6CE63E96B</RequestId>
</ModifyCommonBandwidthPackageAttributeResponse>
```

