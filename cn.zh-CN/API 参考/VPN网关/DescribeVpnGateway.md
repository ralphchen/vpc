# DescribeVpnGateway {#reference_i4w_xmt_ndb .reference}

查询指定VPN网关的详细信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVpnGateways

 |
|RegionId|String|是| VPN网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnGatewayId|String|是| VPN网关所属VPC的ID。

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

``` {#DESCRIBEVPNpub}
https://vpc.aliyuncs.com/?Action=DescribeVpnGateway
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeVpnGatewayResponse>
        <Status>active</Status>
        <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
        <Spec>5M</Spec>
        <BusinessStatus>Normal</BusinessStatus>
        <RequestId>98C99F30-A3D2-42E1-AC75-0C882FBE92F7</RequestId>
        <CreateTime>1492753580000</CreateTime>
        <InternetIp>116.62.69.64</InternetIp>
        <EndTime>1495382400000</EndTime>
        <VSwitchId>vsw-bp1y9ovl1cu9ou4tvma0l</VSwitchId>
        <VpcId>vpc-bp1ub1yt9cvakoelj1y9c</VpcId>
    </DescribeVpnGatewayResponse>
    ```

-   JSON格式

    ```
    {
    "Status": "active",
    "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu",
    "BusinessStatus": "Normal",
    "Spec": "5M",
    "CreateTime": 1492753580000,
    "RequestId": "E98A9651-7098-40C7-8F85-C818D1EBBA85",
    "InternetIp": "116.62.69.64",
    "EndTime": 1495382400000,
    "VSwitchId": "vsw-bp1y9ovl1cu9ou4tvma0l",
    "VpcId": "vpc-bp1ub1yt9cvakoelj1y9c"
    }
    ```


