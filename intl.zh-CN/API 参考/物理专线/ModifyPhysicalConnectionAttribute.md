# ModifyPhysicalConnectionAttribute {#reference_i4w_xmt_ndb .reference}

修改物理专线的配置。

调用该接口时，请注意：

-   只有处于Initial或Rejected状态的物理专线可以修改规格和冗余专线ID。

-   无法修改处于Canceled、Allocating、AllocationFailed和Terminated状态的物理专线。

-   处于Rejected状态的物理专线被修改后会进入Initial状态。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyPhysicalConnectionAttribute

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PhysicalConnectionId|String|是| 物理专线的ID。

 |
|LineOperator|String|否| 提供接入物理线路的运营商，取值：

-   CT：中国电信

-   CU：中国联通

-   CM：中国移动

-   CO：中国其他

-   Equinix：Equinix

-   Other：境外其他


 |
|CircuitCode|String|否| 运营商的为物理专线提供的电路编码。

 |
|PeerLocation|String|否| 本地数据中心的地理位置。

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

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyPhysicalConnectionAttribute
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&Name=test3
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyPhysicalConnectionAttributeResponse>
        <RequestId>8A6A5EC5-6F6C-4906-9689-56ACE58A13E0"</RequestId>
    </ModifyPhysicalConnectionAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "8A6A5EC5-6F6C-4906-9689-56ACE58A13E0"
    }
    ```


