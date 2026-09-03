---
title: Customer Journey Analytics使用的域
description: 如果贵组织的防火墙阻止源自 Adobe 的 IP 地址，请使用此列表更新您的防火墙设置。
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 19%

---

# Customer Journey Analytics使用的域

某些防火墙配置会阻止Customer Journey Analytics作为其产品界面所依赖的域。 您可以使用此域列表来更改组织的网络设置，以允许从组织内部访问产品。 Adobe建议允许这些域通过贵组织的防火墙以获得最佳体验。

| 技术 | 域 |
| --- | --- |
| Customer Journey Analytics域 | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| ® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| ® AZURE CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX Enterprise域

除了上述域外， CX Enterprise还依靠多个域进行数据收集和导出报告。 有关此域列表，请参阅[CX Enterprise使用的域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)。

>[!MORELIKETHIS]
>
>Customer Journey Analytics使用的[IP地址](ip-addresses.md)
>
>CX Enterprise使用的[域](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
