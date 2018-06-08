# DescribeBgpPeers {#reference_i4w_xmt_ndb .reference}

查询指定地域下的BGP邻居。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeBgpPeers

 |
|RegionId|String|是| BGP组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BgpPeerId|String|否| BGP邻居的ID。

 |
|RouterId|String|否| VBR的ID。

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
|BgpPeers|List|BGP邻居的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|BGPPeerId|String|BGP邻居的ID。|
|Name|String|BGP邻居的名称。|
|LocalIpAddress|String|阿里云侧的IP地址。|
|PeerIpAddress|String|BGP邻居的IP地址。|
|PeerASN|String|BGP邻居的ASN。|
|BGPStatus|Integer|BGP的连接状态。|
|AuthKey|String|BGP组的认证密钥。|
|RouterId|String|BGP邻居的状态。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpPeers
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <<?xml version="1.0" encoding="UTF-8" ?>
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
    			<Name></Name>
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

-   JSON格式

    ```
    {
        "TotalCount": 2, 
        "PageSize": 10, 
        "RequestId": "16DFA5E6-9771-41B7-B079-DD7C2DF49BE6", 
        "BgpPeers": {
            "BgpPeer": [
                {
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
                }, 
                {
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
                }
            ]
        }
    }
    ```


