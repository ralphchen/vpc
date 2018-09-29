# Plan and design VPC {#concept_dvk_lj5_sdb .concept}

Before creating VPCs and VSwitches, you need to plan the number of VPCs to create and CIDR blocks of VPCs and VSwitches according to specific business.

VPC \(Virtual Private Cloud\) is a private network dedicated to you on Alibaba Cloud. VPCs are logically isolated from other VPCs in Alibaba Cloud. More and more users use the VPC network because:

-   Isolated network environment

    Based on tunneling technology, VPC isolates the data link layer and provides an independent, isolated, and safe network for each user. Resources within a VPC can communicate with each other over the intranet, but cannot directly communicate with resources in other VPCs unless you have configured an EIP or a NAT IP.

-   Controllable network configurations

    You have full control over your VPC, such as specifying its IP address range and configuring route tables and network gateways, to securely and easily access resources. Additionally, you can connect a VPC to another VPC or to a local IDC network to form an on-demand network environment, which allows you to smoothly migrate applications to Alibaba Cloud and expand the network of your local IDC.

    For more information, see [What is VPC](https://www.aliyun.com/product/vpc?spm=5176.8142029.388261.75.NcXndU).


When using VPC, the first problem encountered is how to design your VPC network. You can start designing your VPC by answering the following questions:

-   [Q1: How many VPCs are required?](reseller.en-US/Best practices/Plan and design VPC.md#section_ocz_5j5_sdb)

-   [Question 2: How many VSwitches are required?](reseller.en-US/Best practices/Plan and design VPC.md#section_ak2_sm5_sdb)

-   [Question 3: How to specify the private IP address range?](reseller.en-US/Best practices/Plan and design VPC.md#section_yzq_tm5_sdb)

-   [Question 4: How to specify the private IP address range when planning to connect a VPC to a local data centers or other VPCs?](reseller.en-US/Best practices/Plan and design VPC.md#section_wn4_tm5_sdb)


## Q1: How many VPCs are required? {#section_ocz_5j5_sdb .section}

-   One VPC

    If you do not have requirements to deploy your system in multiple regions and the system does need to be isolated by using VPC, one VPC is recommended. Currently, a VPC can host up to 15,000 cloud product instances.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2447/1538214222821_en-US.jpg)

-   Multiple VPCs

    If you have the following requirements, two and more VPCs are recommended.

    -   Deploy cloud product resources in different regions

        VPCs are a region-specific resource that cannot be deployed across regions. If you have to deploy different systems in different regions, you have to create multiple VPCs. You can use products such as Express Connect, VPN Gateway and CEN to connect VPCs.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2447/1538214222822_en-US.jpg)

    -   Isolate different systems

        If you have to isolate your systems, such as isolate the production environment from the test environment, create multiple VPCs. Different VPCs are completely isolated.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2447/1538214223824_en-US.jpg)


## Question 2: How many VSwitches are required? {#section_ak2_sm5_sdb .section}

In general, it is recommended that you create at least two VSwitches for each VPC, and deploy these two VSwitches in two different zones \(Zones are physical areas with independent power supplies and networks in a region. Zones within the same region are interconnected over the intranet\). This protects your applications from a single point of failure.

Network latency between different zones in a region is very small. You have to verify the network latency in your real business system. The network latency might be larger than expected due to complicated systems calls or cross-zone calls. Optimize and adjust the system to find a balance between high availability and low latency.

Additionally, the number of VSwitches is related to the system size and system design. If the front-end system requires mutual access to the Internet, consider deploying different front-end systems under different VSwitches for better disaster tolerance. Then, deploy the backend system in other VSwitches.

## Question 3: How to specify the private IP address range? {#section_yzq_tm5_sdb .section}

When creating VPCs and VSwitches, you have to specify the private IP address range for the VPC and the VSwitch in the form of a Classless Inter-Domain Routing \(CIDR\) block.

-   Private IP address range of VPC

    Use 192.168.0.0/16, 172.16.0.0/12, and 10.0.0.0/8 or their subsets as the private IP address range for your VPC. Note the following when planning the private IP address range of VPC:

    -   If you have only one VPC and it does not have to communicate with a local data center, you are free to use any IP address range as listed in the previous table.
    -   If you have multiple VPCs, or you want to build a hybrid cloud composed of one or more VPCs and local data centers, it is recommended that you use the subset of these standard IP address ranges as the IP address range for your VPC and make sure that the netmask is no larger than /16.
    -   You also need to consider whether the classic network is used when selecting a VPC CIDR block. If you plan to connect cloud product instances in a classic network with a VPC, it is recommended that do not use the IP address range 10.0.0.0/8, which is also used by the classic network.
-   Private IP address range of VSwitch

    The IP address range of a VSwitch can be the same as the VPC that it belongs to, or a subset of the IP address range of the VPC. For example, if the IP address range of a VPC is 192.168.0.0/16, then the IP address range of the VSwitch can be 192.168.0.0/16, or any IP address ranges from 192.168.0.0/17 to 192.168.0.0/29.

    Note the following when selecting the IP address range of a VSwitch:

    -   The allowed block size for a VSwitch is between a /16 netmask and /29 netmask, which can provide 8 to 65,536 IP addresses. The /16 netmask is larger enough to use with 65,532 IP addresses, while the /29 netmask is too small.
    -   The first and last three IP addresses of a VSwitch are reserved by the system. For example, if the CIDR block of a VSwitch is 192.168.1.0/24, IP addresses 192.168.1.0, 192.168.1.253, 192.168.1.254, and 192.168.1.255 are reserved.
    -   The ClassicLink function enables ECS instances in the classic network to communicate with ECS instances in VPC of 192.168.0.0/16, 10.0.0.0/8, and 172.16.0.0/12 IP address ranges. If you want to connect an ECS instance in the classic network to a VSwitch using the ClassicLink function, and the IP address range of the VPC is 10.0.0.0/8, make sure the IP address range of the VSwitch is 10.111.0.0/16. For more information, see [ClassicLink overview](../../../../reseller.en-US/User Guide/ClassicLink/ClassicLink overview.md#).
    -   Consider the number of cloud product instances running in the VSwitch.

## Question 4: How to specify the private IP address range when planning to connect a VPC to a local data centers or other VPCs? {#section_wn4_tm5_sdb .section}

If you have to connect a VPC with other VPCs or local data centers, make sure that the CIDR block for networks to be connect do not conflict with each oter.

As shown in the following figure, you have a VPC1 in China \(Hangzhou\), VPC2 in China \(Shanghai\) and VPC3 in China \(Beijing\). VPC1 and VPC2 can communicate with each other over the intranet through Express Connect. VPC3 has no requirements to communicate with other VPCs, but might need to communicate with VPC2 in the future. Additionally, you have a local data center, which is connected to VPC1 by using the physical connection of Express Connect.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2447/1538214223825_en-US.jpg)

When you have to connect a VPC with other VPCs or local data centers, make sure that the CIDR block for each VPC is not the same. Therefore, in this example, the CIDR blocks of VPC1 and VPC2 are different, while the CIDR block of VPC3 is the same as VPC2. However, the VSwitches in these two VPCs use completely different CIDR blocks to meet future demands for communication with each other. For communication among VPCs, the CIDR blocks of VSwitches to communicate with each other cannot be the same, but the CIDR blocks of the VPCs can be the same.

When specifying IP address ranges for VPCs requiring communication with other VPCs or local data centers, follow these rules:

-   Use different IP address ranges for different VPCs. You can use the subsets of the standard IP address ranges to increase the number of VPCs.
-   If the first principle is not feasible, use different CIDR blocks for VSwitches of different VPCs.
-   If neither of the previous conditions is met, make sure that the CIDR blocks of VSwitches requiring communications are different.

