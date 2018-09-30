# DescribeForwardTableEntries {#reference_amt_w2p_51rdb .reference}

Query the list of DNAT entries in a DNAT table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeForwardTableEntries

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|ForwardTableId|String|Yes| The ID of the DNAT table.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_hlq_4gp_rdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|ForwardTableEntries|List|The list of queried DNAT entries.|

|Name|Type|Description|
|:---|:---|:----------|
|ForwardTableId|String| The ID of the DNAT table that the DNAT entries belong to.

 |
|ForwardEntryId|String| The ID of the DNAT entry.

 |
|ExternalIp|Integer| The public IP address.

 |
|ExternalPort|String| The public port.

 |
|IpProtocol|String| The protocol type.

 |
|InternalIp|String| The private IP address.

 |
|InternalPort |String| The private port.

 |
|Status |String| The status of the DNAT entry, valid value:

 -   pending: configuring

-   Available: available

-   Modifying: modifying


 |

## Examples { .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateForwardEntry
&ExternalIp=139.224.22.107
&RegionId=cn-shanghai
&ExternalPort=Any
&InternalIp=192.168.1.1
&ForwardTableId=ftb-11tc6xgmv
&IpProtocol=Any
&InternalPort=Any
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
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

-   JSON format

    ```
    
      "PageNumber": 1,
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "74F2BAD8-AF35-4C57-81F1-5E33BFB0F5F2",
      "ForwardTableEntries": {
        "ForwardTableEntry": [
          
            "Status": "Available",
            "IpProtocol": "any",
            "ForwardEntryId": "fwd-bp18jpb1tlm550di3q5pb",
            "ExternalIp": "47.97.xx.xx",
            "ForwardTableId": "ftb-bp15o9aylj19vfvgtnzoy",
            "ExternalPort": "any",
            "InternalPort": "any",
            "InternalIp": "192.168.xx.xx"
          
        
      
    
    ```


