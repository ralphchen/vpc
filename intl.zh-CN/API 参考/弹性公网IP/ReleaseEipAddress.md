# ReleaseEipAddress {#reference_i4w_xmt_ndb .reference}

释放指定的EIP。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ReleaseEipAddress

 |
|AllocationId|String|是| EIP的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ReleaseEipAddress
&AllocationId=eip-25877c70x
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <<?xml version="1.0" encoding="UTF-8" ?>
    <ReleaseEipAddressResponse>
        <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
    </ReleaseEipAddressResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
    }
    ```


