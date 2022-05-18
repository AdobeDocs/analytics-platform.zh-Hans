---
description: 了解AEPAttribution AI如何与CJA中的工作区集成。
title: 将Attribution AI与CJA集成
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# 将Attribution AI与CJA集成

>[!NOTE]
>
>本页正在构建中。

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)作为Adobe Experience Platform Intelligent Services的一部分，是一项多渠道算法归因服务，用于计算客户交互对特定结果的影响和增量影响。 借助Attribution AI，营销人员可以通过了解客户旅程各个阶段每个客户互动的影响来衡量和优化营销和广告支出。

Attribution AI支持两类得分：算法和基于规则。 算法得分包括增量分数和受影响分数。 基于规则的得分包括“首次接触”、“最近接触”、“线性”、“U型”和“时间衰减”。 Attribution AI支持3种Experience Platform模式：体验事件、Adobe Analytics和消费者体验事件。

Attribution AI与Customer Journey Analytics(CJA)集成，以便Attribution AI针对数据运行模型，然后CJA将这些模型的输出导入为数据集，然后可将其与其余的CJA数据集集成。 然后，可以在CJA的数据视图和报表中利用启用Attribution AI的数据集。

## 工作流程

在CJA中处理输出之前，某些步骤在Adobe Experience Platform中执行。

### 步骤1:下载Attribution AI得分

在Adobe Experience Platform中，下载Attribution AI得分，如所述 [此处](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### 步骤2:创建Attribution AI实例

在Experience Platform中，通过选择和映射数据、定义事件和培训数据来创建Attribution AI实例，如所述 [此处](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### 步骤3:设置与Attribution AI数据集的CJA连接

在CJA中，您现在可以 [创建一个或多个连接](/help/connections/create-connection.md) Experience Platform已针对Attribution AI分析的数据集。 这些Attribution AI集会显示“数据得分”前缀，如下所示：

![AAI分数](assets/aai-scores.png)

### 步骤4:根据这些连接创建数据视图

在CJA中，

## Attribution AI和Attribution IQ之间的差异

因此，您何时应使用Attribution AI数据， [Attribution IQ](/help/analysis-workspace/attribution/overview.md)，是本机CJA功能吗？ 此表显示了功能上的一些差异：

| 功能 | Attribution AI | Attribution IQ |
| --- | --- | --- |
| 小数归因 | 是 | 否 |
| 允许用户调整模型 | 否 | 是 |
| 跨渠道归因吗(注意：AAI使用的拼合数据与CJA不同。) | 是 | 是 |
| 包括增量分数和受影响的分数 | 是 | 否 |
| ML建模吗？ | 是 | 是 |
| 使用预测进行ML建模吗？ | 是 | 否 |

{style=&quot;table-layout:auto&quot;}
