---
description: 配置可发送Customer Journey Analytics数据的云导出帐户
keywords: Analysis Workspace
title: 配置云导出帐户
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# 配置云导出帐户

{{select-package}}

在您可以将Customer Journey Analytics数据导出到云目标之前（如所述） [将Customer Journey Analytics数据导出到云端](/help/analysis-workspace/export/export-cloud.md)，您需要添加并配置发送数据的位置。

此过程包括按照本文所述添加和配置帐户(例如Amazon S3、Google Cloud Platform等)，然后按照所述添加和配置该帐户内的位置（例如帐户内的文件夹） [配置云导出位置](/help/components/exports/cloud-export-locations.md).

有关如何管理现有帐户（包括查看、编辑和删除帐户）的信息，请参阅 [管理云导出位置和帐户](/help/components/exports/manage-export-locations.md).

您需要为Customer Journey Analytics配置访问云目标帐户所需的信息。

要配置云导出帐户，请执行以下操作：

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].
1. 在 [!UICONTROL 导出] 页面上，选择 [!UICONTROL **位置帐户**] 选项卡。
1. 选择 [!UICONTROL **添加帐户**].

   ![添加帐户](assets/account-add.png)

   此时将显示添加帐户对话框。
1. 指定以下信息： |字段 |函数 | ------------------- | [!UICONTROL **位置帐户名称**] |位置帐户的名称。 创建位置时将显示此名称 | | [!UICONTROL **位置帐户说明**] |提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。 | | [!UICONTROL **帐户类型**] |选择您要导出到的云帐户类型。 可用的帐户类型包括Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和Adobe Experience Platform。 |
1. 在 [!UICONTROL **帐户属性**] 部分，指定特定于所选帐户类型的信息。

   有关配置说明，请展开以下对应于 [!UICONTROL **帐户类型**] 你选择的。

   +++Amazon S3 Role ARN

   指定以下信息以配置Amazon S3角色ARN帐户：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必须提供一个角色ARN(Amazon资源名称)，Adobe可以使用该角色来访问Amazon S3帐户。 为此，您需要为源帐户创建IAM权限策略，将策略附加到用户，然后为目标帐户创建角色。 有关具体信息，请参阅 [此AWS文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **用户 ARN**] | 用户ARN(Amazon资源名称)由Adobe提供。 您必须将此用户附加到您创建的策略。 |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定以下信息来配置Google Cloud Platform帐户：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **项目ID**] | 从Google Cloud帐户复制的Google Cloud项目ID。 请参阅 [Google Cloud有关获取项目ID的文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **主体**] | 主体由Adobe提供。 单击 [!UICONTROL **复制**] 图标(位于 [!UICONTROL **主体**] 字段以复制字段的内容，然后确保您向主体授予权限，以便在Google Cloud Platform中将文件上传到此存储段。 <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定以下信息以配置Azure SAS帐户：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **密钥保管库 URI**] | <p>Azure密钥库中SAS令牌的路径。  要配置Azure SAS，您需要使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参见 [有关如何分配密钥保管库访问策略的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **密钥保管库机密名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥库的 **密钥库** 设置页面。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **位置帐户密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定以下信息以配置Azure RBAC帐户：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帐户密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   指定以下信息以配置Snowflake帐户：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **帐户标识符**] | 唯一地标识贵公司内的Snowflake帐户，以及遍布全球由Snowflake支持的云平台和云区域组成的网络。 <p>欲了解更多信息，请参见 [“Snowflake标识符”页面](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **用户**] | 指定连接的用户的登录名。 这是将专门用于Adobe的用户。 在此处指定用户名后，即可在Snowflake中创建用户。 <p>欲了解更多信息，请参见 [Snowflake文档中的“JDBC驱动程序连接参数参考”页](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **角色**] | 驱动程序启动的Snowflake会话中使用的默认访问控制角色。 您应该为具有读写权限的Adobe创建特定的角色。<p>欲了解更多信息，请参见 [Snowflake文档中的“JDBC驱动程序连接参数参考”页](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **公钥**] | 公钥由Adobe提供。 选择旁边的“复制”图标 [!UICONTROL **公钥**] 字段以复制字段的内容，然后在您的Snowflake帐户中使用公钥。 欲了解更多信息，请参见 [Snowflake文档中的“密钥对身份验证和密钥对轮换”页面](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   所有Adobe Experience Platform客户都可以将数据导出到AEP登陆区。

   指定以下信息以配置Adobe Experience Platform帐户。

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 组织 ID**] | IMS组织ID由Adobe提供。 单击旁边的复制图标 [!UICONTROL **IMS组织ID**] 字段以复制字段的内容，然后在您的AdobeExperience Platform帐户中使用ID。 |

+++

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

