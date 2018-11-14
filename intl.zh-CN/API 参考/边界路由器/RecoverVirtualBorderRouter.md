# RecoverVirtualBorderRouter {#reference_i4w_xmt_ndb .reference}

恢复被终止的边界路由器（VBR）。

调用该接口后VBR从Terminated状态变为Recovering状态，恢复成功后进入Enabled状态。在调用本接口恢复VBR之前，请注意：

-   只有物理专线的所有者可以调用该接口。

-   VBR所属的物理专线必须处于Enabled状态。


## 请求参数 {#section_qjj_tpp_vdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 RecoverVirtualBorderRouter

 |
|RegionId|String|是| VBR所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VbrId|String|是| VBR的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=RecoverVirtualBorderRouter
&VbrId=pc-2zeoaxkq3xxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <RecoverVirtualBorderRouterResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </RecoverVirtualBorderRouterResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


