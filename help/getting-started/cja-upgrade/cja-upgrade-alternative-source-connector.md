---
title: 仅使用 Analytics 源连接器升级到 Customer Journey Analytics
description: 学习如何创建 Analytics 源连接器并映射字段
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
autotag-review: '2026-05-19T08:09:45.448Z'
TQID: 'https://experienceleague.adobe.com/KF-XUA12iIq0wGcSc4P-vGXQV56H5j-jKEgRsxLoUrI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 94%

---

# 升级替代方案：仅使用 Analytics 源连接器升级到 Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="仅使用 Analytics 源连接器"
>abstract="（不推荐）您可以使用 Analytics 源连接器作为 Customer Journey Analytics 的唯一实施路径。 <br><br>此选项通过快速将数据发送到 Customer Journey Analytics 来节省实施时间。 不过，它也有各种不足之处，例如延迟较高，将来难以脱离 Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

虽然不推荐，但您可以使用 Analytics 源连接器作为 Customer Journey Analytics 的唯一实施路径。 但是，由于此类升级存在固有的缺点，因此 Adobe 建议将 Analytics 源连接器与 Experience Platform Web SDK 的新实施结合使用。 有关此推荐升级路径的更多信息，请参阅[从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。

## 优点和缺点

使用下表中的信息了解在升级到Customer Journey Analytics时专门使用源连接器的优缺点。

| 优点 | 缺点 |
|----------|---------|
| <ul><li>最省时、最省力的升级途径。 <p>数据可以快速轻松地迁移到 Customer Journey Analytics 中。</p></li></ul> | <ul><li>**数据未发送到 Edge Network**： <p>这会导致以下缺点：</p><ul><li>在所有升级路径中，报告[延迟](/help/technotes/guardrails.md#latencies)级别最高；未针对实时个性化用例进行优化。</li><li>数据无法与其他 Adobe Experience Platform 应用程序共享；仅限于 Customer Journey Analytics</li><li>依赖于 Adobe Analytics 命名法（属性、eVar、事件等）</li></ul><li>**未来很难迁移到 Web SDK**：您最终可能会希望获得 Experience Platform Web SDK 提供的优势。 若要开始使用 Experience Platform Web SDK，您必须进行新的实施。</li><li>**使用架构中的 Analytics Experience Event 字段组**：此字段组添加了许多在您的 Customer Journey Analytics 架构中不需要的 Adobe Analytics 事件。  这可能会导致架构比 Customer Journey Analytics 实际所需的更加混乱和复杂。</li><li>**需要 Adobe Analytics 和 Customer Journey Analytics 的许可证**：使用 Analytics 源连接器需要您同时为 Adobe Analytics 和 Customer Journey Analytics 支付费用。</li></ul> |

{style="table-layout:auto"}

## 基本步骤

如果您决定将 Analytics 源连接器作为 Customer Journey Analytics 的唯一实施路径，请按照[使用源连接器摄取和使用数据](/help/data-ingestion/sources.md)中描述的实施步骤进行操作。

