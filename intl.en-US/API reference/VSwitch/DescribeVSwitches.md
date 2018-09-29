# DescribeVSwitches {#reference_i4w_xmt_ndb .reference}

Query the created VSwitches.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DescribeVSwitches

 |
|RegionId|String|Yes| The region of the VPC to which the VSwitch belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpcId|String|No| The ID of the VPC.

 |
|ZoneId|String|No| The ID of the zone to which the VSwitch belongs.

 You can obtain the region ID by calling the DescribeZones API.

 |
|VSwitchId|String|No| The ID of the VSwitch.

 |
|Isdefault|Boolean |No| Whether to query the default VSwitch in the specified region. 

 -   true \(default value\): Query all VSwitches in the specified region.
-   false: Do not query the default VSwitch.

 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize|Integer|No| The number of rows per page. The maximum value is 50 and the the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of rows per page.|
|Vswitches|List|A list of VSwitches.|

|Name|Type|Description|
|:---|:---|:----------|
|VpcId|String|The ID of the VPC to which the VSwitch belongs.|
|VSwitchId|String|The ID of the VSwitch.|
|Status|String|The status of the VSwitch. Valid value:-   Pending: configuring

-   Available: available


|
|CidrBlock|String|The CIDR block of the VSwitch.|
|ZoneId|String|The zone of the VSwitch.|
|AvailableIpAddressCount|Integer|The number of available IP addresses in the VSwitch.|
|VSwitchName|String|The name of the VSwitch.|
|Description|String|The description of the VSwitch.|
|CreationTime|String|The time when the switch was created.|
|IsDefault|Boolean|Whether the VSwitch is the default VSwitch in the zone.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVSwitches
&VpcId=vpc-25eq58pl3
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
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

-   JSON format

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
            "Cidrblock": 17. 0. 0/24 ",
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


