---
title: 了解 Customer Journey Analytics 独有的功能
description: 了解 Customer Journey Analytics 独有的功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
TQID: https://experienceleague.adobe.com/8yBVFyHrc31-ac8XLV-aW-SWBfDZodlIXirICmdzpkY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 591
ht-degree: 100%

---

# 了解 Customer Journey Analytics 独有的功能 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="将不同来源的数据结合在一起"
>abstract="（推荐）整合来自各种 Web、Mobile 和离线属性的数据，以创建一个单一的、整合的客户行为视图。 将来自其他渠道的分析数据结合起来的能力是 Customer Journey Analytics 的主要用例。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="拼接来自多个数据集的点击量"
>abstract="如果您的任何数据集不共享主要身份标识符（例如 Experience Cloud ID），您仍然可以使用其他维度（例如登录用户名或电子邮件地址）将该数据拼接在一起。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="为相关数据集启用拼接"
>abstract="如果某个字段包含的标识符存在于多个数据集中但不是主标识符，则可以使用拼接功能将数据提升到这些数据集中的一个或多个。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="与 Real-Time CDP 集成"
>abstract="合并来自多个来源的轮廓数据，根据用户特征生成受众和区段。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="暂时与 Adobe Target 集成"
>abstract="Adobe 建议与 Adobe Journey Optimizer 集成以实现个性化用例。 可以与 Adobe Target 集成，但这只是短期的解决方案。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="与 Journey Optimizer 集成"
>abstract="为客户提供贴合心意的、上下文和个性化的体验。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="暂时与 Adobe Audience Manager 集成"
>abstract="Adobe 建议与 Adobe Real-Time CDP 集成，以满足基于受众的用例。 可以与 Audience Manager 集成，但这只是短期的解决方案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表仅显示升级过程中需要考虑的 Customer Journey Analytics 功能。 有关显示哪些 Adobe Analytics 功能在 Customer Journey Analytics 中完全受支持、部分受支持或不受支持的完整列表，请参阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

当您升级到 Customer Journey Analytics 时，请考虑要采用以下哪些 Customer Journey Analytics 功能：

| Customer Journey Analytics 功能 | 功能 |
|---------|----------|
| [将网络数据与来自其他渠道的数据（例如呼叫中心数据）联系起来](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。 使用[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。 Adobe Analytics 主要专注于 Web 和移动分析数据，并具有一些[数据导入](https://experienceleague.adobe.com/docs/analytics/import/home.html)功能。 |
| [使用自定义维度拼接来自其他数据集的匹配项](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/overview) | 通过 Customer Journey Analytics，可从多个报告包[组合数据](/help/connections/combined-dataset.md)，如同它们是 Adobe Analytics 中的单个报告包一样。 |
| [与 Adobe Real-Time CDP 集成](/help/components/audiences/audiences-overview.md) | 您现在可以在 Adobe Experience Platform 中[创建受众并将在 Customer Journey Analytics 中发现的受众](/help/components/audiences/audiences-overview.md)发布到实时客户轮廓，以实现和个性化。 |
| [与 Adobe Target 集成 (A4T)](/help/integrations/at.md) | Customer Journey Analytics 中的 Target 报告可让您直接在 Customer Journey Analytics 中[衡量并报告 Adobe Target 活动](/help/integrations/at.md)。 不过，Adobe 建议与 Adobe Journey Optimizer 集成以实现个性化用例。 |
| [与 Adobe Journey Optimizer 集成](/help/integrations/ajo.md) | 您可以配置 Journey Optimizer 生成的数据，[在 Customer Journey Analytics 中执行高级分析](/help/integrations/ajo.md)。 |
| [与 Adobe Audience Manager 集成](https://experienceleague.adobe.com/zh-hans/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | 您可以[将 Audience Manager 特征和区段共享至 Adobe Experience Platform](https://experienceleague.adobe.com/zh-hans/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing)。 不过，Adobe 建议与 Adobe Real-Time CDP 集成，以实现基于受众的用例。 |
