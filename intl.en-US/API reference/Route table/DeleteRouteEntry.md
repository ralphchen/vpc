# DeleteRouteEntry {#reference_i4w_xmt_ndb .reference}

Delete a router entry from a route table.

Note the following before deleting a router entry:

-   You can only delete a router entry in the available status.

-   You cannot delete a router entry of a VPC that is creating or deleting a VSwitch or route entry.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteRouteEntry

 |
|RouteTableId|String|Yes| The ID of the route table to which the route entry belongs.

 |
|DestinationCidrBlock|String|Yes| The destination CIDR block of the route entry.

 |
|NextHopId|String|No| The ID of the next-hop instance of the route entry. Specify this parameter when deleting a common \(non-ECMP\) route entry.

 |
|NextHopList|List|No| A list of next hops of the router entries.  Specify this parameter when deleting an ECMP route entry.

 |

|Parameter|Type|Required|Description|
|:--------|:---|--------|:----------|
|NextHopType|String|No| The type of the next hop. Valid value:

 -   Instance: ECS instance \(Default\)

HaVip: High availability virtual IP

RouterInterface: Router interface


 |
|NextHopId|String|No|The ID of the next-hop instance.|
|Enabled|Integer|No|Whether to enable the next hop:-   0: unavailable

-   1: available


|
|Weight|Integer|No|The routing weight of the next hop.|

## Response example {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID pf the request.|

## Example {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteRouteEntry
&RouterTableId=vtb-25vtxl5ct
&DestinationCidrBlock=192.168.1.0/24
&NextHopId=i-25skktcp4
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteRouteEntryResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteRouteEntryResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


