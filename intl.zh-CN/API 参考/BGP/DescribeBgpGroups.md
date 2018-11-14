# DescribeBgpGroups {#reference_i4w_xmt_ndb .reference}

查询指定地域下的BGP组。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeBgpGroups

 |
|RegionId|String|否| BGP组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BgpGroupId|String|否| BGP组的ID。

 |
|RouterId|String|否| BGP组关联的VBR的ID。

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
|BGPGroups|List|BGP组的详细信息，详细信息参见。|

|名称|类型|描述|
|:-|:-|:-|
|BgpGroupId|String|BGP组ID。|
|Name|String|BGP组的名称。|
|Status|String|BGP组的状态。|
|RouterId|String|BGP组关联的边界路由器ID。|
|RegionId|String|BGP组的地域。|
|Description|Integer|BGP组的描述。|
|AuthKey|String|BGP组的认证密钥。|
|PeerAsn|String|BGP邻居的ASN。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpGroups
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
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

-   JSON格式

    ```
    {
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "09E2C0FD-37FF-4737-80DF-517AC36D43DB", 
        "BgpGroups": {
            "BgpGroup": [
                {
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
                }
            ]
        }
    }
    ```


