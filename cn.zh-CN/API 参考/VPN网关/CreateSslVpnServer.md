# CreateSslVpnServer {#reference_i4w_xmt_ndb .reference}

创建SSL-VPN服务端。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateSslVpnServer

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
|Name|String|否| SSL-VPN服务端的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|SslVpnServerId|String|SSL-VPN服务端的ID。|
|Name|String|SSL-VPN服务端的名称。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateSslVpnServer
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&LocalSubnet=10.10.10.0/24
&ClientIpPool=10.20.20.0/24
&Name=test
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateSslVpnServerResponse>
        <RequestId>E98A9651-7098-40C7-8F85-C818D1EBBA85</RequestId>
        <SslVpnServerId>vss-bp18q7hzj6largv4vk2fe</SslVpnServerId>
        <Name>test</Name>
    </CreateSslVpnServerResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "E98A9651-7098-40C7-8F85-C818D1EBBA85",
      "SslVpnServerId": "vss-bp18q7hzj6largv4vk2fe",
      "Name": "test"
    }
    ```


