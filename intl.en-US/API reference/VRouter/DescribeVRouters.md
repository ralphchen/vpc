# DescribeVRouters {#reference_i4w_xmt_ndb .reference}

Query the list of VRouters in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVRouters

 |
|RegionId|String|No| The region where the VPC is located.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VRouterId|String|No| The ID of the VRouter.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|VRouters|List|A list of VRouters.|

|Name|Type|Description|
|:---|:---|:----------|
|VRouterId|String|The ID of the VRouter.|
|RegionId|String|The region of the VPC.|
|VpcId|String|The ID of the VPC to which the VRouter belongs.|
|RouteTableIds|String|The ID of the route table of the VRouter.|
|VRouterName|String|The name of the VRouter.|
|Description|String|The description of the VRouter.|
|CreationTime|String|The time when the VRouter was created.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVRouters
&RegionId=us-west-1
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <RouteTableId>vtb-bp145q7glnuzdvzu21pom</RouteTableId>
        <VRouterId>vrt-bp1lhl0taikrteen80oxx</VRouterId>
        <VpcId>vpc-bp15zckdt37pq72zvw3</VpcId>
    </CreateVpcResponse>
    ```

-   JSON format

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


