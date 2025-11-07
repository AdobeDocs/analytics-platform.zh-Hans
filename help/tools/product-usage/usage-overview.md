---
title: 产品使用情况概述
description: 查看有关您的组织如何使用 Customer Journey Analytics 的洞察和报告。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 22f3059ffef5df76028f36ffa00da8f98956dee1
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 91%

---

# 产品使用情况概述

产品使用情况可为您的组织提供查看关于组织如何使用 Customer Journey Analytics 的分析数据。所有使用 Customer Journey Analytics 的组织均可使用该功能。一旦启用，将自动为您创建并连接以下 Adobe Experience Platform 组件。这些组件均为系统所有，且为只读，无法编辑。

* Adobe Experience Platform 中的架构
* Adobe Experience Platform 中的数据集
* Customer Journey Analytics 中的连接
* Customer Journey Analytics 中的数据视图

一旦启用，所有数据收集和设置都会自动为您配置完成。每当用户在 Analysis Workspace 中执行操作时，该操作都会被跟踪并可供报告。

>[!IMPORTANT]
>
>启用“产品使用”后，使用情况数据将存储在您的Adobe Experience Platform数据湖中。 确保贵组织的数据湖存储分配能够容纳通过启用此功能生成的附加数据集。
>
>此功能不计入您许可的Customer Journey Analytics报表行限制或事件数据权限。

## 启用产品使用情况

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]**

在 Customer Journey Analytics 中导航至界面中的这一部分，即可进入[数据设置](data-settings.md)，您可以在其中启用此功能。

## 可用的维度

当启用产品使用情况时，以下维度可用。如果要更改任何维度设置，请创建系统拥有的数据视图的副本，并在 Analysis Workspace 中使用复制的数据视图。

* **[!UICONTROL 操作名称]**：用户采取的操作的类型。您可以通过在数据视图设置中创建一个副本将此维度用作任何所需的量度。维度项包括：
   * [!UICONTROL 添加归因]
   * [!UICONTROL 添加组件]
   * [!UICONTROL 添加面板]
   * [!UICONTROL 添加可视化]
   * [!UICONTROL 创建新的引导式分析]
   * [!UICONTROL 创建新项目]
   * [!UICONTROL 策划组件]
   * [!UICONTROL 下载 CSV]
   * [!UICONTROL 下载 PDF]
   * [!UICONTROL 加载引导式分析]
   * [!UICONTROL 加载项目]
   * [!UICONTROL 已加载新的记分卡]
   * [!UICONTROL 打开数据字典]
   * [!UICONTROL 打开智能标题]
   * [!UICONTROL 项目共享]
   * [!UICONTROL 运行试验面板]
   * [!UICONTROL 保存项目]
   * [!UICONTROL 记分卡已保存]
   * [!UICONTROL 发送文件]
   * [!UICONTROL 按计划发送文件]
   * [!UICONTROL 与任何人共享项目]
   * [!UICONTROL 与工作区用户共享项目]
   * [!UICONTROL 切换数据视图]
* **[!UICONTROL 使用的归因模型]**：组件使用的归因模型的类型。维度项包括：
   * [!UICONTROL 最后接触]
   * [!UICONTROL 首次接触]
   * [!UICONTROL 线性]
   * [!UICONTROL 参与率]
   * [!UICONTROL 同一接触]
   * [!UICONTROL U 型]
   * [!UICONTROL J 型曲线]
   * [!UICONTROL 反向 J]
   * [!UICONTROL 时间衰减]
   * [!UICONTROL 自定义]
   * [!UICONTROL 算法]
* **[!UICONTROL 组件 ID]**：已添加、移除或修改的组件的 ID。
* **[!UICONTROL 组件名称]**：已添加、移除或修改的组件的友好名称。
* **[!UICONTROL 组件类型]**：已添加、移除或修改的组件的类型。维度项包括：
   * [!UICONTROL 维度]
   * [!UICONTROL 量度]
   * [!UICONTROL 区段]
   * [!UICONTROL 计算量度]
   * [!UICONTROL 日期范围]
   * [!UICONTROL 批注]
   * [!UICONTROL 警报]
* **[!UICONTROL 数据视图 ID]**：数据视图的 ID。
* **[!UICONTROL 数据视图名称]**：数据视图的友好名称。
* **[!UICONTROL 登录用户]**：采取该操作的用户。
* **[!UICONTROL 使用的面板]**：已添加、移除或修改的面板。维度项包括：
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
* **[!UICONTROL 项目 ID]**：项目的 ID。
* **[!UICONTROL 项目名称]**：便于用户使用的项目名称。
* **[!UICONTROL 项目类型]**：项目类型。维度项包括：
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 使用的可视化图表]**：已添加、移除或修改的可视化图表。维度项包括：
   * [!UICONTROL 自由格式表]
   * [!UICONTROL 同类群组表]
   * [!UICONTROL 流失]
   * [!UICONTROL 流量]
   * [!UICONTROL 历程画布小型报告]
   * [!UICONTROL 面积图]
   * [!UICONTROL 堆叠的面积图]
   * [!UICONTROL 条形图]
   * [!UICONTROL 堆叠的条形图]
   * [!UICONTROL 项目符号]
   * [!UICONTROL 组合]
   * [!UICONTROL 圆环图]
   * [!UICONTROL 直方图]
   * [!UICONTROL 水平条]
   * [!UICONTROL 堆叠的水平条形图]
   * [!UICONTROL 关键量度摘要]
   * [!UICONTROL 线形图]
   * [!UICONTROL 地图]
   * [!UICONTROL 散点图]
   * [!UICONTROL 分区标头]
   * [!UICONTROL 摘要变化]
   * [!UICONTROL 摘要数字]
   * [!UICONTROL Text]
   * [!UICONTROL 树图]
   * [!UICONTROL 维恩图]

当项目仅被打开或查看时，产品使用情况不会跟踪单个项目组件。但是，用户打开项目的操作会被跟踪。

## 可用模板

现在提供一个 [Adobe 模板](/help/analysis-workspace/templates/use-templates.md)，该模板使用通过此功能自动生成的组件。

**[!UICONTROL Adobe 模板]** > **[!UICONTROL 其他]** > **[!UICONTROL 产品使用概述]**

在数据视图选择器中选择产品使用情况自动创建的数据视图，然后选择&#x200B;**[!UICONTROL 产品使用情况概览]**&#x200B;模板。选择&#x200B;**[!UICONTROL 预览]**，查看模板使用哪些面板并了解理想的用例，或选择&#x200B;**[!UICONTROL 使用模板]**，在 Analysis Workspace 中将其打开。
