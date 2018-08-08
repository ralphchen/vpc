# DescribeEipAddresses {#reference_i4w_xmt_ndb .reference}

查询指定地域已创建的EIP。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeEipAddresses

 |
|RegionId|String|是| EIP所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Status|String|否| EIP的状态：

-   Associating：绑定中

-   Unassociating：解绑中

-   InUse：已分配

-   vailable：可用


 |
|AllocationId|String|否| EIP的ID。

 |
|AssociatedInstanceType|String|否| 要绑定的云产品实例的类型，取值：

 -   EcsInstance（默认值）：VPC类型的ECS实例

-   SlbInstance：VPC类型的SLB实例

-   Nat：NAT网关

-   HaVip：HAVIP


 每个ECS实例、负载均衡实例和HAVIP同时只能绑定一个EIP，NAT网关可以绑定多个EIP。

 |
|AssociatedInstanceId|String|否| 云产品的实例ID。

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
|EipAddresses|List|EIP的详细信息。|

|名称|类型|描述|
|--|--|--|
|RegionId|String|EIP所在的地域。|
|IpAddress|String|EIP的地址。|
|AllocationId|String|EIP的ID。|
|Status|String| EIP的状态：

-   Associating：绑定中

-   Unassociating：解绑中

-   InUse：已分配

-   Available：可用


 |
|InstanceType|String|当前绑定的实例类型。|
|InstanceId|String|当前绑定的实例的ID。|
|Bandwidth|String|EIP的带宽峰值，单位为Mbps。|
|InternetChargeType|String|EIP的计费方式。|
|AllocationTime|String|EIP的创建时间。|
|OperationLocks|String|被锁定的原因，取值：-   financial：因欠费被锁定

-   security：因安全原因被锁定


|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou-1
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
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


