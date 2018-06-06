# DescribeVRouters {#reference_i4w_xmt_ndb .reference}

查询指定地域的路由器列表。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVRouters

 |
|RegionId|String|否| VPC所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VRouterId|String|否| 路由器的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|VRouters|List|路由器的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|VRouterId|String|VPC路由器的ID。|
|RegionId|String|VPC所在的地域。|
|VpcId|String|路由器所属VPC的ID。|
|RouteTableIds|String|VPC路由器的路由表的ID。|
|VRouterName|String|VPC路由器的名称。|
|Description|String|VPC路由器的描述信息。|
|CreationTime|String|VPC路由器的创建时间。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVRouters
&RegionId=us-west-1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <RouteTableId>vtb-bp145q7glnuzdvzu21pom</RouteTableId>
        <VRouterId>vrt-bp1lhl0taikrteen80oxx</VRouterId>
        <VpcId>vpc-bp15zckdt37pq72zvw3</VpcId>
    </CreateVpcResponse>
    ```

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "TotalCount": 1, 
        "VRouters": {
            "VRouter": [
                {
                    "VRouterName": "", 
                    "RouteTableIds": {
                        "RouteTableId": [
                            "vtb-rj9ybe3y0u41mmjspmop0"
                        ]
                    }, 
                    "CreationTime": "2018-03-22T07:46:20Z", 
                    "Description": "", 
                    "RegionId": "us-west-1", 
                    "VRouterId": "vrt-rj98khsezfqpjrxmvl7cy", 
                    "VpcId": "vpc-rj905wotv6y030t1zz5vl"
                }
            ]
        }, 
        "PageSize": 10, 
        "RequestId": "CB2793A8-845F-444C-8E93-76F1BBDF9C78"
    }
    ```


