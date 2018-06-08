# DescribeCustomerGateway {#reference_i4w_xmt_ndb .reference}

查询已创建的用户网关的详细信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCustomerGateway

 |
|RegionId|String|是| 用户网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|CustomerGatewayId|String|是| 用户网关的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|CustomerGatewayId|String|用户网关的ID。|
|Name|String|用户网关的名称。|
|Description|String|用户网关的描述信息。|
|IpAddress|String|用户网关的IP地址。|
|CreateTime|Long|用户网关的创建时间。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeCustomerGateway
&RegionId=cn-beijing
&CustomerGatewayId=cgw-bp1pvpl9r9adju6l5nxck
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCustomerGatewayResponse>
        <Name>test</Name>
        <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
        <CreateTime>1492747187000</CreateTime>
        <RequestId>99506ECB-218F-45A5-AE8E-79518451F615</RequestId>
        <IpAddress>139.196.32.167</IpAddress>
    </DescribeCustomerGatewayResponse>
    ```

-   JSON格式

    ```
    {
      "CustomerGatewayId": "cgw-bp1pvpl9r9adju6l5nxck",
      "Name": "test",
      "RequestId": "A0457BC9-6C0F-4437-AB9D-FB2EABC1D6A2",
      "CreateTime": 1492747187000,
      "IpAddress": "139.196.32.167"
    }
    ```


