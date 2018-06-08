# ModifyCommonBandwidthPackagePayType {#reference_i4w_xmt_ndb .reference}

将共享带宽的付费类型从后付费转换为预付费。

**说明：** 转换过程不会对您的业务产生影响。

## 请求参数 {#section_hpf_5d5_vdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCommonBandwidthPackagePayType

 |
|RegionId|String|是|共享带宽所在的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|BandwidthPackageId|String|是| 共享带宽的ID。

 |
|Name|String|否| 共享带宽的计费周期。取值：

 -   Month（默认值）：按月付费。
-   Year：按年付费。

 |
|Duration|String|否|共享带宽的付费时长，默认值为1。选择按月付费时取值范围为 \[1, 36\]，选择按年付费时取值范围为 \[1, 3\]。

|
|Description|String|否| 指定是否立即支付费用。取值：

 -   false（默认值）：生成订单后再进行支付。
-   true：直接付款。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|OrderId|String|订单ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyCommonBandwidthPackagePayType
&AutoPay=true
&BandwidthPackageId=cbwp-uf61rxnumwwjkttaurhuv
&Duration=2
&PricingCycle=Month
&RegionId=cn-shanghai
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
<ModifyCommonBandwidthPackagePayTypeResponse>
    <RequestId>0CEBAFA2-3FE9-4008-BF1F-B7C5E66015D9</RequestId>
</ModifyCommonBandwidthPackagePayTypeResponse>
```

