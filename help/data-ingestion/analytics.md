---
title: 从传统Adobe Analytics中摄取和使用数据
description: 说明如何从传统Adobe Analytics中摄取数据
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
source-git-commit: 325dcd0862b8ac06b3b26c3ae349a8fce757cb6c
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 10%

---

# 从传统Adobe Analytics中摄取和使用数据

本快速入门指南介绍如何在Customer Journey Analytics中使用Adobe Analytics收集的数据。

>[!PREREQUISITES]
>
>您确实已使用任何记录的实施方法，在一个或多个网站上授权并部署Adobe Analytics:
>
>- [使用 Experience Platform Edge 实施 Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=zh-Hans)
>
>- [使用Adobe Analytics扩展实施Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=zh-Hans)
>
>- [使用 JavaScript 实施 Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


要实现此目的，您需要：

- **设置Adobe Analytics源连接器** 在Adobe Experience Platform。 这可以将您当前的Adobe Analytics数据摄取到Adobe Experience Platform中的数据集中。

- **设置连接** Customer Journey Analytics。 此连接应（至少）包含您的Adobe Experience Platform数据集。

- **设置数据视图** Customer Journey Analytics中定义要在Analysis Workspace中使用的量度和维度。

- **设置项目** Customer Journey Analytics构建报表和可视化。


>[!NOTE]
>
>这是有关如何使用Adobe Analytics源连接器获取数据并在Customer Journey Analytics中使用该数据的简化指南。 强烈建议在提及时研究附加信息。


## 设置Adobe Analytics源连接器

Adobe Analytics源连接器允许您将Adobe Analytics报表包数据导入Adobe Experience Platform。

要创建Adobe Analytics源连接器，请执行以下操作：

1. 在平台UI中，选择 **[!UICONTROL 源]**，从左边栏。

2. 选择 **[!UICONTROL Adobe应用程序]** 从 [!UICONTROL 类别].

3. 选择 **[!UICONTROL 设置]** 或 **[!UICONTROL 添加数据]** 在Adobe Analytics拼贴中。

   ![源](./assets/sources-overview.png)

4. 选择 **[!UICONTROL 报表包]**. 从报表包列表中，选择要使用的报表包。

   ![报表包](./assets/report-suites.png)

   选择&#x200B;**[!UICONTROL 下一步]**。

5. 选择 **[!UICONTROL 默认架构]** 作为 [!UICONTROL 目标架构]. Adobe Experience Platform会自动创建架构和相应的数据集，以映射选定Adobe Analytics报表包中的所有标准字段。

   ![默认架构](./assets/default-schema.png)

   选择&#x200B;**[!UICONTROL 下一步]**。

6. 命名数据流，并（可选）提供描述。

   ![数据流详细信息](./assets/dataflow-detail.png)

   选择&#x200B;**[!UICONTROL 下一步]**。

7. 查看连接并选择 **[!UICONTROL 完成]**.

   ![请查看](./assets/review.png)


创建连接后，将自动创建数据流以使用报表包中的Adobe Analytics数据填充数据集，包括最多摄取13个月的历史数据。

完成初始摄取后，您的Adobe Analytics报表包数据便可供Customer Journey Analytics使用。

请参阅 [在UI中创建Adobe Analytics源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 更全面的教程。


## 设置连接

要在Customer Journey Analytics中使用Adobe Experience Platform数据，请创建一个连接，其中包含设置架构、数据集和工作流后生成的数据。

通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。要报告这些数据集，您必须首先在Adobe Experience Platform和工作区中的数据集之间建立连接。

要创建连接，请执行以下操作：

1. 在Customer Journey AnalyticsUI中，选择 **[!UICONTROL 连接]** 中。

2. 选择 **[!UICONTROL 创建新连接]**.

3. 在 [!UICONTROL 无标题连接] 屏幕：

   在中命名并描述您的连接 [!UICONTROL 连接设置].

   从 [!UICONTROL 沙盒] 列表 [!UICONTROL 数据设置] 并从 [!UICONTROL 平均每日事件数] 列表。

   ![连接设置](./assets/cja-connections-1.png)

   选择 **[!UICONTROL 添加数据集]**.

   在 [!UICONTROL 选择数据集] 步骤 [!UICONTROL 添加数据集]:

   - 选择由Adobe Analytics源连接器自动创建的数据集以及要包含在连接中的任何其他数据集。

      ![添加数据集](./assets/cja-connections-2a.png)

   - 选择&#x200B;**[!UICONTROL 下一步]**。
   在 [!UICONTROL 数据集设置] 步骤 [!UICONTROL 添加数据集]:

   - 对于每个数据集：

      - 选择 [!UICONTROL 人员ID] 从Adobe Experience Platform的数据集架构中定义的可用标识。

      - 从 [!UICONTROL 数据源类型] 列表。 如果您指定 **[!UICONTROL 其他]**，然后为数据源添加描述。

      - 已设置 **[!UICONTROL 导入所有新数据]** 和 **[!UICONTROL 数据集回填现有数据]** 根据您的喜好。

      ![配置数据集](./assets/cja-connections-3a.png)

   - 选择 **[!UICONTROL 添加数据集]**.
   选择&#x200B;**[!UICONTROL 保存]**。

请参阅 [连接概述](../connections/overview.md) 有关如何创建和管理连接以及如何选择和合并数据集的更多信息。

## 设置数据视图

数据视图 是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 它指定所有可在 Analysis Workspace 中找到的维度和指标，以及这些维度和指标从哪些列获取其数据。为准备 Analysis Workspace 中的报表而定义数据视图。

要创建数据视图，请执行以下操作：

1. 在Customer Journey AnalyticsUI中，选择 **[!UICONTROL 数据视图]** 中。

2. 选择 **[!UICONTROL 创建新数据视图]**.

3. 在 [!UICONTROL 配置] 步骤：

   从 [!UICONTROL 连接] 列表。

   名称和（可选）描述您的连接。

   ![数据视图配置](./assets/cja-dataview-1.png)

   选择 **[!UICONTROL 保存并继续]**.

4. 在 [!UICONTROL 组件] 步骤：

   将您要包含的任何架构字段和/或标准组件添加到 [!UICONTROL 量度] 或 [!UICONTROL Dimension] 组件框。

   ![数据视图组件](./assets/cja-dataview-2.png)

   选择 **[!UICONTROL 保存并继续]**.

5. 在 [!UICONTROL 设置] 步骤：

   ![数据视图设置](./assets/cja-dataview-3.png)

   保留设置原样，然后选择 **[!UICONTROL 保存并完成]**.

请参阅 [数据视图概述](../data-views/data-views.md) 有关如何创建和编辑数据视图的更多信息，可在数据视图中使用哪些组件，以及如何使用过滤器和会话设置。


## 设置项目

Analysis Workspace是一个灵活的浏览器工具，允许您快速构建分析并根据数据共享分析。 您可以使用工作区项目来组合数据组件、表格和可视化图表，以便进行分析并与组织中的任何人共享。

要创建项目，请执行以下操作：

1. 在Customer Journey AnalyticsUI中，选择 **[!UICONTROL 项目]** 中。

2. 选择 **[!UICONTROL 项目]** 中。

3. 选择 **[!UICONTROL 创建项目]**.

   ![工作区项目](./assets/cja-projects-1.png)

   选择 **[!UICONTROL 空白项目]**.

   ![工作区 — 空白项目](./assets/cja-projects-2.png)

4. 从列表中选择数据视图。

   ![工作区选择数据视图](./assets/cja-projects-3.png).

5. 开始在 [!UICONTROL 自由格式表] 在 [!UICONTROL 面板] 以创建您的第一个报表。 例如，拖动 `Program Points Balance` 和 `Page View` 作为量度和 `email` 作为维度，可快速查看访问过您的网站且属于收集会员积分的忠诚度计划一部分的用户档案。

   ![工作区 — 首个报表](./assets/cja-projects-5.png)

请参阅 [Analysis Workspace概述](../analysis-workspace/home.md) 有关如何使用组件、可视化图表和面板创建项目和构建分析的更多信息。


>[!SUCCESS]
>
>您已完成所有步骤。 从设置Adobe Analytics数据源连接器并为报表包配置该连接器开始，您的Adobe Analytics数据会自动上传到Adobe Experience Platform。 您在Customer Journey Analytics中定义了一个连接，以利用摄取的Adobe Analytics数据和其他数据。 通过数据视图定义，您可以指定要使用的维度和量度，最后创建了您的第一个项目，并对数据进行可视化和分析。

