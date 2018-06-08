# DeleteRouteEntry {#reference_i4w_xmt_ndb .reference}

删除VPC路由器或边界路由器的路由表中的路由条目。

调用本接口删除路由条目时，请注意：

-   只有处于Available状态的路由条目可以被删除。

-   路由表所在的VPC正在进行创建/删除交换机或路由条目时，无法删除路由条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteRouteEntry

 |
|RouteTableId|String|是| 路由条目所在的路由表的ID。

 |
|DestinationCidrBlock|String|是| 路由条目的目标网段。

 |
|NextHopId|String|否| 路由条目的下一跳实例的ID。在删除普通（非ECMP）路由条目时，指定该参数。

 |
|NextHopList|List|否| 路由条目的下一跳列表。在删除ECMP路由条目时，指定该参数。

 |

|参数|类型|是否必须|描述|
|:-|:-|----|:-|
|NextHopType|String|否| 下一跳的类型，取值：

 -   Instance：ECS实例（默认值）

HaVip：高可用虚拟IP

RouterInterface：路由器接口


 |
|NextHopId|String|否|下一跳实例的ID。|
|Enabled|Integer|否|是否启用下一跳：-   0：不可用

-   1：可用


|
|Weight|Integer|否|下一跳的路由权重。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteRouteEntry
&RouterTableId=vtb-25vtxl5ct
&DestinationCidrBlock=192.168.1.0/24
&NextHopId=i-25skktcp4
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteRouteEntryResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteRouteEntryResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


