# ActiveFlowLog {#reference_i4w_xmt_ndb .reference}

  启动流日志，启动后开始捕获指定资源的流量。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ActiveFlowLog

 |
|RegionId|String|是| 流日志的所属地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|FlowLogId|String|是|流日志ID。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ActiveFlowLog
&RegionId=cn-qingdao
&FlowLogId=fl-m5evbtbptxxxxxxxxxxxx
&公共请求参数
```

**返回示例**

JSON格式

```

{
    "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx",
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<ActiveFlowLogResponse>
    <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxxx</RequestId>
</ActiveFlowLogResponse>

```

