# DescribeBgpGroups {#referen3ce_i4w_xmt_ndb .reference}

Query the created BGP groups.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeBgpGroups

 |
|RegionId|String|No| The region of the BGP group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BgpGroupId|String|No| The ID of the BGP group.

 |
|RouterId|String|No| The ID of the VBR associated with the BGP group.

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
|BGPGroups|List|A list of BGP groups. For more information, see|

|Name|Type|Description|
|:---|:---|:----------|
|BgpGroupId|String|The ID of the BGP group.|
|Name|String|The name of the BGP group.|
|Status|String|The status of the BGP group.|
|RouterId|String|The ID of the VBR associated with the BGP group.|
|RegionId|String|The region of the BGP group.|
|Description|Integer|The description of the BGP group.|
|Authkey|String|The authentication key of the BGP group.|
|PeerAsn|String|The ASN of the BGP peer.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpGroups
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
                            <DescribeBgpGroupsResponse>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>09E2C0FD-37FF-4737-80DF-517AC36D43DB</RequestId>
    	<BgpGroups>
    	<BgpGroup>
    	<BgpGroupId>bgpg-2zev8h2wo414sfhjgdlhh</BgpGroupId>
    	<LocalAsn>45104</LocalAsn>
    	<Hold>30</Hold>
    	<Description></Description>
    	<AuthKey></AuthKey>
    	<IsFake>true</IsFake>
    	<PeerAsn>234</PeerAsn>
    	<Keepalive>10</Keepalive>
    	<RouteLimit>99</RouteLimit>
    	<Name>Group1</Name>
    	<Status>Pending</Status>
    	<RouterId>vbr-2zecmmvg5gvu8i4telkhw</RouterId>
    	<RegionId>cn-beijing</RegionId>
    	</BgpGroup>
    	</BgpGroups>
    	</DescribeBgpGroupsResponse>
    ```

-   JSON format

    ```
    
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "09E2C0FD-37FF-4737-80DF-517AC36D43DB", 
        "BgpGroups": {
            "BgpGroup": [
                
                    "BgpGroupId": "bgpg-2zev8h2wo414sfhjgdlhh", 
                    "LocalAsn": 45104, 
                    "Hold": 30, 
                    "Description": "", 
                    "AuthKey": "", 
                    "IsFake": true, 
                    "PeerAsn": 234, 
                    "Keepalive": 10, 
                    "RouteLimit": 99, 
                    "Name": "Group1", 
                    "Status": "Pending", 
                    "RouterId": "vbr-2zecmmvg5gvu8i4telkhw", 
                    "RegionId": "cn-beijing"
                
            
        
    
    ```


