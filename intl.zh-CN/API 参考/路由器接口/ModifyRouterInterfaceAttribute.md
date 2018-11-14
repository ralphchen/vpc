# ModifyRouterInterfaceAttribute {#reference_i4w_xmt_ndb .reference}

修改路由器接口的配置。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyRouterInterfaceAttribute

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouterInterfaceId|String|是| 路由器接口的ID。

 |
|AccessPointId|String|否| VBR所属的接入点ID。

 您可以通过调用 DescribeAccessPoints接口获取物理专线接入点ID。

 **说明：** 物理专线接入场景下需指定该参数。

 |
|RouterId|String|是| 路由器接口关联的路由器ID。

 |
|DeleteHealthCheckIp|Boolean|否| 是否删除该路由器接口上配置的健康检查IP。取值：

 -   true：删除健康检查IP。

-   false（默认值）：不删除健康检查IP。


 |
|OppositeRouterId|String|否| 对端的路由器的ID。

 |
|OppositeInterfaceId|String|否| 对端路由器接口ID。

 |
|OppositeInterfaceOwnerId|String|否| 对端路由器接口的所有者ID。

 |
|HealthCheckSourceIp|String|否| 健康检查源IP地址，必须是本端VPC内的一个未被使用的IP。

 **说明：** 物理专线接入场景下可指定该参数。

 |
|HealthCheckTargetIp|String|否| 健康检查目的IP地址。

 **说明：** 该参数为必选，当指定了HealthCheckSourceIp后。

 |
|Name|String|否| 路由器接口的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 路由器接口的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyRouterInterfaceAttribute
&Name=test
&RouterInterfaceId=ri-2ze7fbuohm7pc3ybei8nv
&RegionId=cn-hangzhou
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyRouterInterfaceAttributeResponse>
        <RequestId>980960B0-2969-40BF-8542-EBB34FD358AB</RequestId>
    </ModifyRouterInterfaceAttributeResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "980960B0-2969-40BF-8542-EBB34FD358AB"
    }
    ```


