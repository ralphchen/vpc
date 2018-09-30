# DescribePhysicalConnections {#reference_i4w_xmt_n21db .reference}

Query the created physical connections in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribePhysicalConnections

 |
|RegionId|String|Yes| The region of the physical connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|Filter. N. Key|String|No| Filter keys. Up to five filters are supported.  The valid value for n is \[1, 5\].

 The relationship between  the values of a filter is “or”. The physical connection is returned as long as one filter is met.

 The relationship between each filter is “and”. The physical connection is returned only when all the filters are met.

 The following are available filter keys:

-   PhysicalConnectionId: The ID of the physical connection.

-   AccessPointId: The ID of the access point.

-   Type: The type of the physical connection. The default value is VPC.

-   LineOperator: The carrier of the physical connection.

-   Status: The status of the physical connection.

-   Spec: The specification of the physical connection.

-   Name: The name of the physical connection.


 |
|Filter.n.Value.m|String|No| The corresponding value of the specified filter key. The valid value for m is \[1, 5\].

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
|Pagesize|String|The number of entries on the current page.|
|PhysicalConnectionSet|JSON String|A list of physical connections.|
|PhysicalConnectionSet objects|
|PhysicalConnectionId|String|The ID of the physical connection.|
|AccessPointId|String|The ID of the physical connection access point.|
|Status|String|The status of the physical connection.-   Initial: applying

-   Approved: approved

-   Allocating: allocating resources

-   Allocated: access construction.

-   Confirmed: waiting for user confirmation.

-   Enabled: enabled.

-   Rejected: rejected.

-   Canceled: canceled.

-   Allocation Failed: resource allocation failed.

-   Terminated: terminated.


|
|BusinessStatus|String|The payment status of the physical connection.-   Normal: normal

-   FinancialLocked: financially locked

-   SecurityLocked: locked for security reasons


|
|CreationTime|String|The time when the physical connection was created.|
|EnabledTime|String|The time when the physical connection was enabled.|
|LineOperator|String| The carrier of the physical connection:

-   CT: China Telecom

-   CU: China Unicom

-   CM: China Mobile

-   CO: Others in China

-   Equinix：Equinix

-   Other: Others outside China


 |
|Spec|String|The specification of the physical connection.|
|PeerLocation|String|The geographic location of the local data center.|
|PortType|String|The port type of the physical connection. Valid value:-   100Base-T: 100-MB electrical port

-   1000Base-T\(default\): 1-GB electrical port

-   1000Base-LX: 1-GB single-mode optical port \(10 km\)

-   10GBase-T: 10-GB electrical port

-   10GBase-LR: 10-GB single-mode optical port \(10 km\)


|
|RedundantPhysicalConnectionId|String|The ID of the redundant physical connection. |
|Name|String|The name of the physical connection.|
|Description|String|The description of the physical connection.|
|ADLocation|String|The location of the physical access device.|
|PortNumber|String|The port number of the physical access device.|
|CircuitCode|String|The circuit code provided by the carrier for the physical connection.|
|BandWidth|String|The bandwidth of the physical connection.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribePhysicalConnections
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DescribePhysicalConnectionsResponse>
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>7C07B0AF-4FC0-4BB2-9667-F75812824BCD</RequestId>
    	<PhysicalConnectionSet>
    	<PhysicalConnectionType>
    	<Type>VPC</Type>
    	<PhysicalConnectionId>pc-2zeoaxkq3jot5p71qcnuy</PhysicalConnectionId>
    	<PeerLocation>XXX-XX District--XXX Road</PeerLocation>
    	<CreationTime>2017-12-13T02:28:42Z</CreationTime>
    	<Name>TEST</Name>
    	<Status>Enabled</Status>
    	<AdLocation>XXX--XX-XXX Datacenter XX Network Cabinet XXU</AdLocation>
    	<EnabledTime>2017-12-18T04:01:30Z</EnabledTime>
    	<BusinessStatus>Normal</BusinessStatus>
    	<LineOperator>CT</LineOperator>
    	<PortNumber>1/1/4</PortNumber>
    	<AccessPointId>ap-cn-beijing-dx-A</AccessPointId>
    	<PortType>100Base-T</PortType>
    	<Bandwidth>2</Bandwidth>
    	</PhysicalConnectionType>
    	</PhysicalConnectionSet>	
    	</DescribePhysicalConnectionsResponse>
    ```

-   JSON format

    ```
    
      "PageNumber": 1,
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "7C07B0AF-4FC0-4BB2-9667-F75812824BCD",
      "PhysicalConnectionSet": {
        "PhysicalConnectionType": [
          
            "Type": "VPC",
            "PhysicalConnectionId": "pc-2zeoaxkq3jot5p71qcnuy",
            "PeerLocation": "XXX-XX District--XXX Road",
            "CreationTime": "2017-12-13T02:28:42Z",
            "Name": "TEST",
            "Status": "Enabled",
            "AdLocation": "XXX--XX-XXX Datacenter XX Network Cabinet XXU",
            "EnabledTime": "2017-12-18T04:01:30Z",
            "BusinessStatus": "Normal",
            "LineOperator": "CT",
            "PortNumber": "1/1/4",
            "AccessPointId": "ap-cn-beijing-dx-A",
            "PortType": "100Base-T",
            "Bandwidth": 2
          
        
      
    
    ```


