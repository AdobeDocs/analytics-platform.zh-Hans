---
title: 受众分析概述
description: 了解如何在Customer Journey Analytics中从RTCDP分析受众。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 0719a981cd9d2e1480f744494c9a68fdd66c1beb
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 3%

---

# 受众分析概述

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>了解受众分析和受众发布之间的区别：
>
>* **受众分析**：允许您将受众成员资格数据从Experience Platform配置文件数据集摄取到Customer Journey Analytics连接。
>* **受众发布**：允许您创建在Customer Journey Analytics中发现的受众，并将其发布到Adobe Experience Platform以进行客户定位和个性化。 有关受众发布的信息，请参阅[受众发布概述](/help/components/audiences/audiences-overview.md)。

利用Audience Analysis，可将受众成员资格数据从Experience Platform配置文件数据集摄取到Customer Journey Analytics连接。 受众将可用作新维度，以便在Analysis Workspace中使用。

下图和相关表简要展示了Customer Journey Analytics中的受众分析配置如何在Analysis Workspace中使Experience Platform受众数据可用：

![受众分析概述](assets/audience-analysis-overview.png)

| 数值 | 功能 | 功能 |
|---------|----------|---------|
| 1 | 受众分析配置 | Customer Journey Analytics中用于配置受众分析的配置界面。 |
| 2 | 沙盒 | 必须包含要添加到连接的配置文件数据集。 |
| 3 | 轮廓数据集 | 必须包含您要分析的Experience Platform受众数据。 此用户档案数据集将添加到您选择的连接。 |
| 4 | 合并策略 | 与您要分析的Experience Platform受众关联的合并策略。 |
| 5 | 配置文件数据 | 与所选合并策略关联的配置文件数据。 此数据在Experience Platform数据集中可用。 |
| 6 | 新建查找数据集 | 为创建的新受众维度提供易记名称。 <p>系统会自动创建查找数据集并将其添加到连接，以及您选择的用户档案数据集。</p> |
| 7 | 连接 | 要在其中添加所选配置文件数据集的连接。 |
| 8 | 新的受众维度 | 新的受众维度<!--and metrics?-->表示包含在所选配置文件数据集中的Experience Platform受众，可以在Analysis Workspace中进行报告。 这些维度是自动创建的。 |
| 9 | 数据视图 | 您选择的数据视图与您的连接相关联。 在Analysis Workspace中分析Experience Platform受众数据时，要使用这些数据视图。 这些数据视图自动配置了Experience Platform受众数据以用于报表。 |

## 配置受众分析

在配置受众分析时，您可以选择与要分析的Experience Platform受众关联的沙盒和合并策略。 Customer Journey Analytics会创建新的查找数据集，然后自动将查找数据集和配置文件数据集添加到您选择的连接。

>[!IMPORTANT]
>
>每晚重新处理和生成受众数据，使受众数据仅可用于前一天（“昨天”）的分析。
>
>受众在创建受众分析配置的当天即出现在Customer Journey Analytics数据视图中。

有关详细信息，请参阅[配置受众分析](/help/connections/audience-analysis/audience-analysis-configure.md)。

## 管理受众分析配置

您可以在创建受众分析配置后对其进行管理。 您可以查看、编辑和删除配置。

有关管理现有受众分析配置的信息，请参阅[管理受众分析配置](/help/connections/audience-analysis/audience-analysis-manage.md)。

## 在Customer Journey Analytics中分析受众数据

借助Customer Journey Analytics中提供的受众数据，您可以获得关于受众成员在各种渠道中的行为的可操作见解。

例如，您可以跟踪同一电子邮件促销活动中包含的各个客户的行为。 利用Customer Journey Analytics中提供的受众，您可以查看有关每个受众成员的以下类型信息：

* 从电子邮件到网站的点进次数，最终导致购买

* 最终进行店内购买的受众成员

有关详细信息，请参阅[在Customer Journey Analytics中分析Experience Platform受众](/help/connections/audience-analysis/analyze-audiences.md)。

## 受众分析角色和权限要求

受众分析需要以下Customer Journey Analytics角色和Experience Platform权限：

| 功能 | Customer Journey Analytics角色或权限要求 | Experience Platform权限要求 |
|---------|----------|----------|
| [创建受众分析配置](/help/connections/audience-analysis/audience-analysis-configure.md) | 系统管理员 | <ul><li>数据集：读取权限</li><li>架构：读取、写入</li><li>身份命名空间：读取</li></ul> |
| [在数据视图中查看受众分析维度](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | 数据视图所分配到的产品配置文件的产品配置文件管理员 <p>有关详细信息，请参阅[访问控制](/help/technotes/access-control.md)。</p> | 不适用 |
| 在Analysis Workspace中使用受众分析维度 | 访问添加了受众分析维度的数据视图 | 不适用 |

## 受众分析限制

在[配置受众分析](/help/connections/audience-analysis/audience-analysis-configure.md)时，请考虑以下限制：

* 单个沙盒最多可支持100个受众分析配置。

* 一个连接只能与一个受众分析配置相关联。








