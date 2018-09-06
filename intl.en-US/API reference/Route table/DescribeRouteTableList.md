# DescribeRouteTableList {#reference_o4n_ymk_qdb .reference}

Query a route table.

## Request parameters {#section_p4n_ymk_qdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes | The action to perform.  Valid value: 

 DescribeRouteTableList

 |
|RouterType|String| No| The type of the router to which the route table belongs. Valid value:

 -   VRouter \(default\): VRouter

-   VBR: VBR


 |
|VpcId|String| No| The ID of the VRouter to which the route table belongs. The value of the RouterType parameter is set to VRouter automatically when this parameter is specified.

 |
|RouteTableId|String| No| The ID of the route table.

 |
|PageNumber|Integer|No | The number of pages to return. The default value is 1.

 |
|PageSize |Integer|No | The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_fpn_ymk_qdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of rows per page. |
|RouteTableList|List|The detailed information of the route table.|

|Name|Type|Description|
|:---|:---|:----------|
|RouterType|String| The type of the router to which the route table belongs. Valid value:

 -   VRouter: VRouter

-   VBR: VBR


 |
|RouterId|String|The ID of the VRouter to which the route table belongs.|
|RouteTableId|String|The ID of the route table.|
|RouteTableType|String| The type of route table. Valid value:

 -   Custom: A custom route table

-   System: A system route table


 |
|CreationTime|String|The time when the route table was created. The form is YYYY-MM-DDThh:mmZ.|
|RouteTableName|String|The name of the route table.|
|Description|String|The description of the route table.|

## Examples {#section_fqn_ymk_qdb .section}

**Request example**

```
https://vpc.aliyuncs.com/?Action=DescribeRouteTableList
&RegionId=cn-qingdao
&RouteTableName=myRouteTable
&VpcId=vpc-m5epxxxxxxxxxxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
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

-   JSON format

    ```
    {
      "code": "200",
      "message": "successful",
      "Pagenumber": 1,
      "Pagesize": 10,
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
            "routerType":"VRouter"
            "Vswitchids ":{
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


