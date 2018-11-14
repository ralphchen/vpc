# ModifyRouteTableAttributes {#reference_i4w_xmt_ndb .reference}

 修改路由表的名称和描述。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyRouteTableAttributes

 |
|RegionId|String|是| 路由表所属的VPC的地域ID。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouteTableId|String|是|路由表的ID。|
|RouteTableName|String|否| 路由表的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 路由表的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyRouteTableAttributes
&RegionId=cn-qingdao
&RouteTableName=myRouteTable
&RouteTableId=vtb-m5evbtbptnxxxxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyRouteTableAttributesResponse>
        <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxx</RequestId>
    </ModifyRouteTableAttributesResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx"
    }
    ```


