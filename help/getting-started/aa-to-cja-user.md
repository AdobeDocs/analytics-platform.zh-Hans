---
title: 适用于Adobe Analytics用户的CJA用户指南
description: 当您的公司将数据从Adobe Analytics移动到Customer Journey Analytics时，从用户的角度应该考虑什么
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 40%

---


# 适用于Adobe Analytics用户的CJA用户指南

恭喜，您的公司至少已将其部分数据移至Customer Journey Analytics! 在开始使用Customer Journey Analytics时，您会注意到一些重大差异和一些相似之处。 本页旨在解释那些未更改的内容，以及一些主要差异。

我们还将告诉您如何获取有关新概念的更多信息，以及进一步的步骤，以使您的客户历程更轻松、更成功。

## 未更改的内容

您在报表端所熟悉的许多内容并未发生更改。 您仍然可以使用Analysis Workspace的强大功能分析数据，以及Adobe Analytics功能板和新版Report Builder。 工作区和功能板的工作方式与在传统Adobe Analytics中基本相同。 Report Builder具有新的界面，现在可在PC、Mac计算机和Excel的Web版本上运行。 在报告方面，不同之处在于您有权访问要分析的更多跨渠道数据。 以下是的工作区示例

## 新架构

在架构上，Customer Journey Analytics会从Adobe Experience Platform获取其数据。 Experience Platform让您能够集中和标准化来自任何系统或渠道的客户数据和内容，并应用数据科学和机器学习来改进个性化体验的设计和交付。

Platform 中的客户数据将作为数据集存储，数据集由一个架构和批量数据组成。有关 Platform 的更多详细信息，请参阅 [Adobe Experience Platform 体系架构概述](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理员将在平台中建立与数据的连接，并在这些连接中构建数据视图。 将数据视图视为类似于虚拟报表包的视图。 数据视图是报告Customer Journey Analytics的基础。

## 新概念和术语

与传统的Adobe Analytics相比，为了符合行业标准，CJA中的几项功能已重命名并重新构建。 一些更新的术语包括区段、虚拟报表包、分类、客户属性和容器名称。 耳熟能详的概念（如eVar和prop）已不复存在，而且这些概念也存在限制。

### 区段现在为“过滤器”


### 虚拟报表包现在为“数据视图”


### 分类现在为“查找数据集”

### 客户属性现在为“用户档案数据集”


### 点击容器现在为“事件”容器

### 访问容器现在为“会话”容器

### 访客容器现在为“人员”容器

## 有关Adobe Analytics组件的常见问题解答

| 问题 | 回答 |
| --- | --- |
| 我能否将来自[!DNL Customer Journey Analytics]的[!UICONTROL 过滤器]（[!UICONTROL 区段]）共享/发布到 Experience Platform Unified Profile 或其他 Experience Cloud 云应用程序？ | 还不能，但我们正在努力提供这种功能。 |
| 我之前的 [!UICONTROL eVar] 设置发生了什么变化？ | [!UICONTROL Customer Journey Analytics] 中不再存在传统 Adobe Analytics 意义上的 [!UICONTROL eVar]、[!UICONTROL 属性]和[!UICONTROL 事件]。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。 |
| 我的所有会话和变量持久性设置现在位于何处？ | [!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！ |
| 我们的现有区段/计算量度会发生什么？ | [!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段或计算量度都与 [!UICONTROL Customer Journey Analytics] 不兼容。 |
| [!UICONTROL Customer Journey Analytics] 如何处理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！ |
| 如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 [!UICONTROL Customer Journey Analytics]？ | 这取决于您的用例 - 请与您的 Adobe 客户团队合作。您的当前用例可能已经非常适合 Customer Journey Analytics！ |
