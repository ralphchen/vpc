# CreateGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

创建全球加速实例。

**说明：** 本接口只支持创建后付费的全球加速实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateGlobalAccelerationInstance

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ServiceLocation|String|是| 被加速的服务的所属区域。取值：

-   china-mainland：中国大陆

-   north-america：北美

-   asia-pacific：亚太

-   europe：欧洲


 |
|Bandwidth|Integer|是| 全球加速实例的带宽峰值，单位为Mbps。取值范围：\[10,20,30,40,50,60,70,80,90,100,200,300,400,500,600,700,800,900,1000\]

 |
|Name|String|否| 全球加速实例的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 全球加速实例的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|GlobalAccelerationInstanceId|String|全球加速实例的ID。|
|IpAddress|String|全球加速实例的公网IP地址。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateGlobalAccelerationInstance
&RegionId=ap-southeast-1
&Bandwidth=10
&Name=MyGa
&Description=firstGlobalAcceleration
&ServiceLocation=asia-pacific
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "GlobalAccelerationInstanceId": "ga-t4nluhu6",
    "IpAddress": "12.34.56.78",
    "RequestId": "21AAFD16-F784-4BFB-XXXX-XXXXXXXX"
 }
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<CreateGlobalAccelerationInstanceResponse>
	<GlobalAccelerationInstanceId>ga-t4nluhu6</GlobalAccelerationInstanceId>
	<IpAddress>12.34.56.78</IpAddress>
	<RequestId>21AAFD16-F784-4BFB-XXXX-XXXXXXXX</RequestId>
</CreateGlobalAccelerationInstanceResponse>
```

