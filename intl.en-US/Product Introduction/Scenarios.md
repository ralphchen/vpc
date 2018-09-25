# Scenarios {#concept_fhg_jlz_ndb .concept}

VPC applies to scenarios with high requirement on communication security and service availability.

## Host applications {#section_fmj_tlz_ndb .section}

You can host an application that provides external services in a VPC and control Internet access by creating security group rules and whitelist. You can also control the access by isolating the application server from the database. For example, deploy the web server in a subnet that can access the Internet and deploy the database of the application in a subnet without Internet access.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15378597532768_en-US.png)

## Host applications requiring the access to the Internet {#section_dtj_vlz_ndb .section}

You can host an application that requires to access the Internet in a subnet of a VPC and route the traffic through NAT Gateway. By configuring SNAT rules, the instance in the subnet can access the Internet without exposing its private IP address and the private IP address can be changed to a public IP address any time to avoid external attacks.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15378597532769_en-US.png)

## Cross-zone disaster tolerance {#section_nlp_4vh_w2b .section}

You can create one or multiple subnets in a VPC by creating VSwitches. Different VSwitches in a VPC can communicate with one another through the intranet. You can deploy resources in VSwitches of different zones to achieve cross-zone disaster tolerance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15378597539780_en-US.png)

## Business system isolation {#section_bsg_pvh_w2b .section}

Different VPCs are logically isolated from one another. If you must isolate multiple business systems, such as isolating the production environment from the test environment, you can create multiple VPCs. When the VPCs need to communicate with each other, you can create a peer connection between them.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15378597539781_en-US.png)

## Build hybrid cloud {#section_nsl_llz_ndb .section}

You can create a dedicated connection to connect your VPC to a local data center to expand your local network. With the dedicated connection, you can seamlessly migrate your local applications to the cloud without changing the way of the application access.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13390/15378597532767_en-US.png)

