# DescribeNatGateways {#reference_i4w_xmt_n1db .reference}

Query the created NAT Gateways in a specified region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeNatGateways

 |
|RegionId|String|Yes| The region of the NAT gateway.

 You can query the region ID by calling the DescribeRegions API.

 |
|NatGatewayId|String|No| The ID of the NAT gateway.

 |
|VpcId|String|No| The ID of the VPC.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and  the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|NatGateways|List| A list of queried NAT Gateways.|

|Name|Type|Description|
|:---|:---|:----------|
|NatGatewayId|String| The region of the NAT gateway.

 |
|RegionId|String| The ID of the NAT gateway.

 |
|Description|Integer| The description of the NAT gateway.

 |
|Spec|String| The specification of the NAT gateway.

 |
|Status|String| The status of the NAT gateway, valid value:

-   Initiating: Initiating

-   Available: Available

-   Pending: Configuring


 |
|ForwardTableIds|List| The list of DNAT entries.

 |
|BandwidthPackageIds |List|The list of NAT bandwidth packages.|
|SnatTableIds |List|The list of SNAT entries.|
|InstanceChargeType |String|The payment method of NAT gateway.|
|BusinessStatus |String|The payment status of the NAT gateway, valid value:-   Normal: normal

-   FinancialLocked: financially locked

-   SecurityLocked: locked for security reasons


|
|CreationTime |String| The time when the NAT gateway is created.

 |

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeNatGateways
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <DescribeNatGatewaysResponse>
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>1207C80C-7CAB-4874-A9A0-D19EC9F35490</RequestId>
    	<NatGateways>
    	<NatGateway>
    	<Description></Description>
    	<Spec>Small</Spec>
    	<IpLists>
    	<IpList>
    	<IpAddress>118.31.65.181</IpAddress>
    	<AllocationId>eip-bp1xyg5ipmh3nledxywxf</AllocationId>
    	<UsingStatus>UsedBySnatTable</UsingStatus>
    	</IpList>
    	<IpList>
    	<IpAddress>47.97.187.34</IpAddress>
    	<AllocationId>eip-bp19eue77u20cffjcu4ea</AllocationId>
    	<UsingStatus>UsedByForwardTable</UsingStatus>
    	</IpList>
    	</IpLists>
    	<ForwardTableIds>
    	<ForwardTableId>ftb-bp15o9aylj19vfvgtnzoy</ForwardTableId>
    	</ForwardTableIds>
    	<VpcId>vpc-bp15k6sx6fhdz2jw4daz0</VpcId>
    	<NatGatewayId>ngw-bp1047e2d4z7kf2kiy25t</NatGatewayId>
    	<CreationTime>2018-01-10T09:48:29Z</CreationTime>
    	<BandwidthPackageIds></BandwidthPackageIds>
    	<Name></Name>
    	<Status>Available</Status>
    	<BusinessStatus>Normal</BusinessStatus>
    	<RegionId>cn-hangzhou</RegionId>
    	<SnatTableIds>
    	<SnatTableId>stb-bp1tyr0o48w6wymur4gvn</SnatTableId>
    	</SnatTableIds>
    	<InstanceChargeType>PostPaid</InstanceChargeType>
    	</NatGateway>
    	</NatGateways>
    	</DescribeNatGatewaysResponse>
    ```

-   JSON format

    ```
    
        "PageNumber": 1, 
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "1207C80C-7CAB-4874-A9A0-D19EC9F35490", 
        "NatGateways": {
            "NatGateway": [ 
                
                    "Description": "", 
                    "Spec": "Small", 
                    "IpLists": {
                        "IpList": [
                            
                                "IpAddress": "118.31.65.181", 
                                "AllocationId": "eip-bp1xyg5ipmh3nledxywxf", 
                                "UsingStatus": "UsedBySnatTable"
                             
                            
                                "IpAddress": "47.97.187.34", 
                                "AllocationId": "eip-bp19eue77u20cffjcu4ea", 
                                "UsingStatus": "UsedByForwardTable"
                            
                        
                     
                    "ForwardTableIds": {
                        "ForwardTableId": [
                            "ftb-bp15o9aylj19vfvgtnzoy"
                        
                     
                    "VpcId": "vpc-bp15k6sx6fhdz2jw4daz0", 
                    "NatGatewayId": "ngw-bp1047e2d4z7kf2kiy25t", 
                    "CreationTime": "2018-01-10T09:48:29Z", 
                    "BandwidthPackageIds": {
                        "BandwidthPackageId": [ ]
                     
                    "Name": "", 
                    "Status": "Available", 
                    "BusinessStatus": "Normal", 
                    "RegionId": "cn-hangzhou", 
                    "SnatTableIds": {
                        "SnatTableId": [
                            "stb-bp1tyr0o48w6wymur4gvn"
                        
                     
                    "InstanceChargeType": "PostPaid"
                
            
        
    
    ```


