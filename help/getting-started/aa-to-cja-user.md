---
title: 适用于Adobe Analytics用户的CJA用户指南
description: 当您的公司将数据从Adobe Analytics移动到Customer Journey Analytics时，从用户的角度应该考虑什么
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: d31f07d8b26ea4d60481c040a0ca1ba491d4ecf0
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 25%

---


# 适用于Adobe Analytics用户的CJA用户指南

>[!NOTE]
>
>本页正在构建中。

恭喜，贵公司已开始与Customer Journey Analytics合作！ 作为熟悉Adobe Analytics的用户，您已经拥有了良好的开端。 使用Customer Journey Analytics时，您会注意到一些重大差异和一些相似之处。 本页旨在解释那些未更改的内容，以及一些主要差异。 我们还将告诉您如何获取有关新概念的更多信息，以及进一步的步骤，以使您的客户历程更轻松、更成功。

## 未更改的内容

您在报表端所熟悉的许多内容并未发生更改。 您仍然可以使用Analysis Workspace的强大功能分析数据。 您还可以使用相同版本的Adobe Analytics功能板。 工作区和功能板的工作方式与在传统Adobe Analytics中基本相同。 Report Builder具有新的界面，现在可在PC、Mac计算机和Excel的Web版本上运行。 在报告方面，不同之处在于您有权访问要分析的更多跨渠道数据。 以下是一些多渠道可视化图表的示例：

![多渠道](assets/cross-channel.png)

## 新架构

Customer Journey Analytics从Adobe Experience Platform获取其数据。 Experience Platform让您能够集中和标准化来自任何系统或渠道的客户数据和内容，并应用数据科学和机器学习来改进个性化体验的设计和交付。

Platform 中的客户数据将作为数据集存储，数据集由一个架构和批量数据组成。有关 Platform 的更多详细信息，请参阅 [Adobe Experience Platform 体系架构概述](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理员已建立 [连接](/help/connections/create-connection.md) 到平台中的数据集。 然后他们建了 [数据视图](/help/data-views/data-views.md) 在这些关系中。 将数据视图视为类似于虚拟报表包的视图。 数据视图是报告Customer Journey Analytics的基础。

## 新概念和术语

与传统的Adobe Analytics相比，为了符合行业标准，CJA中的几项功能已重命名并重新构建。 一些更新的术语包括区段、虚拟报表包、分类、客户属性和容器名称。 耳熟能详的概念（如eVar和prop）已不复存在，而且这些概念也存在限制。

### eVar和prop

[!UICONTROL Customer Journey Analytics] 中不再存在传统 Adobe Analytics 意义上的 [!UICONTROL eVar]、[!UICONTROL 属性]和[!UICONTROL 事件]。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。

### 区段现在为“过滤器”

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段都与 [!UICONTROL Customer Journey Analytics]. 此外，“区段”已重命名为“过滤器”。

目前，您无法共享/发布 [!UICONTROL 过滤器] ([!UICONTROL 区段])从 [!DNL Customer Journey Analytics] Experience Platform统一配置文件或其他Experience Cloud应用程序。 此功能当前正在开发中。

### 计算量度

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有的计算量度都与 [!UICONTROL Customer Journey Analytics].

### 会话和变量持久性设置

[!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！

### 虚拟报表包现在为“数据视图”



### 分类现在为“查找数据集”

### 客户属性现在为“用户档案数据集”


### 点击容器现在为“事件”容器

### 访问容器现在为“会话”容器

### 访客容器现在为“人员”容器

### `Uniques Exceeded` 限制

[!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！
