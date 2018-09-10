# DescribeSnatTableEntries {#reference_amt_w2p_rdb .reference}

查询已创建的SNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeSnatTableEntries

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|SnatTableId|String|是| SNAT表ID。

 |
|SnatEntryId|String|否| SNAT条目ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_hlq_4gp_rdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|SnatTableEntries|List|SNAT列表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|SnatTableId|String| SNAT条目所属的SNAT表ID。

 |
|SnatEntryId|String| SNAT条目的ID。

 |
|SourceVSwitchId|String| 通过SNAT功能进行公网访问的交换机ID。

 |
|SourceCIDR|String| SNAT条目的源网段。

 |
|SnatIp|String| SNAT条目的公网IP。

 |
|Status |String| SNAT条目的状态，取值：

 -   pending：配置中

-   Available：可用

-   Modifying：修改中


 |

## 示例 {#section_dg4_y5r_rdb .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeSnatTableEntries
&RegionId=cn-shanghai
&SnatTableId=stb-gz3r3odaw
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DescribeSnatTableEntriesResponse>	
    	<PageNumber>1</PageNumber>
    	<PageSize>10</PageSize>
    	<RequestId>6D7E89B1-1C5B-412B-8585-4908E222EED5</RequestId>
    	<SnatTableEntries>
    		<SnatTableEntry>
    			<SnatEntryId>snat-kmd6nv8fy</SnatEntryId>
    			<SnatIp>139.xxx.xx.40</SnatIp>
    			<SnatTableId>stb-gz3r3odaw</SnatTableId>
    			<SourceCIDR>192.168.1.0/24</SourceCIDR>
    			<SourceVSwitchId>vsw-yrv0xxxxx</SourceVSwitchId>
    			<Status>Available</Status>
    		</SnatTableEntry>
    		<SnatTableEntry>
    			<SnatEntryId>snat-bs5bezbme</SnatEntryId>
    			<SnatIp>139.xxx.xx.40</SnatIp>
    			<SnatTableId>stb-gz3r3odaw</SnatTableId>
    			<SourceCIDR>192.168.3.0/24</SourceCIDR>
    			<SourceVSwitchId>vsw-3xbxxxxx</SourceVSwitchId>
    			<Status>Available</Status>
    		</SnatTableEntry>
    	</SnatTableEntries>
    </DescribeSnatTableEntriesResponse>
    ```

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "PageSize": 10, 
        "RequestId": "6D7E89B1-1C5B-412B-8585-4908E222EED5", 
        "SnatTableEntries": {
            "SnatTableEntry": [
                {
                    "SnatEntryId": "snat-kmd6nv8fy", 
                    "SnatIp": "139.xxx.xx.40", 
                    "SnatTableId": "stb-gz3r3odaw", 
                    "SourceCIDR": "192.168.1.0/24", 
                    "SourceVSwitchId": "vsw-yrv0xxxxx", 
                    "Status": "Available"
                }, 
                {
                    "SnatEntryId": "snat-bs5bezbme", 
                    "SnatIp": "139.xxx.xx.40", 
                    "SnatTableId": "stb-gz3r3odaw", 
                    "SourceCIDR": "192.168.3.0/24", 
                    "SourceVSwitchId": "vsw-3xbxxxxx", 
                    "Status": "Available"
                }
            ]
        }
    }
    ```

    \}


