# DescribeSnatTableEntries {#reference_amt_w2p_rdb .reference}

Query SNAT entries in a SNAT table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 Describeforwardtableentries

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|SnatTableId|String|Yes| The ID of the SNAT table.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_hlq_4gp_rdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String| The ID of the request.|
|TotalCount|String| The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|SnatTableEntries|List|A list of SNAT entries.|

|Name|Type|Description|
|:---|:---|:----------|
|SnatTableId|String| The ID of the SNAT table to which the SNAT entries belong.

 |
|SnatEntryId|String| The ID of the SNAT entry.

 |
|SourceVSwitchId|String| The ID of the VSwitch that access the Internet through the SNAT function.

 |
|SourceCIDR|String| The source CIDR block of the SNAT entry.

 |
|SnatIp|String| The public IP of the SNAT entry.

 |
|Status |String| The status of the SNAT entry. Valid value:

 -   pending: configuring

-   Available: available

-   Modifying: modifying


 |

## Examples {#section_dg4_y5r_rdb .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeSnatTableEntries
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
                            <DescribeSnatTableEntriesResponse>	
                            <PageNumber>1</PageNumber>
                            <PageSize>10</PageSize>
                            <RequestId>6D7E89B1-1C5B-412B-8585-4908E222EED5</RequestId>
                            <SnatTableEntries>
                            <SnatTableEntry>
                            <SnatEntryId>snat-kmd6nv8fy</SnatEntryId>
                            <SnatIp>139.xxx.xx. 40</SnatIp>
                            <SnatTableId>stb-gz3r3odaw</SnatTableId>
                            <SourceCIDR>192.168.1.0/24</SourceCIDR>
                            <SourceVSwitchId>vsw-yrv0xxxxx</SourceVSwitchId>
                            <Status>Available</Status>
                            </SnatTableEntry>
                            <SnatTableEntry>
                            <SnatEntryId>snat-bs5bezbme</SnatEntryId>
                            <SnatIp>139.xxx.xx. 40</SnatIp>
                            <SnatTableId>stb-gz3r3odaw</SnatTableId>
                            <SourceCIDR>192.168.3.0/24</SourceCIDR>
                            <SourceVSwitchId>vsw-3xbxxxxx</SourceVSwitchId>
                            <Status>Available</Status>
                            </SnatTableEntry>
                            </SnatTableEntries>
                            </DescribeSnatTableEntriesResponse>
    ```

-   JSON format

    ```
    
        "PageNumber": 1, 
        "PageSize": 10, 
        "RequestId": "6D7E89B1-1C5B-412B-8585-4908E222EED5", 
        "SnatTableEntries": {
            "SnatTableEntry": [
                
                    "SnatEntryId": "snat-kmd6nv8fy", 
                    "SnatIp": "139.xxx.xx. 40", 
                    "SnatTableId": "stb-gz3r3odaw", 
                    "SourceCIDR": "192.168.1.0/24", 
                    "SourceVSwitchId": "vsw-yrv0xxxxx", 
                    "Status": "Available"
                 
                
                    "SnatEntryId": "snat-bs5bezbme", 
                    "SnatIp": "139.xxx.xx. 40", 
                    "SnatTableId": "stb-gz3r3odaw", 
                    "Script Dr": "192.168.3.0/24 ", 
                    "SourceVSwitchId": "vsw-3xbxxxxx", 
                    "Status": "Available"
                
            
        
    
    ```


