# DescribeEipAddresses {#reference_i4w_xmt_ndb .reference}

Queries the EIP that has been created for the specified region.

## Query the created EIPs in a specified region. {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeEipAddresses

 |
|RegionId|String|Yes|  The region of the EIP.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|Status|String|No| The status of the EIP. Valid value:

-   Associating: The EIP is being bound.

-   Unassociating: The EIP is being unbound.

-   InUse: The EIP has been bound to a cloud resource.

-   Available: The EIP is not bound to any cloud resources.


 |
|AllocationId|String|No| The ID of the EIP.

 |
|AssociatedInstanceType|String|No| The cloud resource that the EIP is bound to. Valid value:

 -   EcsInstance \(Default\): An ECS instance of the VPC network

-   SlbInstance: An SLB instance of the VPC network

-   Nat: NAT Gateway

-   HaVip: HAVIP instance


 Each ECS and SLB instance can only binds an EIP. However, a NAT Gateway can bind multiple EIPs.

 |
|AssociatedInstanceId|String|No| The ID of the cloud resource that the EIP is bound to.

 |
|PageNumber|Integer|No|  The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameter {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String| The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|EipAddresses|List|The detailed information of queried EIPs.|

|Name|Type|Description|
|----|----|-----------|
|RegionId|String|The region where the EIP is located.|
|IpAddress|String|The address of the EIP.|
|AllocationId|String|The ID of the EIP.|
|Status|String| The status of the EIP:

-   Associating: The EIP is being bound.

-   Unassociating: The EIP is being unbound.

-   InUse: The EIP has been bound to a cloud resource.

-   Available: The EIP is not bound to any cloud resources.


 |
|InstanceType|String|The instance type of that the EIP is bound.|
|InstanceId|String|The ID of the instance that is being bound.|
|Bandwidth|String|The bandwidth of the EIP in Mbps.|
|InternetChargeType|String|Billing method.|
|AllocationTime|String|The time at which the EIP is created.|
|OperationLocks|String|The reason for being locked. Valid value:-   financial: overdue

-   security: security reasons


|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou-1
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DescribeEipAddressesResponse>
    	<RequestId>7EEF2D6B-D207-4197-AE37-01279C888757</RequestId>
    	<PageNumber>1</PageNumber>
    	<EipAddresses>
    		<EipAddress>
    			<ChargeType>PostPaid</ChargeType>
    			<AllocationTime>2018-01-15T11:17:30Z</AllocationTime>
    			<ResourceGroupId>rg-acfmxazb4ph6aiy</ResourceGroupId>
    			<InstanceId></InstanceId>
    			<Description></Description>
    			<IpAddress>59.110.xx.xx</IpAddress>
    			<AllocationId>eip-2ze88m67qx5zxxxxx</AllocationId>
    			<InternetChargeType>PayByTraffic</InternetChargeType>
    			<InstanceType></InstanceType>
    			<Name></Name>
    			<Status>Available</Status>
    			<BandwidthPackageId></BandwidthPackageId>
    			<InstanceRegionId></InstanceRegionId>
    			<BandwidthPackageType></BandwidthPackageType>
    			<RegionId>cn-beijing</RegionId>
    			<OperationLocks></OperationLocks>
    			<ExpiredTime></ExpiredTime>
    			<AvailableRegions>
    				<AvailableRegion>cn-beijing</AvailableRegion>
    			</AvailableRegions>
            <Bandwidth>1</Bandwidth>
    		</EipAddress>
    	</EipAddresses>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    </DescribeEipAddressesResponse>
    ```


