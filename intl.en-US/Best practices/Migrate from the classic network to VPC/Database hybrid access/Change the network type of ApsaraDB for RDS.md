# Change the network type of ApsaraDB for RDS {#concept_xnk_1w5_sdb .concept}

This document describes how to switch the network type of an ApsaraDB for RDS instance to a VPC network through the console and API while preserving the classic network endpoint.

For more information, see [Migrate from the classic network to VPC](https://help.aliyun.com/document_detail/57978.html).

**Note:** 

-   The classic network endpoint has a retention time limit. You can specify a retention period as needed. When the retention time is reached, the classic network endpoint is automatically deleted by the system. Before the endpoint is deleted, you will receive a message.

-   If the RDS instance is a split table of a DRDS instance, the network connection between the DRDS and the RDS instances will be interrupted and you must reconnect them.


## Prerequisites {#section_vcx_2w5_sdb .section}

-   The access mode of the instance is the safe connection mode. For more information, see . MySQL 5.7, SQL Server 2012, and SQL Server 2016 version only support the standard mode. This mode supports changing the network type.

-   The network type is the classic network.

-   There are available VPC and VSwitches in the zone where the RDS instance is located. For more information, see [Manage a VPC](../../../../reseller.en-US/User Guide/Manage a VPC.md#).


## Change the network type on the console {#section_p5v_fw5_sdb .section}

1.  Log on to the RDS Management Console.
2.  Select the region of the target instance.
3.  Click the ID of the target instance.
4.  In the left-side navigation pane, select **Database Connection**.
5.  In the Instance Connection tab, click **Switch to VPC**.
6.  On the Switch to VPC page, select the VPC and VSwitch where the RDS instance is located.
7.  Select the **Reserve original classic endpoint** check box, and select an **Expiration time**.

    -   From the 7th day before the classic network endpoint is deleted, the system will send a reminder message to the mobile phone bound to your account every day.

    -   When the retention time of the classic network endpoint expires, the classic network endpoint will be automatically released, and you will not be able to access the database through the classic network endpoint. To prevent service interruption, set the retention time according to your needs. After the hybrid access configuration is complete, you can change the expiration time.

8.  Click **OK**. A **Retained Connection Address of the Classic Network** is added on the console.

    ![](images/842_en-US.png)


## Modify the retention time {#section_pnk_cx5_sdb .section}

After setting the retention time for the classic network endpoint, you can extend its retention time through the console before it expires.

During the hybrid access period, you can change the retention time of the classic network endpoint at any time as needed. The expiration time will be calculated from the date the change occurs. For example, if the classic network endpoint is set to expire on August 18, 2017 and you change the expiration date to 14 days later on August 15, 2017, the endpoint will be released on August 29, 2017.

1.  Log on to the RDS Console.
2.  Select the region of the target instance.
3.  Click the ID of the target instance.
4.  In the left-side navigation pane, select **Database Connection**.
5.  In the Instance Connection tab, click **Change Expiration time**.
6.  Select the expiration time and click **OK**.

## Change the network type through API {#section_gyr_xw5_sdb .section}

1.  Download the SDK.
    -   [aliyun-java-sdk-rds-new.zip](http://sdk-release.oss-cn-hangzhou.aliyuncs.com/jarfiles/aliyun-java-sdk-rds-2.1.0.jar?spm=5176.143622.693811.15.tKN4aq&file=aliyun-java-sdk-rds-2.1.0.jar)

    -   [aliyun-python-sdk-rds-new.zip](https://pypi.python.org/pypi/aliyun-python-sdk-rds?spm=5176.143622.695759.10.vdzt6P)

    -   [aliyun-php-sdk-rds-new.zip](https://github.com/aliyun/aliyun-openapi-php-sdk)

2.  Call the ModifyDBInstanceNetworkType API to change the network type.

    **Request parameters**

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |Action|String|Yes|The action to perform. Valid value:ModifyDBInstanceNetworkType

|
    |DBInstanceId|String|Yes|The ID of the instance.|
    |InstanceNetworkType|String|Yes|The network type of the instance:    -   VPC: An instance of the VPC network.

    -   Classic: An instance of the classic network.

|
    |VPCId|String|No|The ID of the VPC.|
    |VSwitchId|String|No|The ID of the VSwitch. This parameter must be specified if the VPC ID is specified.|
    |PrivateIpAddress|String|No|Enter an IP address in the VSwitch CIDR block. If no IP address is entered, the system allocates an intranet IP address according to the VPC ID and the VSwitch ID.|
    |RetainClassic|String|No| Whether to retain the classic network endpoint. The default value is False:

    -   True: Retain
    -   False: Do not retain
 |
    |ClassicExpiredDays|String|No| The retention time of the classic network endpoint. The shortest time is 1 day, the longest time is 120 days, and the default value is 7 days.

 This parameter must be specified if RetainClassic is set to True.

 |

    **Response parameters**

    |Name|Type|Description|
    |:---|:---|:----------|
    |RequestId|String|The ID of the request.|
    |TaskId|String|The ID of the task.|

    **Example code**

    If you want to retain the classic network endpoint:

    -   Set the RetainClassic parameter to True.

    -   Set the ClassicExpiredDays parameter to a value. The classic network endpoint will be deleted when it expires.

    ```
    import com.aliyuncs.DefaultAcsClient;
     import com.aliyuncs.IAcsClient;
     import com.aliyuncs.exceptions.ClientException;
     import com.aliyuncs.exceptions.ServerException;
     import com.aliyuncs.profile.DefaultProfile;
     import com.aliyuncs.profile.IClientProfile;
     import com.aliyuncs.rds.model.v20140815. ModifyDBInstanceNetworkTypeRequest;
     import com.aliyuncs.rds.model.v20140815. ModifyDBInstanceNetworkTypeResponse;
     import org.junit.Test;
     public class ModifyDBInstanceNetworkTypeTest {
         @Test
         public  void switchNetwork_success() {
         ModifyDBInstanceNetworkTypeRequest request=new ModifyDBInstanceNetworkTypeRequest ();
             request.setInstanceId("<Your instance ID>");
             request.setInstanceNetworkType ("VPC");
             request. setVPCId("<VpcId: This parameter is required when the TargetNetworkType is VPC>");
             request.setVSwitchId("<VSwitchId: This parameter is required when the TargetNetworkType is VPC>");
             request.setRetainClassic("<Whether to retain the classic network endpoint>");
             request.setClassicExpiredDays("The retention time of the classic network endpoint");
             IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<Your AK>",
                 "<Your Security>");
             IAcsClient client = new DefaultAcsClient(profile);
         try {
                 ModifyDBInstanceNetworkTypeResponse response
                     response = client.getAcsResponse(request);
                 System.out.println(response.getRequestId());
         }catch (ServerException e) {
                 e.printStackTrace();
         }
             } catch (ClientException e) {
                 e.printStackTrace();
             }
         }
     }
    ```

3.  Call the DescribeDBInstanceNetInfo API to view the classic network endpoint and the VPC endpoint.

    **Request parameters**

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |Action|String|Yes|The action to perform. Valid value:DescribeDBInstanceNetInfo

|
    |DBInstanceId|String|Yes|The ID of the instance.|

    **Response parameters**

    |Name|Type|Description|
    |:---|:---|:----------|
    |DBInstanceNetInfos|List|The connection information of the instance.|
    |InstanceNetworkType|String|The network type of the instance:    -   VPC: An instance of the VPC network.

    -   Classic: An instance of the classic network.

|

    **DBInstanceNetInfo**

    |Name|Type|Description|
    |:---|:---|:----------|
    |ConnectionString|String|The DNS connection string.|
    |IPAddress|String|The IP address.|
    |IPType|String| The IP type of an instance of the classic network: Inner | Public.

 The IP type of an instance of the VPC network: Private | Public.

 |
    |Port|String|The port information.|
    |VPCId|String|The ID of the VPC.|
    |VSwitchId|String|The ID of the VSwitch.|
    |ExpiredTime|String|The time of expiration.|

    **Reference code**

    ```
    import com.aliyuncs.IAcsClient;
     import com.aliyuncs.exceptions.ClientException;
     import com.aliyuncs.exceptions.ServerException;
     import com.aliyuncs.profile.DefaultProfile;
     import com.aliyuncs.profile.IClientProfile;
     import com.aliyuncs.rds.model.v20140815. DescribeDBInstanceNetInfoRequest;
     import com.aliyuncs.rds.model.v20140815. DescribeDBInstanceNetInfoResponse;
     import org.junit.Test;
     public class DescribeDBInstanceNetInfoTest {
         @Test
         public  void describeDBInstanceNetInfo_success() {
             DescribeDBInstanceNetInfoRequest request=new DescribeDBInstanceNetInfoRequest();
             request.setInstanceId("<Your instance ID>");
             IClientProfile profile = DefaultProfile.getProfile("cn-hangzhou", "<Your AK>",
                 "<Your Security>");
             IAcsClient client = new DefaultAcsClient(profile);
             try {
                 DescribeDBInstanceNetInfoResponse response
                     = client.getAcsResponse(request);
                 System.out.println(response.getRequestId());
         }catch (ServerException e) {
                 e.printStackTrace();
         }
             } catch (ClientException e) {
                 e.printStackTrace();
             }
         }
     }
    ```


## Modify the retention time of the classic network endpoint through API {#section_a3s_sy5_sdb .section}

1.  Click the SDK link to download the SDK.
    -   [aliyun-java-sdk-rds-new.zip](http://sdk-release.oss-cn-hangzhou.aliyuncs.com/jarfiles/aliyun-java-sdk-rds-2.1.0.jar?spm=5176.143622.693811.15.tKN4aq&file=aliyun-java-sdk-rds-2.1.0.jar)

    -   [aliyun-python-sdk-rds-new.zip](https://pypi.python.org/pypi/aliyun-python-sdk-rds?spm=5176.143622.695759.10.vdzt6P)

    -   [aliyun-php-sdk-rds-new.zip](https://github.com/aliyun/aliyun-openapi-php-sdk)

2.  Call the ModifyDBInstanceNetworkExpireTime API to modify the retention time of the classic network endpoint.

    **Request parameters**

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |Action|String|Yes|The action to perform. Valid value:ModifyDBInstanceNetworkExpireTime

.|
    |DBInstanceId|String|Yes|The ID of the instance.|
    |ConnectionString|String|Yes|The classic network connection string to be postponed. There are two string types: the classic network endpoint of the current instance and the classic network endpoint separating reading and writing.|
    |ClassicExpiredDays|Integer|Yes|The retention time of the classic network endpoint is \[1-120\] days.|

    **Response parameters**

    |Name|Type|Description|
    |:---|:---|:----------|
    |RequestId|String|The ID of the request.|

    **Reference code**

    ```
    public static void main(String[] args) {
         ModifyDBInstanceNetExpireTimeRequest request = new ModifyDBInstanceNetExpireTimeRequest();
         request.setClassicExpiredDays(3);
         request.setConnectionString("<The link string>");
         request.setDBInstanceId("<The instance ID>");
         IClientProfile profile
                 = DefaultProfile.getProfile("cn-qingdao", "<Your ak>",
                 "<Your sk>");
         IAcsClient client = new DefaultAcsClient(profile);
         try {
             ModifyDBInstanceNetExpireTimeResponse response
                     = client.getAcsResponse(request);
             System.out.println(response.getRequestId());
         }catch (ServerException e) {
             e.printStackTrace();
         }
         } catch (ClientException e) {
             e.printStackTrace();
         }
     }
    ```


