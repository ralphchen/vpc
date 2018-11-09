# CreateRouterInterface {#reference_i4w_xmt_ndb .reference}

创建路由器接口。

调用本接口创建路由器接口时，请注意：

-   任意两个路由器之间，最多只能存在一对互连的路由器接口。

-   一个路由器上可以最多创建5个路由器接口。

-   如果账户下存在欠费状态的路由器接口，则无法再创建路由器接口。

-   同一路由表下的路由条目的目标网段（DestinationCidrBlock）不允许相同。

-   边界路由器（VBR）只能是连接发起端，并且是已激活状态。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateRouterInterface

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouterType|String|是| 路由器接口关联的路由器类型。取值：

 -   VRouter：VPC路由器

-   VBR：边界路由器


 |
|AccessPointId|String|否| VBR所属的接入点ID。

 您可以通过调用 DescribeAccessPoints接口获取物理专线接入点ID。

 **说明：** 物理专线接入场景下需指定该参数。

 |
|RouterId|String|是| 路由器接口关联的路由器ID。

 |
|Role|String|是| 路由器接口的角色，取值：

 -   InitiatingSide：连接发起端。

-   AcceptingSide：连接接收端。


 |
|Spec|String|是| 路由器接口的规格。可用的规格和对应的带宽如下：

 -   Mini.2：2 Mbps

-   Mini.5：5 Mbps

-   Small.1：10 Mbps

-   Small.2：20 Mbps

-   Small.5：50 Mbps

-   Middle.1：100 Mbps

-   Middle.2：200 Mbps

-   Middle.5：500 Mbps

-   Large.1： 1000 Mbps

-   Large.2：2000 Mbps

-   Large.5： 5000 Mbps

-   Xlarge.1：10000 Mbps

**说明：** 当Role为AcceptingSide\(连接接收端\)时，Spec取值为 Negative。


 |
|OppositeRegionId|String|是| 连接接收端所在的地域。

 |
|OppositeAccessPointId|String|否|对端所属的接入点ID。**说明：** 对端路由器接口位于VBR上时需指定该参数，创建路由器接口后无法修改。

|
|OppositeRouterType|String|否| 对端路由器接口关联的路由器类型。取值：

 -   VRouter：VPC路由器

-   VBR：边界路由器


 |
|OppositeRouterId|String|否| 对端的路由器的ID。

 |
|OppositeInterfaceId|String|否| 对端路由器接口ID。

 |
|OppositeInterfaceOwnerId|String|否| 对端路由器接口的所有者ID。

 |
|HealthCheckSourceIp|String|否| 健康检查源IP地址，必须是本端VPC内的一个未被使用的IP。

 **说明：** 物理专线接入场景下可指定该参数。

 |
|HealthCheckTargetIp|String|否| 健康检查目的IP地址。

 **说明：** 该参数为必选，当指定了HealthCheckSourceIp后。

 |
|Name|String|否| 路由器接口的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 路由器接口的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|InstanceChargeType|String|否| 路由器接口的付费方式。取值：

 -   PostPaid（默认值）：后付费。


 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|RouterInterfaceId|String|路由器接口的ID。|
|OrderId|String|订单号，选择预付费时返回该参数。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateRouterInterface
&RegionId=cn-beijing
&Role=InitiatingSide
&OppositeRegionId=cn-beijing
&Spec=Mini.5
&RouterType=VRouter
&RouterId=vrt-2zepuy8qbrq6yhdje53t6
&OppositeRouterId= vrt-2zefso23vmu6xi3jeiw0z
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateRouterInterfaceResponse>
        <RequestId>980960B0-2969-40BF-8542-EBB34FD358AB</RequestId>
        <RouterInterfaceId>ri-2ze7fbuohmxxxxxx</RouterInterfaceId>
    </CreateRouterInterfaceResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "980960B0-2969-40BF-8542-EBB34FD358AB"
        "RouterInterfaceId": "ri-2ze7fbuohmxxxxxx"
    }
    ```


