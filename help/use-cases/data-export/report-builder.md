---
title: Customer Journey Analytics Report Builder
description: 介绍如何使用Report Builder将Customer Journey Analytics数据提取到Excel中以生成重复报表。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

本文概述如何使用[!DNL Report Builder]实现以下[数据导出用例](overview.md)：

* 临时和定期报表

## 简介

[!DNL Report Builder] [!DNL Report Builder]是一个Microsoft Excel加载项，用于将Customer Journey Analytics数据提取到工作簿中的数据块中。 已熟悉Excel的业务用户可以无需学习Analysis Workspace或SQL即可构建循环报表。

## 更多信息

[!DNL Report Builder]中的每个数据块最多返回50,000行。 若要检索更多行，请使用&#x200B;**[!UICONTROL Page]**&#x200B;和&#x200B;**[!UICONTROL Rows]**&#x200B;选项，在超过50,000行限制的连续页面中提取数据。 有关详细信息，请参阅[筛选器维度](/help/report-builder/filter-dimensions.md)。

您可以计划工作簿以通过电子邮件发送，也可以将其导出到云目标，如Amazon S3、Google Cloud Platform或Azure。 有关详细信息，请参阅[通过电子邮件共享计划工作簿](/help/report-builder/schedule-reportbuilder.md)和[通过导出到云目标计划工作簿](/help/report-builder/report-builder-export.md)。

有关设置和使用[!DNL Report Builder]的简介，请参阅[Report Builder概述](/help/report-builder/rb-overview.md)。
