# CreateNatGateway {#reference_i4w_xmt_ndb .reference}

创建一个NAT网关。

在调用本接口创建NAT网关时，请注意：

-   目前不支持NAT网关与自建SNAT网关（使用一台ECS作为SNAT网关）在VPC中并存。

-   NAT网关创建后，系统会在VPC的路由表中自动添加一条目标网段为0.0.0.0/0，下一跳为NAT网关的路由条目，用于将流量路由到NAT网关。

-   如果在创建NAT网关前，VPC的路由表中已经存在一条目标网段为0.0.0.0/0的路由条目，请先删除该路由条目。否则，无法创建NAT网关。


## NAT网关的规格 {#section_bbb_wqb_pdb .section}

NAT网关提供不同的规格。NAT网关的规格会影响SNAT功能的最大连接数和每秒新建连接数，但不会影响数据吞吐量。

NAT网关规格与SNAT性能的关系如下表所示。

|规格|最大连接数|每秒新建连接数|
|:-|:----|:------|
|小型|1万|1千|
|中型|5万|5千|
|大型|20万|1万|
|超大型|100万|3万|

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateNatGateway

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpcId|String|是| VPC的ID。

 |
|Spec|String|否| NAT网关的规格。取值：

-   Small\(默认值\)：小型

-   Middle：中型

-   Large：大型

-   XLarge.1：超大型


 |
|BandwidthPackage.n.Bandwidth|String|否| 第n个共享带宽包的带宽值，取值范围：\[5,5000\]

 **说明：** 本参数仅支持在2018年1月26日之前账号下存在NAT带宽包的用户指定。2018年1月26日之前账号下不存在NAT带宽包的用户，请绑定EIP。

 |
|BandwidthPackage.n.Zone|String|否| 第n个共享带宽包的可用区。不指定该参数时，系统将随机分配一个可用区。

 NAT带宽包的IP与后端ECS不处于同一个可用区，并不影响其连通性；但是位于相同可用区时，可减小延迟。

 **说明：** 本参数仅支持在2018年1月26日之前账号下存在NAT带宽包的用户指定。2018年1月26日之前账号下不存在NAT带宽包的用户，请绑定EIP。

 |
|Name|String|否| NAT网关的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| NAT网关的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|NatGatewayId|String|NAT网关的ID。|
|ForwardTableIds|String|NAT网关的转发条目列表。|
|BandwidthPackageIds|String|NAT网关的共享带宽包。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateNatGateway
&VpcId=vpc-11af8lp67
&Name=MyNatGW
&BandwidthPackage.1.IpCount=5
&RegionId=cn-shanghai
&BandwidthPackage.1.Bandwidth=150
&BandwidthPackage.1.Zone=cn-shanghai-a
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateNatGatewayResponse>
    	<BandwidthPackageIds>
    		<BandwidthPackageId>bwp-11odxu2k7</BandwidthPackageId>
    	</BandwidthPackageIds>
    	<ForwardTableIds>
    		<ForwardTableId>ftb-11tc6xgmv</ForwardTableId>
    	</ForwardTableIds>
    	<NatGatewayId>ngw-112za33e4</NatGatewayId>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </CreateNatGatewayResponse>
    ```

-   JSON格式

    ```
    {
      "BandwidthPackageIds": {
        "BandwidthPackageId": [
          "bwp-11odxu2k7"
        ]
      },
      "ForwardTableIds": {
        "ForwardTableId": [
          "ftb-11tc6xgmv"
        ]
      },
      "NatGatewayId": "ngw-112za33e4",
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


