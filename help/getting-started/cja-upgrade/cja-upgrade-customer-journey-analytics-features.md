---
title: 了解 Customer Journey Analytics 独有的功能
description: 了解Customer Journey Analytics特有的功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: d745e0c3bc75ba6f9d29aedcdbaaae9aa17d6ab8
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 27%

---

# 了解 Customer Journey Analytics 独有的功能 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="将不同来源的数据结合在一起"
>abstract="（推荐）关联来自各种Web、移动和离线属性的数据，以创建客户行为的单个整合视图。 这种组合来自其他渠道的分析数据的功能是Customer Journey Analytics的主要用例。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="拼接来自多个数据集的点击量"
>abstract="如果您的任何数据集不共享主要标识符（例如 Experience Cloud ID），您仍然可以使用其他维度（例如登录用户名或电子邮件地址）将该数据拼接在一起。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="联系Adobe客户关怀团队以生成拼合的数据集"
>abstract="如果某个字段包含的标识符存在于多个数据集中，但不是主标识符，则可以使用该标识符生成具有一致标识符的新数据集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="与实时CDP集成"
>abstract="合并来自多个来源的配置文件数据，以根据用户特征生成受众和区段。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="临时与Adobe Target集成"
>abstract="Adobe建议与Adobe Journey Optimizer集成，以实施个性化用例。 与Adobe Target集成是可能的，但这是一个短期解决方案。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="与Journey Optimizer集成"
>abstract="为客户提供互联、情境式和个性化的体验。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="暂时与 Adobe Audience Manager 集成"
>abstract="对于基于受众的用例，Adobe建议与Adobe Real-time CDP集成。 与Audience Manager集成是可能的，但这是一个短期解决方案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表仅显示那些在升级过程中需要考虑的Customer Journey Analytics功能。 有关显示Customer Journey Analytics完全支持、部分支持或不支持哪些Adobe Analytics功能的完整列表，请参阅[Customer Journey Analytics功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

在升级到Customer Journey Analytics时，请考虑您要采用以下哪些Customer Journey Analytics功能：

| Customer Journey Analytics功能 | 功能 |
|---------|----------|
| [将Web数据与来自其他渠道的数据（如呼叫中心数据）绑定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics 与 Experience Platform 保存各种数据架构和类型的能力相结合。使用[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。Adobe Analytics 主要专注于 Web 和移动分析数据，并具有一些[数据导入](https://experienceleague.adobe.com/docs/analytics/import/home.html)功能。 |
| 使用自定义维度[拼接来自其他数据集的点击](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | 通过 Customer Journey Analytics，可从多个报告包[组合数据](/help/connections/combined-dataset.md)，如同它们是 Adobe Analytics 中的单个报告包一样。 |
| [与Adobe Real-time CDP集成](/help/components/audiences/audiences-overview.md) | 您可以[创建在Customer Journey Analytics中发现的受众](/help/components/audiences/audiences-overview.md)并将其发布到Adobe Experience Platform中的实时客户个人资料，以实现客户定位和个性化。 |
| [与Adobe Target (A4T)集成](/help/integrations/at.md) | Customer Journey Analytics中的Target报表功能允许您直接在Customer Journey Analytics中[测量和报告Adobe Target活动](/help/integrations/at.md)。 但是，Adobe建议与Adobe Journey Optimizer集成以个性化用例。 |
| [与Adobe Journey Optimizer集成](/help/integrations/ajo.md) | 您可以将Journey Optimizer生成的数据配置为在Customer Journey Analytics](/help/integrations/ajo.md)中[执行高级分析。 |
| [与Adobe Audience Manager集成](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | 您可以[将Audience Manager特征和区段共享到Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing)。 但是，对于基于受众的用例，Adobe建议与Adobe Real-time CDP集成。 |
