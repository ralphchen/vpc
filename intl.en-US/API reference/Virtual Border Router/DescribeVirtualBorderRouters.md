# DescribeVirtualBorderRouters {#refer4ence_i4w_xmt_ndb .reference}

Query the created Virtual Border Routers \(VBRs\).

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeVirtualBorderRouters

 |
|RegionId|String|Yes| The region of the VBR.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|Filter.n.Key|String|No| Filter keys.  Up to five filters are supported. Valid value for n is \[1,5\].

 The relationship between the values of a filter is "or". A VBR is returned as long as one filter is met.

 The relationship between each filter is "and". A VBR is returned only when all the filters are met.

 The following are available filter keys:

-   PhysicalConnectionId: The ID of the physical connection.

-   VbrId: The ID of the VBR.

-   Status: The status of the VBR.

-   AccessPointId: The ID of the access point of the associated physical connection.

-   Name: The name of the VBR.


 |
|Filter.n.Value.m|String|No| The corresponding value of the specified filter key. The valid value of m is \[1, 5\].

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String| The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|VirtualBorderRouterSet|List|A list of VBRs. For more information, see [Table 1](#table_px2_zbt_4db).|

|Name|Type|Description|
|:---|:---|:----------|
|VbrId|String|The ID of the VBR.|
|VbrOwnerUid|String|The ID of the VBR owner. When the VBR owner and the physical connection owner are the same, this parameter is empty.|
|CreationTime|Integer|The time when the VBR is created.|
|ActivationTime|String|The first time when the VBR was activated.|
|TerminationTime|String|The last time when the VBR was terminated.|
|RecoveryTime|String|The last time when the VBR recovered from the Terminated status to the Active status.|
|Status|String|The status of the VBR.|
|VlanId|String|The VLAN ID of the VBR.|
|CircuitCode|String|The circuit code provided by the carrier for the leased line.|
|RouteTableId|String|The ID of the route table of the VBR.|
|VlanInterfaceId|String|The ID of the router interface of the VBR.|
|LocalGatewayIp|String|The Alibaba Cloud-side IP.|
|PeerGatewayIp|String|The client-side IP.|
|PeeringSubnetMask|String|The subnet mask for the Alibaba Cloud-side IP and the client-side IP.|
|Name|String|The name of the VBR.|
|Description|String|The description of the VBR.|
|PhysicalConnectionId|String|The ID of the physical connection that the VBR belongs to.|
|AccessPointId|String|The ID of the physical connection access point.|
|Status|String|The status of the physical connection:-   Initial: applying

-   Approved: approved

-   Allocating: allocating resources

-   Allocated: access construction.

-   Confirmed: wait for user confirmation.

-   Enabled: enabled.

-   Rejected: rejected.

-   Canceled: cancelled.

-   Allocation Failed: resource allocation failed.

-   Terminated: terminated.


|
|BusinessStatus|String|The payment status of the physical connection:-   Normal: normal

-   FinancialLocked: financially locked

-   SecurityLocked: locked for security reasons


|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVirtualBorderRouters
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DescribeVirtualBorderRoutersResponse>
                            <RequestId>AE65530E-8436-4FB1-8217-DCD35712AC89</RequestId>
                            <PageNumber>1</PageNumber>
                            <VirtualBorderRouterSet>
                            <VirtualBorderRouterType>
                            <LocalGatewayIp>10.1.1.1</LocalGatewayIp>
                            <PeerGatewayIp>10.2.2.2</PeerGatewayIp>
                            <Description></Description>
                            <PhysicalConnectionOwnerUid>1231579085529123</PhysicalConnectionOwnerUid>
                            <VlanId>10</VlanId>
                            <RecoveryTime></RecoveryTime>
                            <PhysicalConnectionStatus>Enabled</PhysicalConnectionStatus>
                            <PhysicalConnectionId>pc-2zeoaxkq3jot5p71qcnuy</PhysicalConnectionId>
                            <RouteTableId>vtb-2ze9hmd6yofwvb1dd79j9</RouteTableId>
                            <PeeringSubnetMask>255.0.0.0</PeeringSubnetMask>
                            <TerminationTime></TerminationTime>
                            <Name></Name>
                            <CreationTime>2018-03-06T11:16:34Z</CreationTime>
                            <ActivationTime>2018-03-06T11:16:34Z</ActivationTime>
                            <CircuitCode></CircuitCode>
                            <Status>active</Status>
                            <PhysicalConnectionBusinessStatus>Normal</PhysicalConnectionBusinessStatus>
                            <VlanInterfaceId>ri-2zeum6rgu0586gjrocikm</VlanInterfaceId>
                            <AccessPointId>ap-cn-beijing-dx-A</AccessPointId>
                            <VbrId>vbr-2zecmmvg5gvu8i4telkhw</VbrId>
                            </VirtualBorderRouterType>
                            </VirtualBorderRouterSet>
                            <TotalCount>1</TotalCount>
                            <PageSize>10</PageSize>
                            </DescribeVirtualBorderRoutersResponse>
    ```

-   JSON format

    ```
    
      "PageNumber": 1,
      "VirtualBorderRouterSet": {
        "VirtualBorderRouterType": [
          
            "LocalGatewayIp": "10.1.1.1",
            "PeerGatewayIp": "10.2.2.2",
            "Description": "",
            "PhysicalConnectionOwnerUid": "1231579085xxxx",
            "VlanId": 10,
            "RecoveryTime": "",
            "PhysicalConnectionStatus": "Enabled",
            "PhysicalConnectionId": "pc-2zeoaxkq3jotxxxxx",
            "RouteTableId": "vtb-2ze9hmd6yofwxxxxxx",
            "PeeringSubnetMask": "255.0.0.0",
            "TerminationTime": "",
            "Name": "",
            "CreationTime": "2018-03-06T11:16:34Z",
            "ActivationTime": "2018-03-06T11:16:34Z",
            "CircuitCode": "",
            "Status": "active",
            "PhysicalConnectionBusinessStatus": "Normal",
            "VlanInterfaceId": "ri-2zeum6rgu058xxxxxx",
            "AccessPointId": "ap-cn-beijing-dx-A",
            "VbrId": "vbr-2zecmmvg5gvuxxxxxx"
          
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "98B24329-ADC9-4725-A5F8-6C1B282DA17D"
    
    ```


