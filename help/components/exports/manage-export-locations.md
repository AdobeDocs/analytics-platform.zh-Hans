---
description: 管理可发送Customer Journey Analytics数据的云导出位置
keywords: Analysis Workspace
title: 管理云导出位置和帐户
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 管理云导出位置和帐户

您可以查看、编辑和删除云导出位置。

有关如何创建新位置的信息，请参阅 [配置云导出位置](/help/components/exports/cloud-export-locations.md).

## 过滤和搜索位置

要查找所需的信息，可以筛选位置列表或搜索位置。

### 筛选位置列表

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置**] 选项卡。

1. 选择 **筛选** 图标。

   <!-- add screenshot -->

   您可以按以下条件进行筛选：

   | 过滤器 | 描述 |
   |---------|----------|
   | [!UICONTROL **位置类型**]<!--should this be changed to Account type?--> | 与位置关联的帐户类型。 可以使用以下帐户类型： <ul><li>[!UICONTROL **AEP 数据登陆区**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **帐户**] | 与位置关联的帐户的名称。 |
   | [!UICONTROL **创建者**] | 创建位置的用户的电子邮件地址。 |

   {style="table-layout:auto"}

### 搜索位置

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置**] 选项卡。

1. 在搜索字段中，开始键入与要搜索的位置相关联的任何信息。 您可以从表中任何可用的列搜索数据。

## 编辑位置

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置**] 选项卡，然后选择要编辑的位置。

   ![显示位置选项卡和位置列表的“导出”窗口。](assets/locations-edit.png)

1. 选择 [!UICONTROL **编辑**].

1. 进行任何所需的更改，然后选择 [!UICONTROL **保存**].

## 删除位置

如果删除位置，则使用该位置的所有导出也会被删除。 删除时选中确认对话框，以确保没有导出与位置相关联。

要删除位置，请执行以下操作：

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置**] 选项卡，然后选择要删除的一个或多个位置。

   ![显示位置选项卡和位置列表的“导出”窗口](assets/locations-edit.png)

1. 选择&#x200B;[!UICONTROL **删除**]。

   此时将显示“删除位置”对话框。

1. 在“删除位置”对话框中，在确认删除之前，请确保该位置未与任何导出相关联。

   ![删除位置确认对话框](assets/delete-location-confirmation-dialog.png)

1. 选择 [!UICONTROL **删除**] 再次确认。

## 编辑帐户

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置帐户**] 选项卡。

   ![显示位置帐户选项卡的“导出”窗口](assets/account-add.png)

1. 选择 [!UICONTROL **查看详细信息**] 在要编辑的帐户上。

1. 进行任何所需的更改，然后选择 [!UICONTROL **保存**].

## 查看帐户密钥

创建帐户后，您可以查看该帐户的任何关联帐户密钥。 如果您没有通过云提供商完成帐户配置，则可能需要查看此信息 [当您最初配置帐户时](/help/components/exports/cloud-export-accounts.md).

要查看与导出帐户关联的密钥，请执行以下操作：

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置帐户**] 选项卡。

   ![显示位置帐户选项卡的“导出”窗口](assets/account-add.png)

1. 在要编辑的帐户上选择3点图标，然后选择 [!UICONTROL **帐户密钥**].

## 删除帐户

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **位置帐户**] 选项卡。

   ![显示位置帐户选项卡的“导出”窗口](assets/account-add.png)

1. 在要编辑的帐户上选择3点图标，然后选择 [!UICONTROL **删除帐户**].

1. 选择 [!UICONTROL **删除**] 确认对话框。
