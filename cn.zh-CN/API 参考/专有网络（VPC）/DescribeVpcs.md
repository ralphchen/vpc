# DescribeVpcs {#reference_i4w_xmt_ndb .reference}

查询已创建的VPC。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVpcs

 |
|RegionId|String|否| VPC所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpcId|String|否| VPC的ID。

 最多支持指定20个VPC ID，多个VPC的ID之间用半角逗号隔开。

 |
|IsDefault|Boolean|否| 是否查询指定地域下的默认VPC，取值：

 -   true（默认值）：查询指定地域下的所有VPC。
-   false：不查询默认VPC。

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
|Vpcs|JSON String|VPC的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|VpcId|String|VPC的ID。|
|RegionId|String|VPC所在的地域。|
|Status|String|VPC的状态，取值：-   Pending：配置中
-   Available：可用

|
|VpcName|String|VPC的名称。|
|VSwitchIds|String|VPC中交换机的列表。|
|CidrBlock|String|VPC的网段。|
|VRouterId|String|VPC路由器的ID。|
|Description|String|VPC的描述信息。|
|CreationTime|String|VPC的创建时间。|
|IsDefault|Boolean|是否在当是地域的默认VPC。|
|UserCidrs|String|用户侧网段的列表。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVpcs
&RegionId=us-west-1
&CidrBlock=10.10.0.0/24
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <RouteTableId>vtb-bp145q7glnuzdvzu21pom</RouteTableId>
        <VRouterId>vrt-bp1lhl0taikrteen80oxx</VRouterId>
        <VpcId>vpc-bp15zckdt37pq72zvw3</VpcId>
    </CreateVpcResponse>
    ```

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "Vpcs": {
            "Vpc": [
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
                    "VSwitchIds": {
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


