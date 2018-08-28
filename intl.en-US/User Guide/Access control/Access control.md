# Access control {#reference_rvf_pld_sdb .reference}

VPC does not comes with an independent access control policy. Access control in the VPC relies on the access control capabilities of each cloud product. For example, ECS instances use security groups to achieve access control, while SLB and RDS use whitelists to achieve access control.

## ECS security group {#section_yk1_vld_sdb .section}

A security group is a virtual firewall that provides the stateful packet inspection feature. A security group is a virtual firewall that provides the stateful inspection packet filtration feature. Security groups are used to set network access control for one or more ECS instances. As an important measure to isolate networks, security groups are used to divide security domains in the cloud.

When you create an ECS instance of the VPC network, you can use the default security group rule provided by the system. You can change the security rules in the default security group but you cannot delete the default security group.

## RDS whitelist {#section_j1s_wld_sdb .section}

You can use the whitelist feature of ApsaraDB for RDS to set IP addresses that are allowed to access the RDS instances. Access from other IP addresses are denied. When using RDS in a VPC, add the IP address of the ECS instance to the whitelist of the RDS so that the ECS instance can access the RDS instance.

## SLB whitelist {#section_ywv_xld_sdb .section}

SLB is a traffic distribution control service that distributes access traffic to multiple backend ECS instances based on forwarding rules. You can configure whitelists for Server Load Balancer listeners thereby only the IP addresses in the whitelists can access the listeners. It is useful when the application only allows access from certain IP addresses.

