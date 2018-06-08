# DeletePhysicalConnection {#reference_i4w_xmt_ndb .reference}

删除物理专线。

只能删除处于Rejected、Canceled、AllocationFailed和Terminated状态的物理专线。

## 请求参数 {#section_tgk_2pp_vdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeletePhysicalConnection

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
https://vpc.aliyuncs.com/?Action=DeletePhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeletePhysicalConnectionResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeletePhysicalConnectionResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


