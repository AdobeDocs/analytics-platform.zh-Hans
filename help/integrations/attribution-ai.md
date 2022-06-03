---
description: 了解 AEP 归因人工智能如何与 CJA 中的工作区集成。
title: 将归因人工智能与 CJA 集成
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 195a89588d83e27eceb58fec8c66c098f1971250
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 58%

---

# 将归因人工智能与 CJA 集成

[归因人工智能](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=zh-Hans)，作为 Adobe Experience Platform 智能服务的一部分，是一种多渠道、算法归因服务，用于计算客户交互对指定结果的影响和增量影响。借助归因人工智能，营销人员可以通过了解每个客户互动对客户旅程各个阶段的影响来衡量和优化营销和广告支出。

Attribution AI与Customer Journey Analytics(CJA)集成，以便Attribution AI针对客户的营销接触点和转化数据源运行模型。 然后，CJA会将这些模型的输出作为数据集进行导入，或者也可以将其与CJA数据集的其余部分集成。 然后可以在 CJA 中的数据视图和报告中利用启用了归因人工智能的数据集。

归因人工智能支持 3 种 Experience Platform 模式：体验事件、Adobe Analytics 和消费者体验事件。

归因人工智能支持两个类别的分数：算法分数和基于规则的分数。

## 算法得分

算法分数包括增量分数和影响分数。

* **影响分数**&#x200B;在营销渠道之间划分 100% 的转化信用。
* **增量分数**&#x200B;首先考虑到即使没有营销也可以实现的转化基线。由于现有的品牌认知度、忠诚度和口碑，该基线取决于 AI 对模式、季节性等的观察。剩余的信用在营销渠道之间分配。

## 基于规则的分数

基于规则的分数包括

* **[!UICONTROL 首次接触]** 将100%的点数分给在归因回顾窗口中看到的首次接触点。
* **[!UICONTROL 最近联系]** 将100%的点数分给转化前最近发生的接触点。
* **[!UICONTROL 线性]** 将相同的点数分给导致转化的每个接触点。
* **[!UICONTROL U型]** 将40%的点数分给首次交互，40%的点数分给最后交互，并将剩余20%的点数分给这两次交互之间的任意接触点。 对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的转化，两个接触点各分得 50% 的点数。
* **[!UICONTROL 时间衰减]** 采用具有自定义半衰期参数的指数衰减，其默认值为7天。 每个渠道的权重，取决于在接触点启动与最终转化之间流逝的时间。用于确定点数的公式是 `2^(-t/halflife)`，其中 `t` 是接触点与转化之间流逝的时间。然后，所有接触点均被标准化为 100%。

## 工作流程

在使用 CJA 中的输出之前，请在 Adobe Experience Platform 中执行某些步骤。 输出包含一个应用了归因人工智能模型的数据集。

### 第 1 步：创建归因人工智能实例

在 Experience Platform 中，通过选择和映射数据、定义事件和训练数据来创建归因人工智能实例，如[此处](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html)所述。

![AAI实例](assets/aai-instance.png)

### 第 2 步：设置与归因人工智能数据集的 CJA 连接

在 CJA 中，您现在可以[创建一个或多个连接](/help/connections/create-connection.md)到已针对归因人工智能进行检测的 Experience Platform 数据集。这些Attribution AI集会显示“数据得分”前缀，如下所示：

![AAI 分数](assets/aai-scores.png)

![创建连接](assets/aai-create-connection.png)

### 第 3 步：根据这些连接创建数据视图

在 CJA 中，[创建一个或多个包含归因人工智能 XDM 字段的数据视图](/help/data-views/create-dataview.md)。

以下是接触点的XDM架构字段：

![接触点XDM字段](assets/touchpoint-fields.png)

以下是用于转化的XDM架构字段：

![转化XDM字段](assets/conversion-fields.png)

### 第 4 步：在 CJA 工作区中报告 AAI 数据

例如，在 CJA 工作区项目中，您可以提取“AAI 订单”等指标，以及“AAI 营销活动名称”或“AAI 营销渠道”等维度。

![AAI 维度](assets/aai-dims.png)

>[!IMPORTANT]
>
>这些维度和量度不会以这种方式在本地命名。 这些是“友好名称”。 的 [Attribution AI中的命名约定](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/input-output.html?lang=en#attribution-ai-output-data) 遵循架构路径。 我们建议在CJA中将长AAI架构路径名称重命名为更易用的短名称（维度/量度）。 您可以在 **[!UICONTROL 数据视图]** > **[!UICONTROL 编辑数据视图]** > **[!UICONTROL 组件]** 选项卡> **[!UICONTROL 架构字段]** ->单击架构字段 — > **[!UICONTROL 组件名称]**.

![更改维度名称](assets/change-name.png)

**具有影响分数和增量分数的订单**

在这里，我们看到一个带有 AAI 数据的工作区项目，该数据显示了具有影响和增量分数的订单。通过以下方式向下访问任何维度以了解归因：促销活动、产品组、用户区段、地理位置等。

![AAI 项目](assets/aai-project.png)

![AAI 项目](assets/aai-project2.png)

**营销效果**

比较和对比不同归因模型之间的接触点归因：

![比较](assets/compare.png)

**渠道互动**

通过维恩图了解渠道交互，以了解哪些渠道可以最有效地与其他渠道一起使用：

![营销渠道重叠](assets/mc-overlap.png)

**转化的热门路径**

此表显示了转化的热门路径（消除了重复项），以帮助您设计和优化接触点：

![热门渠道](assets/top-channels.png)

**转化前置时间**

在此，我们可以看到在混合接触点中出现转化的前置时间。 它有助于优化前置时间：

![前置时间](assets/lead-time.png)

## 归因人工智能和 Attribution IQ 之间的差异

那么什么时候应该使用归因人工智能数据而非原生 CJA 功能 [Attribution IQ](/help/analysis-workspace/attribution/overview.md)？下表显示了一些功能差异：

| 功能 | 归因人工智能 | Attribution IQ |
| --- | --- | --- |
| 增量归因吗？ | 是 | 否 |
| 允许用户调整模型 | 是 | 是 |
| 跨渠道进行归因（注意：AAI 不使用与 CJA 相同的拼接数据。） | 是 | 是 |
| 包括受影响的得分 | 是 | 是 |
| 进行 ML 建模 | 是 | 是 |
| 基于区域的归因模型 | 是 | 是 |
| 可以在模型中配置营销接触点 | 是 | 否 |

{style=&quot;table-layout:auto&quot;}
