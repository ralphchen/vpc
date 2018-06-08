# DescribeVpnConnections {#reference_amt_w2p_rdb .reference}

查询已创建的IPsec连接。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVpnConnections

 |
|RegionId|String|是| IPsec连接所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnGatewayId|String|否| VPN网关的ID。

 |
|CustomerGatewayId|String|否|用户网关的ID。|
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_hlq_4gp_rdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|VpnConnections|List|IPsec连接列表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|VpnConnectionId|String|IPsec连接的ID。|
|CustomerGatewayId|String|用户网关的ID。|
|VpnGatewayId|String|VPN网关的ID。|
|Name|String|IPsec连接的名称。|
|LocalSubnet|String|VPC侧的网段。|
|RemoteSubnet|String|本地IDC侧的网段。|
|CreateTime|Long|IPsec连接的创建时间。|
|IkeConfig|JSON string|第一阶段协商的配置。|
|IpsecConfig|JSON string|第二阶段协商的配置。|
|Status |String| IPsec连接的状态。

 -   ike\_sa\_not\_established：表示第一阶段协商失败。

-   ike\_sa\_established：表示第一阶段协商成功。

-   ipsec\_sa\_not\_established：表示第二阶段协商失败。

-   ipsec\_sa\_established：第二阶段协商成功。


 |

## 示例 {#section_dg4_y5r_rdb .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVpnConnections
&RegionID=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DescribeVpnConnectionsResponse>
        <PageNumber>1</PageNumber>
        <VpnConnections>
            <VpnConnection>
                <Name>vpn连接测试</Name>
                <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
                <RemoteSubnet>2.2.2.0/24</RemoteSubnet>
                <IpsecConfig>
                    <IpsecLifetime>86400</IpsecLifetime>
                    <IpsecAuthAlg>sha1</IpsecAuthAlg>
                    <IpsecPfs>group2</IpsecPfs>
                    <IpsecEncAlg>aes</IpsecEncAlg>
                </IpsecConfig>
                <EffectImmediately>true</EffectImmediately>
                <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
                <CreateTime>1492753817000</CreateTime>
                <VpnConnectionId>vco-bp10lz7aejumd2vxoqgev</VpnConnectionId>
                <status>ipsec_sa_established
                    <status>
                        <LocalSubnet>1.1.1.0/24,1.1.2.0/24</LocalSubnet>
                        <IkeConfig>
                            <IkeEncAlg>aes</IkeEncAlg>
                            <RemoteId>139.196.32.167</RemoteId>
                            <IkePfs>group2</IkePfs>
                            <IkeAuthAlg>sha1</IkeAuthAlg>
                            <Psk>pgw6dy7d1i8in7x5</Psk>
                            <IkeMode>main</IkeMode>
                            <IkeLifetime>86400</IkeLifetime>
                            <IkeVersion>ikev1</IkeVersion>
                            <LocalId>116.62.69.64</LocalId>
                        </IkeConfig>
                    </VpnConnection>
            </VpnConnections>
            <TotalCount>1</TotalCount>
            <PageSize>10</PageSize>
        <RequestId>3F96DAF2-8A69-4E84-824A-E16E22308703</RequestId>
    </DescribeVpnConnectionsResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "VpnConnections": {
        "VpnConnection": [
          {
            "Name": "vpn连接测试",
            "CustomerGatewayId": "cgw-bp1pvpl9r9adju6l5nxck",
            "RemoteSubnet": "2.2.2.0/24",
            "IpsecConfig": {
              "IpsecLifetime": 86400,
              "IpsecAuthAlg": "sha1",
              "IpsecPfs": "group2",
              "IpsecEncAlg": "aes"
            },
            "EffectImmediately": true,
            "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu",
            "CreateTime": 1492753817000,
            "VpnConnectionId": "vco-bp10lz7aejumd2vxoqgev",
            "status": "ipsec_sa_established",
            "LocalSubnet": "1.1.1.0/24,1.1.2.0/24",
            "IkeConfig": {
              "IkeEncAlg": "aes",
              "RemoteId": "139.196.32.167",
              "IkePfs": "group2",
              "IkeAuthAlg": "sha1",
              "Psk": "pgw6dy7d1i8in7x5",
              "IkeMode": "main",
              "IkeLifetime": 86400,
              "IkeVersion": "ikev1",
              "LocalId": "116.62.69.64"
            }
          }
        ]
      },
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "54A4B3D0-DF4D-4C54-B8DC-5DC8DD49C939"
    }
    ```


