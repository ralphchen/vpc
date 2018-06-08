# DescribeSslVpnClientCerts {#reference_i4w_xmt_ndb .reference}

查询已创建的SSL-VPN客户端证书。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeSslVpnClientCerts

 |
|RegionId|String|是| SSL-VPN客户端证书所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SslVpnServerId|String|否|SSL-VPN客户端证书的ID。|
|Name|String|否|SSL-VPN客户端证书的名称。|
|PageNumber|Integer|否|列表的页码，默认值为1。|
|PageSize|Integer|否|分页查询时每页的行数，最大值为50，默认值为10。|

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|SslVpnClientCertKeys|List|SSL-VPN客户端证书的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|RegionId|String|SSL-VPN客户端证书的地域。|
|SslVpnClientCertId|String|SSL-VPN客户端证书的ID。|
|Name|String|SSL-VPN客户端证书的名称。|
|CreationTime |String|创建时间。|
|EndTime|Integer|客户端证书的到期时间。|
|Status|String| 客户端证书的状态。

 -   expiring-soon：证书将在1周后过期。

-   normal：正常。

-   expired：已过期。


 |

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeSslVpnClientCerts
&RegionID=cn-beijing
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
      "RequestId": "5BE01CD7-5A50-472D-AC14-CA181C5C03BE",
      "SslVpnClientCertKeys": {
        "SslVpnClientCertKey": {
          "RegionId": "cn-beijing",
          "SslVpnClientCertId": "vsc-bp1n8wcf134yl0osrcg98",
          "Name": "test",
          "CreateTime": "1492747187000",
          "EndTime": "1494966335000",
          "Status": "normal"
        }
      }
    }
    ```


