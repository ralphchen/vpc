# DescribeBgpPeers {#reference_i4w_xmt_nd1b .reference}

Query the BGP peers in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeBgpPeers

 |
|RegionId|String|Yes| The region of the BGP peer.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BgpPeerId|String|No| The ID of the BGP peer.

 |
|RouterId|String|No| The ID of the VBR.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and  the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|BgpPeers|List|A list of BGP peers.|

|Name|Type|Description|
|:---|:---|:----------|
|BGPPeerId|String|The ID of the BGP peer.|
|Name|String|The name of the BGP peer.|
|LocalIpAddress|String|The IP address of the Alibaba Cloud side.|
|PeerIpAddress|String|The IP address of the BGP peer.|
|PeerASN|String|The ASN of the BGP peer.|
|BGPStatus|Integer|The connection status of BGP.|
|Authkey|String|The key used by the BGP group.|
|RouterId|String|The status of the BGP peer.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpPeers
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
                            <DescribeBgpGroupsResponse>
    	<TotalCount>2</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>16DFA5E6-9771-41B7-B079-DD7C2DF49BE6</RequestId>
    	<BgpPeers>
    	<BgpPeer>
    	<BgpGroupId>bgpg-2zev8h2wo414sfhjgdlhh</BgpGroupId>
    	<LocalAsn>45104</LocalAsn>
    	<PeerIpAddress>11.11.11.1</PeerIpAddress>
    	<Hold>30</Hold>
    	<Description></Description>
    	<AuthKey></AuthKey>
    	<IsFake>true</IsFake>
    	<PeerAsn>234</PeerAsn>
    	<Keepalive>10</Keepalive>
    	<RouteLimit>99</RouteLimit>
    	<BgpPeerId>bgp-2ze3un0ft1jd1xdppusul</BgpPeerId>
    	<Name> </Name>
    	<Status>Available</Status>
    	<BgpStatus></BgpStatus>
    	<RouterId>vbr-2zecmmvg5gvu8i4telkhw</RouterId>
    	<RegionId>cn-beijing</RegionId>
    	</BgpPeer>
    	<BgpPeer>
    	<BgpGroupId>bgpg-2zev8h2wo414sfhjgdlhh</BgpGroupId>
    	<LocalAsn>45104</LocalAsn>
    	<PeerIpAddress>11.11.11.2</PeerIpAddress>
    	<Hold>30</Hold>
    	<Description></Description>
    	<AuthKey></AuthKey>
    	<IsFake>true</IsFake>
    	<PeerAsn>234</PeerAsn>
    	<Keepalive>10</Keepalive>
    	<RouteLimit>99</RouteLimit>
    	<BgpPeerId>bgp-2zeu54rbreqqzyb5bg1hq</BgpPeerId>
    	<Name></Name>
    	<Status>Available</Status>
    	<BgpStatus></BgpStatus>
    	<RouterId>vbr-2zecmmvg5gvu8i4telkhw</RouterId>
    	<RegionId>cn-beijing</RegionId>
    	</BgpPeer>
    	</BgpPeers>
    	</DescribeBgpGroupsResponse>
    ```

-   JSON format

    ```
    
        "TotalCount": 2, 
        "PageSize": 10, 
        "RequestId": "16DFA5E6-9771-41B7-B079-DD7C2DF49BE6", 
        "BgpPeers": {
            "BgpPeer": [
                
                    "BgpGroupId": "bgpg-2zev8h2wo414sfhjgdlhh", 
                    "LocalAsn": 45104, 
                    "PeerIpAddress": "11.11.11.1", 
                    "Hold": 30, 
                    "Description": "", 
                    "AuthKey": "", 
                    "IsFake": true, 
                    "PeerAsn": 234, 
                    "Keepalive": 10, 
                    "RouteLimit": 99, 
                    "BgpPeerId": "bgp-2ze3un0ft1jd1xdppusul", 
                    "Name": "", 
                    "Status": "Available", 
                    "BgpStatus": "", 
                    "RouterId": "vbr-2zecmmvg5gvu8i4telkhw", 
                    "RegionId": "cn-beijing"
                 
                
                    "BgpGroupId": "bgpg-2zev8h2wo414sfhjgdlhh", 
                    "LocalAsn": 45104, 
                    "PeerIpAddress": "11.11.11.2", 
                    "Hold": 30, 
                    "Description": "", 
                    "AuthKey": "", 
                    "IsFake": true, 
                    "PeerAsn": 234, 
                    "Keepalive": 10, 
                    "RouteLimit": 99, 
                    "BgpPeerId": "bgp-2zeu54rbreqqzyb5bg1hq", 
                    "Name": "", 
                    "Status": "Available", 
                    "BgpStatus": "", 
                    "RouterId": "vbr-2zecmmvg5gvu8i4telkhw", 
                    "RegionId": "cn-beijing"
                
            
        
    
    ```


