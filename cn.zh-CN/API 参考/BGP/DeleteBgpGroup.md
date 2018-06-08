# DeleteBgpGroup {#reference_i4w_xmt_ndb .reference}

删除指定的BGP组。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteBgpGroup

 |
|RegionId|String|是| BGP组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BgpGroupId|String|是| BGP组的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteBgpGroup
&RegionId=cn-beijing
&BgpGroupId=bgpg-2zendnzngq9lkjkhvlrsr
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteBgpGroupResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteBgpGroupResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


