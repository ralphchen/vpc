# ModifyVpnGatewayAttribute {#reference_i4w_xmt_ndb .reference}

修改VPN网关的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyVpnGatewayAttribute

 |
|RegionId|String|是|VPN网关所在的地域。您可以通过调用 DescribeRegions接口获取地域ID。

|
|VpnGatewayId|String|是| VPN网关的ID。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|Name|String|否| VPN网关的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| VPN网关的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VpnGatewayId|String|VPN网关的ID。|
|VpcId|String|VPN网关所属VPC的ID。|
|VSwitchId|String|VPN网关所属交换机的ID。|
|InternetIp|String|公网IP地址。|
|CreateTime|Long|VPN网关的创建时间。|
|EndTime|Long|VPN网关的到期时间。|
|Spec|String|VPN网关的规格。|
|Name|String|VPN网关的名称。|
|Description|String|VPN网关的描述信息。|
|Status|String|VPN网关的状态。|
|BusinessStatus|String|VPN网关的付费状态。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#ModifyVpnGatewayAttribute1}
https://vpc.aliyuncs.com/?Action=ModifyVpnGatewayAttribute
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyVpnGatewayAttributeResponse>
        <Name>aaa</Name>
        <Status>active</Status>
        <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
        <BusinessStatus>Normal</BusinessStatus>
        <Spec>5M</Spec>
        <CreateTime>1492753580000</CreateTime>
        <IntranetIp>172.16.104.158</IntranetIp>
        <RequestId>54B48E3D-DF70-471B-AA93-08E683A1B457</RequestId>
        <InternetIp>116.62.69.64</InternetIp>
        <EndTime>1495382400000</EndTime>
        <VSwitchId>vsw-bp1y9ovl1cu9ou4tvma0l</VSwitchId>
        <VpcId>vpc-bp1ub1yt9cvakoelj1y9c</VpcId>
    </ModifyVpnGatewayAttributeResponse>
    ```

-   JSON格式

    ```
    {
        "Name": "aaa", 
        "Status": "active", 
        "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu", 
        "BusinessStatus": "Normal", 
        "Spec": "5M", 
        "CreateTime": 1492753580000, 
        "IntranetIp": "172.16.104.158", 
        "RequestId": "BA56EAF8-E3A9-4BE6-8511-8F03512153E2", 
        "InternetIp": "116.62.69.64", 
        "EndTime": 1495382400000, 
        "VSwitchId": "vsw-bp1y9ovl1cu9ou4tvma0l", 
        "VpcId": "vpc-bp1ub1yt9cvakoelj1y9c"
    }
    ```


