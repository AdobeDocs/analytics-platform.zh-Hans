---
title: 客户旅程分析入门
description: 客户旅程分析入门。
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# 客户旅程分析入门

要实施客户旅程分析，您需要遵循此工作流。 某些初始任务在Adobe Experience Platform中执行，有些则在客户旅程分析中执行。

| 任务 | 位置 执行 | 详细信息 |
|---|---|---|
| **第1步：将数据导入Adobe Experience Platform** | Adobe Experience Platform |  |
| **第2步：准备数据架构** | Adobe Experience Platform | 使用 [Adobe Experience Data Model(XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) ，标准化客户体验数据并定义客户体验管理的架构。 |
| **第3步：根据架构创建数据集** | Adobe Experience Platform | 平台中的数据由数据集组成，如电子邮件数据集、CRM数据集、POS数据集、Adobe Analytics数据集等。 每个数据集都由一个架构和成批数据组成。 您可以在Experience Platform中创 [建数据集](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md)。<br>尽管可导入客户旅程分析的数据集架构是灵活的，但它必须符合一些基本规则。 最好在将数据上传到平台之前，先确保数据满足这些要求。 （请注意，架构包括度量和维度。）<br>有三种类型的数据与客户旅程分析兼容：<ul><li>**事件数据**:表示及时事件的数据（例如，Web访问、交互、交易、POS数据、调查数据、广告印象数据等）。 这是典型的点击流数据，带有客户ID或cookie ID，以及时间戳。 利用活动数据，我们允许您使用您需要的ID。</li><li>**查找数据**:此数据用于查找在事件或配置文件数据中找到的值或键。 例如，您可以上传查找数据，将事件数据中的数字ID映射到产品名称。</li><li>**个人资料数据**:活动数据中应用于访客、用户或客户的数据。 例如，允许您上传有关客户的CRM数据。</li></ul> |
| **第3步：在平台数据集和客户旅程分析之间建立联系** | 客户历程分析 | 请参 [阅创建连接](/help/connections/create-connection.md)。 |
| **第4步：创建数据视图** | 客户历程分析 | See [Create a data view](/help/data-views/create-dataview.md). |
| **第5步：在Workspace中报告跨渠道数据** | 客户历程分析 | 请参 [阅执行基本分析](/help/projects/perform-basic-analysis.md) , [并执行高级分析](/help/projects/perform-adv-analysis.md)。 |

## 先决条件

客户旅程分析适用于

* Adobe Analytics [Select、Prime或Ultimate客户](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) ，以及
* 为 [Adobe Experience Platform提供](https://www.adobe.com/experience-platform.html)，并且
* 已购买客户旅程分析SKU

## 准备数据架构

[使用架构编辑器创建架构](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## 第1步：将数据导入Adobe Experience Platform

在CJA中利用Experience Platform数据之前，您必须将该数据引入Platform。 可通过以下几种方式执行此操作：

* 如果要导入现有Adobe Analytics数据，请使用Adobe Analytics Platform Connector。
* 要导入其他数据，请使用。csv或Parke格式的文件


## 第1步a:将现有Analytics数据导入Adobe Experience Platform

使用Adobe Analytics Platform Connector将传统的Analytics数据引入Platform。 您可以为每个报表包创建一个源连接。 请参 [阅Adobe Experience Platform文档中的](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) “使用Adobe Analytics创建源连接”。

创建连接后，将自动创建目标架构和数据集以包含传入的数据。 此外，还会进行数据回填，并收集长达13个月的历史数据。 当初始摄取完成时，您可以继续执行步骤x，以在此Analytics数据集和客户旅程分析之间建立连接。

## 步骤1 b:创建架构




