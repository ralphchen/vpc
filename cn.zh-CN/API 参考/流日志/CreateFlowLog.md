# CreateFlowLog {#reference_i4w_xmt_ndb .reference}

 创建流日志。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateFlowLog

 |
|RegionId|String|是| 流日志的所属地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|FlowLogName|String|否| 流日志名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://`或`https://`开头。

 |
|Description|String|否| 流日志描述。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |
|ResourceType|Integer|否|要捕获的流量的资源类型：-   NetworkInterface：弹性网卡
-   VSwitch：交换机内的所有弹性网卡
-   VPC：专有网络内的所有弹性网卡

|
|ResourceId|String|否|要捕获的流量的资源ID。|
|TrafficType|String|是|采集的流量类型：-   All：全部流量
-   Allow：访问控制允许的流量
-   Drop：访问控制拒绝的流量

|
|ProjectName|String|是|存储捕获到的流量的Project。|
|LogStoreName|String|是|存储捕获到的流量的LogStore。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|FlowLogId|String|流日志ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateFlowLog
&RegionId=cn-qingdao
&FlowLogName=myFlowlog
&ResourceType=NetworkInterface
&ResourceId=eni-askldfasxxxxxxxx
&ProjectName=FlowLogProject
&LogStoreName=FlowLogStore
&公共请求参数
```

**返回示例**

JSON格式

```

{
    "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx",
    "FlowLogId": "flowlog-m5evbtbptxxxxxxxxxxxx"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<CreateFlowLogResponse>
    <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxxx</RequestId>
    <FlowLogId>flowlog-m5evbtbptxxxxxxxxxxxx</FlowLogId>
</CreateFlowLogResponse>

```

