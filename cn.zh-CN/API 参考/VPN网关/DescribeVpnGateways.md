# DescribeVpnGateways {#reference_i4w_xmt_ndb .reference}

查询已创建的VPN网关。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVpnGateways

 |
|RegionId|String|是| VPN网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpcId|String|否| VPN网关所属VPC的ID。

 |
|Status|String|否|VPN网关的状态，取值：-   init
-   provisioning
-   active
-   updating
-   deleting

|
|BusinessStatus|String|否|VPN网关的付费状态，取值：Normal | FinancialLocked

|
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VpnGateways|List|VPN网关列表。|
|TotalCount|Integer|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|Integer|当前分页包含的条目数。|
|VpnGateways|List|VPN网关的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|VpnGatewayId|String|VPN网关的ID。|
|VpcId|String|VPN网关所属VPC的ID。|
|VSwitchId|String|VPN网关所属交换机的ID。|
|InternetIp|String|公网IP地址。|
|CreateTime|Long|VPN网关的创建时间。|
|EndTime|Long|VPN网关的到期时间。|
|Spec |String|VPN网关的规格。|
|Name |String|VPN网关的名称。|
|Description |String|VPN网关的描述信息。|
|Status |String|VPN网关的状态。|
|BusinessStatus |String|VPN网关的付费状态。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#DESCRIBEVPN}
https://vpc.aliyuncs.com/?Action=DescribeVpnGateways
&RegionID=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeVpnGatewaysResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <VpnGateways>
            <VpnGateway>
                <Status>active</Status>
                <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
                <BusinessStatus>Normal</BusinessStatus>
                <Spec>5M</Spec>
                <CreateTime>1492753580000</CreateTime>
                <InternetIp>116.62.69.64</InternetIp>
                <EndTime>1495382400000</EndTime>
                <VSwitchId>vsw-bp1y9ovl1cu9ou4tvma0l</VSwitchId>
                <VpcId>vpc-bp1ub1yt9cvakoelj1y9c</VpcId>
            </VpnGateway>
        </VpnGateways>
        <RequestId>DF11D6F6-E35A-41C3-9B20-6FC8A901FE65</RequestId>
    </DescribeVpnGatewaysResponse>
    ```

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "TotalCount": 1, 
        "VpnGateways": {
            "VpnGateway": [
                {
                    "Status": "active", 
                    "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu", 
                    "BusinessStatus": "Normal", 
                    "Spec": "5M", 
                    "CreateTime": 1492753580000, 
                    "InternetIp": "116.62.69.64", 
                    "EndTime": 1495382400000, 
                    "VSwitchId": "vsw-bp1y9ovl1cu9ou4tvma0l", 
                    "VpcId": "vpc-bp1ub1yt9cvakoelj1y9c"
                }
            ]
        }, 
        "PageSize": 10, 
        "RequestId": "B2CD1315-CA2B-47B1-9DA5-8F1D69C48E82"
    }
    ```


