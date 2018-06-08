# CancelPhysicalConnection {#reference_smh_b4k_qdb .reference}

在物理专线开通前取消物理专线接入，取消后物理专线进入Canceled状态。

您只能取消处于Initial、Approved、Allocated和Confirmed状态（未开通状态）的物理专线。

## 请求参数 {#section_vmh_b4k_qdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CancelPhysicalConnection

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PhysicalConnectionId|String|是| 物理专线的ID。

 |

## 返回参数 {#section_nnh_b4k_qdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_qnh_b4k_qdb .section}

**请求示例**

```
hhttp://vpc.aliyuncs.com/?Action=CancelPhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId": "BE36E95A-F83E-4127-A29E-F2F35D4C999A"
}
```

