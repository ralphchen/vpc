# DescribeRegions {#reference_i4w_xmt_ndb .reference}

查询可用地域。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeRegions

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Regions|List|可用地域的集合。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeRegions
&公共请求参数
```

**返回示例**

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeRegionsResponse>
    <RequestId>611CB80C-B6A9-43DB-9E38-0B0AC3D9B58F</RequestId>
    <Regions>
        <Region>
            <RegionId>cn-hangzhou </RegionId>
        </Region>
        <Region>
            <RegionId>cn-qingdao</RegionId>
        </Region>
    </Regions>
</DescribeRegionsResponse>
```

JSON格式

```
{
    "RequestId": "611CB80C-B6A9-43DB-9E38-0B0AC3D9B58F", 
    "Regions": {
        "Region": [
            {
                "RegionId": "cn-hangzhou "
            }, 
            {
                "RegionId": "cn-qingdao"
            }
        ]
    }
}
```

