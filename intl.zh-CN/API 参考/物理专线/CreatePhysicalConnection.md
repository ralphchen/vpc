# CreatePhysicalConnection {#reference_a3b_znk_qdb .reference}

申请物理专线接入。

申请完成后，物理专线的状态为Initial，请联系运营商进行施工。

调用该接口时，请注意：

-   申请物理专线时，处于enabled状态之外的物理专线不得超过5条。

-   若账户下存在欠费状态的物理专线，则不能申请更多的物理专线。


## 请求参数 {#section_d3b_znk_qdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreatePhysicalConnection

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|AccessPointId|String|是| 物理专线所在的接入点。

 您可以通过调用 DescribeAccessPoints接口获取地域ID。

 |
|CircuitCode|String|否| 运营商的为物理专线提供的电路编码。

 |
|LineOperator|String|是| 提供接入物理线路的运营商，取值：

-   CT：中国电信

-   CU：中国联通

-   CM：中国移动

-   CO：中国其他

-   Equinix：Equinix

-   Other：境外其他


 |
|PeerLocation|String|是| 本地数据中心的地理位置。

 |
|Bandwidth|String|否|物理专线接入接口带宽，单位为Mbps，默认值为100，取值范围为 \[2, 10240\]。|
|PortType|String|否| 物理专线接入端口类型，取值：

-   100Base-T：百兆电口

-   1000Base-T（默认值）：千兆电口

-   1000Base-LX：千兆单模光口（10千米）

-   10GBase-T：万兆电口

-   10GBase-LR：万兆单模光口（10千米）


 |
|RedundantPhysicalConnectionId|String|否|冗余物理专线的ID，该专线的状态必须为Allocated、Confirmed或Enabled。|
|Name|String|否| 物理专线的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 物理专线的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_t3b_znk_qdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|PhysicalConnectionId|String|VPC的ID。|

## 示例 {#section_w3b_znk_qdb .section}

**请求示例**

```
https://vpc.aliyuncs.com/?Action=CreatePhysicalConnection
&RegionId=cn-beijing
&AccessPointId=ap-cn-beijing-ft-A
&LineOperator=CT
&PeerLocation=XXX
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreatePhysicalConnectionResponse>
        <RequestId>8A6A5EC5-6F6C-4906-9689-56ACE58A13E0"</RequestId>
        <PhysicalConnectionId>pc-*************</PhysicalConnectionId>
    </CreatePhysicalConnectionResponse>
    ```

-   JSON格式

    ```
    {
      "PhysicalConnectionId": "pc-**************",
      "RequestId": "8A6A5EC5-6F6C-4906-9689-56ACE58A13E0"
    }
    ```


