# DescribeNatGateways {#reference_i4w_xmt_ndb .reference}

查询已创建的NAT网关。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeNatGateways

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|否| NAT网关的ID。

 |
|VpcId|String|否| VPC的ID。

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
|NatGateways|List|NAT网关的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|NatGatewayId|String| NAT网关所在地域。

 |
|RegionId|String| NAT网关的ID。

 |
|Description|Integer| NAT网关的描述信息。

 |
|Spec|String| NAT网关的规格。

 |
|Status|String| NAT的网关的状态，取值：

-   Initiating：初始化中

-   Available：可用

-   Pending：配置中


 |
|ForwardTableIds|List| DNAT列表。

 |
|BandwidthPackageIds |List|NAT带宽包列表。|
|SnatTableIds |List|SNAT列表。|
|InstanceChargeType |String|NAT网关的付费方式。|
|BusinessStatus |String|NAT网关的付费状态，取值：-   Normal：正常

-   FinancialLocked：欠费锁定

-   SecurityLocked：因安全原因被锁定


|
|CreationTime |String| NAT网关的创建时间。

 |

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeNatGateways
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
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

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "1207C80C-7CAB-4874-A9A0-D19EC9F35490", 
        "NatGateways": {
            "NatGateway": [ 
                {
                    "Description": "", 
                    "Spec": "Small", 
                    "IpLists": {
                        "IpList": [
                            {
                                "IpAddress": "118.31.65.181", 
                                "AllocationId": "eip-bp1xyg5ipmh3nledxywxf", 
                                "UsingStatus": "UsedBySnatTable"
                            }, 
                            {
                                "IpAddress": "47.97.187.34", 
                                "AllocationId": "eip-bp19eue77u20cffjcu4ea", 
                                "UsingStatus": "UsedByForwardTable"
                            }
                        ]
                    }, 
                    "ForwardTableIds": {
                        "ForwardTableId": [
                            "ftb-bp15o9aylj19vfvgtnzoy"
                        ]
                    }, 
                    "VpcId": "vpc-bp15k6sx6fhdz2jw4daz0", 
                    "NatGatewayId": "ngw-bp1047e2d4z7kf2kiy25t", 
                    "CreationTime": "2018-01-10T09:48:29Z", 
                    "BandwidthPackageIds": {
                        "BandwidthPackageId": [ ]
                    }, 
                    "Name": "", 
                    "Status": "Available", 
                    "BusinessStatus": "Normal", 
                    "RegionId": "cn-hangzhou", 
                    "SnatTableIds": {
                        "SnatTableId": [
                            "stb-bp1tyr0o48w6wymur4gvn"
                        ]
                    }, 
                    "InstanceChargeType": "PostPaid"
                }
            ]
        }
    }
    ```


