# ModifySslVpnServer {#reference_i4w_xmt_ndb .reference}

修改SSL-VPN服务端的配置信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifySslVpnServer

 |
|RegionId|String|是| VPN网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnGatewayId|String|是| VPN网关的ID。

 |
|LocalSubnet|String|是| 是客户端通过SSL-VPN连接要访问的地址段。

 本端网段可以是VPC的网段、交换机的网段、通过专线和VPC互连的IDC的网段、云服务如RDS/OSS等的网段。

 |
|ClientIpPool|String|是| 是给客户端虚拟网卡分配访问地址的的地址段，不是指客户端已有的内网网段。当客户端通过SSL-VPN连接访问本端时，VPN网关会从指定的客户端网段中分配一个IP地址给客户端使用。

 该网段不能与**LocalSubnet**段冲突。

 |
|Proto|String|否| SSL-VPN服务端所使用的协议。

 取值：UDP（默认值） | TCP

 |
|Port|Integer|否| SSL-VPN服务端所使用的端口，默认值为1194。

 不能用使用以下端口\[22, 2222, 22222, 9000, 9001, 9002, 7505, 80, 443, 53, 68, 123, 4510, 4560, 500, 4500\]。

 |
|Cipher|String|否| SSL-VPN使用的加密算法。取值：

 AES-128-CBC（默认值） |AES-192-CBC | AES-256-CBC | none

 |
|Compress|Boolean|否| 指定是否对通信进行压缩。

 取值：true（默认值） |false

 |
|Name|String|否| SSL-VPN服务端的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|RegionId|String|SSL-VPN服务端的地域。|
|SslVpnServerId|String|SSL-VPN服务端的ID。|
|VpnGatewayId|String|VPN网关实例ID。|
|Name|String|SSL-VPN服务端的名称。|
|CLientIpPool|Long|客户端IP地址池。|
|LocalSubnet|Long|VPNGateway到期时间。|
|Proto |String|SSL-VPN服务端所使用的协议。|
|Port |Integer|SSL-VPN服务端所使用的端口。|
|Cipher |String|使用的加密算法。|
|Compress |Boolean|是否压缩。|
|CreationTime |String|创建时间。|
|Connections|Integer|当前连接数。|
|MaxConnections|Integer|最大连接数。|
|InternetIp|String|公网IP。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifySslVpnServer
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&LocalSubnet=10.20.20.0/24
&CLientIpPool=10.30.30.0/24
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifySslVpnServerResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <SslVpnServers>
            <SslVpnServer>
                <RegionId>cn-hanghzou</RegionId>
                <SslVpnServerId>vss-bp18q7hzj6largv4vk2fe</SslVpnServerId>
                <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
                <Name>test</Name>
                <CLientIpPool>10.30.30.0/24</CLientIpPool>
                <LocalSubnet>10.20.20.0/24</LocalSubnet>
                <Proto>UDP</Proto>
                <Port>1194</Port>
                <Cipher>AES-128-CBC</Cipher>
                <Compress>true</Compress>
                <CreateTime>1492753580000</CreateTime>
                <Connections>0</Connections>
                <MaxConnections>5</MaxConnections>
                <InternetIp>47.98.xx.xx</InternetIp>
            </SslVpnServer>
        </SslVpnServers>
        <RequestId>DF11D6F6-E35A-41C3-9B20-6FC8A901FE65</RequestId>
    </ModifySslVpnServerResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": "1",
      "TotalCount": "1",
      "PageSize": "10",
      "SslVpnServers": {
        "SslVpnServer": {
          "RegionId": "cn-hanghzou",
          "SslVpnServerId": "vss-bp18q7hzj6largv4vk2fe",
          "VpnGatewayId": "vpn-bp1q8bgx4xnkm2ogj0fiu",
          "Name": "test",
          "CLientIpPool": "10.30.30.0/24",
          "LocalSubnet": "10.20.20.0/24",
          "Proto": "UDP",
          "Port": "1194",
          "Cipher": "AES-128-CBC",
          "Compress": "true",
          "CreateTime": "1492753580000",
          "Connections": "0",
          "MaxConnections": "5",
          "InternetIp": "47.98.xx.xx"
        }
      },
      "RequestId": "DF11D6F6-E35A-41C3-9B20-6FC8A901FE65"
    }
    ```


