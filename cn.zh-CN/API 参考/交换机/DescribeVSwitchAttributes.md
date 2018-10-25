# DescribeVSwitchAttributes {#reference_i4w_xmt_ndb2 .reference}

查询指定交换机的配置信息。

## 请求参数 {#section_cch_pjg_m22b .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVSwitchAttributes

 |
|VSwitchId|String|是| 要查询的交换机ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|RouteTable|List|交换机的路由表信息。|
|Description|String|交换机的描述。|
|IsDefault|Boolean|是否是默认交换机。|
|ZoneId|String|交换机的所属可用区。|
|AvailableIpAddressCount|Integer|可用IP数量。|
|VSwitchId|String|交换机的ID。|
|VpcId|String|交换机所属的VPC ID。|
|CidrBlock|String|交换机的私网地址范围。|
|Status|String|交换机的状态。|
|VSwitchName|String|交换机名称。|
|CreationTime|String|交换机的创建时间。|
|CloudResources|String|交换机下的云资源。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVSwitchAttributes
&RegionId=cn-hangzhou
&VSwitchId=20vsw-bp14cagpfysr29feg5t97
&公共请求参数
```

**返回示例**

**XML格式**

```
<?xml version="1.0" encoding="UTF-8" ?>
	<Description></Description>
	<ResourceGroupId></ResourceGroupId>
	<ZoneId></ZoneId>
	<VSwitchId></VSwitchId>
	<VpcId></VpcId>
	<CreationTime></CreationTime>
	<CidrBlock></CidrBlock>
	<Status></Status>
	<RequestId>7B48B4B9-1EAD-469F-B488-594DAB4B6A1A</RequestId>
	<VSwitchName></VSwitchName>
	<CloudResources></CloudResources>

```

**JSON格式**

```
{
    "Description": "", 
    "ResourceGroupId": "", 
    "ZoneId": "", 
    "VSwitchId": "", 
    "VpcId": "", 
    "CreationTime": "", 
    "CidrBlock": "", 
    "Status": "", 
    "RequestId": "7B48B4B9-1EAD-469F-B488-594DAB4B6A1A", 
    "VSwitchName": "", 
    "CloudResources": {
        "CloudResourceSetType": [ ]
    }
}
```

