# ModifyNatGatewaySpec {#reference_i4w_xmt_ndb .reference}

修改一个NAT网关。

NAT网关当天的费用以在当天配置过的最高的规格为准。

NAT网关提供不同的规格。NAT网关的规格会影响SNAT功能的最大连接数和每秒新建连接数，但不会影响数据吞吐量。

NAT网关规格与SNAT性能的关系如下表所示。

|规格|最大连接数|每秒新建连接数|
|:-|:----|:------|
|小型|1万|1千|
|中型|5万|5千|
|大型|20万|1万|

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyNatGatewaySpec

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|是| NAT网关的ID。

 |
|Spec|String|否| NAT网关的规格。取值：

-   Small\(默认值\)：小型

-   Middle：中型

-   Large：大型


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
https://vpc.aliyuncs.com/?Action=ModifyNatGatewaySpec
&NatGatewayId=ngw-112za33e4
&&Spec=Large
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyNatGatewaySpecResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyNatGatewaySpecResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


