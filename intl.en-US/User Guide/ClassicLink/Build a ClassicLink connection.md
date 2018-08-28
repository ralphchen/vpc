# Build a ClassicLink connection {#task_xpf_24c_sdb .task}

You can set up a ClassicLink connection to let the ECS instance of the classic network access the resources deployed in a VPC network.

Make sure that you are aware of the limitations of ClassicLink. For more information, see [ClassicLink overview](intl.en-US/User Guide/ClassicLink/ClassicLink overview.md#).

1.   Log on to the [VPC console](https://vpcnext.console.aliyun.com). 
2.   Select the region of the target VPC, and click the ID of the target VPC. 
3.   On the VPC Details page, click **Enable ClassicLink**. In the displayed dialog box, click **OK**. 
4.   Go to the ECS console. 
5.   In the left-side navigation pane, click **Instances**. 
6.  Select a region, and then locate the target classic ECS instance. 
7.  Click **More** \> **Network and Security Group** \> **Connect to VPC**. 
8.   In the displayed dialog box, select the target VPC and click**OK**. Then click the security group configuration link. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2441/1535435362818_en-US.png)

9.   Click**Add ClassicLink Rules** and configure the security rule according to the following information. Then, click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Classic Security Group**|Display the classic network security group.|
    |**Select VPC Security Group**|Select a security group to use. Up to 5 security groups can be selected.|
    |**Mode**| Select one of the following modes:    -   Classic &lt;=\> VPC: The connected resources can access each other \(recommended\).
    -   Classic =\> VPC: Authorize the classic ECS instance to access cloud resources in the connected VPC.
    -   Classic <= VPC: Authorize the cloud resources in the connected VPC to access the classic ECS instance.
|
    |**Protocol Type and Port Range**|Select the protocol and port used for the communication. The port must be in the form of xx/xx.  For example, if port 80 is used, enter 80/80.|
    |**Priority**|Set the priority for the rule.  A smaller number represents a higher priority.|
    |**Description**|Enter a description for the security rule.|

10.  On the ECS instances page, click the Column Filter icon on the upper-right corner, and then select the **Connection Status** check box. Click**OK**. 

    ![](images/6557_en-US.png "Column Filter")

    ![](images/6556_en-US.png " Connection Status")

    ![](images/819_en-US.png "Connected to a VPC")


