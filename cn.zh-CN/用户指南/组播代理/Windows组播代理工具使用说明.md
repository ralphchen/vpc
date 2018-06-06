# Windows组播代理工具使用说明 {#concept_fxc_rg1_wdb .concept}

本文档介绍如何在VPC环境中配置组播代理。

## 安装组播代理工具 {#section_f4k_mvd_wdb .section}

完成以下操作，安装组播工具：

1.  下载组播代理工具。

    下载地址：[https://github.com/aliyun/multicast\_proxy/tree/master/rpm\_version](https://github.com/aliyun/multicast_proxy/tree/master/rpm_version)

2.  双击下载的安装包，根据提示进行安装，安装目录为C:\\udptopoint。

    **说明：** 在安装过程中如果检测到winpcap已经安装，直接取消安装便可，也可继续覆盖安装。如果没有安装winpcap，则需要单击**安装**


## 启动代理服务 {#section_rgd_xvd_wdb .section}

代理程序以服务的形式，在Windows后台运行，开机启动。当组播工具安装成功后，桌面上会生成一个用户配置命令程序的快捷键。运行它能够重新加载配置以及获取系统当前的数据包信息。

## 修改组播配置 {#section_jpv_xvd_wdb .section}

Windows代理工具只支持配置文件方式进行配置。因为Windows一般不使用客户端，所以暂不提供客户端工具。

## 配置服务端 {#section_twm_wvd_wdb .section}

服务端需要配置组播组以及对应的组播组成员。

1.  在C:\\udptopoint目录下，打开配置文件server\_cfg.json.txt。
2.  修改如下配置添加组播成员。
    -   group\_ip：组播组IP。

    -   group\_port：应用程序的通信端口。

    -   server\_port：代理程序的通信端口。

    -   member\_array：组播组的成员IP。

        ```
        {
            "multi_group_array": [
                {
                    "group_ip": "224.2.2.1", 
                    "group_port": 4321, 
                    "server_port": 4321, 
                    "member_array": [
                        "172.16.1.1", 
                        "172.16.1.2", 
                        "172.16.1.3"
                    ]
                }
            ]
        }
        ```

3.  当配置完成后，单击`udptopoint-1.3.1.exe`，然后输入**reload**重新加载配置文件。
4.  单击`udptopoint-1.3.1.exe`，然后输入**list**查看当前代理系统的收发包情况。

## 日志 {#section_mjg_rwd_wdb .section}

系统会生成日志信息，在目录C:\\udptopoint下的server\_log.txt文件中。

## 升级 {#section_uvj_twd_wdb .section}

卸载后，安装最新的代理工具。

## 卸载代理工具 {#section_vws_qwd_wdb .section}

-   方法1： 从卸载程序中找到代理程序进行卸载。

-   方法2： 通过安装文件夹中卸载程序（uninst.exe）来卸载代理工具。


