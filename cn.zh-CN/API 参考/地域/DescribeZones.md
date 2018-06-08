# DescribeZones {#reference_i4w_xmt_ndb .reference}

查询指定地域中可用区的列表。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeZones

 |
|RegionId|String|是| 地域的ID。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Zones|List|可用区的集合。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeZones
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeZonesResponse>
    <Zones>
        <Zone>
            <AvailableResourceCreation>
                <ResourceTypes>Instance</ResourceTypes>
                <ResourceTypes>Disk</ResourceTypes>
            </AvailableResourceCreation>
            <LocalName></LocalName>
            <ZoneId>cn-hangzhou-d</ZoneId>
            <AvailableDiskCategories>
                <DiskCategories>cloud</DiskCategories>
            </AvailableDiskCategories>
        </Zone>
        <Zone>
            <AvailableResourceCreation>
                <ResourceTypes>Instance</ResourceTypes>
                <ResourceTypes>Disk</ResourceTypes>
            </AvailableResourceCreation>
            <LocalName></LocalName>
            <ZoneId>cn-hangzhou-b</ZoneId>
            <AvailableDiskCategories>
                <DiskCategories>cloud</DiskCategories>
            </AvailableDiskCategories>
        </Zone>
    </Zones>
    <RequestId>6DB97BCC-92BA-424D-A7C8-3F6486612BAE</RequestId>
</DescribeZonesResponse>
```

JSON格式

```
{
  "RequestId": "A347EF0E-BBCC-4EFA-BD79-27AA3ACFD1BF",
  "Zones": {
    "Zone": [
      {
        "AvailableDiskCategories": {
          "DiskCategories": [
            "cloud"
          ]
        },
        "AvailableResourceCreation": {
          "ResourceTypes": [
            "Instance",
            "Disk"
          ]
        },
        "LocalName": "",
        "ZoneId": "cn-hangzhou-d"
      },
      {
        "AvailableDiskCategories": {
          "DiskCategories": [
            "cloud"
          ]
        },
        "AvailableResourceCreation": {
          "ResourceTypes": [
            "Instance",
            "Disk"
          ]
        },
        "LocalName": "",
        "ZoneId": "cn-hangzhou-b"
      }
    ]
  }
}
```

