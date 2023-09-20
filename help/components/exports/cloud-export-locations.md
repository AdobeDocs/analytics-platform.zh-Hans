---
description: 配置云导出位置以发送Customer Journey Analytics数据
keywords: Analysis Workspace
title: 配置云导出位置
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 6%

---

# 配置云导出位置

{{select-package}}

在您可以将Customer Journey Analytics数据导出到云目标之前（如所述） [将Customer Journey Analytics数据导出到云端](/help/analysis-workspace/export/export-cloud.md)，您需要添加并配置发送数据的位置。

此过程包括添加和配置帐户(例如Amazon S3、Google Cloud Platform等)，如中所述 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md)，然后在该帐户中添加和配置位置（例如帐户中的文件夹），如本文所述。

有关如何管理现有位置（包括查看、编辑和删除位置）的信息，请参阅 [管理云导出位置和帐户](/help/components/exports/manage-export-locations.md).

要配置云导出位置，请执行以下操作：

1. 在添加位置之前，您需要添加帐户。 如果还没有帐户，请按照中的说明添加帐户 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md).
1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].
1. 在 [!UICONTROL 导出] 页面上，选择 [!UICONTROL **位置**] 选项卡。
1. 选择 [!UICONTROL **添加位置**].

   ![添加位置按钮](assets/location-add.png)

   此时将显示“位置”对话框。

1. 指定以下信息： |字段 |函数 | ------------------- | [!UICONTROL **名称**] |位置的名称。  | | [!UICONTROL **描述**] |提供帐户的简短描述，以帮助将其与相同帐户类型的其他帐户区分开来。 | | [!UICONTROL **位置帐户**] |选择您在中创建的位置帐户 [配置云导出帐户](/help/components/exports/cloud-export-accounts.md). |

1. 在 [!UICONTROL **位置属性**] 部分，指定特定于您的位置帐户的帐户类型的信息。

   有关配置说明，请展开以下与您在 [!UICONTROL **位置帐户**] 字段。

   +++Amazon S3 Role ARN

   指定以下信息以配置Amazon S3角色ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储段**] | Amazon S3帐户中要将Adobe Analytics数据发送到的存储段。 确保Adobe提供的用户ARN有权将文件上传到此存储段。 |
   | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定以下信息来配置Google Cloud Platform位置：

   <!-- still need to update; can't create GCP account -->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **存储段**] | GCP帐户中要将Customer Journey Analytics数据发送到的存储段。 确保您已授予Adobe提供的承担者将文件上传到此存储段的权限。 (本金于呈报日期 [配置Google Cloud平台帐户](/help/components/exports/cloud-export-accounts.md).) 有关授予权限的信息，请参见 [将主体添加到存储段级别策略](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) 在Google Cloud文档中。 |
   | [!UICONTROL **前缀**] | 存储桶中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定以下信息以配置Azure SAS位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名称**] | 您指定的帐户中要将Customer Journey Analytics数据发送到的容器。 |
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定以下信息以配置Azure RBAC位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定的帐户中要将Adobe Analytics数据发送到的容器。 确保授予将文件上载到您之前创建的Azure应用程序的权限。 |
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |
   | [!UICONTROL **帐户**] | Azure存储帐户。 |

   {style="table-layout:auto"}

+++

   +++Snowflake

   指定以下信息以配置Snowflake位置：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **DB**] | 连接后使用的默认数据库，或指定一个空字符串。 指定的数据库应为指定默认角色具有权限的现有数据库。 <p>欲了解更多信息，请参见 [Snowflake文档中的“JDBC驱动程序连接参数参考”页](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **架构**] | 连接后用于指定数据库的默认架构，或指定空字符串。 指定的架构应为指定默认角色具有权限的现有架构。 <p>欲了解更多信息，请参见 [Snowflake文档中的“JDBC驱动程序连接参数参考”页](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **阶段名称**] | 数据文件在Snowflake中存储位置的名称。 <p>欲了解更多信息，请参见 [在Snowflake文档中选择“本地文件的内部暂存”页](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **阶段路径**] | 数据文件存储在Snowflake中的位置的路径。 <p>欲了解更多信息，请参见 [在Snowflake文档中选择“本地文件的内部暂存”页](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   指定以下信息以配置Adobe Experience Platform位置：

   <!-- still need to update; can't create AEP account -->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 组织 ID**] | IMS组织ID由Adobe提供。 单击旁边的复制图标 [!UICONTROL **IMS组织ID**] 字段以复制字段的内容，然后在您的AdobeExperience Platform帐户中使用ID。 |
   | [!UICONTROL **前缀**] | 容器中要放置数据的文件夹。 指定文件夹名称，然后在名称后添加反斜杠以创建文件夹。 例如，`folder_name/` |

+++

1. 选择&#x200B;[!UICONTROL **保存**]。

1. 您现在可以将数据从Analysis Workspace导出到您配置的帐户和位置。 有关如何将数据导出到云的信息，请参阅 [将项目数据导出到云](/help/analysis-workspace/export/export-cloud.md).