# UnassociateGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

解绑与全球加速实例关联的后端服务实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 UnassociateGlobalAccelerationInstance

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|GlobalAccelerationInstanceId|String|是| 全球加速实例的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=UnassociateGlobalAccelerationInstance
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-t4nluhu6n417xxxxxxxx
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId": "BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<UnassociateGlobalAccelerationInstanceResponse>
    <RequestId>BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX</RequestId>
</UnassociateGlobalAccelerationInstanceResponse>
```

