---
title: 高基数维度
description: 说明Customer Journey Analytics如何处理具有许多唯一值的维度。
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
TQID: https://experienceleague.adobe.com/cDOJq7Dc6x301enIo7h-cm8pGphmnvQAihnLoYGIr-A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 622
ht-degree: 11%

---

# 高基数维度

使用包含许多唯一值的维度时，生成的报表可能包含太多要显示或计算的唯一维度项。 通过删除被认为最不重要的维度项目，截断结果。 这些优化是为了保持项目和产品性能。

当您请求包含具有过多唯一值的维度的报告时，Analysis Workspace 会在维度标题中显示一个指示器，表明并非所有维度项都包含在内。 例如，**[!UICONTROL 行：超过22,343,156]**&#x200B;的1-50。 **[!UICONTROL 大于]**&#x200B;关键字表示已对报表应用了一些优化，以返回最重要的维度项。

![Workspace中的自由格式表显示“大于”关键字，可显示1-50个大于22,343,156](assets/high-cardinality.png)

## 确定要显示的维度项目

Customer Journey Analytics在运行报表时对其进行处理，将组合数据集分发到多台服务器。 数据请求的大小和可用Adobe硬件的数量是许多因素中的两个，这些因素有助于确定分配给处理报告的服务器数量。 由于服务器是动态分配的，在界面中不可见，因此无法查看或控制处理报告的服务器数量。

每个处理服务器的数据按人员ID分组，这意味着单个处理服务器包含给定人员的所有数据。 一旦服务器完成处理，它就会将其处理过的数据的子集交给聚合器服务器。 所有已处理数据的子集都以工作区报表的形式组合并返回。

如果任何单个服务器处理的数据超过唯一阈值，它将先截断结果，然后再返回已处理的数据子集。 已截断的维度项目是根据用于排序的量度确定的。

如果排序量度是计算量度，则服务器使用计算量度中的量度来确定要截断的维度项目。 由于计算量度可以包含多个具有不同重要性的量度，因此结果的准确性可能会降低。 例如，在计算“每人收入”时，会返回总收入金额和人数，并在进行分配前进行汇总。 因此，每个单独的处理服务器都会选择删除哪些项目，而不知道它们的结果如何影响整体排序。

尽管高基数报表中可能缺少某些个别维度项，但列总数是准确的，且并非基于截断的数据。 [[!UICONTROL 近似非重复计数]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)计算量度函数也不受截断维度项的影响。

## 高基数维度的最佳实践

适应高基数维度的最佳方法是限制报表处理的维度项目数。 由于所有报表在请求时都会进行处理，因此您可以调整报表参数以即时获得结果。 Adobe建议对高基数维度进行以下任何优化：

* 使用[区段](/help/components/segments/seg-create.md)。 区段在每个服务器处理数据子集时应用。
* 使用搜索。 从搜索词中排除的Dimension项目将从报表结果中删除，这样您更有可能看到所需的维度项目。
* 使用查找数据集维度。 查找数据集维度将事件数据集维度项组合在一起，从而限制返回的唯一值的数量。
* 在数据视图管理器中使用[包含/排除](/help/data-views/component-settings/include-exclude-values.md)组件设置。
* 缩短请求的日期范围。 如果许多唯一值随时间累积，则缩短Workspace报表的日期范围可以限制要处理的服务器唯一值的数量。
* 考虑使用[完全表导出](/help/analysis-workspace/export/export-cloud.md)返回表的所有行。
* 如果唯一值的数量是主要焦点，请使用[[!UICONTROL 近似非重复计数]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)计算量度函数。
