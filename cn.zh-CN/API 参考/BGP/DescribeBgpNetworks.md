# DescribeBgpNetworks {#reference_i4w_xmt_ndb .reference}

查询已宣告的BGP网络。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeBgpNetworks

 |
|RegionId|String|是| BGP组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|dstCidrBlock|String|否| 已宣告的BGP网络。

 |
|routeId|String|否| VBR的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeBgpNetworks
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeBgpNetworksResponse>
        <BgpNetworks>
            <BgpNetwork>
                <DstCidrBlock>10.1.1.0/24</DstCidrBlock>
                <VpcId></VpcId>
            </BgpNetwork>
        </BgpNetworks>
        <RequestId>6F513A15-669F-419D-B511-08A85292059B</RequestId>
        <PageSize>10</PageSize>
        <TotalCount>1</TotalCount>
    </DescribeBgpNetworksResponse>
    ```

-   JSON格式

    ```
    {
      "BgpNetworks": {
        "BgpNetwork": [
          {
            "DstCidrBlock": "10.1.1.0/24",
            "VpcId": ""
          }
        ]
      },
      "RequestId": "6F513A15-669F-419D-B511-08A85292059B",
      "PageSize": 10,
      "TotalCount": 1
    }
    ```


