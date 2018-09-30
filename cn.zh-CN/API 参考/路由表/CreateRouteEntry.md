# CreateRouteEntry {#reference_i4w_xmt_ndb .reference}

在VPC路由器或边界路由器（VBR）上创建自定义路由条目。

使用该接口为专有网络的路由器的路由表添加自定义路由条目时，请注意：

-   同一个路由表中自定义路由条目不能超过48条。

-   自定义路由条目的目标网段（DestinationCidrBlock）不能和VPC内的交换机的网段相同，也不能包含交换机的网段或者被交换机的网段包含。

-   自定义路由条目的目标网段（DestinationCidrBlock）不能指向100.64.0.0/10，也不能被100.64.0.0/10包含。

-   同一路由表下的路由条目的目标网段（DestinationCidrBlock）不允许相同。

-   如果指定的目标网段（DestinationCidrBlock）是一个IP地址，会按照32位掩码来处理。

-   多条自定义路由条目可以指向同一个下一跳（NextHopId）。
-   自定义路由条目的下一跳（NextHopId）必须和路由表在同一个VPC。
-   支持通过NextHopList参数配置ECMP路由：
    -   添加普通（非 ECMP ）自定义路由时，需指定DestinationCidrBlock、NextHopType和NextHopId参数，且不能指定 NextHopList参数。

    -   添加ECMP路由时，需指定DestinationCidrBlock和NextHopList参数，且不能指定NextHopType 和 NextHopId参数。


使用该接口为VBR的路由表添加自定义路由条目时，请注意：

-   同一个路由表中自定义路由条目不能超过48条。

-   不支持NextHopList参数。

-   自定义路由条目的目标网段（DestinationCidrBlock）不能指向100.64.0.0/10，也不能被100.64.0.0/10包含。

-   同一路由表下的路由条目的目标网段（DestinationCidrBlock）不允许相同。

-   如果指定的目标网段（DestinationCidrBlock）是一个IP地址，会按照32位掩码来处理。

-   多条自定义路由条目可以指向同一个下一跳（NextHopId）。
-   自定义路由条目的下一跳（NextHopId）必须是该VBR关联的路由器接口。
-   只允许在VBR状态是Active，而且对应的物理专线状态是Enabled且没有被欠费锁定的情况下在VBR上新建路由条目。

-   仅支持添加普通路由（非 ECMP），需指定DestinationCidrBlock、NextHopType和NextHopId参数，且不能指定 NextHopList参数。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateRouteEntry

 |
|RouteTableId|String|是| 路由表ID。

 |
|DestinationCidrBlock|String|是| 自定义路由条的目标网段，需满足以下要求：

 -   目标网段不能指向100.64.0.0/10或被100.64.0.0/10包含。

-   同一张路由表内的不同路由条目的目标网段不能相同。

（默认值）

-   如果提供的目标网段是一个IP地址，掩码将按照32位处理。


 |
|NextHopType|String|否| 下一跳的类型。取值：

 -   Instance：ECS实例（默认值）

VpnGateway：VPN网关

-   HaVip：高可用虚拟IP

-   RouterInterface：路由器接口

-   NetworkInterface ：弹性网卡


 **说明：** 创建普通（非ECMP路由）路由条目时必须指定该参数。

 |
|NextHopId|String|否| 路由条目的下一跳实例ID。

 下一跳必须位于路由表所在的VPC或VBR中。

 **说明：** 创建普通（非ECMP路由）路由条目时必须指定该参数。

 |
|NextHopList|List|否| 路由条目的下一跳列表，需满足以下条件：

 -   只支持在VPC中的路由表创建ECMP路由条目。

-   NextHopList中的下一跳数量为2-4个。

-   NextHopList中的下一跳只能是VPC中指向VBR的路由器接口。


 **说明：** 创建ECMP路由条目时必须指定该参数。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

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
https://vpc.aliyuncs.com/?Action=CreateRouteEntry
&VpcId=vpc-257gq642n
&RouteTableId=vrt-5citwfp6a
&DestinationCidrBlock=0.0.0.0/0
&NextHopId=i-25skktcp4
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateRouteEntryResponse>
        <RequestId>12D086F6-8F31-4658-84C1-006DED011A85</RequestId>
    </CreateRouteEntryResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "12D086F6-8F31-4658-84C1-006DED011A85"
    }
    ```


