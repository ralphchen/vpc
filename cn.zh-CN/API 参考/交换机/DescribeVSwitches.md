# DescribeVSwitches {#reference_i4w_xmt_ndb .reference}

查询已创建的交换机。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVSwitches

 |
|RegionId|String|是| 交换机所属VPC所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|VpcId|String|否| VPC的ID。

 |
|ZoneId|String|否| 交换机所属区的ID。

 您可以通过调用 DescribeZones接口获取地域ID。

 |
|VSwitchId|String|否| 交换机的ID。

 |
|IsDefault|Boolean|否| 是否查询指定地域下的默认交换机，取值：

 -   true（默认值）：查询指定地域下的所有交换机。
-   false：不查询默认交换机。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|VSwitches|JSON String|交换机的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|VpcId|String|交换机所属VPC的ID。|
|VSwitchId|String|交换机的ID。|
|Status|String|交换机的状态，取值：-   Pending：配置中

-   Available：可用


|
|CidrBlock|String|交换机的网段。|
|ZoneId|String|交换机所在的可用区。|
|AvailableIpAddressCount|Integer|交换机中可用的IP地址数量。|
|VSwitchName|String|交换机的名称。|
|Description|String|交换机的描述信息。|
|CreationTime|String|交换机的创建时间。|
|IsDefault|Boolean|是否是该可用区的默认交换机。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVSwitches
&VpcId=vpc-25eq58pl3
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeVSwitchesResponse>
        <RequestId>9A572171-4E27-40D1-BD36-D26C9E71E29E</RequestId>
        <VSwitches>
            <VSwitch>
                <VSwitchId> vsw-25b7pv15t </VSwitchId>
                <Status>Available</Status>
                <CidrBlock>172.16.1.0/24</CidrBlock>
                <ZoneId>cn-beijing-a</ZoneId>
                <AvailableIpAddressCount>246</AvailableIpAddressCount>
                <VpcId>vpc-257gq642n</VpcId>
                <Description></Description>
                <VSwitchName></VSwitchName>
                <CreationTime> 2014-10-29T15:21:02Z </CreationTime>
            </VSwitch>
        </VSwitches>
    </DescribeVSwitchesResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "PageSize": 10,
      "RequestId": "9A572171-4E27-40D1-BD36-D26C9E71E29E",
      "TotalCount": 1,
      "VSwitches": {
        "VSwitch": [
          {
            "AvailableIpAddressCount": 246,
            "CidrBlock": "172.16.1.0/24",
            "CreationTime": "2014-10-29T15:21:02Z",
            "Description": "",
            "Status": "Available",
            "VSwitchId": "vsw-25b7pv15t",
            "VSwitchName": "",
            "VpcId": "vpc-257gq642n",
            "ZoneId": "cn-beijing-a"
          }
        ]
      }
    }
    ```


