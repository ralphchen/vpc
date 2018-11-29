# DescribeRouteTables {#reference_o4n_ymk_qdb .reference}

Query route entries in a route table.

## Request parameters {#section_p4n_ymk_qdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeRouteTables

 |
|RouterType|String|No| The type of the router to which the route table belongs. Valid value:

 -   VRouter: VRouter

-   VBR: VBR


 |
|RouterId|String|No| The ID of the VRouter or VBR to which the route table belongs.

 |
|VRouterId|String|No| The ID of the VRouter to which the route table belongs. The value of the RouterType parameter is set to VRouter automatically when this parameter is specified.

 |
|RouteTableId|String|No| The ID of the route table.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_fpn_ymk_qdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|RouteTables|List|A list of route tables.|

|Name|Type|Description|
|:---|:---|:----------|
|RouterType|String|The type of the router to which the route table belongs. Valid value:-   VRouter: VRouter

-   VBR: VBR


|
|RouterId|String|The ID of the VRouter or VBR to which the route table belongs.|
|VRouterId|String|The ID of the VRouter.|
|RouteTableId|String|The ID of the route table.|
|RouteTableType|String|The type of the route table.|
|CreationTime|String|The time when the route table was created.|
|RouteEntrys|List|A list of route entries.|

|Name|Type|Description|
|:---|:---|:----------|
|Type|String|The type of the route entry. Valid values:-   System: System route entry

-   Custom: Custom route entry

-   BGP : BGP route entry


|
|RouteTableId|String|The ID of the router table to which the route entry belongs.|
|DestinationCidrBlock|String|The destination CIDR block of the route entry.|
|NextHopType|String|The type of the next hop.|
|InstanceId|String|The instance ID of the next hop.|
|Status|String|The status of the route entry. Valid value:-   Pending: Configuring

-   Available: Available

-   Modifying: Modifying


|
|RouterId|String|The ID of the VRouter or VBR to which the route table belongs.|
|NextHops|List|The list of next hops of ECMP route entries.|

|Name|Type|Description|
|:---|:---|:----------|
|NextHopType|String| The type of the next hop. Valid value:

 -   Instance: ECS instance \(default\)

HaVip: HaVip

RouterInterface: Router interface


 |
|NextHopId|String|The ID of the next hop instance.|
|Enabled|Integer|Whether the next hop is available:-   0: Unavailable

-   1: Available


|
|Weight|Integer|The routing weight of the next hop.|

## Examples {#section_fqn_ymk_qdb .section}

**Request example**

```
https://vpc.aliyuncs.com/?Action=DescribeRouteTables
&RouteTableId=vtb-2zevpmy9th8cxmwtarqg4
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeRouteTablesResponse>
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>DC668356-BCB4-42FD-9BC3-FA2B2E04B634</RequestId>
    	<RouteTables>
    		<RouteTable>
    			<CreationTime>2017-08-22T10:40:25Z</CreationTime>
    			<RouteEntrys>
    				<RouteEntry>
    					<NextHops></NextHops>
    					<Status>Available</Status>
    					<Type>Custom</Type>
    					<InstanceId>ri-2zeo3xzyf38r4urzdpvfs</InstanceId>
    					<NextHopType>RouterInterface</NextHopType>
    					<RouteTableId>vtb-2zevpmy9th8cxmwtarqg4</RouteTableId>
    					<DestinationCidrBlock>10.10.0.0/24</DestinationCidrBlock>
    				</RouteEntry>
    				<RouteEntry>
    					<NextHops></NextHops>
    					<Status>Available</Status>
    					<Type>Image</Type>
    					<InstanceId></InstanceId>
    					<NextHopType>service</NextHopType>
    					<RouteTableId>vtb-2zevpmy9th8cxmwtarqg4</RouteTableId>
    					<DestinationCidrBlock>100.64.0.0/10</DestinationCidrBlock>
    				</RouteEntry>
    			</RouteEntrys>
    			<RouteTableId>vtb-2zevpmy9th8cxmwtarqg4</RouteTableId>
    			<RouteTableType>System</RouteTableType>
    			<VRouterId>vrt-2zefso23vmu6xi3jeiw0z</VRouterId>
    		</RouteTable>
    	</RouteTables>
    </DescribeRouteTablesResponse>
    ```

-   JSON format

    ```
    {
        "PageNumber": 1, 
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "DC668356-BCB4-42FD-9BC3-FA2B2E04B634", 
        "RouteTables": {
            "RouteTable": [
                {
                    "CreationTime": "2017-08-22T10:40:25Z", 
                    "RouteEntrys": {
                        "RouteEntry": [
                            {
                                "NextHops": {
                                    "NextHop": [ ]
                                }, 
                                "Status": "Available", 
                                "Type": "Custom", 
                                "InstanceId": "ri-2zeo3xzyf38r4urzdpvfs", 
                                "NextHopType": "RouterInterface", 
                                "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                                "DestinationCidrBlock": "10.10.0.0/24"
                            }, 
                            {
                                "NextHops": {
                                    "NextHop": [ ]
                                }, 
                                "Status": "Available", 
                                "Type": "System", 
                                "Instanceid ":"", 
                                "NextHopType": "service", 
                                "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                                "DestinationCidrBlock": "100.64.0.0/10"
                            }
                        ]
                    }, 
                    "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                    "RouteTableType": "System", 
                    "VRouterId": "vrt-2zefso23vmu6xi3jeiw0z"
                }
            ]
        }
    }
    ```


