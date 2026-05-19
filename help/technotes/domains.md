---
title: Customer Journey Analytics使用的域
description: 如果贵组织的防火墙阻止源自 Adobe 的 IP 地址，请使用此列表更新您的防火墙设置。
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

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
