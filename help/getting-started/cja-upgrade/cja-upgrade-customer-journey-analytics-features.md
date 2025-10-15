---
title: 了解 Customer Journey Analytics 独有的功能
description: 了解 Customer Journey Analytics 独有的功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 100%

---

# 了解 Customer Journey Analytics 独有的功能 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="将不同来源的数据结合在一起"
>abstract="（推荐）整合来自各种 Web、Mobile 和离线属性的数据，以创建一个单一的、整合的客户行为视图。将来自其他渠道的分析数据结合起来的能力是 Customer Journey Analytics 的主要用例。"

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
>title="联系 Adobe 客户关怀部门以生成拼接数据集"
>abstract="如果您的某个字段包含标识符，而此标识符不是主要标识符且存在于多个数据集中，则可以使用它生成具有一致标识符的新数据集。"

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
>abstract="Adobe 建议与 Adobe Journey Optimizer 集成以实现个性化用例。可以与 Adobe Target 集成，但这只是短期的解决方案。"

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
>abstract="Adobe 建议与 Adobe Real-Time CDP 集成，以满足基于受众的用例。可以与 Audience Manager 集成，但这只是短期的解决方案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表仅显示升级过程中需要考虑的 Customer Journey Analytics 功能。有关显示哪些 Adobe Analytics 功能在 Customer Journey Analytics 中完全受支持、部分受支持或不受支持的完整列表，请参阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

当您升级到 Customer Journey Analytics 时，请考虑要采用以下哪些 Customer Journey Analytics 功能：

| Customer Journey Analytics 功能 | 功能 |
|---------|----------|
| [将网络数据与来自其他渠道的数据（例如呼叫中心数据）联系起来](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。使用[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。Adobe Analytics 主要专注于 Web 和移动分析数据，并具有一些[数据导入](https://experienceleague.adobe.com/docs/analytics/import/home.html)功能。 |
| [使用自定义维度拼接来自其他数据集的匹配项](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/overview) | 通过 Customer Journey Analytics，可从多个报告包[组合数据](/help/connections/combined-dataset.md)，如同它们是 Adobe Analytics 中的单个报告包一样。 |
| [与 Adobe Real-Time CDP 集成](/help/components/audiences/audiences-overview.md) | 您现在可以在 Adobe Experience Platform 中[创建受众并将在 Customer Journey Analytics 中发现的受众](/help/components/audiences/audiences-overview.md)发布到实时客户轮廓，以实现和个性化。 |
| [与 Adobe Target 集成 (A4T)](/help/integrations/at.md) | Customer Journey Analytics 中的 Target 报告可让您直接在 Customer Journey Analytics 中[衡量并报告 Adobe Target 活动](/help/integrations/at.md)。不过，Adobe 建议与 Adobe Journey Optimizer 集成以实现个性化用例。 |
| [与 Adobe Journey Optimizer 集成](/help/integrations/ajo.md) | 您可以配置 Journey Optimizer 生成的数据，[在 Customer Journey Analytics 中执行高级分析](/help/integrations/ajo.md)。 |
| [与 Adobe Audience Manager 集成](https://experienceleague.adobe.com/zh-hans/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | 您可以[将 Audience Manager 特征和区段共享至 Adobe Experience Platform](https://experienceleague.adobe.com/zh-hans/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing)。不过，Adobe 建议与 Adobe Real-Time CDP 集成，以实现基于受众的用例。 |
