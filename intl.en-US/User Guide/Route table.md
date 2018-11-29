# Route table {#concept_ym5_jhv_q2b .concept}

A route table consists of one or more route entries. Each route entry specifies the destination for the specified traffic. In addition to the default route table, you can create custom route tables for a VPC to route traffic through subnets.

## System route table and custom route table {#section_rmh_4nb_r2b .section}

After creating a VPC, Alibaba Cloud automatically creates a route table to control the VPC routing. All VSwitches in the VPC use this route table by default. You cannot create a default route table, nor delete the default route table, but you can create a custom route table and associate it with a VSwitch to control the subnet routing.

Note the following when you manage route tables:

-   A VPC can have up to 10 route tables, including the system route table.
-   One VSwitch can only associate with one route table. The routing of a VSwitch \(subnet\) is managed by the route table associated with the VSwitch.
-   After a VSwitch is created, the VSwitch is associated with the system route table by default.
-   If you want to replace the custom route table associated with a VSwitch with the system route table, unbind the custom route table directly. Then, the VSwtich is automatically associated with the system route table. If you want to replace the custom route table associated with a VSwitch with another custom route table, unbind the custom route table and then associate it with the custom route table that you want to use.
-   Currently, customized route tables are available in most regions apart from China \(Beijing\), China \(Hangzhou\), and China \(Shenzhen\) regions.

## Create a custom route table {#section_kyq_v41_r2b .section}

To create a custom route table, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Route Tables**.
3.  On the Route Tables page, click **Create Route Table**.
4.  Configure the route table according to the following information, and then click **OK**.

    |Configuration|Description|
    |:------------|:----------|
    |**Name**| Enter a name for the route table.

 The name can contain 2 to 128 characters. It must begin with English or Chinese characters and can contain numbers, hyphens \(-\) and underscores \(\_\).

 |
    |**VPC**|Select the VPC that the route table belongs to.|
    |**Description**| Enter a description for the route table.

 The description can contain 2 to 256 characters, but cannot begin with `http://` and `https://`.

 |

    You can view and manage custom route tables on the Route Tables page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17037/15434934758671_en-US.png)


## Associate a custom route table with a VSwitch {#section_yry_52b_r2b .section}

You can associate a custom route table with a VSwitch to control the traffic through it. A VSwitch can only associate with one route table, including the system route table.

To associate a custom route table with a VSwitch, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Route Tables**.
3.  On the Route Tables page, locate the target custom route table.
4.  Click the **Associated VSwitches** tab, and then click **Associate VSwitch**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17037/15434934758675_en-US.png)

5.  In the displayed dialog box, select the VSwitch to bind, and then click **OK**.
6.  Click the **Route Entry List** tab, add custom route entries.

    For more information, see [Add custom route entry](reseller.en-US/User Guide/Routing.md#section_k5r_n5y_rdb).


## Unbind a custom route table from a VSwitch {#section_p1c_jjb_r2b .section}

You can unbind a custom route table with a VSwitch. Then the VSwitch uses the default route table if you do not associate it with another custom route table.

To unbind a custom route table from a VSwitch, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Route Tables**.
3.  On the Route Tables page, click the ID of the target custom route table.
4.  On the **Associated VSwitches** page, locate the target VSwitch.
5.  Click **Unbind**. In the displayed dialog box, click **OK**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17037/15434934759790_en-US.png)


## Edit the custom route table {#section_svh_r4b_r2b .section}

To modify the name and description of a custom route table, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Route Tables**.
3.  On the Route Tables page, click the ID of the target custom route table.
4.  In the **Route Table Details** area, modify the name and description accordingly.

## Related operations {#section_f54_dlj_w2b .section}

[Add custom route entry](reseller.en-US/User Guide/Routing.md#section_k5r_n5y_rdb)

