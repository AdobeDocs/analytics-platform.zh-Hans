---
title: 为什么GA4和Customer Journey Analytics数据不同
description: 了解为什么GA4和Customer Journey Analytics之间的数据可以不同，以及如何审核差异。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# 为什么GA4和Customer Journey Analytics数据不同

GA4和Customer Journey Analytics通常报告同一时间段内不同的数字和相同的表观量度。 不同的数据收集方法、量度定义、身份模型和会话规则都会造成差异。 本页说明了最常见的差异来源，并为审计无法解释的差距提供了指导。

## 参与会话

GA4将会话视为&#x200B;**已参与**（如果会话持续10秒或更长时间，包含至少一个关键事件，或者有2次或更多页面查看）。 这个单一定义支持多个GA4量度，包括参与率、跳出率和活动用户背后的参与度阈值。

Customer Journey Analytics没有内置的参与会话量度或维度；您可以定义参与以匹配您的业务。 Adobe建议创建一个区段来捕获您的参与标准，并在参与很重要的任何地方重复使用该区段。 您的管理员还可以将此定义提升为数据视图中的量度，以便所有人都可以使用该定义。

在制定您自己的标准时，请选取能够真正指示您网站价值的信号。 参与的三大通用构建块包括：

* **持续时间**：最小会话长度，如10秒或更长
* **深度**：事件或页面查看的最小数目，如2个或更多
* **操作**：存在转化或密钥事件，例如注册或购买

您可以将它们与`OR`组合，这样，如果会话满足任一条件（如GA4那样），则将其计为已参与，或者将它们与`AND`组合以满足更严格的要求。 如果目标是实现与GA4的等同性，则从其默认值开始，然后从此处进行调整。

### 参与率

一旦您定义了参与会话的定义，参与率即是参与会话的份额。 要将其构建为计算量度，请执行以下操作：

1. 在Analysis Workspace中，选择指标列表旁边的&#x200B;**[!UICONTROL +]**&#x200B;图标以打开计算指标生成器。
2. 将其命名为“参与率”，并将格式设置为&#x200B;**[!UICONTROL 百分比]**。
3. 将公式定义为参与会话区段除以&#x200B;**[!UICONTROL 会话]**。
4. 选择&#x200B;**[!UICONTROL 保存]**。

### 跳出率

在GA4中，跳出与参与会话相反，因此GA4的跳出率等于`1 - Engagement Rate`。 在Customer Journey Analytics中使用该公式将其构建为第二个计算量度。

Customer Journey Analytics还提供了内置&#x200B;**[!UICONTROL 跳出率]**&#x200B;指标，但其默认定义有所不同：它计算仅记录单个事件的会话数，这与许多网站的GA4定义在方向相反。 将GA4的跳出率与默认的[!UICONTROL 跳出率]量度进行比较（而不是与您的`1 - Engagement Rate`计算进行比较）会生成截然不同的数字。

>[!TIP]
>
>Customer Journey Analytics中的会话定义可根据数据视图进行配置。 如果退回和参与定义是贵组织的报告要求，则可以对其进行调整以符合GA4的标准（10秒持续时间、2个以上页面查看次数或关键事件）。

## 会话

GA4和Customer Journey Analytics都默认设置为30分钟的非活动超时，并且两者都保持会话在午夜和会话期间营销活动更改中运行。 （在这两种情况下，Universal Analytics会重置会话，因此这些会话是常见的混淆源，但在GA4和Customer Journey Analytics之间没有区别。） 有差异的规则包括：

| 规则 | GA4 | Customer Journey Analytics |
|---|---|---|
| 非活动状态超时 | 可在整个属性范围内调整（默认为30分钟，最长为7小时55分钟） | 可按数据视图配置 |
| 会话开始事件 | 仅`session_start` （自动） | 可配置；任何事件都可以启动会话 |
| 会话结束事件 | 无 | 可配置；任何事件都可以结束会话 |

由于可以配置Customer Journey Analytics的会话定义，因此会话计数取决于数据视图的设置方式。 将数据视图的超时和会话开始事件与GA4属性进行匹配，可使平台之间的会话计数更接近。

## 人员和活动用户

GA4的主要用户量度&#x200B;**活动用户**&#x200B;计算在日期范围内至少有一个参与会话的用户。 Customer Journey Analytics中的&#x200B;**[!UICONTROL 人员]**&#x200B;指标计算日期范围内的唯一人员ID。

由于以下几种原因，预计这些量度会有所不同：

* **参与阈值**： GA4活动用户不包括没有[参与会话](#engaged-sessions)的访客。 Customer Journey Analytics中的[!UICONTROL 人员]量度包含每个人，而不管参与度级别如何。
* **[!UICONTROL 拼接]**：如果启用了拼接，则在Customer Journey Analytics中，从移动设备和桌面访问过的用户可以计为一个人，但在GA4中可以计为两个用户。 拼接通常使[!UICONTROL 人员]量度低于拼接数据集上的GA4用户。
* **身份模型**： GA4使用级联身份模型；Customer Journey Analytics使用数据集中定义的任意人员ID。 这些差异会影响人员计数，而不依赖于拼接。

## 标识和拼接

GA4使用级联标识模型来标识用户：

1. 用户ID（如果由您的实施设置）
2. Google信号（如果用户登录到启用了个性化的Google帐户）
3. 设备ID（基于Cookie的客户端ID）

在大多数实施中，该人员ID是一个ECID (Experience Cloud ID)。 可选&#x200B;**[!UICONTROL 拼接]**&#x200B;功能随后可以使用基于字段或基于图形的方法解析跨设备和跨渠道身份，从而允许将移动应用程序会话和桌面浏览器会话与同一人关联。

由于不同平台之间的标识解析度不同，因此用户级别计数很少完全匹配。 此差异是预期行为，并不表示数据质量有问题。

## 归因

GA4会应用在属性级别（在“管理员”下）配置的报表归因模型，默认使用数据驱动归因。 与Customer Journey Analytics一样，GA4会在报告时评估此模型，因此更改它将会以追溯方式更新历史和未来报告。 但是，在GA4中，该模型是属性范围的模型，仅影响使用事件范围的流量维度的关键事件报表（例如Source、Medium和Campaign）。

Customer Journey Analytics还可以在报表时应用归因，但可以更精细地控制。 可以在以下两个位置对其进行配置：

* **数据视图设置**：可以在数据视图中的任何量度组件上设置[归因模型](/help/data-views/component-settings/attribution.md)，从而在所有报表中为该量度设置默认值。 默认情况下，不应用任何归因模型。 您可以将数据视图配置为包含同一量度的多个副本，每个副本使用不同的默认归因模型。
* **组件级覆盖**：将量度拖入[!UICONTROL 自由格式表]后，右键单击其列标题并选择&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;为该实例覆盖它。 您还可以将同一量度拖入表中多次，每一次都使用不同的归因模型来进行直接的并排比较。

由于GA4默认使用数据驱动归因，而Customer Journey Analytics除非您配置模型，否则不应用任何模型，因此转化和渠道量度在您将它们调整之前可能会有所不同。 将GA4设置为最后点击模型并在Customer Journey Analytics中配置匹配的最后接触模型是建立类似基线的最可靠方法。 Customer Journey Analytics中的任何模型更改都将逆向应用于所有历史数据，而无需重新处理。

## 审核差异

当数字的差异超出预期时，可以使用三个审核路径：

* **Assurance**： Adobe的产品内验证工具将确认XDM事件正确触发，并发送到Edge Network和写入Platform数据集。 在比较报表数量之前，请使用此工具验证实施。
* **数据集预览**：在Platform UI中，您可以预览任何数据集中的原始行。 将这些规则与GA4的DebugView或BigQuery导出进行比较，以验证字段级别的准确性。
* **Adobe Consulting**：对于持续存在且无法解释的差异，您的Adobe客户团队可以安排与Adobe顾问进行正式的实施审核。
* **摄取检查**：如果您怀疑差异产生于GA数据被引入Platform的方式而不是报告定义中，请查看[从Google Analytics迁移数据](/help/use-cases/third-party/ga/overview.md)中的摄取设置。
