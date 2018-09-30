# DescribeBgpNetworks {#reference_i4w_xmt_n3db .reference}

Query the advertised BGP networks.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeBgpNetworks

 |
|RegionId|String|Yes| The region of the BGP network.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|dstCidrBlock|String|No| The advertised BGP network.

 |
|routeId|String|No| The ID of the VBR.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpNetworks
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DescribeBgpNetworksResponse>
                            <BgpNetworks>
                            <BgpNetwork>
                            <DstCidrBlock>10.1.1.0/24</DstCidrBlock>
                            <VpcId></VpcId>
                            </BgpNetwork>
                            </BgpNetworks>
                            <RequestId>6F513A15-669F-419D-B511-08A85292059B</RequestId>
                            <PageSize>10</PageSize>
                            <TotalCount>1</TotalCount>
                            </DescribeBgpNetworksResponse>
    ```

-   JSON format

    ```
    
      "BgpNetworks": {
        "BgpNetwork": [
          
            "DstCidrBlock": "10.1.1.0/24",
            "VpcId": ""
          
        
      
      "RequestId": "6F513A15-669F-419D-B511-08A85292059B",
      "PageSize": 10,
      "TotalCount": 1
    
    ```


