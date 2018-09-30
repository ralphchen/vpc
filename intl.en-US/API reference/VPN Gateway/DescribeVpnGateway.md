# DescribeVpnGateway {#reference_i4w_xmt_ndb .reference}

Query the detailed information of a VPN gateway.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVpnGateways

 |
|RegionId|String|Yes| The region of the VPN gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpnGatewayId|String|Yes| The ID of the VPC to which the VPN gateway belongs.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|VpnGatewayId|String|The ID of the VPN gateway.|
|VpcId|String|The ID of the VPC to which the VPN gateway belongs.|
|VSwitchId|String|The ID of the VSwitch to which the VPN gateway belongs.|
|InternetIp|String|The public IP address.|
|CreateTime|Long|The time when the VPN gateway was created.|
|EndTime|Long|The time when the VPN gateway expires.|
|Spec|String|The specification of the VPN gateway.|
|Name|String|The name of the VPN gateway.|
|Description|String|The description of the VPN gateway.|
|Status|String|The status of the VPN gateway. |
|BusinessStatus|String|The business status of the VPN gateway.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#DESCRIBEVPNpub}
https://vpc.aliyuncs.com/?Action=DescribeVpnGateway
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
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

-   JSON format

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


