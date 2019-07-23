# API概览 {#doc_40398 .concept}

极致互联网服务提供以下相关API接口。

## 极致互联网网络服务 {#section_apm_bg0_xfi .section}

|API|描述|
|---|--|
|[CreateUis](cn.zh-CN/API参考/极致互联网网络服务/CreateUis.md)|调用CreateUis接口创建一个Uis实例。实例创建后会指定隧道协议，并生成VPN数据库的管理口令。|
|[ModifyUisAttribute](cn.zh-CN/API参考/极致互联网网络服务/ModifyUisAttribute.md)|调用ModifyUisAttribute接口修改已创建的实例的配置。|
|[DescribeUises](cn.zh-CN/API参考/极致互联网网络服务/DescribeUises.md)|调用DescribeUises接口查询已创建的实例。|
|[DeleteUis](cn.zh-CN/API参考/极致互联网网络服务/DeleteUis.md)|调用DeleteUis接口删除已创建的实例。|

## 节点实例 {#section_cgk_n7w_m16 .section}

|API|描述|
|---|--|
|[CreateUisNode](cn.zh-CN/API参考/上车点实例/CreateUisNode.md)|调用CreateUisNode接口为已创建的实例添加节点实例。|
|[ModifyUisNodeAttribute](cn.zh-CN/API参考/上车点实例/ModifyUisNodeAttribute.md)|调用ModifyUisNodeAttribute接口修改已创建的节点实例配置。|
|[DescribeUisNodes](cn.zh-CN/API参考/上车点实例/DescribeUisNodes.md)|调用DescribeUisNodes接口查询已创建的节点实例。|
|[DeleteUisNode](cn.zh-CN/API参考/上车点实例/DeleteUisNode.md)|调用DeleteUisNode接口删除节点实例。|
|[DescribeAreas](cn.zh-CN/API参考/上车点实例/DescribeAreas.md)|调用DescribeAreas接口查询UIS节点支持的地域信息。|
|[DescribeUiseNodeStatus](cn.zh-CN/API参考/上车点实例/DescribeUiseNodeStatus.md)|调用DescribeUiseNodeStatus接口查询UIS节点的状态信息。|

## 隧道连接 {#section_ayc_2nc_dck .section}

|API|描述|
|---|--|
|[CreateUisConnection](cn.zh-CN/API参考/隧道连接/CreateUisConnection.md)|调用CreateUisConnection接口创建隧道连接。|
|[ModifyUisConnectionAttribute](cn.zh-CN/API参考/隧道连接/ModifyUisConnectionAttribute.md)|调用ModifyUisConnectionAttribute接口修改隧道连接的配置信息。|
|[DescribeUisConnections](cn.zh-CN/API参考/隧道连接/DescribeUisConnections.md)|调用DescribeUisConnections接口查看已创建的隧道连接信息。|
|[DeleteUisConnection](cn.zh-CN/API参考/隧道连接/DeleteUisConnection.md)|调用DeleteUisConnection接口删除隧道连接。|
|[CreateSubConnection](cn.zh-CN/API参考/隧道连接/CreateSubConnection.md)|调用CreateSubConnection接口创建GRE连接。|
|[DescribeSubConnection](cn.zh-CN/API参考/隧道连接/DescribeSubConnection.md)|调用DescribeSubConnection接口查询GRE的连接详情。|
|[DescribeSubConnections](cn.zh-CN/API参考/隧道连接/DescribeSubConnections.md)|调用DescribeSubConnections接口查询GRE的连接。|
|[ModifySubConnection](cn.zh-CN/API参考/隧道连接/ModifySubConnection.md)|调用ModifySubConnection接口修改GRE的连接信息。|
|[DeleteSubConnection](cn.zh-CN/API参考/隧道连接/DeleteSubConnection.md)|调用DeleteSubConnection接口删除GRE的连接。|

## 添加节点IP {#section_kvt_zl2_gsx .section}

|API|描述|
|---|--|
|[AddUisNodeIp](cn.zh-CN/API参考/添加节点IP/AddUisNodeIp.md)|调用AddUisNodeIp接口为UisNode增加IP。|
|[DeleteUisNodeIp](cn.zh-CN/API参考/添加节点IP/DeleteUisNodeIp.md)|调用DeleteUisNodeIp接口删除UIS节点上的IP。|

## 添加目标IP {#section_awn_mi5_bci .section}

|API|描述|
|---|--|
|[AddHighPriorityIp](cn.zh-CN/API参考/添加目标IP/AddHighPriorityIp.md)|调用AddHighPriorityIp接口向List中批量添加IP地址或URL。|
|[ModifyHighPriorityIp](cn.zh-CN/API参考/添加目标IP/ModifyHighPriorityIp.md)|调用ModifyHighPriorityIp接口修改指定实例的地址列表信息。可以用来修改路由的节点信息。|
|[DeleteHighPriorityIp](cn.zh-CN/API参考/添加目标IP/DeleteHighPriorityIp.md)|调用DeleteHighPriorityIp接口删除指定实例的HighPriorityIp地址列表信息。|
|[DescribeHighPriorityIp](cn.zh-CN/API参考/添加目标IP/DescribeHighPriorityIp.md)|调用DescribeHighPriorityIp接口查询指定的实例中目标IP地址或域名列表，并返回指定地址的节点信息。|
|[GetDroppedIpList](cn.zh-CN/API参考/添加目标IP/GetDroppedIpList.md)|调用GetDroppedIpList接口查询报文丢失的IP列表。|
|[DescribeHighPriorityIps](cn.zh-CN/API参考/添加目标IP/DescribeHighPriorityIps.md)|调用DescribeHighPriorityIps接口查询uis实例中的目的地址（ip或者URL）列表。|

## 弹性网卡 {#section_vhj_5xe_mix .section}

|API|描述|
|---|--|
|[CreateUisNetworkInterface](cn.zh-CN/API参考/弹性网卡/CreateUisNetworkInterface.md)|调用CreateUisNetworkInterface接口创建弹性网卡，并将已创建的弹性网卡绑定到UIS服务中。|
|[DescribeUisNetworkInterfaces](cn.zh-CN/API参考/弹性网卡/DescribeUisNetworkInterfaces.md)|调用DescribeUisNetworkInterfaces接口查询已创建的弹性网卡。|
|[DeleteUisNetworkInterface](cn.zh-CN/API参考/弹性网卡/DeleteUisNetworkInterface.md)|调用DeleteUisNetworkInterface接口将弹性网卡从UIS服务中解绑，并删除该弹性网卡。|

## DNAT规则 {#section_lby_iv4_4rs .section}

|API|描述|
|---|--|
|[CreateDnatEntry](cn.zh-CN/API参考/DNAT规则/CreateDnatEntry.md)|调用CreateDnatEntry接口在指定的UIS Node上配置DNAT规则。|
|[DeleteDnatEntry](cn.zh-CN/API参考/DNAT规则/DeleteDnatEntry.md)|调用DeleteDnatEntry接口删除DNAT规则。|
|[DescribeDnatEntries](cn.zh-CN/API参考/DNAT规则/DescribeDnatEntries.md)|调用DescribeDnatEntries接口查询已创建的DNAT规则。|
|[ModifyDnatEntry](cn.zh-CN/API参考/DNAT规则/ModifyDnatEntry.md)|调用ModifyDnatEntry接口修改DNAT规则。|

## 访问控制 {#section_t9f_sry_vg6 .section}

|API|描述|
|---|--|
|[DescribeWhiteList](cn.zh-CN/API参考/访问控制/DescribeWhiteList.md)|调用DescribeWhiteList接口查询访问认证数据库的白名单。|
|[ModifyWhiteList](cn.zh-CN/API参考/访问控制/ModifyWhiteList.md)|调用ModifyWhiteList接口修改访问认证数据库的白名单。|

