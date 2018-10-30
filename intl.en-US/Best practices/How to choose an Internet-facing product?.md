# How to choose an Internet-facing product? {#concept_d5j_5p5_sdb .concept}

In the VPC network, you can use EIP, NAT Gateway, Internet SLB instance and the public IP of an ECS instance to access the Internet.

## Public IP address {#section_t1p_2q5_sdb .section}

In Alibaba Cloud, there are various types of public IP addresses, such as the public IP of an ECS instance of the VPC network, the public IP of a NAT bandwidth package, the public IP of an Internet SLB instance, and the public IP of a VPN Gateway. To facilitate the unified management of the public IP addresses, ECS instances of the VPC network, NAT Gateways, and intranet SLB instances have supported binding EIP.

You can add EIPs to [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) to flexibly cope with traffic and bandwidth fluctuation and reduce the Internet cost.

## Internet-facing products {#section_brw_n12_sdb .section}

The following table lists available Internet-facing products and the corresponding features.

Besides, to reduce the cost of Internet bandwidth and traffic, Alibaba Cloud provides [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) for VPCs. You can choose different products based on your service model to reduce cost.

|Product|Feature|Benefit|
|:------|:------|:------|
|The public IP of an ECS instance of the VPC network| The public IP allocated by Alibaba Cloud when creating an ECS instance of the VPC network. With this public IP, the ECS instance can access the Internet \(SNAT\) and also can be accessed from the Internet \(DNAT\).

 | After changing a public IP to an EIP, you can also use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp).

 |
|Elastic IP Address \(EIP\)|With an EIP, the ECS instance can access the Internet \(SNAT\) and also can be accessed from the Internet \(DNAT\).| You can bind and unbind an EIP from an ECS instance at any time.

 You can use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) to reduce Internet cost.

 |
|NAT Gateway|NAT Gateway is an enterprise-class Internet gateway, supporting multiple ECS instances accessing the Internet with one EIP \(SNAT\) and being accessed from the Internet \(DNAT\).**Note:** Compared to Server Load Balancer, NAT Gateway itself does not provide the traffic balancing function.

| The core difference between NAT Gateway and EIP is that NAT Gateway supports Internet access of multiple ECS instances but EIP can only be used by an ECS instance.

 |
|Server Load Balancer| Port-based load balancing, Server Load Balancer provides Layer-4 \(TCP and UDP protocols\) and Layer-7 \(HTTP and HTTPS protocols\) load balancing. Server Load Balancer can forward the client requests from the Internet to the backend ECS instances.

 **Note:** The ECS instance without a public IP cannot access the Internet \(SNAT\) through Server Load Balancer.

 | In DNAT, Server Load Balancer supports forwarding an Internet request to multiple ECS instances.

 Server Load Balancer is a traffic distribution control service that distributes the incoming traffic among multiple ECS instances according to the configured forwarding rules. It expands application service capabilities and enhances application availability.

 After binding with an EIP, you can use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) to reduce the Internet cost.

 |

## Scenario 1: provide external services {#section_jcr_l35_sdb .section}

-   Provide external services with a single ECS instance

    If you have only one application and the business is not large, a single ECS instance can meet your requirements. You can deploy applications, databases, and files on this ECS instance. Then, bind an EIP to the ECS instance. Therefore, users can access the deployed application through the Internet.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2449/1540872822826_en-US.png)

-   Provide external services with Layer-4

    When the traffic is large, one ECS cannot support all access traffic. You must configure multiple ECS instances. In this case, you can configure an Internet SLB instance with a Layer-4 listener and add these ECS instances as the backend servers.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2449/1540872822827_en-US.png)

-   Provide external services with Layer-7 load balancing

    In addition to the basic traffic distribution, if you want to distribute different requests to different backend servers, you can add URL forwarding rules to a Layer-7 listener. In this case, you can configure an Internet SLB instance with a Layer-7 listener and add these ECS instances as the backend servers.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2449/1540872822828_en-US.png)


## Scenario 2: Internet access of an ECS instance without a public IP {#section_sdf_yq5_sdb .section}

-   Bind an EIP

    When you have fewer ECS instances, you can bind an EIP to each ECS instance. The ECS instance then can access the Internet using the EIP. Unbind the EIP from the ECS instance whenever the Internet access is not needed.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2449/1540872822826_en-US.png)

-   Configure SNAT entries using NAT Gateway

    If you bind an EIP to each ECS instance respectively, the management cost is high when you have many ECS instances. Additionally, users can access the ECS instance from the Internet through the EIP. In this case, you can configure an SNAT entry for the ECS instances in a VSwitch to access the Internet, but do not configure any DNAT entries. Therefore, the ECS instances can access the Internet, but users cannot access these ECS instances from the Internet, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2449/1540872822829_en-US.png)


