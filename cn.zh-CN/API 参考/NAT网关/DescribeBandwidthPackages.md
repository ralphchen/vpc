# DescribeBandwidthPackages {#reference_i4w_xmt_ndb .reference}

查询指定地域的NAT带宽包。

**说明：** 本接口仅支持在2017年11月3日之前账号下存在NAT带宽包的用户调用。2017年11月3日之前账号下不存在NAT带宽包的用户，请绑定EIP，详情参见[AssociateEipAddress](cn.zh-CN/API 参考/NAT网关/AssociateEipAddress.md#)。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeBandwidthPackages

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|否| NAT网关的ID。

 |
|BandwidthPackageId|String|否| NAT网关带宽包的ID。

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
|BandwidthPackages|List|NAT带宽包的详细信息，详情参见[表 1](#table_rn4_qyb_pdb)。|

|名称|类型|描述|
|:-|:-|:-|
|BandwidthPackageId|String| NAT带宽包的ID。

 |
|RegionId|String| NAT带宽包的ID。

 |
|Description|Integer| NAT带宽包的描述信息。

 |
|Name|String| NAT带宽包的名称。

 |
|ZoneId|String| NAT带宽包所在的可用区。

 |
|GatewayId|String| NAT网关的ID。

 |
|Bandwidth |String|NAT带宽包的带宽，单位为Mbps。|
|SnatTableIds |List|SNAT列表。|
|InstanceChargeType |String|NAT带宽包的付费方式，取值：PostPaid。|
|InternetChargeType |String|NAT带宽包的计费方式，取值：PayByBandwidth。|
|BusinessStatus |String|NAT带宽包的付费状态，取值：-   Normal：正常

-   FinancialLocked：欠费锁定

-   SecurityLocked：因安全原因被锁定


|
|CreationTime |String| NAT带宽包的创建时间。

 |
|ISP |String| NAT带宽包的运营商类型，取值：BGP

 |
|PublicIpAddresses |String| NAT带宽包的公网IP列表，详情参见[表 2](#table_znm_frc_pdb)

 |
|CreationTime |String| NAT带宽包的创建时间。

 |

|名称|类型|描述|
|:-|:-|:-|
|AllocationId|String| 公网IP的ID。

 |
|IpAddress|String| 公网IP地址。

 |

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBandwidthPackages
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <DescribeBandwidthPackagesResponse>
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<BandwidthPackages>
    		<BandwidthPackage>
    			<Description></Description>
    			<IpCount>2</IpCount>
    			<ISP>BGP</ISP>
    			<ZoneId>cn-hangzhou-b</ZoneId>
    			<InternetChargeType>PayByTraffic</InternetChargeType>
    			<NatGatewayId>ngw-bp1uewa15k4iy5770ya89</NatGatewayId>
    			<Name></Name>
    			<CreationTime>2018-03-06T07:33:51Z</CreationTime>
    			<Status>Available</Status>
    			<BandwidthPackageId>bwp-bp1xea10o8qxw8lkw2xa1</BandwidthPackageId>
    			<BusinessStatus>Normal</BusinessStatus>
    			<RegionId>cn-hangzhou</RegionId>
    			<InstanceChargeType>PostPaid</InstanceChargeType>
    			<PublicIpAddresses>
    				<PublicIpAddresse>
    					<IpAddress>118.31.xx.xx</IpAddress>
    					<AllocationId>nateip-bp1jb1uijvm9o8z30ejqp</AllocationId>
    					<UsingStatus>Idle</UsingStatus>
    				</PublicIpAddresse>
    				<PublicIpAddresse>
    					<IpAddress>118.31.xx.xx</IpAddress>
    					<AllocationId>nateip-bp1dt4hpe8847yj4oh10w</AllocationId>
    					<UsingStatus>UsedBySnatTable</UsingStatus>
    				</PublicIpAddresse>
    			</PublicIpAddresses>
    			<Bandwidth>5</Bandwidth>
    		</BandwidthPackage>
    	</BandwidthPackages>
    	<PageSize>10</PageSize>
    </DescribeBandwidthPackagesResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "TotalCount": 1,
      "BandwidthPackages": {
        "BandwidthPackage": [
          {
            "Description": "",
            "IpCount": "2",
            "ISP": "BGP",
            "ZoneId": "cn-hangzhou-b",
            "InternetChargeType": "PayByTraffic",
            "NatGatewayId": "ngw-bp1uewa15k4iy5770ya89",
            "Name": "",
            "CreationTime": "2018-03-06T07:33:51Z",
            "Status": "Available",
            "BandwidthPackageId": "bwp-bp1xea10o8qxw8lkw2xa1",
            "BusinessStatus": "Normal",
            "RegionId": "cn-hangzhou",
            "InstanceChargeType": "PostPaid",
            "PublicIpAddresses": {
              "PublicIpAddresse": [
                {
                  "IpAddress": "118.31.xx.xx",
                  "AllocationId": "nateip-bp1jb1uijvm9o8z30ejqp",
                  "UsingStatus": "Idle"
                },
                {
                  "IpAddress": "118.31.xx.xx",
                  "AllocationId": "nateip-bp1dt4hpe8847yj4oh10w",
                  "UsingStatus": "UsedBySnatTable"
                }
              ]
            },
            "Bandwidth": "5"
          }
        ]
      },
      "PageSize": 10,
      "RequestId": "8909013D-4A64-41A6-93E6-E3FD08A3EAFE"
    }
    ```


