# DescribeVpcs {#reference_i4w_xmt_ndb .reference}

Query the created VPCs in a region.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVpcs

 |
|RegionId|String|No| The region where the VPC is located.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpcId|String|No| The ID of the VPC.

 Up to 20 VPCs can be specified. Separate multiple VPCs using commas.

 |
|Isdefault|Boolean |No| Whether to query the default VPC in the specified region. Valid value:

 -   true  \(Default\): Query all VPCs in the specified region.
-   false: Do not query the default VPC.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of entries on the current page.|
|Vpcs|JSON string|The detailed information of the VPC.|

|Name|Type|Description|
|:---|:---|:----------|
|VpcId|String|The ID of the VPC.|
|RegionId|String|The region where the VPC is located.|
|Status|String|The status of the VPC. Valid value:-   Pending: configuring
-   Available: available

|
|VpcName|String|The name of the VPC.|
|VSwitchIds|String|A list of VSwitches in the VPC.|
|CidrBlock|String|The CIDR block of the VPC.|
|VRouterId|String|The ID of the VRouter.|
|Description|String|The description of the VPC.|
|CreationTime|String|The time when the VPC is created.|
|IsDefault|Boolean|Whether the VPC is the default VPC in the region.|
|UserCidrs|String|A list of customer-side CIDR blocks.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVpcs
&RegionId=us-west-1
&CidrBlock=10.10.0.0/24
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <RouteTableId>vtb-bp145q7glnuzdvzu21pom</RouteTableId>
        <VRouterId>vrt-bp1lhl0taikrteen80oxx</VRouterId>
        <VpcId>vpc-bp15zckdt37pq72zvw3</VpcId>
    </CreateVpcResponse>
    ```

-   JSON format

    ```
    {
        "PageNumber": 1, 
        "Vpcs": {
            "VPC ":[
                {
                    "VpcName": "vpc1", 
                    "Description": "", 
                    "IsDefault": false, 
                    "ResourceGroupId": "rg-acfmxazb4ph6aiy", 
                    "UserCidrs": {
                        "UserCidr": [ ]
                    }, 
                    "NatGatewayIds": {
                        "NatGatewayIds": [ ]
                    }, 
                    "RouterTableIds": {
                        "RouterTableIds": [
                            "vtb-bp145q7glnuzdvzu21pom"
                        ]
                    }, 
                    "VpcId": "vpc-bp15zckdt37pq72zvw30k", 
                    "VRouterId": "vrt-bp1lhl0taikrteen80oxx", 
                    "CreationTime": "2018-04-18T15:02:37Z", 
                    "Status": "Available", 
                    "CidrBlock": "10.0.0.0/24", 
                    "Vswitchids ":{
                        "VSwitchId": [ ]
                    }, 
                    "RegionId": "cn-hangzhou"
                }
            ]
        }, 
        "TotalCount": 1, 
        "PageSize": 10, 
        "RequestId": "9B941224-B647-4644-A746-641906D6B954"
    }
    ```


