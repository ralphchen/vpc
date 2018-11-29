# Configure multicast for Linux kernel {#concept_bqh_sg1_wdb .concept}

The Linux multicast tool is mainly used in the Alibaba Cloud VPC network and the classic network. A Linux kernel module and a command line are included in the client and server of the multicast tool. The kernel module is used to convert multicast packets and unicast packets to adapt to the current network environment. The command line is used to configure multicast groups.

## Prepare the environment {#section_dpj_lxc_wdb .section}

The multicast tool depends on the `kernel-devel` and `rpm-build` packages. Run the following command to check if `kernel-devel` and `rpm-build` are installed:

```

#rpm -qa | grep kernel-devel-`uname -r
#rpm -qa | grep rpm-build
```

If not, run the following command to install:

```

#yum install kernel-devel-`uname -r` -y 
#yum install rpm-build -y
```

## Install the multicast agent tool {#section_vck_txc_wdb .section}

To install the multicast agent tool, complete these steps:

1.  Download the multicast agent tool.

    Download address: [https://github.com/aliyun/multicast\_proxy](https://github.com/aliyun/multicast_proxy)

    Select the multicast\_kernel folder.

2.  Run the following command to check the kernel version.

    ```
    uname -r
    ```

    **Note**: If the kernel version is greater than or equal to 4.0, you need to install a patch by executing the following command in the code directory:

    ```
    patch -p1 &lt; multicast_kernel/patch/kernel_v4.0.patch
    ```

3.  Run the following command to generate the installation package.

    ```
    sh tmcc_client_auto_rpm.sh;sh tmcc_server_auto_rpm.sh
    ```

4.  Run the following command to install the agent tool.

    ```
    rpm -Uvh multi_server-1.1-1.x86_64.rpm
    rpm -Uvh multi_client-1.1-1.x86_64.rpm
    
    ```

5.  Run the following command to set the auto-startup `multis` and `multic` services.

    **Note:** The service is automatically stopped when the agent is stopped.

    ```
    
    chkconfig multis on --level 2345
    chkconfig multis off --level 016
    
    chkconfig multic on --level 2345
    chkconfig multic off --level 016
    ```


## Start and stop the agent service {#section_odv_hyc_wdb .section}

-   Start the agent service

    The multicast tool starts the client and the server through the service. The starting process includes loading the kernel module and loading configurations from the configuration files. In this tutorial, JSON format is used to store configuration files.

    **Note:** Configuration files are not required for the first-time start up. The runtime configuration files are automatically saved.

    -   Server \(root permission\)

        Run service multis start

    -   Client \(root permission\)

        Run `service multic start`

-   Stop the agent service

    The stopping process is to save the configuration and uninstall the corresponding kernel module. The configuration is saved as the configuration file for next-time startup by default, that is, the configuration is automatically restored by default when the agent is restarted. If you do not want to save the configuration, clear the configuration using command line before stopping the service.

    -   Server \(root permission\)

        Run service multis stop

    -   Client \(root permission\)

        Run service multic stop

-   Restart the agent service

    -   Server \(root permission\)

        Run service multis restart

    -   Client \(root permission\)

        Run service multic restart


## Configure the multicast agent by using the script {#section_dbj_ryc_wdb .section}

You can also use the provided script for multicast configuration. Click [Here](https://github.com/aliyun/multicast_proxy/tree/master/multicast_kernel/conf_auto_make_script) to obtain the script.

**Note:** We recommend that you use an automated script for multicast configuration. Read the readme before running the script.

**Server configuration**

You must configure multicast groups on the server and add multicast members to the groups. Each server supports 10 multicast groups. Each multicast group supports 128 server multicast members. The command line is installed under the /usr/local/sbin directory by default.

Use the multis\_admin command to configure the server and run multis\_admin -help to view detailed description.

```

multis_admin -- This command can be used to configure multicast server.
Usage:
multis_admin -A -m {multi_ip} -j {ip1,ip2,ip3...}
multis_admin -A -m {multi_ip} -q {ip1,ip2,ip3...}
multis_admin -D -m {multi_ip} 
multis_admin -C 
multis_admin -P -m {multi_ip}
multis_admin -L -m {multi_ip} 
multis_admin -S 
multis_admin -H 
Options:
-A/-- Add add multicast group
-D/--delete del multicast group
-C/--clear clear multicast group
-P/--stats packets statistic
-S/--show show multicast group
-L/--list list multicast group member
-H/--help help info
-j/--join vm join multicast group
-q/--quit vm quit multicast group
-m/--multiip multicast ip
```

**Client configuration**

You must configure the information of the multicast groups that the client is added to. A client server can belong to 10 different multicast groups at most.

Configure the client with the multic\_admin command, and execute multic\_admin-help to view detailed instructions.

```

multic_admin -- This command can be used to configure multicast client.
Usage:
multic_admin -A -i {ip} -p {port} -m {multi_ip}
multic_admin -D -i {ip} -p {port} 
multic_admin -C 
multic_admin -P -i {ip} -p {port} 
multic_admin -L
multic_admin -H 
Options:
-A/--add add multicast server ip and port
-D/--delete del multicast server ip and port
-C/--clear clear multicast server information
-P/--stats recv packets statistic
-L/--list list all multicast server ip and port
-H/--help help info
-i/--ip multicast server ip, the ip of multicast provider
-P/-- Port UDP port, the multicast Port
-m/--multi_ip multicast ip
```

