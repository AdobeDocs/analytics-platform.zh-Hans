---
title: 归因常见问题解答
description: 获取有关归因的常见问题解答。
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
translation-type: tm+mt
source-git-commit: 93f4f65a3b321d16a37ed21339ef811e1f55f9ca
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 88%

---

# 归因常见问题解答

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

**使用归因时，“无”行项目是什么？**

“无”行项目是一个全包项，它表示在回顾窗口内发生的不含任何接触点的所有转化。请尝试在报告窗口中包含更长的时间范围。

**在使用归因模型时，为什么有时会看到超出报告窗口以外的日期？**

这些额外的日期是由于访客报表回顾窗口造成的。有关更多信息，请参阅 Analytics KB 中的[出现报表窗口以外的数据](https://helpx.adobe.com/cn/analytics/kb/data-appearing-outside-reporting-window.html)。Adobe 计划在即将发布的版本中过滤掉这些额外的行。

**何时应使用访问归因回顾？何时应使用访客归因回顾？**

归因回顾的选择取决于您的用例。如果转化通常比单次访问花费的时间长，则建议使用访客回顾。创建具有较长访问定义的数据视图也是一个潜在的解决方案。

**使用归因时，如何进行 prop 和 eVar 比较？**

归因在报表运行时会重新计算，因此在归因建模时，prop 或 eVar（或任何其他维度）之间没有区别。使用任意回顾窗口或归因模型时 Prop 会持久保留，但是 eVar 分配/到期设置会被忽略。

**不支持哪些维度和量度？**

归因面板支持所有维度。不支持的量度包括：

* 独特访客
* 访问
* 发生次数
* 页面查看次数
* A4T 量度
* 逗留时间量度
* 跳出次数
* 跳出率
* 登录
* 退出
* 页面未找到
* 搜索
* 单页面访问量
* 单次存取

**归因如何与过滤器协作？**

归因始终在过滤器之前运行，分段在应用任何其他报表过滤器之前运行。
