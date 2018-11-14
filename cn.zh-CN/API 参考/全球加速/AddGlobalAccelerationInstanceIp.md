# AddGlobalAccelerationInstanceIp {#reference_i4w_xmt_ndb .reference}

添加EIP到指定的带宽共享实例中。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AddGlobalAccelerationInstanceIp

 |
|RegionId|String|是| 共享带宽所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|GlobalAccelerationInstanceId|String|是| 共享型实例ID。

 |
|IpInstanceId|String|是| EIP实例的ID。

 您可以通过调用DescribeEipAddresses接口查询EIP实例的ID。

**说明：** 确保EIP的计费类型为后付费，且EIP的地域和共享型实例相同。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AddGlobalAccelerationInstanceIp
&RegionID=cn-hangzhou
&GlobalAccelerationInstanceId=ga-m5ex47zwya1sejynidhms
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
<AddGlobalAccelerationInstanceIpResponse>
    <RequestId>01FDDD49-C4B7-4D2A-A8E5-A93915C450A6</RequestId>
</AddGlobalAccelerationInstanceIpResponse>
```

