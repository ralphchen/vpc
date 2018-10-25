# DescribeVpcAttribute {#reference_wkg_tqt_4fb .reference}

查询指定VPC的配置信息。

## 请求参数 {#section_mrw_vqt_4fb .section}

|名称|类型|是否必须|描述|
|--|--|----|--|
|Action|String|是|要执行的操作。 取值：DescribeVpcAttribute|
|VpcId|String|是|要查询的VPC ID。|
|RegionId|String|是|VPC的所属地域ID。|
|IsDefault|Boolean|否|是否是默认VPC，取值：-   false：不是默认VPC
-   true：是默认VPC

|

## 返回参数 {#section_c5z_nrt_4fb .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|请求ID。|
|VpcName|String|VPC的名称。|
|Description|String|VPC的描述。|
|IsDefault|Boolean|是否是默认VPC。|
|VRouterId|String|VPC的路由器ID。|
|VpcId|String|VPC ID。|
|CidrBlock|String|VPC的私网网段。|
|VSwitchIds|List|VPC下的交换机列表。|
|Status|String|VPC的状态。|
|CreationTime|String|VPC的创建时间。|
|CloudResources|List|VPC下的资源列表。|

## 示例 {#section_zvp_gtt_4fb .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVpcAttribute
&RegionId=cn-hangzhou
&VpcId=vpc-bp18sth14qii3pnvodkvt
&公共请求参数
```

**返回示例**

-   **XML格式**

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    	<VpcName>doctest2</VpcName>
    	<Description></Description>
    	<IsDefault>false</IsDefault>
    	<ResourceGroupId>rg-acfmxazb4ph6aiy</ResourceGroupId>
    	<UserCidrs></UserCidrs>
    	<ClassicLinkEnabled>false</ClassicLinkEnabled>
    	<AssociatedCens>
    		<AssociatedCen>
    			<CenStatus>Attached</CenStatus>
    			<CenOwnerId>1231579085529123</CenOwnerId>
    			<CenId>cen-7qthudw0ll6jmc4gsu</CenId>
    		</AssociatedCen>
    	</AssociatedCens>
    	<VRouterId>vrt-bp1jso6ng1at0ajsc8mbe</VRouterId>
    	<VpcId>vpc-bp18sth14qii3pnvodkvt</VpcId>
    	<CreationTime>2018-10-16T07:31:09Z</CreationTime>
    	<CidrBlock>192.168.0.0/16</CidrBlock>
    	<Status>Available</Status>
    	<VSwitchIds>
    		<VSwitchId>vsw-bp14cagpfysr29feg5t97</VSwitchId>
    	</VSwitchIds>
    	<RequestId>7486AE4A-129D-43DB-A714-2432C074BA04</RequestId>
    	<RegionId>cn-hangzhou</RegionId>
    	<CloudResources>
    		<CloudResourceSetType>
    			<ResourceType>VSwitch</ResourceType>
    			<ResourceCount>1</ResourceCount>
    		</CloudResourceSetType>
    		<CloudResourceSetType>
    			<ResourceType>VRouter</ResourceType>
    			<ResourceCount>1</ResourceCount>
    		</CloudResourceSetType>
    		<CloudResourceSetType>
    			<ResourceType>RouteTable</ResourceType>
    			<ResourceCount>1</ResourceCount>
    		</CloudResourceSetType>
    	</CloudResources>
    ```

-   **JSON格式**

    ```
    {
        "VpcName": "doctest2", 
        "Description": "", 
        "IsDefault": false, 
        "ResourceGroupId": "rg-acfmxazb4ph6aiy", 
        "UserCidrs": {
            "UserCidr": [ ]
        }, 
        "ClassicLinkEnabled": false, 
        "AssociatedCens": {
            "AssociatedCen": [
                {
                    "CenStatus": "Attached", 
                    "CenOwnerId": "1231579085529123", 
                    "CenId": "cen-7qthudw0ll6jmc4gsu"
                }
            ]
        }, 
        "VRouterId": "vrt-bp1jso6ng1at0ajsc8mbe", 
        "VpcId": "vpc-bp18sth14qii3pnvodkvt", 
        "CreationTime": "2018-10-16T07:31:09Z", 
        "CidrBlock": "192.168.0.0/16", 
        "Status": "Available", 
        "VSwitchIds": {
            "VSwitchId": [
                "vsw-bp14cagpfysr29feg5t97"
            ]
        }, 
        "RequestId": "7486AE4A-129D-43DB-A714-2432C074BA04", 
        "RegionId": "cn-hangzhou", 
        "CloudResources": {
            "CloudResourceSetType": [
                {
                    "ResourceType": "VSwitch", 
                    "ResourceCount": 1
                }, 
                {
                    "ResourceType": "VRouter", 
                    "ResourceCount": 1
                }, 
                {
                    "ResourceType": "RouteTable", 
                    "ResourceCount": 1
                }
            ]
        }
    }
    ```


