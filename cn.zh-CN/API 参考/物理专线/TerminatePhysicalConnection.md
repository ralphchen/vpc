# TerminatePhysicalConnection {#reference_i4w_xmt_ndb .reference}

在物理专线开通后终止物理专线接入。调用本接口后物理专线进入Terminating状态，处理完成后进入Terminated状态。

调用本接口终止物理专线时，请注意：

-   只能终止处于Enabled状态的物理专线。

-   终止物理专线之前，必须删除与其关联的VBR。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 TerminatePhysicalConnection

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PhysicalConnectionId|String|是| 物理专线的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=TerminatePhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

XML格式

```
<?xml version="1.0" encoding="UTF-8"?>
{
  "RequestId": "513E0A50-4F2D-4CBE-BF35-40559DF65D79"
}
```

