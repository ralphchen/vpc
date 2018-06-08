# CreateVpc {#reference_i4w_xmt_ndb .reference}

创建一个专有网络（VPC）。

调用该接口创建VPC时，请注意：

-   VPC只能指定一个网段，网段的范围包括10.0.0.0/8、172.16.0.0/12和192.168.0.0/16以及它们的子网，网段的掩码为8-24位，默认为172.16.0.0/12。

-   VPC创建后无法修改网段。

-   每个VPC包含的云产品实例数量不超过15000个。

-   创建VPC后，会自动创建一个虚拟路由器和一个路由表。

-   每个VPC支持三个用户侧网段。如果多个用户侧网段之间存在互相包含，掩码较短的网段实际生效。例如10.0.0.0/8和10.1.0.0/16中，10.0.0.0/8实际生效。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateVpc

 |
|RegionId|String|是| VPC所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|CidrBlock|String|否| VPC的网段。您可以使用以下网段或其子集：

 -   10.0.0.0/8
-   172.16.0.0/12（默认值）
-   192.168.0.0/16

 |
|VpcName|String|否| VPC的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| VPC的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|UserCidr|String|否| 用户侧网络的网段，如需定义多个网段请使用半角逗号隔开，最多支持3个网段。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VpcId|String|VPC的ID。|
|VRouterId|String|路由器的ID。|
|RouteTableId|String|路由表的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateVpc
&RegionId=cn-hangzhou
&CidrBlock=10.10.0.0/24
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <RouteTableId>vtb-bp145q7glnuzdvzu21pom</RouteTableId>
        <VRouterId>vrt-bp1lhl0taikrteen80oxx</VRouterId>
        <VpcId>vpc-bp15zckdt37pq72zvw3</VpcId>
    </CreateVpcResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "RouteTableId": "vtb-bp145q7glnuzdvzu21pom", 
        "VRouterId": "vrt-bp1lhl0taikrteen80oxx", 
        "VpcId": "vpc-bp15zckdt37pq72zvw30k"
    }
    ```


