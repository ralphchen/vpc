# DescribeRouterInterfaces {#reference_i4w_x11mt_ndb .reference}

Query router interfaces in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeRouterInterfaces

 |
|RegionId|String|Yes| The region of the router interface.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|Filter.n.Key|String|No| Filter keys. Up to five filters are supported. The valid value for n is \[1, 5\].

 The relationship between the values of a filter is “or”.  A router interface is returned as long as one filter is met.

 The relationship between each filter is “and”. A router interface is returned only when all the filters are met.

 The following are available filter keys:

-   RouterInterfaceId: The ID of the router interface.

-   RouterId: The ID of the VRouter or VBR.

-   RouterType: The type of the router associated with the router interface.

-   RouterInterfaceOwnerId: The owner ID of the router interface.

-   OppositeInterfaceId: The ID of the peer router interface.

-   OppositeRouterType: The type of the router associated with the peer router interface.

-   OppositeRouterId: The ID of the peer router.

-   OppositeInterfaceOwnerId: The owner ID of the peer router interface.

-   Status: The status of the router interface.

-   Name: The name of the router interface.


 |
|Filter.n.Value.m|String|No| The corresponding value of the specified filter key. The valid value for m is \[1, 5\].

 |
|PageNumber|Integer|No|  The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of entries per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|RouterInterfaceSet|List|A list of router interfaces.|

|Name|Type|Description|
|----|----|-----------|
|RouterType|String|The type of the VRouter to which the route table belongs. Valid value:-   VRouter: VRouter

-   VBR: VBR


|
|RouterId|String|The ID of the VRouter to which the route table belongs. |
|VRouterId|String|The ID of the VRouter.|
|RouteTableId|String|The ID of the route table.|
|RouteTableType|String|The type of the route table.|
|CreationTime|String|The time when the route table is created.|
|RouteEntrys|List|A list of route entries.|

|Name|Type|Description|
|----|----|-----------|
|Type|String|The type of the route entry. Valid value:-   System: system route

-   Custom: custom route

-   BGP: BGP route


|
|RouteTableId|String|The ID of the route table to which the route entry belongs.|
|DestinationCidrBlock|String|The destination CIDR block of the route entry.|
|NextHopType|String|The type of the next hop.|
|InstanceId|String|The ID of the next-hop instance.|
|Status|String|The status of the route entry. Valid value:-   Pending: configuring

-   Available: available

-   Modifying: modifying


|
|RouterId|String|The ID of the VRouter to which the route entry belongs.|
|NextHops|List|The next hop list of ECMP routing.|

|Name|Type|Description|
|----|----|-----------|
|NextHopType|String| The type of next hop. Valid value:

 -   Instance: ECS instance \(default\)

HaVip: High availability virtual IP

RouterInterface: Router interface


 |
|NextHopId|String|The ID of the next-hop instance.|
|Enabled|Integer|Whether to enable the next hop:-   1: enable

-   1: not enable


|
|Weight|Integer|The routing weight of the next hop.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
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
    	<Type>System</Type>
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
    
        "PageNumber": 1, 
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "DC668356-BCB4-42FD-9BC3-FA2B2E04B634", 
        "RouteTables": {
            "RouteTable": [
                
                    "CreationTime": "2017-08-22T10:40:25Z", 
                    "RouteEntrys": {
                        "RouteEntry": [
                            
                                "NextHops": {
                                    "NextHop": [ ]
                                 
                                "Status": "Available", 
                                "Type": "Custom", 
                                "InstanceId": "ri-2zeo3xzyf38r4urzdpvfs", 
                                "NextHopType": "RouterInterface", 
                                "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                                "DestinationCidrBlock": "10.10.0.0/24"
                             
                            
                                "NextHops": {
                                    "NextHop": [ ]
                                 
                                "Status": "Available", 
                                "Type": "System", 
                                "InstanceId": "", 
                                "NextHopType": "service", 
                                "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                                "DestinationCidrBlock": "100.64.0.0/10"
                            
                        
                     
                    "RouteTableId": "vtb-2zevpmy9th8cxmwtarqg4", 
                    "RouteTableType": "System", 
                    "VRouterId": "vrt-2zefso23vmu6xi3jeiw0z"
                
            
        
    
    ```


