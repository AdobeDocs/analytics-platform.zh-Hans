---
description: 配置云导出位置以发送Customer Journey Analytics数据
keywords: Analysis Workspace
title: 配置云导出位置
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 8fc8e3e4057663bd4bdf38e41bb3129df442f749
workflow-type: tm+mt
source-wordcount: '1888'
ht-degree: 20%

---

# 配置云导出位置

在按照[将Customer Journey Analytics报表导出到Customer Journey Analytics](/help/analysis-workspace/export/export-cloud.md)中所述将Cloud报表导出到云目标之前，您需要添加并配置希望发送数据的位置。

此过程包括按照[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)中的说明添加和配置帐户(如Amazon S3、Google Cloud Platform等)，然后按照本文中的说明添加和配置该帐户内的位置（如帐户内的文件夹）。

有关如何管理现有位置（包括查看、编辑和删除位置）的信息，请参阅[管理云导出位置和帐户](/help/components/exports/manage-export-locations.md)。

## 开始创建云导出位置

1. 在添加位置之前，您需要添加帐户。 如果还没有帐户，请按照[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)中的说明添加帐户。

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡，然后选择&#x200B;[!UICONTROL **添加位置**]。

   ![选定了“位置”选项卡的“导出”窗口，突出显示“添加位置”按钮](assets/location-add.png)

   或

   选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡，在要添加位置的现有帐户上选择3点图标，然后选择&#x200B;[!UICONTROL **添加位置**]。

   ![GCP帐户和省略号下拉菜单，显示添加选定位置](assets/add-location-existing-account.png)

   此时将显示“位置”对话框。

1. 指定以下信息：
|字段 | 函数 |
&#x200B;-------------------
| [!UICONTROL **名称**] | 位置的名称。  |
| [!UICONTROL **描述**] | 提供位置的简短描述，以帮助将其与帐户上的其他位置区分开来。 |
| [!UICONTROL **使位置对组织中的所有用户都可用**] | 启用此选项可允许组织中的其他用户使用该位置。 <p>共享位置时，请考虑以下事项：</p><ul><li>无法取消共享您共享的位置。</li><li>共享位置只能由位置的所有者编辑。</li><li>仅当与位置关联的帐户也共享时，才能共享位置。</li></ul> |
| [!UICONTROL **位置帐户**] | 选择要创建位置的帐户。 有关如何创建帐户的信息，请参阅[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)。 |

1. 在&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定特定于位置帐户的帐户类型的信息。

   继续下面的部分，该部分对应于您在&#x200B;[!UICONTROL **位置帐户**]&#x200B;字段中选择的帐户类型。

   * [AEP 数据登陆区](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP 数据登陆区

>[!IMPORTANT]
>
>将Customer Journey Analytics报表导出到Adobe Experience Platform数据登陆区时，请确保在7天内下载数据，然后从AEP数据登陆区中删除该数据。 7天后，数据将自动从AEP数据登陆区中删除。

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Adobe Experience Platform数据登录区位置：

   <!-- still need to update; can't create AEP account -->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。

1. 在AEP数据登录区中访问数据的最简单方法是使用Microsoft Azure Storage Explorer。 此工具与配置[AEP数据登录区帐户](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)的说明中使用的工具相同。

   1. 打开[Microsoft Azure存储资源管理器](https://azure.microsoft.com/en-us/products/storage/storage-explorer/)。

   1. 转到&#x200B;[!UICONTROL **存储帐户**] > [!UICONTROL **（附加的容器）**] > [!UICONTROL **Blob容器**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***。

      >[!NOTE]
      >
      >文件夹名称&#x200B;**[!UICONTROL cjaexport-_number_]**是Azure存储资源管理器提供的默认名称。 如果您只有与SAS URI关联的单个连接（正常），则此文件夹的名称将为&#x200B;**[!UICONTROL cjaexport-1]**。


      ![访问Azure存储资源管理器](assets/azure-storage-explorer-access.png)中的文件

   1. 选择要下载的导出，然后选择&#x200B;[!UICONTROL **下载**]&#x200B;进行下载。

### Amazon S3 Role ARN

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Amazon S3 Role ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储桶**] | Amazon S3帐户中要将Customer Journey Analytics数据发送到的存储段。 <p>确保Adobe提供的用户ARN具有`S3:PutObject`权限，以便将文件上载到此存储段。 </p><p>桶名称必须符合特定的命名规则。例如，它们的长度必须在 3 到 63 个字符之间，只能由小写字母、数字、点 (.) 和连字符 (-) 组成，并且必须以字母或数字开头和结尾。[若要了解完整的命名规则列表，请参阅 AWS 文档](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。

### Google Cloud Platform

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Google Cloud Platform位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储桶**] | GCP帐户中要将Customer Journey Analytics数据发送到的存储段。 <p>确保您已向Adobe提供的主体授予`roles/storage.objectCreator`权限。 (在[配置Google Cloud Platform帐户](/help/components/exports/cloud-export-accounts.md)时提供了主体。) <p>有关授予权限的信息，请参阅 Google Cloud 文档中的[将主体添加到存储段级策略](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add)。</p><p>如果您的组织使用[组织策略约束](https://cloud.google.com/storage/docs/org-policy-constraints)，仅允许在允许列表中使用 Google Cloud Platform 帐户，则需要以下 Adobe 拥有的 Google Cloud Platform 组织 ID： <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **前缀**] | 存储段中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。

### Azure SAS

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Azure SAS位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名称**] | 您指定的帐户中要将Customer Journey Analytics数据发送到的容器。 |
   | [!UICONTROL **前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/`<p>确保在配置 Azure SAS 帐户时，在密钥保管库密码名称字段中指定的 SAS 令牌存储具有 `Write` 权限。这将允许 SAS 令牌在 Azure 容器中创建文件。 <p>如果您希望 SAS 令牌也覆盖文件，请确保 SAS 令牌存储具有 `Delete` 权限。</p><p>有关更多信息，请参阅 Azure Blob 存储文档中的 [Blob 存储资源](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)。</p> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。

### Azure RBAC

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Azure RBAC位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定的帐户中要将Customer Journey Analytics数据发送到的容器。 确保授予将文件上传到您之前创建的 Azure 应用程序的权限。 |
   | [!UICONTROL **前缀**] | 容器中要用于放置数据的文件夹。指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/`<p>确保您在配置 Azure RBAC 帐户时指定的应用程序 ID 已被授予 `Storage Blob Data Contributor` 角色，以便访问容器（文件夹）。</p> <p>有关更多信息，请参阅 [Azure 内置角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)。</p> |
   | [!UICONTROL **帐户**] | Azure存储帐户。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。

### Snowflake

1. 通过下列任一方式开始创建云导出位置：

   * 从如上所述的“导出”页面，在[开始创建云导出位置](#begin-creating-a-cloud-export-location)中

   * 当[从Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)导出完整表时

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;对话框的&#x200B;[!UICONTROL **位置属性**]&#x200B;部分中，指定以下信息来配置Snowflake位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **数据库**] | 指定的数据库应为现有数据库。 您创建的角色需要拥有访问此数据库的权限。<p>这是与阶段名称关联的数据库。</p><p>可以使用以下命令向Snowflake中的数据库授予此角色权限： `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>有关详细信息，请参阅Snowflake文档](https://docs.snowflake.com/en/sql-reference/commands-database)中的[数据库、架构和共享命令页。</p> |
   | [!UICONTROL **架构**] | 指定的架构应为现有架构。 您创建的角色需要拥有访问此方案的权限。<p>这是与阶段名称关联的架构。<p>您可以使用以下命令将您创建的权限授予Snowflake中的架构：`GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>有关详细信息，请参阅Snowflake文档](https://docs.snowflake.com/en/sql-reference/commands-database)中的[数据库、架构和共享命令页。</p> |
   | [!UICONTROL **阶段名称**] | 以Snowflake存储数据文件的内部阶段的名称。<p>请确保您在帐户中指定的角色对此阶段名称具有读写访问权限。 (由于您授予了读取和写入权限，因此我们建议使用仅由Adobe使用的阶段。)<p>您可以使用以下命令授予Snowflake中暂存名称的读取和写入权限： `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>有关向角色授予权限的信息，请参阅Snowflake文档](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege)中的[授予权限。 <p>有关暂存名称的详细信息，请参阅Snowflake文档中的[为本地文件选择内部暂存页](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)。</p> |
   | [!UICONTROL **阶段路径**] | 数据文件存储在Snowflake中的位置的路径。 <p>有关详细信息，请参阅Snowflake文档](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)中的[为本地文件选择内部暂存。</p> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)。
