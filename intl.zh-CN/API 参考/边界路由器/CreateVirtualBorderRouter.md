# CreateVirtualBorderRouter {#reference_i4w_xmt_ndb .reference}

新建边界路由器（VBR）。

每条物理专线下可以存在各属于其所有者和其他账号的两个VBR。调用本接口为物理专线所有者创建VBR后，VBR进入Enabled状态。如果为其他账号创建VBR，创建后VBR进入Unconfirmed状态。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateVirtualBorderRouter

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PhysicalConnectionId|String|是| 物理专线的ID。

 |
|VbrOwnerId|String|否| VBR所有者的账号ID。

 默认为当前用户的账号ID，即为物理专线的所有者创建VBR。

 |
|VlanId|String|是| VBR的VLAN ID，取值范围为：\[1,2999\]。

 **说明：** 只有物理专线的所有者可以指定该参数，同一条物理专线下的两个VBR的VLAN ID不能相同。

 |
|CircuitCode|String|是| 运营商为物理专线提供的电路编码。

 **说明：** 只有物理专线的所有者可以指定该参数。

 |
|LocalGatewayIp|String|否| VBR的阿里云侧互联IP。

 |
|PeerGatewayIps|String|否| VBR的客户侧互联IP。

 |
|PeeringSubnetMask|String|否| VBR的阿里云侧和客户侧互联IP的子网掩码。

 两个IP地址必须位于同一个子网中。

 |
|Name|String|否| VBR的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| VBR的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VbrId|String|VBR的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateVirtualBorderRouter
&PhysicalConnectionId=pc-2zeoaxkq3jotxxxxxxxx
&RegionId=cn-hangzhou
&VlanId=10
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateRouterInterfaceResponse>
        <RequestId>980960B0-2969-40BF-8542-EBB34FD358AB</RequestId>
        <VbrId>vbr-2zecmmvg5gvu8i4telkhw</VbrId>
    </CreateRouterInterfaceResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "980960B0-2969-40BF-8542-EBB34FD358AB"
        "VbrId": "vbr-2zecmmvg5gvu8i4telkhw"
    }
    ```


