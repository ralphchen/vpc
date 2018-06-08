# DescribeSslVpnServers {#reference_i4w_xmt_ndb .reference}

查询已创建的SSL-VPN服务端。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeSslVpnServers

 |
|RegionId|String|是| SSL-VPN服务端所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpnGatewayId|String|否|VPN网关的ID。|
|SslVpnServerId|String|否|SSL-VPN服务端的ID。|
|Name|String|否|SSL-VPN服务端的名称。|
|PageNumber|Integer|否|列表的页码，默认值为1。|
|PageSize|Integer|否|分页查询时每页的行数，最大值为50，默认值为10。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|SslVpnServers|List|SSL-VPN服务端的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|RegionId|String|SSL-VPN服务端的地域。|
|SslVpnServerId|String|SSL-VPN服务端的ID。|
|VpnGatewayId|String|VPN网关实例ID。|
|Name|String|SSL-VPN服务端名称。|
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
https://vpc.aliyuncs.com/?Action=DescribeSslVpnServers
&RegionID=cn-beijing
&VpnGatewayId=vpn-bp1q8bgx4xnkm2ogj0fiu
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeSslVpnServersResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>1</TotalCount>
        <PageSize>10</PageSize>
        <SslVpnServers>
            <SslVpnServer>
                <RegionId>cn-hanghzou</RegionId>
                <SslVpnServerId>vss-bp18q7hzj6largv4vk2fe</SslVpnServerId>
                <VpnGatewayId>vpn-bp1q8bgx4xnkm2ogj0fiu</VpnGatewayId>
                <Name>test</Name>
                <CLientIpPool>10.10.10.20/24</CLientIpPool>
                <LocalSubnet>10.10.10.10/24</LocalSubnet>
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
    </DescribeSslVpnServersResponse>
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
          "CLientIpPool": "10.10.10.20/24",
          "LocalSubnet": "10.10.10.10/24",
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


