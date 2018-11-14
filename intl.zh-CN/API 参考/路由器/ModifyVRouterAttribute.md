# ModifyVRouterAttribute {#reference_i4w_xmt_ndb .reference}

修改路由器的名称和描述信息。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyVRouterAttribute

 |
|VRouterId|String|是| 路由器的ID。

 |
|VRouterName|String|否| 路由器的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 路由器的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyVRouterAttribute
&VRouterId=vrt-25bezkd03
&VRouterName=VRouter
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyVRouterAttributeResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </ModifyVRouterAttributeResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "RouteTableId": "vtb-bp145q7glnuzdvzu21pom", 
        "VRouterId": "vrt-bp1lhl0taikrteen80oxx", 
        "VpcId": "vpc-bp15zckdt37pq72zvw30k"
    }
    ```


