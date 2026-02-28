---
title: 构建用于 Customer Journey Analytics 的架构
description: 了解如何设计一个能够释放Customer Journey Analytics灵活性并支持从Adobe Analytics进行实际迁移的XDM架构。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 5808de9b39d3c8fa5632755958ddb887c081b203
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 9%

---

# 构建用于 Customer Journey Analytics 的架构 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="架建架构"
>abstract="在您的组织内讨论数据收集的要求，并确定如何生成用于 Adobe Experience Platform 的架构。出现此步骤是因为您想要使用一个为您的组织定制的架构的使用推荐过程。正确执行此步骤至关重要，因为组织内所有团队都遵循一个架构可以使数据摄取变得更加容易。<br><br>将组织中的所有相关方聚集在一起以遵循一个统一架构的预计时间为 1-2 个月。这个时间范围在很大程度上取决于需要协调的团队数量以及需要统一的维度 + 量度的数量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe建议在实施[Customer Journey Analytics数据收集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home)时为Adobe Experience Platform创建自定义[Experience Data Model](https://experienceleague.adobe.com/en/docs/experience-platform/collection/home) (XDM)架构。 创建此架构通常在涉及任何实施更改或代码之前完成。 通过自定义架构，您可以设计简洁的、特定于组织的数据合同，而无需继承Adobe Analytics的约束。 请参阅[选择您的Customer Journey Analytics架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)，了解有关您的组织可用的架构类型的更多信息。

架构旨在完善您想要长期构建数据的方式。 对架构的更改成本高昂，因为它们会影响数据收集、验证和下游服务。 您可以在业务要求允许的情况下随着时间的推移添加到架构中；但是，一旦数据开始流入架构字段，就无法删除架构字段。

## 比较架构与数据视图

Customer Journey Analytics的数据管道包含单独的区域，可用于数据收集和数据解释。 从Adobe Analytics升级时，一个常见的错误步骤是尝试通过prop和eVar在XDM中的行为重新创建prop和eVar。 请改用Web SDK来收集数据，并使用[数据视图](/help/data-views/data-views.md)来确定如何在报表中解释该数据。

| 图层 | 主要目的 | 灵活性 | 属于什么 | 不属于 |
|---|---|---|---|---|
| **XDM架构** | 定义所收集数据的持久结构和含义 | 刚性；被视为不可变数据点 | 事件和实体形状、字段含义、关系、允许的值、跨渠道重用 | 编号的“插槽”(eVar1/prop1)、归因/持久性逻辑、特定于报表的解决方法 |
| **数据视图** | 定义收集的数据在分析中的行为方式 | 灵活；可以自由修改，并且可以追溯性地重新解释数据 | 组件设置、归因和持久性行为、派生字段、过滤量度、计算量度 | 字段的基本含义；该含义在架构中应是稳定的 |

## 比较架构与Adobe Analytics数据收集

Customer Journey Analytics使用的Experience Data Model比大多数其他Analytics解决方案(包括Adobe Analytics)具有更大的灵活性。 建立一个稳固的架构是贵组织避免执行其他Analytics产品中存在的限制的机会。

| Adobe Analytics的常见习惯 | XDM + Customer Journey Analytics中更好的方法 |
|---|---|
| 围绕编号插槽(`eVar1`-`eVar250`， `prop1`-`prop75`)进行设计 | 创建具有稳定含义的字段（例如，`search.term`、`content.category`、`user.membershipTier`）并一致地重复使用它们 |
| 将持久性/分配/到期编码到数据模型中 | 捕获架构中的持久事实；在数据视图级别应用归因和持久性行为 |
| 在多个变量中复制相同的值以实现报告行为 | 将该值存储一次，并在数据视图中从中创建多个组件（维度/量度） |
| 为每个可能需要的计数创建一个唯一的“量度字段” | 捕获一次正确的事实（通常为枚举/布尔值/字符串），然后将量度定义为数据视图中的过滤计数 |
| 设计变量以“预解决”报表 | 设计架构以捕获事实并使用数据视图解决报告语义 |

## 使用通用属性建立架构

当您标准化出现在许多事件中的一组可重用属性时，就有可能实现跨渠道的统一架构。 一些示例包括：

* **体验上下文：**&#x200B;站点/应用程序名称、环境、区域设置、渠道、品牌
* **历程上下文：**&#x200B;营销活动标识符，引用上下文，试验标识符
* **用户状态：**&#x200B;登录状态、成员层、帐户类型
* **交互详细信息：**&#x200B;交互名称/类型、UI区域、元素标签、错误类别

关键是要标准化字段代表的含义，而不管渠道如何。 避免跨渠道以不同的方式建模相同的概念，除非它们真正表示不同的概念。 例如，可能明智的做法是避免为Web营销活动ID和移动营销活动ID设置单独的架构字段。 单独的架构字段使得建立广告支出数据的跨渠道回报率更加困难。 如果报表中需要区分，您可以按渠道进行细分或连接多个字段以提供该区分。 同一架构字段可用于任意数量的维度或量度。

在保持单个架构策略的同时支持多个渠道的实用方法是使用&#x200B;**核心+扩展**&#x200B;模式：

* **核心：**&#x200B;广泛适用于各个渠道和团队的字段
* **扩展：**&#x200B;特定于渠道或域的字段组，这些字段组仅在需要时适用（Web交互、商务、移动生命周期、服务器端详细信息）

此模式支持单一组织模式策略，不会强制团队填充不必要的字段。

## 首选适合的标准字段组

Adobe建议在符合您需求的地方使用标准化的字段组，并使用自定义字段进行扩展，以了解特定于组织的概念。

标准字段组通常可帮助您：

* 使用已知字段语义减少歧义
* 更轻松地跨团队校准
* 支持跨Adobe Experience Platform应用程序的互操作性

自定义字段适用于以下情况：

* 您的组织具有无法完全映射到标准字段的概念
* 您需要其他属性以满足报告、治理或激活要求
* 您希望表示特定于业务的分类（例如，内部内容类别）

## 确定如何计算指标

在Adobe Analytics中，许多团队将`events`变量视为跟踪量度的唯一方法。 在Customer Journey Analytics中，您可以通过多种方式跟踪量度，具体取决于您需要计数的内容以及您希望如何解释这些内容。

在构建架构时，要坚持事实。 例如，`error.type = "validation"`，`user.isLoggedIn = true`，`checkout.step = "shipping"`。 将数据视图中的量度定义为这些事实的计数和过滤计数。 例如：

* `checkout.step` （枚举/字符串）可以为：
   * “结帐：到达送货步骤”（此处为`checkout.step == "shipping"`计数）
   * “结帐：已到达付款步骤”
* `error.type` （枚举/字符串）可以为：
   * “验证错误”
   * “授权错误”
* `user.isLoggedIn` （布尔值）可以为：
   * “经过身份验证的会话”
   * &quot;经过身份验证的转化&quot;

>[!TIP]
>
>在决定某个内容是否应是架构中的专用字段还是之后的派生字段时，如果持久事实广泛有用且稳定，则偏好捕获架构中的持久事实。 您可以使用派生字段在收集后更正数据或调整数据形状。

## 在过渡期间保持与Adobe Analytics的等同性，而不带架构包袱

某些组织在升级到Customer Journey Analytics时需要继续Adobe Analytics报表。 您可以使用以下方法维护对等性，而无需将特定于Analytics的工件引入长期架构设计：

1. **使用Adobe Analytics可识别和自动映射的XDM字段路径：**&#x200B;当您通过Edge Network将可识别的XDM字段发送到Adobe Analytics时，这些字段会[自动映射](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/xdm-var-mapping)，无需额外配置。
1. **对特定于组织的概念使用自定义XDM字段：**&#x200B;任何未自动映射到Analytics变量的XDM字段在Adobe Analytics中作为[上下文数据变量](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/vars/page-vars/contextdata)转发。
1. **使用Adobe Analytics处理规则将这些上下文数据变量映射到prop/eVars：** [处理规则](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview)最终使您可以将任何自定义XDM字段映射到任何eVar或prop。 此概念支持Adobe Analytics中的奇偶校验报表，同时保持架构干净并以Customer Journey Analytics为中心。

## 确定利益相关者并确定所有权

如果同意并维护字段含义，则架构设计成功。 虽然组织结构不同，但通常由以下角色参与：

* **Analytics管理员/分析员**：定义报告问题，验证字段表示有意义的概念，并审查数据视图中的分析语义。
* **开发人员/实施所有者**：确保可以使用Web SDK可靠地收集字段，并与数据层/应用程序检测一致。
* **数据架构师/工程师**：确保架构一致性、跨域重用以及与下游服务的兼容性。
* **隐私/治理利益相关者**：审查数据最小化、同意期望和数据使用约束。

为架构更改定义一个清除所有者。 具有严格变更控制的稳定模式可以防止下游中断并减少返工。 考虑使用跟踪治理工作流或工具使请求民主化并管理一段时间的更改控制。

## 隐私和治理注意事项

架构设计应根据贵组织的隐私政策反映隐私和治理期望。 在架构架构时，请考虑以下几点：

* 仅收集支持定义的用例所需的内容。
* 确保在收集策略中反映同意和数据使用要求。 有关详细信息，请参阅[使用Web SDK处理客户同意数据](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/consent/sdk)。
* 考虑如何在Adobe Experience Platform治理工具中标记和控制敏感字段。 有关详细信息，请参阅[Adobe Customer Journey Analytics和数据管理](/help/privacy/privacy-overview.md)。

## 后续步骤

一旦您建立并同意架构架构，就可以开始在Adobe Experience Platform中创建它。 有关详细信息，请参阅[创建要与Customer Journey Analytics一起使用的自定义架构](cja-upgrade-schema-create.md)。
