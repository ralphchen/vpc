# AssociateGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

绑定后端服务实例。

调用本接口绑定后端服务实例时，请注意：

-   仅支持专有网络类型的ECS实例和负载均衡实例作为全球加速实例的后端服务实例。

-   一个全球加速实例只能添加一个后端服务实例。

-   多个全球加速实例可以绑定同一个后端服务实例。

-   后端服务实例和全球加速实例需要属于同一个云账号。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AssociateGlobalAccelerationInstance

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|GlobalAccelerationInstanceId|String|是| 全球加速实例的ID。

 |
|BackendServerRegionId|String|是| 后端服务实例所属的地域，该地域需要属于全球加速实例指定的服务区域。

 |
|BackendServerType|String|否| 后端服务实例的类型，取值：

 -   EcsInstance（默认值）：ECS实例
-   SlbInstance：负载均衡实例

 |
|BackendServerId|String|是| 后端服务实例的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AssociateGlobalAccelerationInstance 
&RegionId=ap-southeast-1
&GlobalAccelerationInstanceId=ga-aabbccddaabb
&BackendServerRegionId=ap-northeast-1
&BackendServerId=i-6we1ge5qfxxxxxx
&BackendServerType=EcsInstance
&公共请求参数
```

**返回示例**

JSON格式

```
{
    "RequestId": "DDF2CC38-76C7-4000-909D-B2088158AEDA"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<AssociateGlobalAccelerationInstanceResponse>
    <RequestId>DDF2CC38-76C7-4000-909D-B2088158AEDA</RequestId>
</AssociateGlobalAccelerationInstanceResponse>
```

