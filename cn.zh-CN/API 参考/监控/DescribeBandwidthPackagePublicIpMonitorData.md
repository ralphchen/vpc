# DescribeBandwidthPackagePublicIpMonitorData {#reference_i4w_xmt_ndb .reference}

查询NAT带宽包中指定公网IP的监控数据。

**说明：** 本接口仅支持在2017年11月3日之前账号下存在NAT带宽包的用户调用。2017年11月3日之前账号下不存在NAT带宽包的用户，请绑定EIP，详情参见[AssociateEipAddress](cn.zh-CN/API 参考/NAT网关/AssociateEipAddress.md#)。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeBandwidthPackagePublicIpMonitorData

 |
|RegionId|String|是| NAT带宽包所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|AllocationId|Integer|是|公网IP的ID。|
|StartTime|String|是| 获取数据的起始时间点，按照ISO8601标准表示，并需要使用UTC+8时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 如果秒不是00，则自动取下一分钟为起始时间点。

 |
|EndTime|String|是| 获取数据的结束时间点，按照ISO8601标准表示，并需要使用UTC+8时间。格式为：YYYY-MM-DDThh:mm:ssZ。

 如果秒不是00，则自动取下一分钟为结束时间点。

 |
|Period|Integer|否| 每条监控数据的时间长度，单位为秒，默认值为60。

 取值：\[60, 600, 3600\]。

 （EndTime – StartTime）/ Peroid必须大于200，即最多返回200条监控数据。

 如果EndTime – StartTime小于200则只返回起始时间点的监控数据。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|MonitorDatas|List|指定公网IP监控数据的详细信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBandwidthPackagePublicIpMonitorData
&AllocationId=eip-2578g5v5a
&StartTime=2014-10-29T23:00:00Z
&EndTime=2014-10-30T08:00:00Z
&公共请求参数
```

**返回示例**

JSON格式

```
{
  "DescribeBandwidthPackagePublicIpMonitorDataResponse": {
    "MonitorDatas": {
      "MonitorData": {
        "EipRX": "122",
        "EipTX": "343",
        "EipFlow": "675",
        "EipPackets": "3434",
        "EipBandwidth": "10",
        "TimeStamp": "2010-01-21T09:50:23Z"
      }
    },
    "RequestId": "3D0439A4-0480-4D76-B8A9-02B80DB4E406"
  }
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeBandwidthPackagePublicIpMonitorDataResponse>
<MonitorDatas><MonitorData>
            <EipRX>122</EipRX>
            <EipTX>343</EipTX>
            <EipFlow>675</EipFlow>
            <EipPackets>3434</EipPackets>
            <EipBandwidth>10</EipBandwidth>
            <TimeStamp>2010-01-21T09:50:23Z</TimeStamp>
       </MonitorData></MonitorDatas>
<RequestId>3D0439A4-0480-4D76-B8A9-02B80DB4E406</RequestId>
</DescribeBandwidthPackagePublicIpMonitorDataResponse>
```

