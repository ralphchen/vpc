# ModifyVpnConnectionAttribute {#reference_i4w_xmt_ndb .reference}

修改IPsec连接的配置信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyVpnConnectionAttribute

 |
|RegionId|String|是| IPsec连接所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnConnectionId|String|是|IPsec连接的ID。|
|Name|String|否| IPsec连接的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|LocalSubnet|String|是|需要和本地IDC互连的VPC侧的网段，用于第二阶段协商。多个网段之间用逗号分隔，例如：192.168.1.0/24,192.168.2.0/24。|
|RemoteSubnet|String|是|本地IDC的网段，用于第二阶段协商。多个网段之间用逗号分隔，例如：192.168.3.0/24,192.168.4.0/24。|
|EffectImmediately|Boolean|否| 是否删除当前已协商成功的IPsec隧道并重新发起协商。取值：

-   true：配置完成后立即进行协商。

-   false （默认值）：当有流量进入时进行协商。


 |
|IkeConfig|JSON String|否| 第一阶段协商的配置信息：

-   IkeConfig.Psk：用于IPsec VPN网关与用户网关之间的身份认证。默认情况下会随机生成，也可以手动指定密钥。长度限制为100个字符。

-   IkeConfig.IkeVersion：IKE协议的版本。取值：ikev1 | ikev2，默认值：ikev1。

-   IkeConfig. IkeMode：IKE V1版本的协商模式。取值：main（主模式） | aggressive（野蛮模式），默认值：main。

-   IkeConfig. IkeEncAlg：第一阶段协商的加密算法，取值：aes | aes192 | aes256 | des | 3des，默认值：aes。

-   IkeConfig.IkeAuthAlg：第一阶段协商的认证算法，取值：md5 | sha1，默认值：sha。

-   IkeConfig.IkePfs：第一阶段协商使用的Diffie-Hellman密钥交换算法，取值：group1 | group2 | group5 | group14 | group24，默认值：group2。

-   IkeConfig.IkeLifetime：第一阶段协商出的SA的生存周期。取值范围为 \[0, 86400\]，单位为秒，默认值：86400。

-   IkeConfig.LocalIdIPsec：VPN网关的标识，长度限制为100个字符，默认值为VPN网关的公网IP地址。

-   IkeConfig.RemoteId：用户网关的标识，长度限制为100个字符，默认值为用户网关的公网IP地址。


 |
|IpsecConfig|JSON String|否| 第二阶段协商的配置信息：

-   IpsecConfig.IpsecEncAlg：第二阶段协商的加密算法，取值：aes | aes192 | aes256 | des | 3des，默认值：aes。

-   IpsecConfig. IpsecAuthAlg：第二阶段协商的认证算法，取值：md5 | sha1，默认值：sha1。

-   IpsecConfig. IpsecPfs：转发所有协议的报文。第一阶段协商使用的Diffie-Hellman密钥交换算法，取值：group1 | group2 | group5 | group14 | group24，默认值：group2。

-   IpsecConfig. IpsecLifetime：第二阶段协商出的SA的生存周期。取值范围为 \[0, 86400\]，单位为秒，默认值：86400。


 |

## 返回参数 {#section_ugs_f1g_cz .section}

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

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyVpnConnectionAttribute
&RegionID=cn-beijing
&VpnConnectionId=vco-bp10lz7aejumd2vxoqgev
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyVpnConnectionAttributeResponse>
        <Name>vpn连接测试</Name>
        <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
        <RemoteSubnet>2.2.2.0/24</RemoteSubnet>
        <IpsecConfig>
            <IpsecLifetime>86400</IpsecLifetime>
            <IpsecAuthAlg>sha1</IpsecAuthAlg>
            <IpsecPfs>group2</IpsecPfs>
            <IpsecEncAlg>aes</IpsecEncAlg>
        </IpsecConfig>
        <EffectImmediately>false</EffectImmediately>
        <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
        <CreateTime>1492753817000</CreateTime>
        <VpnConnectionId>vco-bp10lz7aejumd2vxoqgev</VpnConnectionId>
        <RequestId>57070A3D-38F2-40A6-A1C9-DB14542EF54D</RequestId>
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
    </ModifyVpnConnectionAttributeResponse>
    ```

-   JSON格式

    ```
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
      "EffectImmediately": false,
      "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu",
      "CreateTime": 1492753817000,
      "VpnConnectionId": "vco-bp10lz7aejumd2vxoqgev",
      "RequestId": "7DB79D0C-5F27-4AB5-995B-79BE55102F90",
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
    ```


