# CreateBandwidthPackage {#reference_i4w_xmt_ndb .reference}

创建NAT带宽包。

NAT网关上的公网IP和带宽，被封装为NAT带宽包。一个NAT网关最多可创建四个NAT带宽包。

一个NAT带宽包包含：

-   一份共享带宽

-   一组公网IP


**说明：** 本接口仅支持在2017年11月3日之前账号下存在NAT带宽包的用户调用。2017年11月3日之前账号下不存在NAT带宽包的用户，请通过绑定EIP的方式申请公网IP。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateBandwidthPackage

 |
|RegionId|String|是| NAT带宽包所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|是| NAT网关的ID。

 |
|IpCount|Integer|是| NAT带宽包中的公网IP数量。取值范围：\[1,50\]

 |
|Bandwidth|Integer|是| NAT带宽包的带宽。取值范围：\[5,1000\]

 |
|Zone|String|否| NAT带宽包所在的可用区。

 不指定该参数时，系统将随机分配一个可用区。

 **说明：** NAT带宽包上的IP与后端ECS不处于同一个可用区，并不影响其连通性；但是位于相同可用区时，可减小延迟。

 |
|Name|String|否| NAT带宽包的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| NAT带宽包的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|BandwidthPackageId|String|NAT带宽包的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateBandwidthPackage
&NatGatewayId=ngw-7mwb327j1
&RegionId=cn-shanghai
&Bandwidth=5
&ZoneId=cn-shanghai-a
&IpCount=1
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateBandwidthPackageResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
            <BandwidthPackageId>bwp-s6lmotmkk</BandwidthPackageId>
    </CreateBandwidthPackageResponse>
    ```

-   JSON格式

    ```
    {
      "BandwidthPackageId": "bwp-s6lmotmkk", 
      "RequestId": "54ED4074-3F89-4F11-B166-837DD3E20FE3"
    }
    ```


