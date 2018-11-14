# DeleteVirtualBorderRouter {#reference_i4w_xmt_ndb .reference}

删除边界路由器（VBR）。

在调用本接口删除VBR之前，请注意：

-   删除VBR之前，必须删除VBR上所有的路由器接口。
-   只能删除Unconfirmed，Enabled或Terminated状态的VBR。
-   其他用户的VBR只有处于Unconfirmed状态时，才可以被物理专线的所有者删除。


## 请求参数 {#section_fpn_kpp_vdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteVirtualBorderRouter

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
https://vpc.aliyuncs.com/?Action=DeleteVirtualBorderRouter
&VbrId=pc-2zeoaxkq3xxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteVirtualBorderRouterResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteVirtualBorderRouterResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


