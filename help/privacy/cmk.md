---
title: 客户管理的密钥
description: 了解如何为 CJA 设置客户管理的密钥。
hide: true
hidefromtoc: true
source-git-commit: 3aa5d9e1b426e67f27ef1909a2640f335719502a
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 33%

---

# 客户管理的密钥

>[!NOTE]
>
>此功能将于 2022 年 11 月推出。

Customer Journey Analytics(CJA)提供了 [医疗盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) 和Privacy &amp; Security Shield客户使用Azure客户管理密钥(CMK)应用于您的CJA数据。  请注意，此过程与 [Adobe Experience Platform CMK设置](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>客户管理的密钥目前仅适用于已购买 [Healthcare Shield 或 Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html?lang=zh-Hans%3Flang%3Den) 附加产品的组织。

## 为CJA设置CMK

按照以下步骤为 CJA 设置 CMK：

1. 通过与Adobe帐户团队确认，确保您有权AdobeCJA CMK。
1. 确保在Azure中，您是具有特权角色（如应用程序管理员、云应用程序管理员或全局管理员）的管理员。 [从Microsoft了解更多](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. 创建一个新的仅用于 CJA 的 Azure 密钥库。[从Microsoft了解更多](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. 授予AdobeAzure应用程序对密钥保管库中的密钥的访问权限。 这是Adobe应用程序ID:251e3919-1940-4296-bb8b-6b9a5e8a4805。 [从Microsoft了解更多](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. 创建一个请求 CMK 设置的 Adobe 客户关怀票证。在您的票证中包含 Azure URI。
1. Adobe客户关怀团队将确认您的CJA数据上的CMK应用程序已完成。
