---
title: GA4数据模型如何映射到Customer Journey Analytics
description: 了解GA4基于事件的数据模型如何转换为Customer Journey Analytics中的XDM架构和数据集。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# GA4数据模型如何映射到Customer Journey Analytics

GA4和Customer Journey Analytics都是基于事件的平台，这使得它们之间的数据模型转换比Universal Analytics中的数据模型转换更直接。 通过了解GA4的事件和参数如何与Customer Journey Analytics的XDM字段和数据集相对应，可以更轻松地解释报表并与实施团队协作。

## GA4基于事件的数据模型

GA4中的每个交互都是&#x200B;**事件**：具有提供上下文的可选&#x200B;**参数**&#x200B;集的命名操作。 页面查看、会话或目标没有单独的对象类型 — 它们都是事件。

| GA4事件类型 | 示例 |
|---|---|
| 自动收集 | `page_view`, `session_start`, `first_visit`, `scroll` |
| 增强的测量 | `file_download`, `video_start`, `form_submit` |
| 建议 | `purchase`, `add_to_cart`, `sign_up` |
| 自定义 | 您定义的任何事件名称 |

每个事件最多可包含25个参数。 例如，`purchase`事件通常包括`transaction_id`、`value`、`currency`和`items`作为参数。

## Customer Journey Analytics如何存储数据

Customer Journey Analytics从&#x200B;**Adobe Experience Platform**&#x200B;获取数据。 Platform中的数据存储在&#x200B;**数据集**&#x200B;中，每个数据集都符合使用&#x200B;**体验数据模型(XDM)**&#x200B;构建的&#x200B;**架构**。 XDM是Adobe用于表示客户体验数据的开放标准。

Customer Journey Analytics中使用了三种数据集类型：

| CJA数据集类型 | GA4等效项 | 它包含的内容 |
|---|---|---|
| [!UICONTROL 事件数据集] | GA4事件流 | 时间序列交互（页面查看次数、点击次数、购买次数） |
| [!UICONTROL 配置文件数据集] | GA4用户属性 | 人员级别属性（CRM字段、忠诚度状态、人口统计） |
| [!UICONTROL 查找数据集] | 用作参考表的GA4自定义维度 | 键值引用数据（产品目录、促销活动名称） |

Customer Journey Analytics没有eVar、prop或成功事件。 所有维度和量度都直接源自XDM架构字段。 唯一维度值的数量没有限制。

## 自动收集的事件

GA4通过其SDK自动收集一组事件。 下表将这些事件映射到其XDM或Customer Journey Analytics等效项。

| GA4自动收集事件 | XDM/Customer Journey Analytics等效项 |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` （标准XDM字段） |
| `session_start` | 会话开始（自动，根据数据视图会话定义） |
| `first_visit` | [!UICONTROL 第一个会话]区段 |
| `scroll` | 自定义事件（需要显式实现映射） |
| `click` | `xdm.web.webInteraction`字段（需要实施） |
| `video_start` / `video_complete` | 媒体收集架构字段（使用Adobe流媒体服务） |
| `purchase` | `xdm.commerce.purchases`，`xdm.commerce.order` （标准XDM商务架构） |
| `add_to_cart` | `xdm.commerce.productListAdds` （标准XDM商务架构） |

>[!NOTE]
>
>使用Web SDK实施时，几个GA4的增强型测量事件（如滚动、文件下载或视频）需要明确映射到XDM字段。 它们自动收集的方式与GA4的SDK处理它们的方式不同。

## 自定义事件和参数

在GA4中，自定义事件具有名称和最多25个参数。 在Customer Journey Analytics中，自定义事件映射到实施期间定义的自定义XDM架构字段：

* **事件名称**&#x200B;成为XDM字段中的字段值（通常为[`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)）。
* 每个&#x200B;**参数**&#x200B;都成为单独的XDM架构字段。 在[配置数据视图](/help/data-views/component-settings/overview.md)时，任何XDM字段都可以公开为维度或量度。

>[!NOTE]
>
>贵组织的自定义事件的特定XDM字段路径是在Web SDK实施期间确定的。 在构建报告之前，请与您的实施团队合作，了解您的特定字段映射。 有关详细信息，请参阅[架构您的架构](../cja-upgrade/cja-upgrade-schema-architect.md)。

## 用户属性

GA4用户属性是在用户上设置的永久属性（例如，`membership_tier`或`account_type`）。 在Customer Journey Analytics中，这些映射到Platform中的&#x200B;**配置文件数据集**。

用户档案数据集与事件数据单独摄取，并在Customer Journey Analytics中使用共享的人员ID与其联接。 在此上下文中使用的常见人员ID包括客户ID或电子邮件哈希。 在联接后，这些配置文件属性将作为维度与事件级别的数据一起在Analysis Workspace中可用。

此方法比GA4的用户属性模型提供了Customer Journey Analytics更大的灵活性：GA4将您限制为只能使用其SDK中定义的用户属性，而Customer Journey Analytics配置文件数据集可以包含来自任何系统（CRM、忠诚度平台、支持记录）的任何属性，前提是它共享一个可联合的标识符。

如果您的组织仍需要将GA数据引入Adobe Experience Platform，请参阅[摄取Google Analytics历史数据](/help/use-cases/third-party/ga/backfill.md)和[为面向管理员的设置指南配置流式传输Google Analytics数据](/help/use-cases/third-party/ga/streaming.md)。
