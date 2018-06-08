# DeleteSslVpnClientCert {#reference_i4w_xmt_ndb .reference}

删除SSL-VPN客户端证书。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteSslVpnClientCert

 |
|RegionId|String|是| SSL-VPN客户端证书所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SslVpnClientCertId|String|是| SSL-VPN客户端证书的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateSslVpnClientCert
&RegionID=cn-beijing
&SslVpnClientCertId=vsc-bp1n8wcf134yl0osrcg98
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteSslVpnClientCertResponse>
        <RequestId>606998F0-B94D-48FE-8316-ACA81BB230DA</RequestId>
    </DeleteSslVpnClientCertResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId":"606998F0-B94D-48FE-8316-ACA81BB230DA"
    }
    ```


