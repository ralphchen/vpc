# Build ClassicLink connection {#task_xpf_24c_sdb .task}

You can enable the ClassicLink function to build ClassicLink connection, so that an ECS instance in the classic network can communicate with cloud resources in VPC.

For more information, see ClassicLink overview.Make sure that you are aware of the limitations of establishing a connection, see [ClassicLink overview](http://intl.en-US/User Guide/ClassicLink/ClassicLink overview.md).

1.   Log on to the [VPC console](https://vpcnext.console.aliyun.com). 
2.  3.   Select the region of the target VPC, and click the ID of the target VPC. 
4.   On the VPC Details page, click **Enable ClassicLink**. In the displayed dialog box, click **OK**. 
5.   Log on to the VPC console. 
6.   In the left-side navigation pane, click **Instances**. 
7.   Find the target ECS instance in the classic network, and click** More** \> **Link to VPC**. 
8.   In the displayed dialog box, select the target VPC and click**OK**. Then click the link to add the ClassicLink security group rule. 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2441/818_en-US.png)

9.   On the Security Groups page, click**Configure Rules** in the Actions column of the target security group and then click **Add ClassicLink Rule**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Classic network security group**|Display the classic network security group.|
    |**Select VPC security groups**|Select VPC security groups.|
    |**Mode**| Select one of the following modes:    -   Classic <=\> VPC: The connected resources can access each other \(recommended\).
    -   Classic Network =\> exclusive network: authorize Classic Network ECs to access cloud resources within a proprietary network.
    -   Classic =\> VPC: The connected ECS instance in the classic network can access instances in the VPC.
|
    |**Protocol Type and Port Range**|Select the protocol and port used for the communication. The port must be in the form of xx/xx.  For example, if port 80 is to be used, enter 80/80. For more information, see Add a security group rule.|
    |**Priority**|Set priority for the rule.  A smaller number represents a higher priority.|
    |**Description**|Enter the description information.|

10.  On the ECS instance list page, click the **Set Display Items** icon and select Link Status. Click**OK**. 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2441/819_en-US.png)


