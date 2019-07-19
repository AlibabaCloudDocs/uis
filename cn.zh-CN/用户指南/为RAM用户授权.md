# 为RAM用户授权 {#concept_1236891 .concept}

UIS支持RAM用户，您可以通过RAM用户使用UIS，但需要先使用云账号（主账号）为RAM用户（子账号）授权，授权之后的RAM用户才能访问云账号下的UIS资源。

## 前提条件 {#section_yfa_kms_m83 .section}

使用云账号为RAM用户授权前，您需要开通RAM。详细信息，请参见[开通方法](../../../../cn.zh-CN/产品定价/开通方法.md#)。

## 步骤一 创建RAM用户 {#section_l9r_kxz_rny .section}

完成以下操作，创建RAM用户。

1.  登录[RAM控制台](https://ram.console.aliyun.com/policies/new)。
2.  在左侧导航栏，单击**人员管理** \> **用户**。
3.  在用户页面，单击**新建用户**。
4.  在新建用户页面，输入登录名称和显示名称。

    单击**+添加用户**，支持创建多个用户。

5.  在访问方式区域，选择访问方式，然后单击**确认**。

    -   **控制台密码登录**：可以完成对登录安全的基本设置，包括自动生成或自定义登录密码，是否要求下次登录时重置密码，以及是否要求开启多因素认证。
    -   **编程访问**：将会自动为用户创建访问密钥，支持通过API或其他开发工具访问阿里云资源。
    **说明：** 为了保障账号安全，建议仅为RAM用户选择一种访问方式，避免RAM用户离开组织后仍可以通过访问密钥访问阿里云资源。


## 步骤二 创建自定义权限策略 {#section_a8y_tez_df9 .section}

完成以下操作，创建自定义权限策略。

1.  登录[RAM控制台](https://ram.console.aliyun.com/policies/new)。
2.  在左侧导航栏，单击**权限管理** \> **权限策略管理**。
3.  在权限策略管理页面，单击**新建权限策略**。
4.  在新建自定义权限策略页面，输入策略名称和备注，然后选择脚本配置，输入策略内容。

    目前，UIS还未上线系统权限，需要您自定义权限策略，UIS权限策略如下。

    |策略名称|备注|策略详请|说明|
    |----|--|----|--|
    |UisFullAccess|管理极致互联网服 务\(UIS\)的权限|     ``` {#codeblock_gwt_v0m_3pr}
{
     "Statement": [
        {
             "Action": "uis:*",
             "Effect": "Allow",
             "Resource": "*"
         }
     ],
     "Version": "1"
 }
    ```

 |具有该权限的子账号，可以操作主账号下的UIS的所有资源。|
    |UisReadOnlyAccess|只读访问极致互联 网服务\(UIS\)的权限|     ``` {#codeblock_al9_ikc_unj}
{
     "Version": "1",
     "Statement": [
        {
             "Effect": "Allow",
             "Action": [
                 "uis:Describe*",
                 "uis:Get*"
             ],
             "Resource": [
                 "*"
             ],
             "Condition": {}
         }
     ]
}
    ```

 |具有该权限的子账号，仅可以查询UIS的所有资源。|

5.  单击**确定**完成创建。

## 步骤三 授权RAM用户 {#section_jjr_70n_w10 .section}

完成以下操作，授权RAM用户。

1.  登录[RAM控制台](https://ram.console.aliyun.com/policies/new)。
2.  在左侧导航栏，单击**人员管理** \> **用户**。
3.  在用户页面，找到目标RAM用户，单击**操作**列下的**添加权限**。
4.  在添加权限页面，选择UIS自定义权限策略。
5.  单击**确定**完成授权。

