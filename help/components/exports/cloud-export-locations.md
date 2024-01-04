---
description: 配置云导出位置以发送Customer Journey Analytics数据
keywords: Analysis Workspace
title: 配置云导出位置
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 3%

---

# 配置云导出位置

在您可以将Customer Journey Analytics报表导出到Cloud目标之前（如所述） [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md)，您需要添加并配置发送数据的位置。

此过程包括添加和配置帐户(例如Amazon S3、Google Cloud Platform等)，如中所述 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md)，然后在该帐户中添加和配置位置（例如帐户中的文件夹），如本文所述。

有关如何管理现有位置（包括查看、编辑和删除位置）的信息，请参阅 [管理云导出位置和帐户](/help/components/exports/manage-export-locations.md).

## 开始创建云导出位置

1. 在添加位置之前，您需要添加帐户。 如果还没有帐户，请按照中的说明添加帐户 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md).

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置**] 选项卡，然后选择 [!UICONTROL **添加位置**].

   ![已选中“位置”选项卡并突出显示“添加位置”按钮的“导出”窗口](assets/location-add.png)

   或

   选择 [!UICONTROL **位置帐户**] 选项卡，选择要添加位置的现有帐户上的3点图标，然后选择 [!UICONTROL **添加位置**].

   ![GCP帐户和省略号下拉菜单，其中显示已选择添加位置](assets/add-location-existing-account.png)

   此时将显示“位置”对话框。

1. 指定以下信息： |字段 | 函数 | ------------------- | [!UICONTROL **名称**] | 位置的名称。  | | [!UICONTROL **描述**] | 提供帐户的简短描述，以帮助将其与同一帐户类型的其他帐户区分开来。 | | [!UICONTROL **位置帐户**] | 选择要创建位置的帐户。 有关如何创建帐户的信息，请参阅 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md). |

1. 在 [!UICONTROL **位置属性**] 部分，指定特定于您的位置帐户的帐户类型的信息。

   继续下面的部分，该部分与您在 [!UICONTROL **位置帐户**] 字段。

### AEP 数据登陆区

>[!IMPORTANT]
>
>将Customer Journey Analytics报表导出到Adobe Experience Platform数据登陆区时，请确保在7天内下载数据，然后从AEP数据登陆区中删除该数据。 7天后，数据将自动从AEP数据登陆区中删除。

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框中，指定以下信息来配置Adobe Experience Platform数据登录区位置：

   <!-- still need to update; can't create AEP account -->

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).

1. 在AEP数据登录区中访问数据的最简单方法是使用Microsoft Azure Storage Explorer。 此工具与配置 [AEP数据登陆区帐户](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. 打开 [Microsoft Azure存储资源管理器](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. 转到 [!UICONTROL **存储帐户**] > [!UICONTROL **（附加的容器）**] > [!UICONTROL **Blob容器**] > **[!UICONTROL cjaexport-_数字_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >文件夹名称 **[!UICONTROL cjaexport-_数字_]**是Azure存储资源管理器提供的默认名称。 如果您只有与SAS URI关联的单个连接（正常），则此文件夹的名称将为&#x200B;**[!UICONTROL cjaexport-1]**.


      ![访问Azure存储资源管理器中的文件](assets/azure-storage-explorer-access.png)

   1. 选择要下载的导出，然后选择 [!UICONTROL **下载**] 下载。

### Amazon S3 Role ARN

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框中，指定以下信息来配置Amazon S3 Role ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **分段**] | Amazon S3帐户中要将Adobe Analytics数据发送到的存储段。 确保Adobe提供的用户ARN有权将文件上传到此存储段。 |
   | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如， folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框中，指定以下信息来配置Google Cloud Platform位置：

   <!-- still need to update; can't create GCP account -->

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **分段**] | GCP帐户中要将Customer Journey Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 (本金于呈报日期 [配置Google Cloud平台帐户](/help/components/exports/cloud-export-accounts.md).) 有关授予权限的信息，请参见 [将主体添加到存储段级别策略](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) 在Google Cloud文档中。 |
   | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如， folder_name/ |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框，请指定以下信息以配置Azure SAS位置：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **容器名称**] | 您指定的帐户中要将Customer Journey Analytics数据发送到的容器。 |
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/` |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框，请指定以下信息以配置Azure RBAC位置：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 确保授予将文件上载到您之前创建的Azure应用程序的权限。 |
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加斜杠以创建文件夹。 例如，`folder_name/` |
   | [!UICONTROL **帐户**] | Azure存储帐户。 |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. [开始创建云导出位置](#begin-creating-a-cloud-export-location)，如上所述。

1. 在 [!UICONTROL **位置属性**] 的部分 [!UICONTROL **添加位置**] 对话框中，指定以下信息来配置Snowflake位置：

   | 字段 | 函数 |
   |---------|----------|
   | [!UICONTROL **DB**] | 指定的数据库应为现有数据库。 您创建的角色需要拥有访问此数据库的权限。<p>这是与阶段名称关联的数据库。</p><p>可以使用以下命令将此角色权限授予Snowflake中的数据库： `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>欲了解更多信息，请参见 [Snowflake文档中的“数据库、方案和共享命令”页](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **架构**] | 指定的架构应为现有架构。 您创建的角色需要拥有访问此方案的权限。<p>这是与阶段名称关联的架构。<p>可以使用以下命令将您创建的权限授予Snowflake中的方案： `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>欲了解更多信息，请参见 [Snowflake文档中的“数据库、方案和共享命令”页](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **阶段名称**] | 以Snowflake存储数据文件的内部阶段的名称。<p>请确保您在帐户中指定的角色对此阶段名称具有读写访问权限。 (由于您授予了读取和写入权限，因此我们建议使用仅由Adobe使用的阶段。)<p>可以使用以下命令授予Snowflake中阶段名称的读取和写入权限： `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>有关向角色授予权限的信息，请参见 [在Snowflake文档中授予权限](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>有关阶段名称的更多信息，请参见 [在Snowflake文档中选择“本地文件的内部暂存”页](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **暂存路径**] | 数据文件存储在Snowflake中的位置的路径。 <p>欲了解更多信息，请参见 [在Snowflake文档中选择“本地文件的内部暂存”页](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).
