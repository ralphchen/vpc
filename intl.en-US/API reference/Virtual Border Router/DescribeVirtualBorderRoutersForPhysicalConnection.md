# DescribeVirtualBorderRoutersForPhysicalConnection {#ref3erence_i4w_xmt_ndb .reference}

Query the Virtual Border Routers created for a physical connection.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVirtualBorderRoutersForPhysicalConnection

 |
|RegionId|String|Yes| The region of the physical connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|PhysicalConnectionId|String|No| The ID of the physical connection.

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
|VirtualBorderRouterForPhysicalConnectionSet|List|A list of VBRs.|

|Name|Type|Description|
|:---|:---|:----------|
|VbrId|String|The ID of the VBR.|
|VbrOwnerUid|String|The account ID of the VBR owner. This parameter is empty when the VBR owner and the physical connection owner are the same.|
|CreationTime|Integer|The time when the VBR is created.|
|ActivationTime|String|The first time when the VBR was activated.|
|TerminationTime|String|The last time when the VBR was terminated.|
|RecoveryTime|String|The last time when the VBR recovered from the Terminated status to the Active status.|
|VlanId|String|The VLAN ID of the VBR.|
|CircuitCode|String|The circuit code provided by the carrier for the physical connection.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVirtualBorderRoutersForPhysicalConnection
&RegionId=cn-beijing
&PhysicalConnectionId=pc-2zeoaxkq3joxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DescribeVirtualBorderRoutersForPhysicalConnectionResponse>
    	<RequestId>03E8CB87-5876-4034-BBB2-6E0851281C37</RequestId>
    	<PageNumber>1</PageNumber>
    	<TotalCount>2</TotalCount>
    	<PageSize>10</PageSize>
    	<VirtualBorderRouterForPhysicalConnectionSet>
    	<VirtualBorderRouterForPhysicalConnectionType>
    	<ActivationTime>2018-03-06T11:16:34Z</ActivationTime>
    	<CreationTime>2018-03-06T11:16:34Z</CreationTime>
    	<CircuitCode></CircuitCode>
    	<VlanId>10</VlanId>
    	<RecoveryTime></RecoveryTime>
    	<VbrOwnerUxxx231579085529123</VbrOwnerUid>
    	<TerminationTime></TerminationTime>
    	<VbrId>Vbrxxxxx-2zecmmvg5gvu8i4telkhw</VbrId>
    	</VirtualBorderRouterForPhysicalConnectionType>
    	<VirtualBorderRouterForPhysicalConnectionType>
    	<ActivationTime>2018-01-04T13:34:18Z</ActivationTime>
    	<CreationTime>2018-01-04T13:34:18Z</CreationTime>
    	<CircuitCode></CircuitCode>
    	<VlanId>100</VlanId>
    	<RecoveryTime></RecoveryTime>
    	<VxxxbrOwnerUid>1231579085529123</VbrOwnerUid>
    	<TerminationTime></TerminationTime>
    	<VbrId>vbr-2zee2e2cwetx4k0tohakw</VbrId>
    	</VirtualBorderRouterForPhysicalConnectionType>
    	</DescribeVirtualBorderRoutersForPhysicalConnectionResponse>
    ```

-   JSON format

    ```
    
        "PageNumber": 1, 
        "TotalCount": 2, 
        "Pagesize": 10, 
        "RequestId": "03E8CB87-5876-4034-BBB2-6E0851281C37", 
        "VirtualBorderRouterForPhysicalConnectionSet": {
            "VirtualBorderRouterForPhysicalConnectionType": [
                
                    "ActivationTime": "2018-03-06T11:16:34Z", 
                    "CreationTime": "2018-03-06T11:16:34Z", 
                    "CircuitCode": "", 
                    "VlanId": 10, 
                    "RecoveryTime": "", 
                    "VbrOwnerUid": "1231579085xxxxxx529123", 
                    "TerminationTime": "", 
                    "VbrId": "vbr-2zecmmvg5gvu8xxxxw"
                 
                
                    "ActivationTime": "2018-01-04T13:34:18Z", 
                    "CreationTime": "2018-01-04T13:34:18Z", 
                    "Porteritcode ":"", 
                    "VlanId": 100, 
                    "RecoveryTime": "", 
                    "VbrOwnerUid": "1231579085xxx", 
                    "TerminationTime": "", 
                    "VbrId": "vbr-2zee2e2cwetx4k0txxxxakw"
                
            
        
    
    ```


