# How to use cloud products in a VPC？ {#concept_d3v_bp5_sdb .concept}

Most cloud products have supported the VPC network. You can select the VPC network when creating cloud resources, or create a VPC first and then create cloud resources in the VPC.

## How to use VPC? {#section_phq_hp5_sdb .section}

VPC is an isolated private network. By default, different VPCs cannot communicate with one another through intranet. ECS instances in a VPC cannot access the Internet or be accessed by the Internet, and cannot access the classic network through intranet. But Alibaba Cloud provides a lot of connectivity options to allow Internet and intranet access.

**Note:** Cloud products requiring intranet communication must use the same network type. For example, if an ECS instance in a VPC network needs to access an SLB instance or RDS instance through intranet, the SLB instance and the RDS instance must also use the VPC network, otherwise the access will fail.

For different cloud products, the way you choose to use VPC is different:

-   Choose to use VPC on the purchase page

    This method mainly applies to cloud products such as ECS, RDS and SLB. These cloud products provide different networks for you to choose. You can select the VPC to use when purchasing an instance. After create an instance, a private IP address or a private endpoint will be allocated to the instance.

-   Choose to use VPC on the console

    This method applies to cloud products such as Table Store, Container Service, E-MapReduce and Network Attached Storage.

    You can set a VPC endpoint for a Table Store instance on the Table Store console, choose to use VPC when creating a Container Service cluster or E-MapReduce cluster on the console.

-   Provide VPC endpoints

    This applies to cloud products such as Log Service and Object Storage Service.

    You can view help documents of the following products:

    -       -   
## How to change the network type? {#section_h4s_lp5_sdb .section}

-   For some instance cloud products such as ApsaraDB for RDS, you can change the network type from the classic network to VPC on the console.

-   Server Load Balancer does not support changing the network type. You can purchase an SLB instance of the VPC network and then add ECS instances of the VPC network to it.


For more information, see [Migration overview](reseller.en-US/Best practices/Migrate from the classic network to VPC/Migration overview.md#).

