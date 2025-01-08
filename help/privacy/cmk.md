---
title: 客户管理的密钥
description: 了解如何设置客户管理的密钥以进行Customer Journey Analytics。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 14%

---

# 客户管理的密钥

Adobe Customer Journey Analytics为[Healthcare Shield](https://www.adobe.com/cn/trust/compliance/hipaa-ready.html)和Privacy &amp; Security Shield客户提供了将客户管理的密钥(CMK)用于Customer Journey Analytics数据的选项。 请注意，此过程与[Adobe Experience Platform CMK设置](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview)不同。 客户管理的密钥仅适用于已购买[Healthcare Shield或Privacy &amp; Security Shield](https://experienceleague.adobe.com/zh-hans/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield)附加产品的组织。

## 设置客户管理的密钥以在Azure上Customer Journey Analytics

按照以下步骤为Azure上运行的Customer Journey Analytics设置CMK：

1. 确保您有权使用Adobe Customer Journey Analytics CMK，并且您的组织使用在Azure上运行的Adobe Experience Platform。 您可以通过联系Adobe客户团队来检查这些权利。
1. 确保您在 Azure 中是具有特权角色的管理员，例如应用程序管理员、云应用程序管理员或全局管理员。有关详细信息，请参阅[Microsoft Entra内置角色](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)。
1. 创建仅用于Customer Journey Analytics的新Azure密钥库。 有关详细信息，请参阅[Microsoft Azure Key Vault文档](https://learn.microsoft.com/zh-cn/azure/key-vault/general/)。
1. 授予 Adobe Azure 应用程序访问您在密钥库中的密钥的权限。有关详细信息，请参阅[为现有帐户配置客户管理的密钥](https://learn.microsoft.com/zh-cn/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)。 Adobe的应用程序ID为：

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. 创建一个请求 CMK 设置的 Adobe 客户关怀票证。在您的票证中包含 Azure URI。可在Azure密钥的&#x200B;**密钥标识符**&#x200B;字段中找到URI：

   ![键标识符字段显示https://cmkoberontest.vault.azure.net](assets/key-identifier.png)的URI

1. Adobe客户关怀部门会确认对您的Customer Journey Analytics数据完成了CMK应用。

无论是否使用客户管理的密钥，Platform使用的所有数据在传输和静止时都经过加密，以确保您的数据安全。 有关Adobe Experience Platform加密的信息，请参阅[Adobe Experience Platform中的数据加密](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption)。

## 设置客户管理的密钥，以在Amazon Web Services上Customer Journey Analytics

>[!AVAILABILITY]
>
>本节适用于在Amazon Web Services (AWS)上运行的Experience Platform的实施。 在AWS上运行的Experience Platform当前仅对有限数量的客户可用。 要了解有关支持的Experience Platform基础架构的更多信息，请参阅[Experience Platform多云概述](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud)。

如果您的组织使用在Amazon Web Services上运行的Adobe Experience Platform，则已为您配置了CMK。 无需其他设置。
