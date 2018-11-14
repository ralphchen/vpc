# DescribeRouteTableList {#reference_o4n_ymk_qdb .reference}

查询路由表。

## 请求参数 {#section_p4n_ymk_qdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeRouteTableList

 |
|RouterType|String|否| 路由表所属的路由器类型。取值：

 -   VRouter（默认值）：VPC路由器

-   VBR：边界路由器


 |
|VpcId|String|否| 路由表所属的VPC路由器的ID。指定该参数后，参数RouterType的值自动设置为VRouter。

 |
|RouteTableId|String|否| 路由表的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_fpn_ymk_qdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|RouteTableList|List|路由表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|RouterType|String| 路由表所属的路由器类型。取值：

 -   VRouter：VPC路由器

-   VBR：边界路由器


 |
|RouterId|String|路由表所属的路由器ID。|
|RouteTableId|String|路由表的ID。|
|RouteTableType|String| 路由表的类型。取值：

 -   Custom：自定义路由表

-   System：系统路由表


 |
|CreationTime|String|路由表的创建时间。按照ISO8601标准表示，使用UTC时间，格式为YYYY-MM-DDThh:mmZ。|
|RouteTableName|String|路由表的名称。|
|Description|String|路由表的描述。|

## 示例 {#section_fqn_ymk_qdb .section}

**请求示例**

```
https://vpc.aliyuncs.com/?Action=DescribeRouteTableList
&RegionId=cn-qingdao
&RouteTableName=myRouteTable
&VpcId=vpc-m5epxxxxxxxxxxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <
    DescribeRouteTableListsResponse>
    	<Code>200</Code>
    	<Message>successful</Message>
    	<PageNumber>1</PageNumber>
    	<PageSize>10</PageSize>
    	<RequestId>87261511-FEB9-4BEC-85BF-70XXXXXXXXX</RequestId>
    	<RouterTableList>
    		<RouterTableListType>
    			<CreationTime>2018-08-03T08:14:54Z</CreationTime>
    			<Description>ddd</Description>
    			<RouteTableId>vtb-m5evbtbptnx2bXXXXXXXXX</RouteTableId>
    			<RouteTableName>aaa1111</RouteTableName>
    			<RouteTableType>Custom</RouteTableType>
    			<RouterId>vrt-m5egeuhgj52xgXXXXXXXXX</RouterId>
    			<RouterType>VRouter</RouterType>
    			<VSwitchIds>
    				<VSwitchId>vsw-m5e3r57pxkgijXXXXXXXXX</VSwitchId>
    			</VSwitchIds>
    			<VpcId>vpc-m5epe3ag3qXXXXXXXXX</VpcId>
    		</RouterTableListType>
    	</RouterTableList>
    	<Success>true</Success>
    	<TotalCount>1</TotalCount> 
    </DescribeRouteTableList>
    ```

-   JSON格式

    ```
    {
      "Code": "200",
      "Message": "successful",
      "PageNumber": 1,
      "PageSize": 10,
      "RequestId": "87261511-FEB9-4BEC-85BF-70XXXXXXXXX",
      "RouterTableList": {
        "RouterTableListType": [
          {
            "CreationTime": "2018-08-03T08:14:54Z",
            "Description": "ddd",
            "RouteTableId": "vtb-m5evbtbptnx2bXXXXXXXXX",
            "RouteTableName": "aaa1111",
            "RouteTableType": "Custom",
            "RouterId": "vrt-m5egeuhgj52xgXXXXXXXXX",
            "RouterType": "VRouter",
            "VSwitchIds": {
              "VSwitchId": [
                "vsw-m5e3r57pxkgijXXXXXXXXX"
              ]
            },
            "VpcId": "vpc-m5epe3ag3qXXXXXXXXX"
          }
        ]
      },
      "Success": true,
      "TotalCount": 1
    }
    ```


