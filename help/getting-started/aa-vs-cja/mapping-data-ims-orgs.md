---
title: 映射来自多个IMS组织的Analytics数据
description: 了解如何请求将来自多个源IMS组织的报表包中的数据映射到目标IMS组织中的报表包以及最终的数据集。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: ff0a5eb5b04f604eff41a18b05199b517d1a2d14
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---

# 跨IMS数据映射

本文概述如何在一个IMS组织中将多个IMS组织中报表包的数据映射到报表包，并最终映射到数据集。

默认情况下，Analytics Source Connector会从Adobe Analytics报表包中的单个组织内摄取数据。 *跨IMS数据映射*&#x200B;是一种用于映射来自多个IMS组织的Analytics数据的功能，它提供了针对此限制的解决方案。 本文概述了启用此功能的过程。


## 场景

您配置了多个IMS组织，并且在这些IMS组织的多个报表包中具有Analytics数据。 此设置可能是以下结果：

* 收购或合并
* 组织结构要求
* 区域部署限制

开箱即用型报表包无法在Customer Journey Analytics中跨多个IMS组织报告来自多个报表包的数据组合。 此限制的原因是，通过Analytics Source Connector从Adobe Analytics摄取到Experience Platform的数据仅支持摄取单个IMS组织拥有的数据。 您为其配置了以及用于登录到Adobe Analytics、Experience Platform和Customer Journey Analytics的IMS组织。

使用&#x200B;*跨IMS数据映射*&#x200B;功能，您可以请求Adobe来映射数据。 该功能使用Analytics源连接器将数据从跨多个&#x200B;*源* IMS组织的报表包映射到属于一个&#x200B;*目标* IMS组织的报表包（并最终映射到数据集）。 例如：

| 插图 | 说明 |
|---|---|
| ![跨多个IMS组织映射数据](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 利用此映射，可通过在IMS组织3中设置的Customer Journey Analytics中的一个连接，报告存在于IMS组织1、IMS组织2和IMS组织3中的报表包。 |

{style="table-layout:fixed"}

## 使用方法

要配置和启用&#x200B;*跨IMS数据映射*&#x200B;功能，您必须通过Adobe客户经理请求该映射。 操作方法：

1. 作为目标IMS组织管理员，请向要映射报表包的所有源IMS组织管理员请求批准电子邮件。 您可以使用以下文本作为电子邮件模板，以请求源IMS组织管理员批准。

   | 示例电子邮件模板 |
   | --- |
   | *公司名称代表*，要授予所选目标组织访问以下IMS组织（源IMS组织列表）的权限，我们需要确保每个IMS组织的管理员提交其批准以允许访问其数据。 这有助于确保我们遵守来自任何受影响的IMS组织的数据访问权限。 为确保我们获得适当的批准，请为每个管理员组织回复拥有注册的Adobe管理员，并注明其姓名及其代表的IMS组织，说“我批准”即表示他们同意将此IMS组织的数据显示在目标组织[列表目标IMS组织]中。 请注意，此管理员必须是在Adobe系统中注册为该IMS组织管理员的管理员。 |

1. 代表目标IMS组织管理员向Adobe客户经理发送电子邮件，请求将多个源IMS组织中的报表包映射到目标IMS组织。 附上您从源IMS组织管理员收到的批准电子邮件。

Adobe客户经理收到一封电子邮件，其中包含从多个组织映射Analytics数据的请求，随后将在Adobe中审核该请求。 有关任何其他问题、可选培训及其他信息，Adobe客户经理将与您联系。

批准后，将创建请求的映射，并通知您。 源IMS组织名称已附加到Experience Platform中Analytics报表包[的](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)列表中的报表包名称。


## 限制

以下限制适用于&#x200B;*跨IMS数据映射*&#x200B;功能：

* 一个报表包只能跨组织连接一次。
* 您必须先删除在映射中定义为目标IMS组织的IMS组织的所有连接，然后才能请求删除映射。
* ECID在映射的源IMS组织之间不兼容，并且与目标IMS组织不兼容。


## 注意事项

在请求&#x200B;*跨IMS数据映射*&#x200B;功能之前，您可能需要考虑以下主题：

### 轮廓

*跨IMS数据映射*&#x200B;功能获得批准后，您可以将目标IMS组织中一个或多个报表包的数据添加到Experience Platform。 您通过[Analytics源连接器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)的配置来执行此操作。 然后，将在Experience Platform中创建目标数据集。 在此配置和流程中，您可以选择将一个或多个报表包中的配置文件数据发送到配置文件服务。

如上所述，估计由配置和流程产生的配置文件总数。 确保总数不超过您按照合同规定有权访问目标组织的用户档案数。 应用[筛选规则和条件](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"}以选择性地包含或排除要引入到Profile服务的数据。 或者禁用将配置文件数据发送到相关报表包的配置文件服务的选项。


#### 拼接

您可以在目标数据集上同时使用[基于字段的](/help/stitching/fbs.md)和[基于图形的](/help/stitching/gbs.md)拼合。 当您对这些目标数据集中的一个或多个使用基于图形的拼接时，请确保按照[用户档案](#profiles)部分中所述遵守用户档案数量的合同权利。

如果您未获得实时客户个人资料的许可，但仍希望对一个或多个目标数据集使用基于图形的拼合，请确保仅为这些目标数据集启用[Identity Service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。


### 权限

具有足够权限可在目标IMS组织中配置Analytics源连接器的用户可以从任何映射的源IMS组织中摄取Analytics数据。 不会为该用户检查任何源IMS组织的权限。

### 数据报表

*跨IMS数据映射*&#x200B;功能只是确保您可以将数据用作Customer Journey Analytics [连接](/help/connections/overview.md)、一个或多个[数据视图](/help/data-views/data-views.md)和[工作区项目](/help/analysis-workspace/home.md)的一部分的第一步。 您需要仔细检查您现在在一个IMS组织中可用的数据。 在能够正确报告此数据之前，还要考虑数据准备、派生字段、其他查找表等功能。

