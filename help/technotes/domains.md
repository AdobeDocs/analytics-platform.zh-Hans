---
title: Customer Journey Analytics使用的域
description: 如果贵组织的防火墙阻止源自 Adobe 的 IP 地址，请使用此列表更新您的防火墙设置。
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Customer Journey Analytics使用的域

某些防火墙配置会阻止Customer Journey Analytics依赖其产品界面的域。 您可以使用此域列表来更改组织的网络设置，以允许从组织内部访问产品。 Adobe建议允许这些域通过贵组织的防火墙以获得最佳体验。

| 技术 | 域 |
| --- | --- |
| Customer Journey Analytics域 | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob存储 | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud 域

除了上述域之外，Adobe Experience Cloud还依靠多个域来收集和导出报表。 有关此域列表，请参阅[Adobe Experience Cloud使用的域](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/domains)。

>[!MORELIKETHIS]
>
>Customer Journey Analytics使用的[IP地址](ip-addresses.md)
>
>[Adobe Experience Cloud使用的域](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/domains)
