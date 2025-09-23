---
title: 配置Customer Journey Analytics
description: 了解如何为Experience Platform Data Mirror for Customer Journey Analytics配置Customer Journey Analytics连接、数据视图和项目
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta 版"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# 配置Customer Journey Analytics

要对Customer Journey Analytics使用Experience Platform Data Mirror功能，您必须创建或更新连接、数据视图和工作区项目，以使用基于模型的数据。

## 连接

在您的连接中，添加基于模型的数据集，以表示来自数据仓库本机解决方案的数据。 这些数据集具有模型数据集类型。

添加基于模型的数据集时，如果其中包含来自Data Warehouse本机解决方案的镜像数据，则该数据通常是事件数据。 请确保为数据集选择正确的设置。 例如，选择正确的数据集类型、标识字段和时间戳字段。


## 数据视图

将基于模型的架构中的字段定义为数据视图中的组件（量度和维度）。 数据镜像字段在&#x200B;**[!UICONTROL 事件数据集]**&#x200B;文件夹的&#x200B;**[!UICONTROL 临时和基于模型的字段]**&#x200B;子文件夹中可用。 使用诸如[派生字段](/help/data-views/derived-fields/derived-fields.md)或[组件设置](/help/data-views/component-settings/overview.md)之类的功能来修改基于基于模型的字段的组件。


## Workspace 项目

设置使用来自您的基于模型的数据的量度和维度的Workspace项目。 最终基于Data Warehouse本机解决方案中数据的组件。 并根据您配置的数据镜像功能对和进行更新。

>[!MORELIKETHIS]
>
>[Data Mirror快速入门指南：镜像并使用基于模型的数据](data-mirror.md)
>