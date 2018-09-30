# CreateBgpPeer {#reference_i4w_xmt_ndb6 .reference}

Add a BGP peer to a BGP group.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 CreateBgpPeer

 |
|RegionId|String|Yes| The region of the BGP group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BgpGroupId|String|Yes| The ID of the BGP group.

 |
|PeerIpAddress|String|Yes| The IP address of the BGP peer.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|BgpPeerId|String|The ID of the BGP peer.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateBgpPeer
&RegionId=cn-beijing
&PeerIpAddress=11.11.11.11
&BgpGroupId=bgpg-2zendnzngq9lkjkhvlrsr
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateBgpPeerResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </CreateBgpPeerResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


