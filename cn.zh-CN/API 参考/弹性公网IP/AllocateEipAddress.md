# AllocateEipAddress {#reference_i4w_xmt_ndb .reference}

申请弹性公网IP（EIP）。

调用本接口后将在指定的地域内随机获取一个状态为Available的EIP。EIP在传输层目前只支持ICMP、TCP和UDP协议，不支持IGMP和SCTP等协议。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AllocateEipAddress

 |
|RegionId|String|是| EIP所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Bandwidth|String|否| EIP的带宽峰值，单位为Mbps，默认值为5。

 |
|InternetChargeType|String|否| EIP的计费方式。取值：

-   PayByBandwidth（默认值）：按带宽计费

-   PayByTraffic：按流量计费。


 |
|InstanceChargeType|String|否| EIP的付费方式。取值：

 -   PrePaid：预付费

-   PostPaid（默认值）：后付费。


 |
|PricingCycle|String|否| 预付费的计费周期，取值：

 -   Month（默认值）：按月付费

-   Year：按年付费。


 **说明：** InstanceChargeType参数的值为PrePaid时，该参数必选。

 |
|Period|String|否| 购买时长。取值：

 -   当选择按月付费时，取值范围为 \[1, 9\]

-   当选择按年付费时，取值范围为 \[1, 3\]


 **说明：** InstanceChargeType参数的值为PrePaid时，该参数必选。

 |
|AutoPay|String|否| 是否自动付费，取值：

 -   false：不开启自动付费，生成订单后需要到[订单中心](https://expense.console.aliyun.com/?#/order/list/)完成支付。

-   true：开启自动付费，自动支付订单。


 **说明：** InstanceChargeType参数的值为PrePaid时，该参数必选。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|EipAddress|String|分配的EIP。|
|AllocationId|String|EIP的ID。|
|OrderId|String|订单号，选择预付费时返回该参数。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#AllocateEipAddress}
https://vpc.aliyuncs.com/?Action=AllocateEipAddress
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <AllocateEipAddressResponse>
        <AllocationId>eip-25877c70x</AllocationId>
        <EipAddress>123.56.0.206</EipAddress>
        <RequestId>B6B9F518-60F8-4D81-9242-1207B356754D</RequestId>
    </AllocateEipAddressResponse>
    ```

-   JSON格式

    ```
    {
      "AllocationId": "eip-25877c70x",
      "EipAddress": "123.56.0.206",
      "RequestId": "B6B9F518-60F8-4D81-9242-1207B356754D"
    }
    ```


