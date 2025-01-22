---
title: 产品使用情况概述
description: 查看有关贵组织如何使用Customer Journey Analytics的见解和报表。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: ae22dc84406427567d45b670aa9737ea3a8b2f7b
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

---

# 产品使用情况概述

{{release-limited-testing}}

产品使用情况使贵组织能够查看有关贵组织如何使用Customer Journey Analytics的分析数据。 它适用于使用Customer Journey Analytics的所有组织。 启用后，将自动创建并关联以下Adobe Experience Platform组件。 这些组件全部为系统所有、只读，无法编辑。

* Adobe Experience Platform中的架构
* Adobe Experience Platform中的数据集
* Customer Journey Analytics中的连接
* Customer Journey Analytics中的数据视图

启用后，将自动为您配置所有数据收集和设置。 无论用户何时在Analysis Workspace中执行操作，都会跟踪该操作并可用于报表。

>[!IMPORTANT]
>
>此功能计入Adobe Experience Platform中的合同行限制。 在启用此功能之前，请确保您的组织可以容纳由此功能生成的数据。

## 启用产品使用

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]**

导航到Customer Journey Analytics界面的此部分会将您转到[数据设置](data-settings.md)，您可以在其中启用此功能。

## 可用维度

启用产品使用情况时，以下维度可用。 如果要更改任何维度设置，请创建系统拥有的数据视图的副本，并在Analysis Workspace中使用复制的数据视图。

* **[!UICONTROL 操作名称]**：用户执行的操作类型。 您可以通过在数据视图设置中创建副本，将此维度用作任何所需的量度。 Dimension项目包括：
   * [!UICONTROL 添加归因]
   * [!UICONTROL 添加组件]
   * [!UICONTROL 添加面板]
   * [!UICONTROL 添加可视化图表]
   * [!UICONTROL 创建新的引导式分析]
   * [!UICONTROL 创建新项目]
   * [!UICONTROL 策划组件]
   * [!UICONTROL 下载 CSV]
   * [!UICONTROL 下载 PDF]
   * [!UICONTROL 加载引导分析]
   * [!UICONTROL 加载项目]
   * [!UICONTROL 新记分卡已加载]
   * [!UICONTROL 打开数据字典]
   * [!UICONTROL 打开智能字幕]
   * [!UICONTROL 项目共享]
   * [!UICONTROL 运行试验面板]
   * [!UICONTROL 保存项目]
   * [!UICONTROL 记分卡已保存]
   * [!UICONTROL 发送文件]
   * [!UICONTROL 按计划发送文件]
   * [!UICONTROL 与任何人共享项目]
   * [!UICONTROL 与Workspace用户共享项目]
* **[!UICONTROL 使用的归因模型]**：组件使用的归因模型类型。 Dimension项目包括：
   * [!UICONTROL 最近联系]
   * [!UICONTROL 首次联系]
   * [!UICONTROL 线性]
   * [!UICONTROL 参与率]
   * [!UICONTROL 同一接触]
   * [!UICONTROL U型]
   * [!UICONTROL J曲线]
   * [!UICONTROL 反向J]
   * [!UICONTROL 时间衰减]
   * [!UICONTROL 自定义]
   * [!UICONTROL 算法]
* **[!UICONTROL 组件名称]**：已添加、删除或修改的组件的名称。
* **[!UICONTROL 组件类型]**：已添加、删除或修改的组件类型。 Dimension项目包括：
   * [!UICONTROL 维度]
   * [!UICONTROL 量度]
   * [!UICONTROL 过滤器]
   * [!UICONTROL 计算指标]
   * [!UICONTROL 日期范围]
   * [!UICONTROL 批注]
   * [!UICONTROL 警报]
* **[!UICONTROL 登录用户]**：执行操作的用户。
* **[!UICONTROL 使用的面板]**：在其中添加、删除或修改组件的面板。 Dimension项目包括：
   * [!UICONTROL 归因]
   * [!UICONTROL 空白面板]
   * [!UICONTROL 试验]
   * [!UICONTROL 自由格式表]
   * [!UICONTROL 下一项或上一项]
   * [!UICONTROL 快速洞察]
   * [!UICONTROL 趋势]
   * [!UICONTROL 漏斗]
   * [!UICONTROL 用户增长]
   * [!UICONTROL 影响]
   * [!UICONTROL 用户流]
   * [!UICONTROL 保留]
   * [!UICONTROL 功能矩阵]
* **[!UICONTROL 项目名称]**：项目的友好名称。
* **[!UICONTROL 项目类型]**：项目类型。 Dimension项目包括：
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 用户ID]**：触发事件的用户ID。
* **[!UICONTROL 已使用可视化图表]**：已添加、删除或修改可视化图表。 Dimension项目包括：
   * [!UICONTROL 自由格式表]
   * [!UICONTROL 同类群组表]
   * [!UICONTROL 流失]
   * [!UICONTROL 流]
   * [!UICONTROL 历程画布缩图报表]
   * [!UICONTROL 面积图]
   * [!UICONTROL 堆叠的面积图]
   * [!UICONTROL 条形图]
   * [!UICONTROL 栈叠的条形图]
   * [!UICONTROL 项目符号]
   * [!UICONTROL 组合]
   * [!UICONTROL 圆环图]
   * [!UICONTROL 直方图]
   * [!UICONTROL 水平条]
   * [!UICONTROL 栈叠的水平条形图]
   * [!UICONTROL 关键量度摘要]
   * [!UICONTROL Line]
   * [!UICONTROL 地图]
   * [!UICONTROL 散点图]
   * [!UICONTROL 节标题]
   * [!UICONTROL 概要变化]
   * [!UICONTROL 摘要数字]
   * [!UICONTROL Text]
   * [!UICONTROL 树图]
   * [!UICONTROL 维恩图]

仅打开或查看项目时，产品使用情况不会跟踪单个项目组件。 但是，会跟踪打开项目的用户操作。
