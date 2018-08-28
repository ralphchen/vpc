# Scenarios {#concept_fhg_jlz_ndb .concept}

VPC is a completely isolated network environment and can be used in different scenarios.

## Scenario 1: Hybrid cloud \(local IDC + cloud\) {#section_nsl_llz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[Express Connect](https://www.aliyun.com/product/expressconnect)+[ECS](https://www.aliyun.com/product/ecs)+[RDS](https://www.aliyun.com/product/rds).

-   Place the internal core system and core data in the self-built data center to avoid data disclosure.
-   Deploy applications on the cloud to handle business traffic surge in real time.

Architecture description:

This is a typical hybrid cloud architecture. Use VPC, RDS, ECS to build your cloud business system and place the core data in your on-premises data center. By using Express Connect to connect your IDC to cloud, data on and under the cloud is interchangeable.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15354348052767_en-US.png)

## Scenario 2: Security isolation {#section_fmj_tlz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[ECS](https://www.aliyun.com/product/ecs)+[RDS](https://www.aliyun.com/product/rds)+[SLB](https://www.aliyun.com/product/slb).

-   Build a completely isolated business environment on the cloud, because the multi-tenant sharing mechanism in the traditional cloud architecture cannot guarantee data security.
-   Have full control over the private network.

Architecture description:

You can create a VPC to deploy your systems. VPC is logically isolated from other virtual networks in Alibaba Cloud.  You have full control over your own VPC, including choosing your preferred IP address range, network segment, route table, and gateway, to achieve safe and easy access to your resources and applications. In addition, you can also establish connections via a leased line or VPN between your VPC and the traditional data center to form an on-demand network environment for smooth app migration to the cloud and expansion of data centers.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15354348052768_en-US.png)

## Scenario 3: Web scraping applications that actively access the Internet {#section_dtj_vlz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[ECS](https://www.aliyun.com/product/ecs)+[NAT Gateway](https://www.aliyun.com/product/nat).

-   Allow multiple servers in the Virtual Private Cloud \(VPC\) to actively access to the Internet.
-   Prevent the public IP of these servers from being exposed on the Internet.

Architecture description:

About the architecture: You can implement a SNAT configuration for all the ECSs under the same VSwitch in the VPC to allow several ECSs to access the Internet using a public IP, and this public IP can be replaced anytime to prevent external attacks.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15354348052769_en-US.png)

