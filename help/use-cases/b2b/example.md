---
title: B2B 项目示例
description: 了解如何设置、配置和报告B2B数据
solution: Customer Journey Analytics
feature: Use Cases
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 20756b289912dfcc4e0539db4d1ae36d1496a266
workflow-type: tm+mt
source-wordcount: '1205'
ht-degree: 7%

---

# B2B 项目示例

本文介绍了如何在Customer Journey Analytics中设置、配置和报告基于用户档案（人员）级别的B2B数据。

## 连接

定义您的连接以包含Experience Platform中的所有相关B2B数据集。 可以考虑添加到连接的数据集：

| 数据集 | 架构 | 架构类型 | 基类 | 描述 |
|---|---|---|---|---|
| B2B活动数据集 | B2B活动模式 | 事件 | XDM ExperienceEvent | ExperienceEvent是所发生情况的事实记录，包括时间点和所涉及的个人身份。 ExperienceEvents可以是显式的（可直接观察的人类行为）或隐式的（在没有直接人类行为的情况下引发），并且无需聚合或解释即可记录。 体验事件对于时域分析至关重要，因为它们允许观察和分析给定时间段内发生的变化，并在多个时间段之间进行比较以跟踪趋势。 |
| B2B人员数据集 | B2B人员模式 | 配置文件 | XDM个人资料 | XDM个人资料形成已识别和部分识别的个人的属性和兴趣的单一表示。 识别度较低的用户档案可能仅包含匿名行为信号，如浏览器Cookie，而识别度较高的用户档案可能包含详细的个人信息，如姓名、出生日期、位置和电子邮件地址。 随着用户档案的发展，它成为个人信息、身份信息、联系人详细信息和个人通信偏好设置的强大存储库。 |
| B2B帐户数据集 | B2B帐户架构 | 查询 | XDM业务帐户 | XDM业务帐户是一个标准体验数据模型(XDM)类，可捕获业务帐户的最低要求属性。 此XDM类只能包含在具有B2B或B2P版本的客户的配置文件中。 |
| B2B Opportunity数据集 | B2B机会架构 | 查询 | XDM商业机会 | XDM业务机会是一个标准体验数据模型(XDM)类，可捕获业务机会的最低要求属性。 此XDM类只能包含在具有B2B或B2P版本的客户的配置文件中。 |
| B2B Campaign数据集 | B2B营销活动模式 | 查询 | XDM商业营销活动 | XDM商业营销活动是一个标准体验数据模型(XDM)类，可捕获商业营销活动的最低要求属性。 此XDM类只能包含在具有B2B或B2P版本的客户的配置文件中。 |
| B2B营销列表数据集 | B2B营销列表架构 | 查询 | XDM业务营销列表 | XDM业务营销列表是一个标准体验数据模型(XDM)类，可捕获营销列表的最低要求属性。 营销列表允许您优先考虑最有可能购买您的产品的潜在客户。 此XDM类只能包含在具有B2B或B2P版本的客户的配置文件中。 |
| B2B帐户人员关系数据集 | B2B帐户人员关系架构 | 查询 | XDM 业务帐户人员关系 | XDM业务帐户人员关系是一个标准体验数据模型(XDM)类，可捕获与业务帐户关联的人员的最低要求属性。 |
| B2B机会人员关系数据集 | B2B机会人员关系架构 | 查询 | XDM 业务机会人员关系 | XDM业务机会人员关系是一个标准体验数据模型(XDM)类，可捕获与业务机会关联的人员的最低要求属性。 |
| B2B营销列表成员数据集 | B2B营销列表成员架构 | 查询 | XDM营销列表成员 | XDM业务营销列表成员是一个标准的体验数据模型(XDM)类，它描述了与营销列表关联的成员、人员或联系人。 |
| B2B营销活动成员数据集 | B2B营销活动成员架构 | 查询 | XDM 商业营销活动成员 | XDM商业营销活动成员是一个标准体验数据模型(XDM)类，它描述了与商业营销活动关联的联系人或商机。 |

<!--
| B2B Account Dataset | B2B Account Schema | Lookup | XDM Business Account | XDM Business Account is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business account.  |
| B2B Opportunity Dataset | B2B Opportunity Schema | Lookup | XDM Business Opportunity | XDM Business Opportunity is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business opportunity.  |
| B2B Campaign Dataset | B2B Campaign Schema | Lookup | XDM Business Campaign | XDM Business Campaign is a standard Experience Data Model (XDM) class that captures the minimum required properties of a business campaign.  |
| B2B Marketing List Dataset | B2B Marketing List Schema | Lookup | XDM Marketing List | XDM Business Marketing List is a standard Experience Data Model (XDM) class that captures the minimum required properties of a marketing list. Marketing lists allow you to prioritize on prospect clients who are most likely to buy your product.  |
-->


B2B查找架构、配置文件架构和事件架构之间的关系在Experience Platform内的B2B设置中定义。 查看[Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b)中的架构和[在Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/relationship-b2b)中定义两个架构之间的多对一关系。


要确保正确设置支持B2B数据基于人员的查找的连接，请使用下图进行概述并执行以下步骤：

![已注释的B2B架构](assets/b2b-schemas-annotated.svg)

1. 将上表中的数据集添加到您的连接。
1. 对于您添加到连接的每个查找数据集，必须在&#x200B;**[!UICONTROL 编辑数据集]**&#x200B;对话框中使用&#x200B;**[!UICONTROL 键]**&#x200B;和&#x200B;**[!UICONTROL 匹配键]**&#x200B;显式定义与事件数据集的关系。
1. 对于要为基于人员的B2B查找转换的每个查找数据集，请启用&#x200B;**[!UICONTROL 转换数据集]**&#x200B;以确保为基于人员的查找转换数据。 有关详细信息，请参阅[转换B2B查找的数据集](/help/connections/transform-datasets-b2b-lookups.md)。

   ![键 — 匹配的键](assets/key-matchingkey.png)

   下表提供了每个数据集的[!UICONTROL 人员ID]、[!UICONTROL 键]和[!UICONTROL 匹配键]值的示例概述。

   | 数据集 | 人员 ID | 键 | 匹配键<br/>（在事件数据集中） |
   |---|---|---|---| 
   | B2B活动数据集 | `personKey.sourceKey` | | |
   | B2B人员数据集 | `b2b.personKey.sourceKey` | | |
   | B2B帐户数据集 | | `accountKey.sourceKey`❶<br/>Source密钥 | `b2b.accountKey.sourceKey`❶<br/>（B2B人员数据集） |
   | B2B Opportunity数据集 | | `opportunityKey.sourceKey`❷<br/>Source密钥 | `opportunityKey.sourceKey`❷<br/>（B2B机会关系数据集） |
   | B2B Campaign数据集 | | `campaignKey.sourceKey`❸<br/>Source密钥 | `campaignKey.sourceKey`❸<br/>（B2B营销活动成员数据集） |
   | B2B营销列表数据集 | | `marketingListKey.sourceKey`❹<br/>Source密钥 | `marketingListKey.sourceKey`❹<br/>（B2B营销列表成员数据集） |
   | B2B帐户人员关系数据集 | | `personKey.sourceKey`❺<br/>Source密钥 | `personKey.sourceKey`❺<br/>Source密钥（事件数据集） |
   | B2B机会人员关系数据集 | | `personKey.sourceKey`❻<br/>Source密钥 | `personKey.sourceKey`❻<br/>Source密钥（事件数据集） |
   | B2B营销活动成员数据集 | | `personKey.sourceKey`❼<br/>Source密钥 | `personKey.sourceKey`❼<br/>Source密钥（事件数据集） |
   | B2B营销列表成员数据集 | | `personKey.sourceKey`❽<br/>Source密钥 | `personKey.sourceKey`❽<br/>Source密钥（事件数据集） |

{style="table-layout:auto"}

有关如何为数据集配置设置的详细信息，请参阅[添加和配置数据集](../../connections/create-connection.md)。


## 数据视图

要在构建Workspace项目时访问相关的B2B维度和量度，您必须相应地定义数据视图。

例如，您可以向数据视图添加以下组件，以确保可根据B2B数据报告基于人员的级别。 组件名称有时会从其原始架构名称中修改以更清楚。

+++量度

| 组件名称 | 数据集 | 数据类型 | 架构路径 |
|---|---|---|---|
| 年度帐户收入 | B2B帐户数据集 | 双线 | accountOrganization.annualRevenue.amount |
| 员工数 | B2B帐户数据集 | 整数 | accountOrganization.numberOfEmployees |
| 实际营销活动成本 | B2B Campaign数据集 | 双线 | actualCost.amount |
| 预算营销活动成本 | B2B Campaign数据集 | 双线 | budgetedCost.amount |
| 预期机会收入 | B2B Opportunity数据集 | 双线 | expectedRevenue.amount |
| 预期营销活动收入 | B2B Campaign数据集 | 双线 | expectedRevenue.amount |
| 机会金额 | B2B Opportunity数据集 | 双线 | opportunityAmount.amount |

+++

+++Dimension

| 组件名称 | 数据集 | 数据类型 | 架构路径 |
|---|---|---|---|
| 帐户名称 | B2B帐户数据集 | 字符串 | 帐户名称 |
| 营销活动名称 | B2B Campaign数据集 | 字符串 | campaignName |
| 渠道名称 | B2B Campaign数据集 | 字符串 | channelname |
| 国家/地区 | B2B帐户数据集 | 字符串 | accountBillingAddress.country |
| 预测类别名称 | B2B Opportunity数据集 | 字符串 | forecastCategoryName |
| 行业 | B2B帐户数据集 | 字符串 | accountOrganization.industry |
| 姓氏 | B2B人员数据集 | 字符串 | person.name.lastName |
| 营销列表名称 | B2B营销列表数据集 | 字符串 | marketingListName |
| 机会名称 | B2B Opportunity数据集 | 字符串 | 机会名称 |
| 机会阶段 | B2B Opportunity数据集 | 字符串 | opportunityStage |
| 机会类型 | B2B机会类型数据集 | 字符串 | opportunityType |
| 网络研讨会会话名称 | B2B Campaign数据集 | 字符串 | 网络研讨会会话名称 |

+++

## 工作区

通过在数据视图中正确定义组件，您现在可以在Workspace项目中构建特定的B2B报告和可视化图表。

以下是依赖于上述连接和数据视图的示例项目的屏幕截图。 可视化图表描述解释了哪些自由格式表可视化图表依赖于转换后的B2B查找数据。

![示例项目](assets/sample-workspace-project.png)

