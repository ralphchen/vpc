# CreateCustomerGateway {#reference_i4w_xmt_ndb .reference}

创建用户网关。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateCustomerGateway

 |
|RegionId|String|是| 用户网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|IpAddress|String|是| 用户网关的IP地址。

 |
|Name|String|否| 用户网关的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 用户网关的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|CustomerGatewayId|String|用户网关的ID。|
|IpAddress|String|用户网关的IP地址。|
|Name|String|用户网关的名称。|
|Description|String|用户网关的描述信息。|
|CreateTime|Long|用户网关的创建时间。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateCustomerGateway
&RegionID=cn-beijing
&IpAddress=100.1.1.2
&<公共请求参数>
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <CreateCustomerGatewayResponse>
        <CustomerGatewayId>cgw-bp1aw0a5nfff03xp1pcqc</CustomerGatewayId>
        <RequestId>185E81B1-3916-4667-B48F-C52409B33F2B</RequestId>
        <CreateTime>1493363486000</CreateTime>
        <IpAddress>100.1.1.2</IpAddress>
    </CreateCustomerGatewayResponse>
    
    ```

-   JSON格式

    ```
    {
        "CustomerGatewayId":"cgw-bp1jrawp82av6bws9h2ut",
        "CreateTime":1493363599000,
        "RequestId":"D32B3C26-6C6C-4988-93E9-D2A6444CE6AE",
        "IpAddress":"100.1.1.2"
    }
    ```


