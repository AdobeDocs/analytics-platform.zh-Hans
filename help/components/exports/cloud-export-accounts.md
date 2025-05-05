---
description: 配置可发送Customer Journey Analytics数据的云导出帐户
keywords: Analysis Workspace
title: 配置云导出帐户
feature: Components
exl-id: 7c9d100f-0dbd-4dd2-b20b-d2ee117f1b7a
role: User, Admin
source-git-commit: cb4c2721867585fd11c0929f0947436872272da6
workflow-type: tm+mt
source-wordcount: '2230'
ht-degree: 26%

---

# 配置云导出帐户

在按照[将Customer Journey Analytics报表导出到Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md)中所述将Cloud报表导出到云目标之前，您需要添加并配置要将数据发送到的目标。

此过程包括按照本文所述添加和配置帐户(如Amazon S3、Google Cloud Platform等)，然后按照[配置云导出位置](/help/components/exports/cloud-export-locations.md)中所述，添加和配置该帐户内的位置（如帐户内的文件夹）。

有关如何管理现有帐户（包括查看、编辑和删除帐户）的信息，请参阅[管理云导出位置和帐户](/help/components/exports/manage-export-locations.md)。

## 开始创建云导出帐户

1. 确保您满足将报表导出到云的[最低要求](/help/analysis-workspace/export/export-cloud.md#minimum-requirements)。
1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。
1. 在[!UICONTROL 导出]页上，选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

   ![导出页面选项显示添加其他帐户](assets/account-add.png)

1. 选择&#x200B;[!UICONTROL **添加帐户**]。

   此时将显示添加帐户对话框。

1. 在&#x200B;[!UICONTROL **位置帐户名称**]&#x200B;字段中，指定位置帐户的名称。 创建位置时将显示此名称。

1. 在&#x200B;[!UICONTROL **位置帐户说明**]&#x200B;字段中，提供帐户的简短说明，以帮助区分该帐户与相同帐户类型的其他帐户。

1. 启用选项&#x200B;[!UICONTROL **如果您希望允许组织中的其他用户使用该帐户，则让组织中的所有用户都可以使用该帐户**]。

   共享帐户时，请考虑以下事项：

   * 无法取消共享您共享的帐户。

   * 共享帐户只能由帐户的所有者编辑。

   * 任何人都可以为共享帐户创建位置。

1. 在&#x200B;[!UICONTROL **帐户类型**]&#x200B;字段中，选择要导出到的云帐户类型。 可用的帐户类型包括Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和AEP Data Landing Zone。

1. 继续下面的部分，该部分与您选择的&#x200B;[!UICONTROL **帐户类型**]&#x200B;相对应。

   * [AEP 数据登陆区](#aep-data-landing-zone)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### AEP 数据登陆区

>[!IMPORTANT]
>
>在为导出帐户使用AEP数据登陆区时，请考虑以下事项：
>
> * 将Customer Journey Analytics报表导出到Adobe Experience Platform数据登陆区时，请确保在7天内下载数据，然后从AEP数据登陆区中删除该数据。 7天后，数据将自动从AEP数据登陆区中删除。
> * AEP数据登录区域使用Azure或AWS Storage。 如果您的组织使用配置为使用Azure的登录公司，则AEP数据登录区域使用Azure。 如果登录公司配置为使用AWS，则AEP Data Landing Zone将使用AWS。
>

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;**[!UICONTROL 帐户类型]**&#x200B;字段中选择&#x200B;**[!UICONTROL AEP数据登录区]**&#x200B;后，选择&#x200B;[!UICONTROL **保存**]。

   根据您的AEP数据登录区配置为使用Azure还是AWS Storage，系统将显示以下任一对话框：

   * **Azure存储：**

     此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

     ![导出帐户对话框AEP数据登录区](assets/export-account-aep.png)

   * **AWS存储：**

     >[!AVAILABILITY]
     >
     >本节适用于在Amazon Web Services (AWS)上运行的Experience Platform的实施。 在AWS上运行的Experience Platform当前仅对有限数量的客户可用。 要了解有关支持的Experience Platform基础架构的更多信息，请参阅[Experience Platform多云概述](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud)。

     显示&#x200B;[!UICONTROL **创建的帐户**]&#x200B;对话框。

     ![导出帐户对话框AEP数据登录区](assets/export-account-aep-aws.png)

1. （视情况而定）如果您使用的是Azure存储：

   1. 将&#x200B;[!UICONTROL **SAS URI**]&#x200B;字段的内容复制到剪贴板。 您将使用此SAS URI访问从Analysis Workspace从AEP数据登陆区导出的数据。

      如果此字段为空，您需要被授予访问Adobe Experience Platform的权限。

   1. 在Adobe Experience Platform中，配置数据登陆区容器以使用您复制的SAS URI。

      >[!NOTE]
      >
      >使用基于Azure的AEP数据登陆区帐户时，访问导出到AEP数据登陆区的报告的最简单方法是使用Azure存储资源管理器。 以下步骤使用此方法。

      1. 如果没有，请下载[Microsoft Azure Storage Explorer](https://azure.microsoft.com/en-us/products/storage/storage-explorer/)。

      1. 在Adobe Experience Platform文档中，按照[将数据登陆区域容器连接到Azure Storage Explorer](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#connect-your-data-landing-zone-container-to-azure-storage-explorer)中描述的步骤操作。

         您可以跳过[检索数据登陆区域的凭据](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#retrieve-dlz-credentials)和[更新数据登陆区域凭据](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone.html#update-dlz-credentials)部分中描述的任务，因为您复制的URI包含这些凭据。

      1. 在遵循Adobe Experience Platform文档并进入&#x200B;[!UICONTROL **Blob容器SAS URL**]&#x200B;字段时，粘贴您在步骤3中复制的SAS URI。

         >[!NOTE]
         >
         >您需要每7天执行一次此操作，因为SAS URI在创建后7天过期。 您可以创建一个脚本来自动执行此过程。

         ![输入显示SAS URL字段的连接信息窗口](assets/blob-container-sas-uri.png)

   1. 选择&#x200B;[!UICONTROL **下一步**] > [!UICONTROL **连接**]。

   1. 在Customer Journey Analytics的&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框中，选择&#x200B;[!UICONTROL **确定**]。

      ![导出帐户对话框AEP数据登录区](assets/export-account-aep.png)

1. （视情况而定）如果您使用的是AWS存储：

   1. 将以下字段的内容复制到剪贴板(您将使用此信息访问从Analysis Workspace从AEP数据登录区域导出的数据)：

      * [!UICONTROL **访问密钥ID**]

      * **[!UICONTROL 访问密钥]**

      * **[!UICONTROL 会话令牌]**

      * **[!UICONTROL 存储段名称]**

      * **[!UICONTROL DLZ文件夹]**

      ![导出帐户对话框AEP数据登录区](assets/export-account-aep-aws.png)

   1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

### Amazon S3 Role ARN

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框的&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必须提供角色 ARN（Amazon 资源名称），Adobe 可以使用它来获取对 Amazon S3 帐户的访问权限。为此，您需要为源帐户创建 IAM 权限策略，将该策略附加到用户，然后为目标帐户创建角色。有关特定信息，请参阅[此 AWS 文档](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/)。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

   ![导出帐户创建对话框Amazon S3角色ARN](assets/export-account-amazons3.png)

1. 将&#x200B;[!UICONTROL **用户ARN**]&#x200B;字段的内容复制到剪贴板。 用户 ARN（Amazon 资源名称）由 Adobe 提供。您必须将此用户附加到您在Amazon S3角色ARN中创建的策略。

1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

### Google Cloud Platform

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框的&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **项目 ID**] | 从Google Cloud帐户复制的Google Cloud项目ID。 请参阅[有关获取项目 ID 的 Google Cloud 文档](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects)。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

   ![导出帐户创建的对话框](assets/export-account-gcp.png)

1. 将&#x200B;[!UICONTROL **主体**]&#x200B;字段的内容复制到剪贴板，然后确保您向主体授予权限，以便在Google Cloud Platform中将文件上载到此存储段。<!-- add link to Google Cloud docs on how to do this -->

1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

### Azure SAS

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框的&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **密钥保管库 URI**] | <p>Azure Key Vault 中 SAS URI 的路径。要配置 Azure SAS，需要使用 Azure Key Vault 将 SAS URI 存储为密码。有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。</p><p>创建密钥保管库 URI 后：<ul><li>在密钥保管库上添加访问策略，以便向您创建的 Azure 应用程序授予权限。<p><p>有关信息，请参阅[有关如何分配密钥保管库访问策略的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal)。</p>或</p><p>如果要直接授予访问角色而不创建访问策略，请参阅[Microsoft Azure文档，了解如何使用Azure门户分配Azure角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal)。 这会添加应用程序ID的角色分配，以访问密钥保管库URI。 </p></li><li>确保已将应用程序 ID 授予 `Key Vault Certificate User` 内置角色，以便访问密钥保管库 URI。</br><p>有关更多信息，请参阅 [Azure 内置角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)。</p></li></ul> |
   | [!UICONTROL **密钥保管库密码名称**] | 将密码添加到 Azure 密钥保管库时创建的密码名称。在 Microsoft Azure 中，此信息位于您在&#x200B;**密钥保管库**&#x200B;设置页面上创建的密钥保管库中。有关信息，请参阅[有关如何从 Azure 密钥保管库设置和检索密码的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations)。 |
   | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关详细信息，请参阅[Microsoft Azure文档，了解如何向Microsoft Identity Platform注册应用程序](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。<!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

   ![导出帐户创建的对话框](assets/export-account-azure.png)

1. 如果您尚未这样做，请确保向Azure SAS中的存储段授予权限。<!-- add link to Google Cloud docs on how to do this -->

1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

### Azure RBAC

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框的&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **应用程序 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **租户 ID**] | 从您创建的 Azure 应用程序复制此 ID。在 Microsoft Azure 中，此信息位于应用程序内的&#x200B;**概述**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |
   | [!UICONTROL **位置帐户密码**] | 从您创建的 Azure 应用程序复制密码。在 Microsoft Azure 中，此信息位于应用程序中的&#x200B;**证书和密码**&#x200B;选项卡上。有关更多信息，请参阅[有关如何向 Microsoft 身份标识平台注册应用程序的 Microsoft Azure 文档](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

   ![导出帐户创建的对话框](assets/export-account-azure.png)

1. 如果您尚未这样做，请确保向Azure RBAC中的存储段授予权限。<!-- add link to Google Cloud docs on how to do this -->

1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

### Snowflake

1. 通过以下任一方式开始创建云导出帐户：

   * 如上所述，从“导出”页面中，在[开始创建云导出帐户](#begin-creating-a-cloud-export-account)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加帐户**]&#x200B;对话框的&#x200B;[!UICONTROL **帐户属性**]&#x200B;部分中，指定以下信息：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **帐户标识符**] | 唯一地标识贵公司内的Snowflake帐户，以及遍布全球由Snowflake支持的云平台和云区域组成的网络。 <p>您需要从Snowflake帐户中获取帐户标识符，然后在此处粘贴信息。</p><p>若要了解从何处获取此信息，请参阅Snowflake文档[&#128279;](https://docs.snowflake.com/en/user-guide/admin-account-identifier)中的帐户标识符页面。</p> |
   | [!UICONTROL **用户**] | 用于连接的用户的登录名。 我们建议创建一个将专门用于Adobe的新用户。 在此处指定名称，然后以Snowflake创建具有相同名称的用户。 您可以使用`CREATE USER`命令在Snowflake中创建用户。  <p>有关详细信息，请参阅[用户、角色和权限命令](https://docs.snowflake.com/en/sql-reference/commands-user-role)。</p> |
   | [!UICONTROL **角色**] | 将分配给用户的角色。 我们建议创建一个将专门用于Adobe的新角色。 在此处指定角色，然后在Snowflake中创建具有相同名称的角色，并将角色授予用户。 您可以使用`CREATE ROLE`命令在Snowflake中创建角色。 <p>有关详细信息，请参阅[用户、角色和权限命令](https://docs.snowflake.com/en/sql-reference/commands-user-role)。</p> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

   此时将显示&#x200B;[!UICONTROL **导出帐户创建**]&#x200B;对话框。

   ![导出帐户创建的对话框](assets/export-account-snowflake.png)

1. 将&#x200B;[!UICONTROL **公钥**]&#x200B;字段的内容复制到剪贴板。 公钥由Adobe提供。

   在Snowflake中使用公钥连接到Snowflake帐户。 您必须将您创建的用户与此公钥相关联。

   例如，在Snowflake中，指定以下命令：

   ```
   CREATE USER <your_adobe_user> RSA_PUBLIC_KEY = '<your_public_key>';
   ```

   有关详细信息，请参阅Snowflake文档[&#128279;](https://docs.snowflake.com/en/user-guide/key-pair-auth)中的密钥对身份验证和密钥对轮换页面。

1. 选择&#x200B;[!UICONTROL **确定**]。

1. 继续[配置云导出位置](/help/components/exports/cloud-export-locations.md)。
