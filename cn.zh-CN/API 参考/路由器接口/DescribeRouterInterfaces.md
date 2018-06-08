# DescribeRouterInterfaces {#reference_i4w_xmt_ndb .reference}

查询指定地域内的路由器接口。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeRouterInterfaces

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Filter.n.Key|String|否| 过滤条件，最多可提供5个过滤条件。n的取值范围为\[1,5\]。

 每个过滤条件（filter key）可以提供多个值，多个值之间是“or”关系，即只要与其中一个值符合则视为符合参数的过滤条件。

 各个过滤条件（filter key）之间为“and”逻辑关系，即符合所有参数的过滤条件，才会被查询出来。

 支持的过滤条件如下：

-   RouterInterfaceId：路由器接口ID。

-   RouterId：路由器（VRouter或者VBR）的ID。

-   RouterType：路由器接口关联的路由器类型，VRouter或VBR。

-   RouterInterfaceOwnerId：路由器接口的账号ID。

-   OppositeInterfaceId：对端路由器接口ID。

-   OppositeRouterType：对端路由器接口关联的路由器类型，VRouter或VBR。

-   OppositeRouterId：对端路由器（VRouter或者VBR）的ID。

-   OppositeInterfaceOwnerId：对端路由器接口的账号ID。

-   Status：路由器接口的状态。

-   Name：路由器接口的名称。


 |
|Filter.n.Value.m|String|否| 指定的过滤条件对应的值。m的取值范围为\[1，5\]。

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
|RouterInterfaceSet|List|路由器接口的详细信息。|

|名称|类型|描述|
|--|--|--|
|RouterType|String|路由表所在路由器的类型，取值：-   VRouter：VPC路由器

-   VBR：边界路由器


|
|RouterId|String|路由表所在路由器的ID。|
|VRouterId|String|VPC路由器的ID。|
|RouteTableId|String|路由表的ID。|
|RouteTableType|String|路由表的类型。|
|CreationTime|String|路由表的创建时间。|
|RouteEntrys|List|路由条目的详细信息。|

|名称|类型|描述|
|--|--|--|
|Type|String|路由条目的类型，取值：-   System：系统路由

-   Custom：自定义路由

-   BGP：BGP路由


|
|RouteTableId|String|路由条目所属路由表的ID。|
|DestinationCidrBlock|String|路由条目的目标网段。|
|NextHopType|String|下一跳的类型。|
|InstanceId|String|下一跳的实例ID。|
|Status|String|路由条目的状态，取值：-   Pending：配置中

-   Available：可用

-   Modifying：修改中


|
|RouterId|String|路由条目所在路由器的ID。|
|NextHops|List|ECMP路由的下一跳列表。|

|名称|类型|描述|
|--|--|--|
|NextHopType|String| 下一跳的类型，取值：

 -   Instance：ECS实例（默认值）

HaVip：高可用虚拟IP

RouterInterface：路由器接口


 |
|NextHopId|String|下一跳实例的ID。|
|Enabled|Integer|是否启用下一跳：-   1：启用

-   1：不启用


|
|Weight|Integer|下一跳的路由权重。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeRouteTables
&RouteTableId=vtb-2zevpmy9th8cxmwtarqg4
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
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

-   JSON格式

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
                                "InstanceId": "", 
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


