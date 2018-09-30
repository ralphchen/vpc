# DeleteBgpPeer {#reference_i4w_x1mt_ndb .reference}

Delete a BGP peer.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteBgpPeer

 |
|RegionId|String|Yes| The region of the BGP group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BgpPeerId|String|Yes| The ID of the BGP peer.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteBgpPeer
&RegionId=cn-beijing
&BgpGroupId=bgpg-2zendnzngq9lkjkhvlrsr
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeleteBgpPeerResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeleteBgpPeerRe>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


