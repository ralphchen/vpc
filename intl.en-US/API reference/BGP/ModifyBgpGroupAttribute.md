# ModifyBgpGroupAttribute {#referen1ce_i4w_xmt_ndb .reference}

Modify the configurations of a BGP group.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifyBgpGroupAttribute

 |
|RegionId|String|Yes| The region of the BGP group.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|PeerASN|String|Yes| The ASN of the BGP peer. It can be 2 bytes or 4 bytes in length. The ASN of the BGP peer cannot be the same as the Alibaba Cloud-side ASN \(45104\).

 |
|RouterId|String|No| The ID of the VBR.

 |
|Name|String|No| The name of the BGP group.

 The name can contain from 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://`  or `https://`.

 |
|Description|String|No| The description of the BGP group.

 The description can contain from 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Request parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyBgpGroupAttribute
&RegionId=cn-beijing
&BgpGroupId=2010
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <ModifyBgpGroupAttributeResponse>
        <RequestId>C1221A1F-2ACD-4592-8F27-474E02883159</RequestId>
        </ModifyBgpGroupAttributeResponse>
    ```

-   JSON format

    ```
    
      "RequestId": "C1221A1F-2ACD-4592-8F27-474E02883159"
    
    ```


