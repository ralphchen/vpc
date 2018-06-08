# Scenarios {#concept_fhg_jlz_ndb .concept}

As an isolated network environment that can be flexibly configured, VPC can be used in different scenarios.

## Scenario 1: hybrid cloud \(on-premises IDC + cloud business\) {#section_nsl_llz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[Express Connect](https://www.aliyun.com/product/expressconnect)+[ECS](https://www.aliyun.com/product/ecs)+[RDS](https://www.aliyun.com/product/rds).

-   Place the internal core system and core data in the self-built data center to avoid data disclosure.
-   Deploy customer applications on the cloud to handle business traffic surge in real time.

Architecture description:

This is a typical hybrid cloud architecture. Use VPC, RDS, ECS to build your cloud business system and place the core data in your on-premises data center. By using Express Connect to connect your IDC to cloud, data on and under the cloud is interchangeable.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/2767_en-US.png)

## Scenario 2: security isolation {#section_fmj_tlz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[ECS](https://www.aliyun.com/product/ecs)+[RDS](https://www.aliyun.com/product/rds)+[SLB](https://www.aliyun.com/product/slb).

-   Build a completely isolated business environment on the cloud, because the multi-tenant sharing mechanism in the traditional cloud architecture cannot guarantee data security.
-   Have full control over the private network.

Architecture description:

You can create a VPC to deploy your systems. VPC is logically isolated from other virtual networks in Alibaba Cloud.  You have full control over your VPC, for example, you can select its IP address range, further segment your VPC into subnets, as well as configure route tables and network gateways.  Additionally, you can connect your VPC to your on-premises network using a physical connection or a VPN to form an on-demand customizable network environment. 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/2768_en-US.png)

## Scenario 3: Web scraping applications that actively access the Internet {#section_dtj_vlz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[ECS](https://www.aliyun.com/product/ecs)+[NAT Gateway](https://www.aliyun.com/product/nat).

-   Allows multiple servers in the Virtual Private Cloud \(VPC\) to actively access to the Internet.
-   Prevents the public IP of these servers from being exposed on the Internet.

Architecture description:

You can implement a SNAT configuration for all the ECSs under the same VSwitch in the VPC to allow several ECSs to access the Internet using a public IP, and this public IP can be replaced anytime to prevent external attacks.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/2769_en-US.png)

## Scenario 4: Great traffic fluctuation of multiple applications--shared bandwidth package {#section_i4s_wlz_ndb .section}

If you have the following demands, we recommend that you use the architecture of VPC+[NAT Gateway](https://www.aliyun.com/product/nat)+[ECS](https://www.aliyun.com/product/ecs).

-   There are multiple Internet-facing applications in the system;
-   All applications need to provide external services, but with inconsistent peak time.

Architecture description:

You can purchase multiple ECS instances of the VPC network to provide different services respectively. Then you can use a NAT gateway and configure DNAT IP forwarding rules to allow the multiple IPs to share the bandwidth, thereby mitigating the peak effect and reducing cost.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/2770_en-US.png)

