# DescribeVpnConnections {#reference_amt_w2p_rdb .reference}

Query created IPsec connections.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVpnConnections

 |
|RegionId|String|Yes| The region of the IPsec connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpnGatewayId|String|No| The ID of the VPN gateway.

 |
|CustomerGatewayId|String|No|The ID of the customer gateway.|
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_hlq_4gp_rdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|VpnConnections|List|A list of IPsec connections.|

|Name|Type|Description|
|:---|:---|:----------|
|VpnConnectionId|String|The ID of the IPsec connection.|
|CustomerGatewayId|String|The ID of the customer gateway.|
|VpnGatewayId|String|The ID of the VPN gateway.|
|Name|String|The name of the IPsec connection.|
|LocalSubnet|String|The CIDR block of the VPC.|
|RemoteSubnet|String|The CIDR block of the local data center.|
|CreateTime|Long|The time when the IPsec connection was created.|
|IkeConfig|JSON string|Configurations of phase-one negotiation.|
|IpsecConfig|JSON string|Configurations of phase-two negotiation.|
|Status |String| The status of IPsec connection.

 -   ike\_sa\_not\_established: The phase-one negotiation fails.

-   ike\_sa\_established: The phase-one negotiation succeeds.

-   ipsec\_sa\_not\_established: The phase-two negotiation fails.

-   ipsec\_sa\_established: The phase-two negotiation succeeds.


 |

## Examples {#section_dg4_y5r_rdb .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVpnConnections
&RegionID=cn-hangzhou
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
    <DescribeVpnConnectionsResponse>
        <PageNumber>1</PageNumber>
        <VpnConnections>
            <VpnConnection>
                <Name>vpn connection test</Name>
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

-   JSON format

    ```
    {
      "PageNumber": 1,
      "VpnConnections": {
        "VpnConnection": [
          {
            "Name": "vpn connection test",
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


