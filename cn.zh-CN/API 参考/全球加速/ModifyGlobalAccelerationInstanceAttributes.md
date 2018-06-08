# ModifyGlobalAccelerationInstanceAttributes {#reference_i4w_xmt_ndb .reference}

修改全球加速实例的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyGlobalAccelerationInstanceAttributes

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|GlobalAccelerationInstanceId|String|是| 全球加速实例的ID。

 |
|Name|String|否| 全球加速实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 全球加速实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyGlobalAccelerationInstanceAttributes 
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-t4nluhu6n4xxxxxxxxxx
&Name=AdjustName
&Description=ModifyDescription
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
<ModifyGlobalAccelerationInstanceAttributesResponse>
    <RequestId>185E81B1-3916-4667-B48F-C52409B33F2B</RequestId>
</ModifyGlobalAccelerationInstanceAttributesResponse>
```

