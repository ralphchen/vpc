# ModifySslVpnClientCert {#reference_i4w_xmt_ndb .reference}

修改SSL-VPN客户端证书的名称。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifySslVpnClientCert

 |
|RegionId|String|是| SSL-VPN客户端证书所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SslVpnClientCertId|String|是| SSL-VPN客户端证书的ID。

 |
|Name|String|否| SSL-VPN客户端证书的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|SslVpnServerId|String|客户端证书的ID。|
|Name|String|客户端证书的名称。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifySslVpnClientCert
&RegionID=cn-beijing
&SslVpnClientCertId=vsc-bp1n8wcf134yl0osrcg98
&Name=test
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifySslVpnClientCertResponse>
        <SslVpnClientCertId>vsc-bp1n8wcf134yl0osrcg98</SslVpnClientCertId>
        <Name>test</Name>
        <RequestId>606998F0-B94D-48FE-8316-ACA81BB230DA</RequestId>
    </ModifySslVpnClientCertResponse>
    ```

-   JSON格式

    ```
    {
      "SslVpnClientCertId": "vsc-bp1n8wcf134yl0osrcg98",
      "Name": "test",
      "RequestId": "606998F0-B94D-48FE-8316-ACA81BB230DA"
    }
    ```


