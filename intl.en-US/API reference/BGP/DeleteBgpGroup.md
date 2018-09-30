# DeleteBgpGroup {#reference_1i4w_xmt_ndb5 .reference}

Delete a BGP group.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteBgpGroup

 |
|RegionId|String|Yes| The region of the BGP group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|BgpGroupId|String|Yes| The ID of the BGP group.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteBgpGroup
&RegionId=cn-beijing
&BgpGroupId=bgpg-2zendnzngq9lkjkhvlrsr
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DeleteBgpGroupResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </DeleteBgpGroupResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


