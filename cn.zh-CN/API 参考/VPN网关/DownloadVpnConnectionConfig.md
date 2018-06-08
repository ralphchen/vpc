# DownloadVpnConnectionConfig {#reference_amt_w2p_rdb .reference}

获取IPsec连接的配置信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DownloadVpnConnectionConfig

 |
|RegionId|String|是| IPsec连接所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnConnectionId|Integer|是| IPsec连接的ID。

 |

## 返回参数 {#section_hlq_4gp_rdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VpnConnectionConfig|List|IPsec连接的配置信息。|

|名称|类型|描述|
|:-|:-|:-|
|CustomerGatewayId|String| 用户网关的ID。

 |
|VpnGatewayId|String| VPN网关的ID。

 |
|Local|Integer| IPsec VPN网关的标识。

 |
|LocalSubnet|String| VPC侧的网段。

 |
|RemoteSubnet|String| 本地IDC侧的网段。

 |
|Remote|String| 用户网关的标识。

 |
|IkeConfig |JSON string| 第一阶段协商的配置。

 |
|IpsecConfig |JSON string| 第二阶段协商的配置。

 |

## 示例 { .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DownloadVpnConnectionConfig
&RegionId=cn-hangzhou
&VpnConnectionId=vco-bp10lz7aejumd2vxoqgev
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DownloadVpnConnectionConfigResponse>
        <RequestId>6F4A035F-7060-45D7-B9BD-719372782AF6</RequestId>
        <VpnConnectionConfig>
            <RemoteSubnet>1.1.1.0/24,1.1.2.0/24</RemoteSubnet>
            <Local>139.196.32.167</Local>
            <IpsecConfig>
                <IpsecLifetime>86400</IpsecLifetime>
                <IpsecAuthAlg>sha1</IpsecAuthAlg>
                <IpsecPfs>group2</IpsecPfs>
                <IpsecEncAlg>aes</IpsecEncAlg>
            </IpsecConfig>
            <Remote>116.62.69.64</Remote>
            <LocalSubnet>2.2.2.0/24</LocalSubnet>
            <IkeConfig>
                <IkeEncAlg>aes</IkeEncAlg>
                <IkePfs>group2</IkePfs>
                <RemoteId>116.62.69.64</RemoteId>
                <IkeAuthAlg>sha1</IkeAuthAlg>
                <Psk>pgw6dy7d1i8in7x5</Psk>
                <IkeMode>main</IkeMode>
                <IkeLifetime>86400</IkeLifetime>
                <IkeVersion>ikev1</IkeVersion>
                <LocalId>139.196.32.167</LocalId>
            </IkeConfig>
        </VpnConnectionConfig>
    </DownloadVpnConnectionConfigResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "0C68048B-0F70-40DA-B8AE-1B79B5CF62E3",
      "VpnConnectionConfig": {
        "RemoteSubnet": "1.1.1.0/24,1.1.2.0/24",
        "Local": "139.196.32.167",
        "IpsecConfig": {
          "IpsecLifetime": 86400,
          "IpsecAuthAlg": "sha1",
          "IpsecPfs": "group2",
          "IpsecEncAlg": "aes"
        },
        "Remote": "116.62.69.64",
        "LocalSubnet": "2.2.2.0/24",
        "IkeConfig": {
          "IkeEncAlg": "aes",
          "IkePfs": "group2",
          "RemoteId": "116.62.69.64",
          "IkeAuthAlg": "sha1",
          "Psk": "pgw6dy7d1i8in7x5",
          "IkeMode": "main",
          "IkeLifetime": 86400,
          "IkeVersion": "ikev1",
          "LocalId": "139.196.32.167"
        }
      }
    }
    ```


