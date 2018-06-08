# DescribeAccessPoints {#reference_i4w_xmt_ndb .reference}

查询指定地域中的物理专线接入点。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeAccessPoints

 |
|RegionId|String|是| 接入点所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

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
|AccessPointSet|List|接入点信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeAccessPoints
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

JSON格式

```
{
  "AccessPointSet": {
    "AccessPointType": [
      {
        "Name": "北京-丰台-A",
        "Status": "recommended",
        "Description": "cn-beijing-ft-cxp32",
        "Type": "VPC",
        "Location": "",
        "HostOperator": "皓宽",
        "AttachedRegionNo": "cn-beijing",
        "AccessPointId": "ap-cn-beijing-ft-A"
      },
      {
        "Name": "北京-亦庄-A",
        "Status": "recommended",
        "Description": "cn-beijing-yz-ne203",
        "Type": "VPC",
        "Location": "",
        "HostOperator": "世纪互联",
        "AttachedRegionNo": "cn-beijing",
        "AccessPointId": "ap-cn-beijing-yz-A"
      },
      {
        "Name": "北京-大兴-B",
        "Status": "recommended",
        "Description": "cn-beijing-dx-nu16",
        "Type": "VPC",
        "Location": "",
        "HostOperator": "中国联通",
        "AttachedRegionNo": "cn-beijing",
        "AccessPointId": "ap-cn-beijing-dx-B"
      },
      {
        "Name": "北京-昌平-A",
        "Status": "recommended",
        "Description": "ap-cn-beijing-cp-CM12",
        "Type": "VPC",
        "Location": "",
        "HostOperator": "中国电信",
        "AttachedRegionNo": "cn-beijing",
        "AccessPointId": "ap-cn-beijing-cp-A"
      },
      {
        "Name": "北京-大兴-A",
        "Status": "recommended",
        "Description": "cn-beijing-dx-nu17-a",
        "Type": "VPC",
        "Location": "",
        "HostOperator": "GDS",
        "AttachedRegionNo": "cn-beijing",
        "AccessPointId": "ap-cn-beijing-dx-A"
      }
    ]
  },
  "PageNumber": 1,
  "TotalCount": 5,
  "PageSize": 10,
  "RequestId": "3E85D803-C7CF-4BCD-9CFE-6DBA1DFFA027"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
</DescribeAccessPointsResponse>	
	<AccessPointSet>
		<AccessPointType>
			<Name>北京-丰台-A</Name>
			<Status>recommended</Status>
			<Description>cn-beijing-ft-cxp32</Description>
			<Type>VPC</Type>
			<Location></Location>
			<HostOperator>xxx</HostOperator>
			<AttachedRegionNo>cn-beijing</AttachedRegionNo>
			<AccessPointId>ap-cn-beijing-ft-A</AccessPointId>
		</AccessPointType>
		<AccessPointType>
			<Name>北京-亦庄-A</Name>
			<Status>recommended</Status>
			<Description>cn-beijing-yz-ne203</Description>
			<Type>VPC</Type>
			<Location></Location>
			<HostOperator>xxx</HostOperator>
			<AttachedRegionNo>cn-beijing</AttachedRegionNo>
			<AccessPointId>ap-cn-beijing-yz-A</AccessPointId>
		</AccessPointType>
		<AccessPointType>
			<Name>北京-大兴-B</Name>
			<Status>recommended</Status>
			<Description>cn-beijing-dx-nu16</Description>
			<Type>VPC</Type>
			<Location></Location>
			<HostOperator>中国联通</HostOperator>
			<AttachedRegionNo>cn-beijing</AttachedRegionNo>
			<AccessPointId>ap-cn-beijing-dx-B</AccessPointId>
		</AccessPointType>
		<AccessPointType>
			<Name>北京-昌平-A</Name>
			<Status>recommended</Status>
			<Description>ap-cn-beijing-cp-CM12</Description>
			<Type>VPC</Type>
			<Location></Location>
			<HostOperator>中国电信</HostOperator>
			<AttachedRegionNo>cn-beijing</AttachedRegionNo>
			<AccessPointId>ap-cn-beijing-cp-A</AccessPointId>
		</AccessPointType>
		<AccessPointType>
			<Name>北京-大兴-A</Name>
			<Status>recommended</Status>
			<Description>cn-beijing-dx-nu17-a</Description>
			<Type>VPC</Type>
			<Location></Location>
			<HostOperator>GDS</HostOperator>
			<AttachedRegionNo>cn-beijing</AttachedRegionNo>
			<AccessPointId>ap-cn-beijing-dx-A</AccessPointId>
		</AccessPointType>
	</AccessPointSet>
	<PageNumber>1</PageNumber>
	<TotalCount>5</TotalCount>
	<PageSize>10</PageSize>
	<RequestId>3E85D803-C7CF-4BCD-9CFE-6DBA1DFFA027</RequestId>
</DescribeAccessPointsResponse>
```

