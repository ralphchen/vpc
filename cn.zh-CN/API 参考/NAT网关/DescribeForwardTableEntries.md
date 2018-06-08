# DescribeForwardTableEntries {#reference_amt_w2p_rdb .reference}

查询已创建的DNAT条目。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeForwardTableEntries

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ForwardTableId|String|是| DNAT列表的ID。

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
|ForwardTableEntries|List|DNAT列表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|ForwardTableId|String| DNAT条目所属DNAT表的ID。

 |
|ForwardEntryId|String| DNAT条目的ID。

 |
|ExternalIp|Integer| 公网IP地址。

 |
|ExternalPort|String| 公网端口。

 |
|IpProtocol|String| 协议类型。

 |
|InternalIp|String| 私网IP地址。

 |
|InternalPort |String| 私网端口。

 |
|Status |String| DNAT条目的状态，取值：

 -   pending：配置中

-   Available：可用

-   Modifying：修改中


 |

## 示例 { .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateForwardEntry
&ExternalIp=139.224.22.107
&RegionId=cn-shanghai
&ExternalPort=Any
&InternalIp=192.168.1.1
&ForwardTableId=ftb-11tc6xgmv
&IpProtocol=Any
&InternalPort=Any
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DescribeForwardTableEntriesResponse>	
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>74F2BAD8-AF35-4C57-81F1-5E33BFB0F5F2</RequestId>
    	<ForwardTableEntries>
    		<ForwardTableEntry>
    			<Status>Available</Status>
    			<IpProtocol>any</IpProtocol>
    			<ForwardEntryId>fwd-bp18jpb1tlm550di3q5pb</ForwardEntryId>
    			<ExternalIp>47.97.xx.xx</ExternalIp>
    			<ForwardTableId>ftb-bp15o9aylj19vfvgtnzoy</ForwardTableId>
    			<ExternalPort>any</ExternalPort>
    			<InternalPort>any</InternalPort>
    			<InternalIp>192.168.xx.xx</InternalIp>
    		</ForwardTableEntry>
    	</ForwardTableEntries>
    </DescribeForwardTableEntriesResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "74F2BAD8-AF35-4C57-81F1-5E33BFB0F5F2",
      "ForwardTableEntries": {
        "ForwardTableEntry": [
          {
            "Status": "Available",
            "IpProtocol": "any",
            "ForwardEntryId": "fwd-bp18jpb1tlm550di3q5pb",
            "ExternalIp": "47.97.xx.xx",
            "ForwardTableId": "ftb-bp15o9aylj19vfvgtnzoy",
            "ExternalPort": "any",
            "InternalPort": "any",
            "InternalIp": "192.168.xx.xx"
          }
        ]
      }
    }
    ```


