# ModifyCustomerGatewayAttribute {#reference_i4w_xmt_ndb .reference}

修改用户网关的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyCustomerGatewayAttribute

 |
|RegionId|String|是| 用户网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|是| 用户网关的ID。

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
|Name|String|用户网关的名称。|
|Description|String|用户网关的描述信息。|
|IpAddress|String|用户网关的IP地址。|
|CreateTime|Long|用户网关的创建时间。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyCustomerGatewayAttribute
&RegionID=cn-beijing
&CustomerGatewayId=cgw-bp1pvpl9r9adju6l5nxck
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyCustomerGatewayAttributeResponse>
        <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
        <RequestId>E61293C8-AF07-4E87-A272-542680038F93</RequestId>
        <CreateTime>1492747187000</CreateTime>
        <IpAddress>139.196.32.167</IpAddress>
    </ModifyCustomerGatewayAttributeResponse>
    ```

-   JSON格式

    ```
    {
        "CustomerGatewayId":"cgw-bp1pvpl9r9adju6l5nxck",
        "RequestId":"8AA5CE21-2E6A-4530-BDF5-F055849476E6",
        "CreateTime":1492747187000,
        "IpAddress":"139.196.32.167"
    }
    ```


