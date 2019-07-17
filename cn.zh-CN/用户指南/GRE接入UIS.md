# GRE接入UIS {#task_1198721 .task}

本文介绍如何通过GRE协议实现终端接入UIS。

请确保满足以下条件：

-   您已经创建了UIS实例并添加了目标地址。详细信息，请参见[创建UIS实例](cn.zh-CN/用户指南/管理UIS实例/创建UIS实例.md#)和[添加目标地址](cn.zh-CN/用户指南/管理目标地址/添加目标地址.md#)。
-   您已经创建了节点并添加了节点IP地址。详细信息，请参见[创建节点](cn.zh-CN/用户指南/管理节点/创建节点.md#)和[添加节点IP地址](cn.zh-CN/用户指南/管理节点IP/添加节点IP地址.md#)。
-   您已经创建了连接。详细信息，请参见[创建连接](cn.zh-CN/用户指南/管理连接/创建连接.md#)。

本文以ECS实例（Ubuntu系统）搭建GRE网关为例，介绍私网IP 192.168.0.xx如何通过GRE网关接入阿里云UIS，访问公网47.254.87.xx。

![GRE接入UIS](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/908822/156335627151590_zh-CN.png)

1.  执行以下命令在ECS实例上搭建GRE网关。 

    ``` {#codeblock_g88_op4_lec .lanuage-shell}
    modprobe ip_gre
    ip link add gre1 type gre local 192.168.0.xx remote 47.95.197.xx
    ip link set gre1 up
    ip addr add 10.0.1.xx/30 dev gre1
    ip addr add 192.168.0.xx/32 dev gre1
    ip route add 47.254.87.xx/32 dev gre1
    ```

    其中：

    -   192.168.0.xx为ECS实例的私网IP。
    -   47.95.197.xx为UIS的节点IP。
    -   10.0.1.xx为客户Tunnel设备的IP。
    -   47.254.87.xx为要访问的目标IP。
2.  执行modprobe ip\_gre命令，加载GRE模块。

ECS实例可以正常访问目标地址。

![检测GRE接入UIS](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/961338/156335627151722_zh-CN.png)

