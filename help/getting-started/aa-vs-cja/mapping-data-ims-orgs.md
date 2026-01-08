---
title: 映射来自多个IMS组织的Analytics数据
description: 了解如何请求将数据从多个源IMS组织的报表包映射到目标IMS组织。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 映射来自多个IMS组织的Analytics数据

Analytics Source Connector只能从属于您有权使用Customer Journey Analytics的同一组织的Adobe Analytics报表包中摄取数据。 从多个IMS组织映射Analytics数据的功能提供了针对此限制的解决方案。 本文概述了启用此功能的过程。


## 场景

您配置了多个IMS组织，并且在这些IMS组织的多个报表包中具有Analytics数据。 此设置可能是以下结果：

* 收购或合并
* 组织结构要求
* 区域部署限制

开箱即用型报表包无法在Customer Journey Analytics中跨多个IMS组织报告来自多个报表包的数据组合。 此限制的原因是，通过Analytics Source Connector从Adobe Analytics摄取到Experience Platform的数据仅支持摄取单个IMS组织拥有的数据。 您为其配置了以及用于登录到Adobe Analytics、Experience Platform和Customer Journey Analytics的IMS组织。

通过从多个IMS组织&#x200B;*映射Analytics数据*，您可以请求Adobe来映射数据。 该功能使用Analytics源连接器将数据从跨多个&#x200B;*源* IMS组织的报表包映射到一个&#x200B;*目标* IMS组织一部分的数据集。 例如：

| 插图 | 说明 |
|---|---|
| ![跨多个IMS组织映射数据](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 利用此映射，可通过在IMS组织3中设置的Customer Journey Analytics中的一个连接，报告存在于IMS组织1、IMS组织2和IMS组织3中的报表包。 |

{style="table-layout:fixed"}

## 使用方法

要配置和启用来自多个IMS组织的&#x200B;*映射Analytics数据*&#x200B;功能，您必须通过Adobe客户经理请求该映射。 操作方法：

1. 作为目标IMS组织管理员，请向要映射报表包的所有源IMS组织管理员请求批准电子邮件。 您可以使用以下文本作为电子邮件模板，以请求源IMS组织管理员批准。

   | 示例电子邮件模板 |
   | --- |
   | *公司名称代表*，要授予所选目标组织访问以下IMS组织（源IMS组织列表）的权限，我们需要确保每个IMS组织的管理员提交其批准以允许访问其数据。 这有助于确保我们遵守来自任何受影响的IMS组织的数据访问权限。 为确保我们获得适当的批准，请为每个管理员组织回复拥有注册的Adobe管理员，并注明其姓名及其代表的IMS组织，说“我批准”即表示他们同意将此IMS组织的数据显示在目标组织[列表目标IMS组织]中。 请注意，此管理员必须是在Adobe系统中注册为该IMS组织管理员的管理员。 |

1. 以目标IMS组织管理员身份向Adobe客户经理发送电子邮件，请求将多个源IMS组织内的报表包映射到目标IMS组织。 附上您从源IMS组织管理员收到的批准电子邮件。

客户经理收到一封电子邮件，其中包含从多个组织映射Analytics数据的请求，随后将在Adobe中审核该请求。 客户经理联系您以获取任何其他问题、可选培训及其他信息。

批准后，将创建请求的映射，并通知您。 源IMS组织名称已附加到Experience Platform中Analytics报表包[的](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)列表中的报表包名称。

## 限制和风险

以下限制适用于来自多个IMS组织的&#x200B;*映射Analytics数据*&#x200B;功能：

* 一个报表包只能跨组织连接一次。
* 您必须先删除在映射中定义为目标IMS组织的IMS组织的所有连接，然后才能请求删除映射。
* ECID在映射的源IMS组织之间不兼容，并且与目标IMS组织不兼容。
* 具有足够权限可在目标IMS组织中配置Analytics源连接器的用户可以从任何映射的源IMS组织中摄取Analytics数据。 不会为该用户检查任何源IMS组织的权限。
