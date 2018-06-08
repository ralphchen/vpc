# DescribeVpnConnection {#reference_amt_w2p_rdb .reference}

查询已创建的IPsec连接的详细信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVpnConnection

 |
|RegionId|String|是| IPsec连接所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnConnectionId|String|是| IPsec连接的ID。

 |

## 返回参数 {#section_hlq_4gp_rdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
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
https://vpc.aliyuncs.com/?Action=DescribeVpnConnection
&RegionID=cn-beijing
&VpnConnectionId=vco-bp10lz7aejumd2vxoqgev
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DescribeVpnConnectionResponse>
        <PageNumber>1</PageNumber>
        <VpnConnections>
            <VpnConnection>
                <Name>c2</Name>
                <CustomerGatewayId>cgw-bp1wl8dtz3auwlavwhgcw</CustomerGatewayId>
                <Status>ike_sa_not_established</Status>
                <RemoteSubnet>192.168.0.0/16</RemoteSubnet>
                <IpsecConfig>
                    <IpsecLifetime>86400</IpsecLifetime>
                    <IpsecAuthAlg>md5</IpsecAuthAlg>
                    <IpsecPfs>group2</IpsecPfs>
                    <IpsecEncAlg>aes</IpsecEncAlg>
                </IpsecConfig>
                <EffectImmediately>false</EffectImmediately>
                <VpnGatewayId>vpn-bp1yfrjxn4d5t63tbqq70</VpnGatewayId>
                <CreateTime>1519391420000</CreateTime>
                <VpnConnectionId>vco-bp1w3m1p23iftycvseuc2</VpnConnectionId>
                <LocalSubnet>172.16.0.0/12</LocalSubnet>
                <IkeConfig>
                    <IkeEncAlg>aes</IkeEncAlg>
                    <RemoteId>47.97.176.95</RemoteId>
                    <IkePfs>group2</IkePfs>
                    <IkeAuthAlg>sha1</IkeAuthAlg>
                    <Psk>1234567</Psk>
                    <IkeMode>aggressive</IkeMode>
                    <IkeLifetime>86400</IkeLifetime>
                    <IkeVersion>ikev1</IkeVersion>
                    <LocalId>116.62.119.2</LocalId>
                </IkeConfig>
            </VpnConnection>
        </VpnConnections>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>7D598A10-26EF-44F2-9F47-E417842F3CEA</RequestId>
    </DescribeVpnConnectionResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "VpnConnections": {
        "VpnConnection": [
          {
            "Name": "c2",
            "CustomerGatewayId": "cgw-bp1wl8dtz3auwlavwhgcw",
            "Status": "ike_sa_not_established",
            "RemoteSubnet": "192.168.0.0/16",
            "IpsecConfig": {
              "IpsecLifetime": 86400,
              "IpsecAuthAlg": "md5",
              "IpsecPfs": "group2",
              "IpsecEncAlg": "aes"
            },
            "EffectImmediately": false,
            "VpnGatewayId": "vpn-bp1yfrjxn4d5t63tbqq70",
            "CreateTime": 1519391420000,
            "VpnConnectionId": "vco-bp1w3m1p23iftycvseuc2",
            "LocalSubnet": "172.16.0.0/12",
            "IkeConfig": {
              "IkeEncAlg": "aes",
              "RemoteId": "47.97.176.95",
              "IkePfs": "group2",
              "IkeAuthAlg": "sha1",
              "Psk": "1234567",
              "IkeMode": "aggressive",
              "IkeLifetime": 86400,
              "IkeVersion": "ikev1",
              "LocalId": "116.62.119.2"
            }
          }
        ]
      },
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "7D598A10-26EF-44F2-9F47-E417842F3CEA"
    }
    ```


