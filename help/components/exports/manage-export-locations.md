---
description: 管理可将Customer Journey Analytics数据发送到的云导出位置
keywords: Analysis Workspace
title: 管理云导出位置和帐户
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '1371'
ht-degree: 3%

---

# 管理云导出位置和帐户

您可以查看、编辑和删除云导出位置。

有关如何创建新位置的信息，请参阅[配置云导出位置](/help/components/exports/cloud-export-locations.md)。

## 过滤和搜索位置

要查找所需的信息，您可以在位置列表中进行筛选或搜索位置。

### 筛选位置列表

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. 选择&#x200B;**筛选器**&#x200B;图标。

   <!-- add screenshot -->

   您可以按以下条件进行筛选：

   | 过滤器 | 描述 |
   |---------|----------|
   | [!UICONTROL **位置类型**]<!--should this be changed to Account type?--> | 与位置关联的帐户类型。 可以使用以下帐户类型： <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **帐户**] | 与位置关联的帐户的名称。 |
   | [!UICONTROL **创建者**] | 创建位置的用户的电子邮件地址。 |

   {style="table-layout:auto"}

### 搜索位置

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 在搜索字段中，开始键入与要搜索的位置相关联的任何信息。 您可以从表中任何可用的列搜索数据。

## 编辑位置

位置只能由创建该位置的用户或系统管理员编辑。

要编辑位置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择要编辑的位置。

   ![显示“位置”选项卡和位置列表的“导出”窗口。](assets/locations-edit.png)

1. 选择&#x200B;[!UICONTROL **编辑**]。

1. 进行任何所需的更改，然后选择&#x200B;[!UICONTROL **保存**]。

## 删除位置

如果删除位置，则使用该位置的所有导出也会被删除。 删除时选中确认对话框，以确保没有导出与位置相关联。

要删除位置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置**]&#x200B;选项卡。

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的位置**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择一个或多个要删除的位置。

   ![显示“位置”选项卡和位置列表的“导出”窗口](assets/locations-edit.png)

1. 选择&#x200B;[!UICONTROL **删除**]。

   此时将显示“删除位置”对话框。

1. 在“删除位置”对话框中，在确认删除之前，请确保该位置未与任何导出相关联。

   ![删除位置确认对话框](assets/delete-location-confirmation-dialog.png)

1. 再次选择&#x200B;[!UICONTROL **删除**]&#x200B;以确认。

## 编辑帐户

帐户只能由创建该帐户的用户或系统管理员编辑。

要编辑帐户，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

   显示“位置帐户”选项卡的![导出窗口](assets/account-add.png)

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的帐户**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择&#x200B;[!UICONTROL **查看要编辑的帐户的详细信息**]。

1. 进行任何所需的更改，然后选择&#x200B;[!UICONTROL **保存**]。

## 查看帐户密钥

创建帐户后，您可以查看该帐户的任何关联帐户密钥。 如果您在最初配置帐户[&#128279;](/help/components/exports/cloud-export-accounts.md)时没有完成与云提供商的帐户配置，您可能需要查看此信息。

要查看与导出帐户关联的密钥，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

   显示“位置帐户”选项卡的![导出窗口](assets/account-add.png)

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的帐户**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择要编辑的帐户上的3点图标，然后选择&#x200B;[!UICONTROL **帐户密钥**]。

## 删除帐户

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **位置帐户**]&#x200B;选项卡。

   显示“位置帐户”选项卡的![导出窗口](assets/account-add.png)

1. （视情况而定）如果您是系统管理员，则可以启用&#x200B;[!UICONTROL **查看所有用户的帐户**]&#x200B;选项以查看由您组织中的所有用户创建的位置。

1. 选择要编辑的帐户上的3点图标，然后选择&#x200B;[!UICONTROL **删除帐户**]。

1. 在确认对话框上再次选择&#x200B;[!UICONTROL **删除**]。

## 配置公司范围的设置（仅限管理员）

系统管理员可以限制用户创建帐户和位置，也可以限制用户可以创建和使用的帐户类型。

![管理员设置选项卡](assets/locations-admin-settings.png)

### 配置用户是否可以创建和编辑帐户

默认情况下，组织中的所有用户都可以创建帐户并编辑他们在Customer Journey Analytics环境中创建的帐户，如[配置Cloud Export帐户](/help/components/exports/cloud-export-accounts.md)中所述。

您可以限制用户创建帐户。 执行此操作时，用户仍可以使用他们已创建的任何帐户，但无法再编辑这些帐户。 您可以删除用户已创建的帐户，如[删除帐户](#delete-an-account)中所述。

要限制所有用户创建和编辑帐户，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 导出]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **位置帐户**]&#x200B;部分中，取消选择选项&#x200B;[!UICONTROL **允许用户创建和管理位置帐户**]。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. （可选）按照[删除帐户](#delete-an-account)中的说明，删除用户已创建但不再希望他们使用的任何帐户。

### 配置用户是否可以创建和编辑位置

默认情况下，组织中的所有用户都可以在Customer Journey Analytics环境中创建位置并编辑他们创建的位置，如[配置云导出位置](/help/components/exports/cloud-export-locations.md)中所述。

您可以限制用户创建位置。 执行此操作时，用户仍可以使用他们已创建的任何位置，但无法再编辑这些位置。 您可以删除用户已创建的位置，如[删除位置](#delete-a-location)中所述。

要限制所有用户创建和编辑位置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 报表]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;部分中，取消选择选项&#x200B;[!UICONTROL **允许用户创建和管理位置**]。

1. 选择&#x200B;[!UICONTROL **保存**]。

1. （可选）按照[删除位置](#delete-a-location)中的说明，删除用户已创建但不再希望他们使用的任何位置。

### 限制用户可以创建和使用的帐户类型

在以下情况下，您可以限制用户看到的帐户类型：

* 在[创建新帐户](/help/components/exports/cloud-export-accounts.md)时。
* 在使用[完整表导出](/help/analysis-workspace/export/export-cloud.md)导出文件时选择使用哪些帐户时。

当按本节所述限制帐户类型时，用户将无法再看到您限制的任何类型的帐户。 这意味着在使用完整表导出导出文件时，无法创建该类型的新帐户，并且无法使用该类型的现有帐户。

但是，如果要限制使用为计划导出配置的现有帐户，则必须删除这些帐户。

#### 确保未将帐户用于计划导出

限制帐户类型时，会隐藏现有帐户，而不会删除现有帐户。

如果计划已配置为将数据发送到您限制类型的帐户，则即使在您限制帐户类型后，计划仍将继续运行，并且数据将继续发送到该帐户。 例如，如果计划了完全表导出，以将数据发送到您限制的帐户类型，则计划将继续运行。

如果您需要确保特定类型的帐户未在计划导出中使用，则可以在[限制帐户类型](#limit-the-account-types-that-are-available-to-users)之前删除这些帐户。

要删除帐户，请执行以下操作：

1. 找到计划限制的帐户类型的帐户，这些帐户正用于计划导出。

1. 按照[删除帐户](#delete-an-account)中的说明删除帐户。

1. 继续下面的部分，[限制用户可用的帐户类型](#limit-the-account-types-that-are-available-to-users)。

#### 限制用户可用的帐户类型

要限制用户在创建和使用帐户时可用的帐户类型，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 导出]**，然后选择&#x200B;[!UICONTROL **管理员设置**]&#x200B;选项卡。

1. 找到&#x200B;[!UICONTROL **允许的帐户类型**]&#x200B;部分。

   默认情况下，用户可以使用以下帐户类型。 取消选择要限制用户使用的任意帐户类型。

   * [!UICONTROL **AEP Data Landing Zone**]

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Snowflake**]

1. 选择&#x200B;[!UICONTROL **保存**]。
