# DescribeCustomerGateways {#reference_i4w_xmt_ndb .reference}

查询已创建的用户网关。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeCustomerGateways

 |
|RegionId|String|是| 用户网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|CustomerGatewayId|String|否| 用户网关的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|CustomerGateways|List|用户网关的列表。|
|TotalCount|Integer|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|Integer|每页包含多少条目。|
|CustomerGateways|List|用户网关的详细信息。|

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
https://vpc.aliyuncs.com/?Action=DescribeCustomerGateways
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeCustomerGatewaysResponse>
        <PageNumber>1</PageNumber>
        <TotalCount>3</TotalCount>
        <PageSize>10</PageSize>
        <RequestId>5BE01CD7-5A50-472D-AC14-CA181C5C03BE</RequestId>
        <CustomerGateways>
            <CustomerGateway>
                <Name>test</Name>
                <CustomerGatewayId>cgw-bp1pvpl9r9adju6l5nxck</CustomerGatewayId>
                <CreateTime>1492747187000</CreateTime>
                <IpAddress>139.196.32.167</IpAddress>
            </CustomerGateway>
        </CustomerGateways>
    </DescribeCustomerGatewaysResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "TotalCount": 3,
      "PageSize": 10,
      "RequestId": "E82612A9-CB90-4D7E-B394-1DB7F6509B29",
      "CustomerGateways": {
        "CustomerGateway": [
          {
            "Name": "test",
            "CustomerGatewayId": "cgw-bp1pvpl9r9adju6l5nxck",
            "CreateTime": 1492747187000,
            "IpAddress": "139.196.32.167"
          }
        ]
      }
    }
    ```


