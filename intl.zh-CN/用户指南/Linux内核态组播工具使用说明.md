# Linux内核态组播工具使用说明 {#concept_bqh_sg1_wdb .concept}

Linux组播工具主要应用于阿里云VPC网络和经典网络环境内。组播工具的客户端和服务端分别包括一个Linux内核模块和用户态的配置命令行，内核模块用于将组播包与单播包相互转换以适应当前的网络环境，命令行用于组播组的配置。

## 环境准备 {#section_dpj_lxc_wdb .section}

该组播工具依赖`kernel-devel`和`rpm-build`安装包。运行以下命令检查是否已安装`kernel-devel`和`rpm-build`：

```

#rpm -qa | grep kernel-devel-`uname -r`
#rpm -qa | grep rpm-build
```

如果尚未安装，运行以下命令进行安装：

```

#yum install kernel-devel-`uname -r` -y 
#yum install rpm-build -y
```

## 安装组播代理工具 {#section_vck_txc_wdb .section}

完成以下操作，安装组播代理工具：

1.  下载组播代理工具。

    下载地址：[https://github.com/aliyun/multicast\_proxy](https://github.com/aliyun/multicast_proxy)

    选择multicast\_kernel文件夹。

2.  运行以下命令检查Kernel版本。

    ```
    uname -r
    ```

    **注意**：如果内核版本大于等于4.0，需要在代码目录执行以下命令安装patch：

    ```
    patch -p1 < multicast_kernel/patch/kernel_v4.0.patch
    ```

3.  运行以下命令生成安装包。

    ```
    sh tmcc_client_auto_rpm.sh;sh tmcc_server_auto_rpm.sh
    ```

4.  运行以下命令安装代理工具。

    ```
    rpm -Uvh multi_server-1.1-1.x86_64.rpm
    rpm -Uvh multi_client-1.1-1.x86_64.rpm
    
    ```

5.  运行以下命令设置开机自动启动`multis`和`multic`服务。

    **说明：** 关机会自动停止服务。

    ```
    
    chkconfig multis on --level 2345
    chkconfig multis off --level 016
    
    chkconfig multic on --level 2345
    chkconfig multic off --level 016
    ```


## 启动和停止代理服务 {#section_odv_hyc_wdb .section}

-   启动代理服务

    组播工具通过service来启动客户端和服务端。启动流程主要包括加载内核模块，从配置文件中加载配置。本操作中采用JSON格式保存配置文件。

    **说明：** 首次启动可以不需要配置文件，每次配置时都会自动保存运行时配置文件。

    -   服务端（root权限）

        执行service multis start

    -   客户端（root权限）

        执行`service multic start`

-   停止代理服务

    停止的流程是保存配置，卸载对应的内核模块。这里配置默认保存为下次启动的配置文件，也就是说默认情况下停止运行后再重新启动，配置会自动恢复。如果不想要保存配置，可以在停止之前，通过命令行清除配置。

    -   服务端（root权限）

        执行service multis stop

    -   客户端（root权限）

        执行service multic stop

-   重启

    -   服务端（root权限）

        执行service multis restart

    -   客户端（root权限）

        执行service multic restart


## 脚本配置组播代理 {#section_dbj_ryc_wdb .section}

您也可以使用提供的脚本进行组播配置，点击[这里](https://github.com/aliyun/multicast_proxy/tree/master/multicast_kernel/conf_auto_make_script)获取脚本。

**说明：** 建议您使用自动化脚本进行组播配置。运行前，请先阅读脚本的readme。

**服务端配置**

服务端需要配置组播组以及添加对应的组播成员。每个服务器支持10个组播。每个组播组支持128个服务器组播成员。命令行默认安装到/usr/local/sbin目录下。

使用multis\_admin命令配置服务端，执行multis\_admin -help查看详细说明。

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
-A/--add add multicast group
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

**客户端配置**

客户端需要配置加入的组播组信息，一个客户端服务器最多属于10个不同的组播组。

使用multic\_admin命令配置客户端，执行multic\_admin -help查看详细说明。

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
-p/--port udp port, the multicast port
-m/--multi_ip multicast ip
```

