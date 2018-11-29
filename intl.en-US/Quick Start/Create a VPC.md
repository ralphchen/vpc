# Create a VPC {#concept_isl_ghv_rdb .concept}

This tutorial illustrates how to create an ECS instance in a VPC and bind an EIP to the ECS instance, thereby the instance can access the Internet.

## Step 1 Create a VPC and a VSwitch {#section_ufw_rhv_rdb .section}

To deploy cloud resources in a VPC, you must create at least one VSwitch. To create a VPC and a VSwitch, complete these steps:

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc) .
2.  Select the region of the VPC.

    The VPC and the cloud resources to deploy must be in the same region. In this tutorial, **China \(Qingdao\)** is selected.

3.  Click **Create VPC**, configure the VPC and the VSwitch according to the following information, and click **OK**.

    |Configuration|Description|
    |:------------|:----------|
    |VPC configurations|
    |**Name**|Enter a name for the VPC.The name can contain 2 to 128 characters. It must begin with English or Chinese characters and can contain numbers, hyphens \(-\) and underscores \(\_\).

In this tutorial, enter **webVPC**.

|
    |**CIDR**|Select the CIDR block of the VPC. Limitations on the VPC CIDR blocks are as follows:    -   You can use the standard CIDR blocks: 192.168.0.0/16, 172.16.0.0/12, and 10.0.0.0/8, or their subsets as the IP address range of the VPC. If you want to use a subnet of a standard CIDR block as the IP address range, you must use the CreateVpc API to create a VPC.

    -   If you want to connect a VPC to another VPC, or to a local network to build a hybrid cloud, it is recommended that you use the subset of the standard CIDR blocks, and make sure that the network mask is no longer than /16.

    -   If you only have one VPC and it does not need to communicate with your local network, you can use any of the standard CIDR blocks or their subsets.

**Note:** After the VPC is created, you cannot change its CIDR block.

In this tutorial, select **172.16.0.0/12**.

|
    |VSwitch configurations|
    |**Name**|Enter a name for the VSwitch.The name can contain 2 to 128 characters. It must begin with English letters or Chinese characters and can contain numbers, hyphens \(-\) and underscores \(\_\).

In this tutorial, enter **webVS**.

|
    |**Zone**|Select the zone of the VSwitch. In a VPC, VSwitches in different zones can communicate with each other through the intranet.In this tutorial, select **Zone B**.

|
    |**CIDR**|Enter the CIDR block of the VSwitch. Note the following when specifying the VSwitch CIDR block:    -   The CIDR block of the VSwitch can be the same as that of the VPC to which it belongs, or a subset of the VPC CIDR block.

For example, if the CIDR block of the VPC is 192.168.0.0/16, the CIDR block of the VSwitch in the VPC can be 192.168.0.0/16, 192.168.0.0/17, …, till 192.168.0.0/29.

**Note:** If the CIDR block of the VSwitch is the same as that of the VPC to which it belongs, you can only create one VSwitch in the VPC.

    -   The size of the subnet mask for the VSwitch can be /16 to /29, which can provide 8 to 65536 IP addresses.

    -   The first and last three IP addresses are reserved by the system.

Take the IP address range 192.168.1.0/24 as an example, IP addresses 192.168.1.0, 192.168.1.253, 192.168.1.254, and 192.168.1.255 are reserved by the system.

    -   Make sure the CIDR block does not conflict with that of the VSwitch in another VPC or the local data center that the VSwitch connects to.

**Note:** After the VSwitch is created, you cannot change its CIDR block.

In this tutorial, enter **172.16.1.0/12**.

|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2434/1543493258807_en-US.png)


## Step 2 Create an ECS instance {#section_b1n_rhw_rdb .section}

Complete these steps to create an ECS instance in the created VPC:

1.  In the left-side navigation pane, click **VSwitches**.
2.  Select the region of the VSwitch. In this tutorial, select **China \(Qingdao\)**.
3.  Find the created VSwitch, and click**Purchase** \> **ECS Instance**.
4.  Configure the ECS instance and click **Buy Now**.

    For network configurations, the following are used in this tutorial:

    -   Network Type: Select the created VPC and VSwitch.
    -   Public IP address: Do not allocate.
5.  Go back to the ECS console to view the created ECS instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2434/1543493258808_en-US.png)


## Step 3 Create an EIP {#section_xw3_lkw_rdb .section}

An Elastic IP \(EIP\) address is a public IP address resource that you can purchase and possess independently. Complete these steps to create an EIP:

1.  In the left-side navigation pane, click **Elastic IP addresses**.
2.  Select the region of the EIP and click **Create EIP**. In this tutorial, select **China \(Qingdao\)**.
3.  Configure the EIP, and click Buy Now.

## Step 4 Bind an EIP {#section_ux1_cmw_rdb .section}

Complete these steps to bind EIP to the created ECS instance:

1.  In the left-side navigation pane, click **Elastic IP addresses**.
2.  Select the region of the EIP.
3.  Find the created EIP and click **Bind**.
4.  In the displayed dialog box, select **ECS Instance** as the **Instance Type**, and select the created ECS instance.
5.  Click **OK**.

## Step 5 Verification {#section_q5d_smw_rdb .section}

After binding an EIP, the ECS instance of the VPC network can communicate with the Internet.

**Note:** Make sure the security group rules of the ECS instance allow remote access and ping.

