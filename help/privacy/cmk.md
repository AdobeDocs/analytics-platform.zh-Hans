---
title: 客户管理的密钥
description: 了解如何为CJA设置客户管理的密钥。
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 客户管理的密钥

>[!NOTE]
>
>此功能将于2022年11月提供。

Customer Journey Analytics(CJA)提供了 [医疗盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) 和Privacy &amp; Security Shield客户使用Azure客户管理密钥(CMK)应用于您的CJA数据。  请注意，此过程与 [Adobe Experience Platform CMK设置](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>客户管理的密钥当前仅适用于已购买 [医疗保健盾或隐私与安全盾](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 附加产品。

请按照以下步骤为CJA设置CMK:

1. 通过与您的Adobe帐户团队核实，确保您有权使用CMK。
1. 创建新的Azure密钥保管库，以便仅与CJA一起使用。
1. 将您的Azure密钥值绑定到Azure CJA CMK应用程序（链接如下）。
1. 创建请求CMK设置的Adobe客户关怀票证。 将Azure URI包含在票证中。
1. Adobe客户关怀团队将确认您的CJA数据上的CMK应用程序已完成。
