---
description: 配置可发送Customer Journey Analytics数据的云导出帐户
keywords: Analysis Workspace
title: 配置云导出帐户
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 3d4017ba36ac4b0c9ccb10a3e3127c6ea386fb1e
workflow-type: tm+mt
source-wordcount: '1600'
ht-degree: 5%

---

# 配置云导出帐户

在您可以将Customer Journey Analytics报表导出到Cloud目标之前（如所述） [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md)，您需要添加并配置要将数据发送到的目标。

此过程包括按照本文所述添加和配置帐户(例如Amazon S3、Google Cloud Platform等)，然后按照所述添加和配置该帐户内的位置（例如帐户内的文件夹） [配置云导出位置](/help/components/exports/cloud-export-locations.md).

有关如何管理现有帐户（包括查看、编辑和删除帐户）的信息，请参阅 [管理云导出位置和帐户](/help/components/exports/manage-export-locations.md).

## 开始创建云导出帐户

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].
1. 在 [!UICONTROL 导出] 页面上，选择 [!UICONTROL **位置帐户**] 选项卡。
1. 选择 [!UICONTROL **添加帐户**].

   ![添加帐户](assets/account-add.png)

   此时将显示添加帐户对话框。

1. 在 [!UICONTROL **位置帐户名称**] 字段，指定位置帐户的名称。 创建位置时将显示此名称。

1. 在 [!UICONTROL **位置帐户说明**] 字段，提供帐户的简短描述，以帮助将其与同一帐户类型的其他帐户区分开来。

1. 在 [!UICONTROL **帐户类型**] 字段中，选择要导出到的云帐户类型。 可用的帐户类型包括Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和AEP Data Landing Zone。

1. 继续下面的对应章节 [!UICONTROL **帐户类型**] 您已选择。

   * [Adobe Experience Platform数据登陆区](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### AEP数据登陆区

>[!IMPORTANT]
>
>将Customer Journey Analytics报表导出到Adobe Experience Platform数据登陆区时，请确保在7天内下载数据，然后从AEP数据登陆区中删除该数据。 7天后，数据将自动从AEP数据登陆区中删除。

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，将显示以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 组织 ID**] | IMS组织ID由Adobe提供。 通常不需要此信息。 如果您遇到帐户问题并需要联系客户关怀团队，此功能可能会很有用。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 复制 [!UICONTROL **SAS**] 字段到剪贴板。 使用此SAS令牌可访问从Analysis Workspace从AEP登录区域导出的数据。 了解如何访问您的数据&quot; |

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必须提供一个角色ARN(Amazon资源名称)，Adobe可以使用该角色来访问Amazon S3帐户。 为此，您需要为源帐户创建IAM权限策略，将策略附加到用户，然后为目标帐户创建角色。 有关具体信息，请参阅 [此AWS文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 复制 [!UICONTROL **用户ARN**] 字段到剪贴板。 用户ARN(Amazon资源名称)由Adobe提供。 您必须将此用户附加到您在Amazon S3角色ARN中创建的策略。

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **项目ID**] | 从Google Cloud帐户复制的Google Cloud项目ID。 请参阅 [Google Cloud有关获取项目ID的文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 复制 [!UICONTROL **主体**] 字段到剪贴板，然后确保您向主体授予权限，以便在Google Cloud Platform中将文件上传到此存储桶。 <!-- add link to Google Cloud docs on how to do this -->

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **密钥保管库 URI**] | <p>Azure密钥库中SAS令牌的路径。  要配置Azure SAS，您需要使用Azure密钥库将SAS令牌存储为密钥。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>创建密钥保管库URI后，在密钥保管库中添加访问策略，以授予您创建的Azure应用程序的权限。 有关信息，请参见 [有关如何分配密钥保管库访问策略的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **密钥保管库机密名称**] | 将密钥添加到Azure密钥库时创建的密钥名称。 在Microsoft Azure中，此信息位于您创建的密钥库的 **密钥库** 设置页面。 有关信息，请参见 [有关如何从Azure密钥库中设置和检索密钥的Microsoft Azure文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **位置帐户密码**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 如果您尚未这样做，请确保您向Azure SAS中的存储段授予权限。 <!-- add link to Google Cloud docs on how to do this -->

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租户 ID**] | 从您创建的Azure应用程序中复制此ID。 在Microsoft Azure中，此信息位于 **概述** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帐户密码**] | 从您创建的Azure应用程序中复制密钥。 在Microsoft Azure中，此信息位于 **证书和密钥** 选项卡。 欲了解更多信息，请参见 [Microsoft Azure有关如何使用Microsoft Identity Platform注册应用程序的文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 如果您尚未这样做，请确保您向Azure RBAC中的存储段授予权限。 <!-- add link to Google Cloud docs on how to do this -->

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [开始创建云导出帐户](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帐户属性**] 的部分 [!UICONTROL **添加帐户**] 对话框，请指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **帐户标识符**] | 唯一地标识贵公司内的Snowflake帐户，以及遍布全球由Snowflake支持的云平台和云区域组成的网络。 <p>您需要从Snowflake帐户中获取帐户标识符，然后在此处粘贴信息。</p><p>要了解从何处获取此信息，请参阅 [“Snowflake标识符”页面](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **用户**] | 用于连接的用户的登录名。 我们建议创建一个将专门用于Adobe的新用户。 在此处指定名称，然后以Snowflake创建具有相同名称的用户。 您可以使用在Snowflake中创建用户 `CREATE USER` 命令。  <p>欲了解更多信息，请参见 [用户、角色和权限命令](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |
   | [!UICONTROL **角色**] | 将分配给用户的角色。 我们建议创建一个将专门用于Adobe的新角色。 在此处指定角色，然后在Snowflake中创建具有相同名称的角色，并将角色授予用户。 您可以使用在Snowflake中创建角色 `CREATE ROLE` 命令。 <p>欲了解更多信息，请参见 [用户、角色和权限命令](https://docs.snowflake.com/en/sql-reference/commands-user-role).</p> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此 [!UICONTROL **已创建导出帐户**] 对话框随即显示。

   <!-- add screen shot -->

1. 复制 [!UICONTROL **公钥**] 字段到剪贴板。 公钥由Adobe提供。

   在Snowflake中使用公钥连接到Snowflake帐户。 您必须将您创建的用户与此公钥相关联。

   例如，在Snowflake中，指定以下命令：

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   欲了解更多信息，请参见 [Snowflake文档中的“密钥对身份验证和密钥对轮换”页面](https://docs.snowflake.com/en/user-guide/key-pair-auth).

1. 选择 [!UICONTROL **确定**].

1. 继续 [配置云导出位置](/help/components/exports/cloud-export-locations.md).



