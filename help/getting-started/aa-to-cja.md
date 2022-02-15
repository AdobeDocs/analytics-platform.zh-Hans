---
title: 从Adobe Analytics迁移到Customer Journey Analytics
description: 从Adobe Analytics迁移到Customer Journey Analytics的步骤
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: 2f38b38328816a523427d73f812041904e294bc7
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 5%

---

# 准备从Adobe Analytics迁移到Customer Journey Analytics

在将数据从Adobe Analytics迁移到Customer Journey Analytics之前，请探索以下注意事项，以准备数据并了解这两种技术之间的关键差异。

## 准备数据

为Adobe Analytics数据准备无缝迁移到Customer Journey Analytics，对于数据完整性和报告一致性至关重要。

### 1.收集身份

了解客户历程的最关键组件或许是了解客户在每个步骤中的角色。 对于Customer Journey Analytics，如果具有跨所有渠道的标识符以及相应的数据，则可以在CJA内将多个源拼合在一起。
标识的示例可能是客户ID、帐户ID或电子邮件ID。 无论身份是什么（可能有多个），请确保为每个ID考虑以下事项：

* ID存在，或可以添加到要引入CJA的所有数据源中
* 每行数据中都会填充ID
* ID不包含PII。 对任何可能敏感的内容应用哈希处理。
* ID在所有源中使用相同的格式（相同长度、相同的哈希方法等）

在Adobe Analytics等数据集中，身份并不存在于每行数据中，但辅助身份存在。 在这种情况下，当客户仅通过其ECID进行标识，并收集身份（例如，客户进行验证）时，可以使用跨渠道分析（以前称为“基于字段的拼合”）来弥合行之间的差距。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans)

### 2.调整变量

将Adobe Analytics数据迁移到Customer Journey Analytics的最简单方法是 [全局报表包](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=en) Experience Platform [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans). 此连接器可将您的Adobe Analytics变量直接映射到AEP中的XDM架构和数据集，这反过来又可以轻松连接到CJA。

完整的全局报表包可能并非总是适用于实施。 如果您计划将多个报表包Customer Journey Analytics，则必须提前计划以使这些报表包中的变量保持一致。

例如，报表包 1 中的 eVar1 可能指向[!UICONTROL 页面]。在报表包2中，eVar1可能指向 [!UICONTROL 内部营销活动]. 将这些变量引入CJA后，这些变量将混合到单个eVar1维度中，从而导致报表可能会造成混淆和不准确。

如果您由于 [!UICONTROL 超出的唯一值] 或 [!UICONTROL 低流量]，知道CJA没有 [维度的基数限制](/help/components/dimensions/high-cardinality.md). 它允许显示和计数任何唯一值。

### 3. （重新）配置营销渠道

传统的Adobe Analytics营销渠道设置在CJA中不会执行相同的设置。 原因有二：

* 摄取到Adobe Experience Platform的Adobe Analytics数据的处理级别，以及

* Customer Journey Analytics的报告时间性质

Adobe已发布 [更新了营销渠道实施的最佳实践](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). 这些更新的建议可帮助您充分利用Adobe Analytics中已有的包含Attribution IQ的功能。 它们还可帮助您在过渡到Customer Journey Analytics时取得成功。

### 4.决定使用Analytics源连接器与Experience PlatformSDK

作为 [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans) 数据收集会不断发展，您可能会迁移到 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=en) 或 [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=en) Adobe Experience Platform边缘网络。 虽然SDK的典型实施会将数据发送到Adobe Analytics，但现在正是一个将数据直接发送到Adobe Experience Platform的新机会。 然后，可以将其摄取到Customer Journey Analytics中，同时维护发送到Adobe Analytics的数据。

此方法极大地扩展了数据收集的可能性：字段数量不再受到限制，或者需要将数据元素映射到prop、eVar和事件（如在Analytics中）。 您可以使用无限的不同类型的架构元素，并使用CJA以多种方式表示它们 [数据视图](/help/data-views/data-views.md). 直接发送到Adobe Experience Platform时，数据可用性的速度会随着通过Adobe Analytics进行数据处理的时间的删除而提高。

**使用Experience PlatformSDK的优势**

* 灵活的架构，可定义您需要的任何字段
* 不依赖Adobe Analytics命名法(prop、eVar、事件等)
* 无字符限制问题（prop的字符数为100个字符）
* 更快的Adobe Experience Platform数据可用性

**使用Experience PlatformSDK的缺陷**

不支持以下Adobe Analytics功能或组件：

* 营销渠道
* 机器人筛选
* 地域、域、设备查找
* Analytics for Target (A4T)

## 为重大差异做好准备

### 熟悉报表时间处理

Adobe Analytics中的报表依赖大量数据预处理来生成结果，如您在中看到的持久性 [!UICONTROL eVar]. 相反，Customer Journey Analytics在报表运行时运行这些计算。

[!UICONTROL 报表时间处理] 打开应用具有可回溯性的设置并创建多个版本的变量持久性的功能，而无需更改基础数据的收集方式。

这种转变会在报告数据的方式上产生一些差异，尤其是对于任何可能具有较长过期时间的变量。 您可以首先使用 [虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### 识别关键区段和计算量度

Adobe Analytics区段(称为 [!UICONTROL 过滤器] （在CJA中）和计算量度与Customer Journey Analytics不兼容。 在很多情况下，可以使用新的可用架构和数据在CJA中重新构建这些组件。

要在用户在系统之间进行过渡时，使过渡尽可能顺利，请提前制定计划

1. 确定这些组件中最关键的组件。

1. 记录其定义，以及

1. 确定数据中需要哪些字段才能在CJA中将它们复制为 [过滤器](/help/components/filters/filters-overview.md) 和 [计算量度](/help/components/calc-metrics/calc-metr-overview.md).

以下是几个视频，可为您提供指导：

* [将Adobe Analytics区段移动到Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [将计算量度从 Adobe Analytics 移动到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)

### 其他注意事项

* 使用CJA数据视图的强大功能，您在定义量度和维度方面具有更大的灵活性，而且Customer Journey Analytics中的量度和维度更灵活。 例如，您可以使用维度的值作为量度的定义。 [了解详情](/help/data-views/data-views-usecases.md)

* 如果您在Adobe Analytics中定义了自定义日历，则CJA中将具有类似的日历功能。 您需要确保日历的定义正确。

* 在Customer Journey Analytics中，您可以定义自定义访问/会话超时，以及定义将启动新会话的量度。 您可以使用不同的会话定义创建数据视图，以深入了解Adobe Analytics中可能包含的内容。 此功能可能对移动数据集特别有用。

## 后续步骤

迁移到CJA后，如果您发现任何数据差异，则可以将原始Adobe Analytics数据与当前处于Customer Journey Analytics中的Adobe Analytics数据进行比较。 [了解详情](/help/troubleshooting/compare.md)
