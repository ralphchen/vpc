# DescribeEipMonitorData {#reference_i4w_xmt_ndb .reference}

查看EIP的监控信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeEipMonitorData

 |
|AllocationId|Integer|是|EIP的实例ID。|
|StartTime|String|是| 获取数据的起始时间。

 使用UTC时间。按照ISO8601标准，格式为YYYY-MM-DDThh:mm:ssZ。 例如，北京时间2013年1月10日20点0分0秒，表示为2013-01-10T12:00:00Z

 如果秒不是00，则自动取下一分钟为起始时间点。

 |
|EndTime|String|是| 获取数据的结束时间。

 使用UTC时间。按照ISO8601标准，格式为YYYY-MM-DDThh:mm:ssZ。 例如，北京时间2013年1月10日20点0分0秒，表示为2013-01-10T12:00:00Z

 如果秒不是00，则自动取下一分钟为起始时间点。

 |
|Period|Integer|否| 每条监控数据的时间长度，单位为秒，默认值为60，取值：

 \[60, 600, 3600\]

 **说明：** （EndTime – StartTime）/ Peroid必须大于200，即最多返回200条监控数据。如果EndTime – StartTime小于200则只返回起始时间点的监控数据。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|EipMonitorDatas|List|EIP监控数据的详细信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeEipMonitorData
&AllocationId=eip-2578g5v5a
&StartTime=2014-10-29T23:00:00Z
&EndTime=2014-10-30T08:00:00Z
&公共请求参数
```

**返回示例**

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeEipMonitorDataResponse>
<RequestId>C8B26B44-0189-443E-9816-D951F59623A9</RequestId>
<EipMonitorDatas>
    <EipMonitorData>
            <EipRX>122</EipRX>
            <EipTX>343</EipTX>
            <EipFlow>675</EipFlow>
            <EipPackets>3434</EipPackets>
            <EipBandwidth>10</EipBandwidth>
            <TimeStamp>2010-01-21T09:50:23Z</TimeStamp>
       </EipMonitorData>
    </EipMonitorDatas>
</DescribeEipMonitorDataResponse>
```

JSON格式

```
{
  "RequestId": "C8B26B44-0189-443E-9816-D951F59623A9",
  "EipMonitorDatas": {
    "EipMonitorData": [
      {
        "EipRX": "122",
        "EipTX": "343",
        "EipFlow": "675",
        "EipPackets": "3434",
        "EipBandwidth": "10",
        "IntranetFlow": 675,
        "IntranetBandwidth": 10,
        "TimeStamp": "2010-01-21T09:50:23Z"
      }
    ]
  }
}
```

