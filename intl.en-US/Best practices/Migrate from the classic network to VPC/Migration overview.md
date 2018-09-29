# Migration overview {#concept_wjl_hv5_sdb .concept}

You can migrate resources deployed in the classic network to a VPC network. VPC is an isolated network environment.

## Why migrate to VPC? {#section_mmn_mv5_sdb .section}

Virtual Private Cloud \(VPC\) is a private network dedicated to you on Alibaba Cloud. You can use Alibaba Cloud resources and products in your own VPC. The VPC network has the following advantages:

-   Secure and isolated network environment

    Based on tunneling technology, VPC isolates the data link layer and provides an independent, isolated, and safe network for each user. Different VPCs are completely isolated from each other.

-   Controllable network configurations

    You have full control over your own VPC network. You can select its IP address range, create subnets, and configure route tables and gateways. Additionally, you can connect a VPC to your local IDC network through leased lines or VPN to form an on-demand network environment, which allows you to smoothly migrate applications to Alibaba Cloud and expand the network topology of the local IDC.


## How to migrate? {#section_omn_mv5_sdb .section}

You can use the following two methods to migrate your system to a VPC network. You can use these methods independently or together to meet the demands of different scenarios:

-   Hybrid addition and hybrid access migration

    If your system is deployed on RDS, SLB, or other cloud products, it is recommended using this solution. It is a seamless migration solution, allowing you to migrate your system to a VPC network without interrupting your services.

    With the ClassicLink function, ECS instances in the classic network can access resources in the VPC network. For more information, see [ClassicLink overview](../../../../reseller.en-US/User Guide/ClassicLink/ClassicLink overview.md#).

-   Single ECS migration

    If your application is deployed on the ECS instance, and restarting the ECS instance does not affect your system, it is recommended using this method.


## Hybrid access and hybrid addition {#section_qmn_mv5_sdb .section}

The hybrid access and hybrid addition solution is a seamless migration solution. Firstly, you must create the required cloud resources \(such as ECS\) in the VPC network to be migrated to, and then use this method to smoothly migrate your system to the VPC. After all the resources have been migrated to VPC, release the cloud resources in the classic network to complete the whole migration process. For more information, see [Example of hybrid access and hybrid addition migration](reseller.en-US/Best practices/Migrate from the classic network to VPC/Example of hybrid access and hybrid addition migration.md#).

-   **Hybrid addition**

    Hybrid addition means that Server Load Balancer supports adding ECS instances of both the classic and VPC networks as backend servers to handle forwarded requests. Hybrid addition is also supported by VServer groups.

    Both Internet and intranet SLB support hybrid addition.

    **Note:** If you add both classic ECS instances and VPC ECS instances to an intranet SLB instance, and configure a Layer-4 \(TCP and UDP protocols\) listener, you can obtain the real IP address of the client on the ECS instances of the VPC network but cannot obtain it on the classic ECS instances. There is no impact on Layer-7 listeners. You can obtain the real IP address no matter the network type of backend servers.

-   **Hybrid access**

    Cloud products like RDS and OSS support hybrid access, that is, they can be accessed by an ECS instance of the classic network and an ECS instance of the VPC network at the same time. In general, these products have two endpoints, one is used for accessing the classic network access and the other one is used for accessing the VPC network.


Note the following when using this method:

-   This solution meets the migration requirements of most systems. If the ECS instances in the classic network has to communicate with the cloud resources in the VPC network, use the ClassicLink function.

-   This method can only be used to migrate a system from the classic network to the VPC network.


