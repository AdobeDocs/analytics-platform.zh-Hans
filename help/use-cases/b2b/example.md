---
title: B2B 项目示例
description: 了解如何设置、配置和报告B2B数据
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
exl-id: e8ebf5e7-0b80-4d46-8a5f-b7ae832eda4f
role: User
source-git-commit: 9c60c00818e82a6ca891ab9d90260922437c6cca
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 10%

---

# B2B 项目示例

本文介绍了如何在Customer Journey Analytics中设置、配置和报告基于用户档案（人员）级别的B2B数据。

## 连接

定义您的连接以包含Experience Platform中的所有相关B2B数据集。 确保包含并转换典型的、基于B2B人员的报表方案所需的所有相关查找数据集。 有关详细信息，请参阅[转换B2B查找数据集](/help/connections/transform-datasets-b2b-lookups.md)。

可以考虑添加到连接的数据集：

| 数据集 | 架构 | 架构类型 | 基类 | 描述 |
|---|---|---|---|---|
| B2B活动数据集 | B2B活动模式 | 事件 | XDM ExperienceEvent | ExperienceEvent是所发生情况的事实记录，包括时间点和所涉及的个人身份。 ExperienceEvents可以是显式的（可直接观察的人类行为）或隐式的（在没有直接人类行为的情况下引发），并且无需聚合或解释即可记录。 它们对于时域分析至关重要，因为它们允许观察和分析给定时间段内发生的变化，并比较多个时间段以跟踪趋势。 |
| B2B人员数据集 | B2B人员模式 | 配置文件 | XDM个人资料 | XDM个人资料形成已识别和部分识别的个人的属性和兴趣的单一表示。 识别度较低的用户档案可能仅包含匿名行为信号，如浏览器Cookie，而识别度较高的用户档案可能包含详细的个人信息，如姓名、出生日期、位置和电子邮件地址。 随着用户档案的发展，它成为个人信息、身份信息、联系人详细信息和个人通信偏好设置的强大存储库。 |
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


查找架构、配置文件架构和事件架构之间的关系在Experience Platform内的B2B设置中定义。 有关更多详细信息，请参阅[Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html)中的架构和[在Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html)中定义两个架构之间的多对一关系。

![B2B架构之间的关系](assets/classes.png)

对于您添加到连接的每个查找数据集，必须在&#x200B;**[!UICONTROL 编辑数据集]**&#x200B;对话框中使用&#x200B;**[!UICONTROL 键]**&#x200B;和&#x200B;**[!UICONTROL 匹配键]**&#x200B;显式定义与事件数据集的关系。 例如：

![键 — 匹配的键](assets/key-matchingkey.png)

明确使用四个架构将人员架构与其他相关架构相关联：帐户、机会、营销活动和营销列表。 这些架构基于以下架构类：

* XDM 业务帐户人员关系
* XDM 业务机会人员关系
* XDM 商业营销列表成员
* XDM 商业营销活动成员

对于每个查找数据集，对于基于此类架构类的架构，您还可以启用&#x200B;**[!UICONTROL 转换数据集]**&#x200B;以确保转换数据以用于基于人员的查找。 参见 [转换数据集以进行 B2B 查找](/help/connections/transform-datasets-b2b-lookups.md) 了解更多信息。

下表提供了每个数据集的[!UICONTROL 人员ID]、[!UICONTROL 键]和[!UICONTROL 匹配键]值的示例概述。


| 数据集 | 人员 ID | 键 | 匹配键（在事件数据集中） |
|---|---|---|---|
| B2B活动数据集 | `personKey.sourceKey` | | |
| B2B人员数据集 | `b2b.personKey.sourceKey` | | |
| B2B帐户人员数据集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B Opportunity数据集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B营销活动成员数据集 | | `personKey.sourceKey` | `personKey.sourceKey` |
| B2B营销列表数据集 | | `personKey.sourceKey` | `personKey.sourceKey` |

{style="table-layout:auto"}

有关如何为数据集配置设置的详细信息，请参阅[添加和配置数据集](../../connections/create-connection.md)。


## 数据视图

要在构建Workspace项目时访问相关的B2B维度和量度，您必须相应地定义数据视图。

可将以下组件作为维度添加到数据视图，以确保可根据B2B数据报告基于人员的级别。 为清楚起见，将修改组件名称。

| 组件名称 | 数据集 | 架构数据类型 | 架构路径 |
|---|---|---|---|
| 人员 | B2B活动 | 字符串 | `personID` |
| 帐户 | B2B帐户人员 | 字符串 | `accountKey.sourceID` |
| 促销活动 | B2B营销活动成员 | 字符串 | `campaignKey.sourceKey` |
| 营销列表名称 | B2B营销列表 | 字符串 | `marketingListID` |
| 机会 | B2B机会人员 | 字符串 | `opportunityKey.sourceID` |


<!--
This section provides recommendations and suggestions on what dimensions and metrics to include when defining the [components](../../data-views/create-dataview.md#components) for B2B datasets in your data view.

For each component, the name, schema type, schema path, and (when applicable) details about the configuration are provided.


+++ B2B Activity dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Add To Campaign | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.addToCampaign` |
| Add To Opportunity | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.addToOpportunity` |
| Application Closed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.close` |
| Application Launch | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `application.launch` |
| Campaign Stream | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** ` leadOperation.changeCampaignStream` |
| Checkout | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.checkouts` |
| Convert Lead | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.convertLead` |
| Email Clicked | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailClicked` |
| Email Delivered | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailDelivered` |
| Email Opened | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailOpened` |
| Email Sent | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailSent` |
| Email Unsubscribed | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `directMarketing.emailUnsubscribed` |
| Form Filled Out | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `web.formFilledOut` |
| Form Started | String | `web.fillOutForm.webFormName` | |
| Leads | String | eventType | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `leadOperation.newLead` |
| Opportunity Updated | String | `eventType` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.opportunityUpdated` |
| Price | Double | *_organizationID*`.interactions.products.price` |  |
| Priority | Integer | `leadOperation.changeScore.priority` |  |
| Prod List Add | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListAdds.value` |
| Prod List Open | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productListOpens.value` |
| Prod View | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |
| Purchases | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.purchases.value` |
| Remove From Opportunity | String | `eventType` |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `opportunityEvent.removeFromOpportunity` |
| Save for Laters | String | eventType |  **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `commerce.productViews.value` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Account Key (Source Key) | String | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| Converted Status | String | `leadOperation.convertLead.convertedStatus` | |
| Event Type | String | `eventType` | |
| Form Name | String | `leadOperation.newLead.formName` | |
| Identifier | String | `_id` | |
| Is Sent Notification | Boolean | `leadOperation.convertLead.isSentNotificationEmail` | |
| Keywords | String | `search.keywords` | |
| List ID | String | `listOperations.listID` | |
| List Name | String | `leadOperation.newLead.listName` | |
| Page Name | String | `web.webPageDetails.name` | |
| Person Key (Source Key) | String | `personKey.sourceKey` | |
| Produced By | String | producedBy | |
| Product Name | String | *_organizationID*`.Interactions.products.name` | |
| Role | String | `opportunityEvent.role` | | 
| Timestamp | Date-time | `timestamp` | Date-Time format: **[!UICONTROL Day]** |
| URL | String | `web.webPageDetails.URL` | |
| Web Form Name | String | `web.fillOutForm.webFormName` | |
| Product URL | String | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B Person dataset


### Metrics

No metric components are defined as part of this dataset.


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Last Activity Date | Date-time | `extSourceSystemAudit.lastActivityDate` | Date-Time format: **[!UICONTROL Day]** |
| Person ID | String | `personID` | |

{style="table-layout:auto"}

+++

+++ B2B Account Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Annual Revenue | Double | `accountOrganization.annualRevenue.amount` | |
| Number of employees | Integer | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Acount | String | `accountKey.sourceID` | 

{style="table-layout:auto"}

| Account Identifier | String | `accountID` | |
| Account Type | String | `accountType` | |
| City | String | `accountBillingAddress.city` | |
| Country | String | `accountBillingAddress.country` | |
| Industry | String | `accountOrganization.industry` | |
| Region | String | `accountBillingAddress.region` | |
| Source ID | String | `accountKey.sourceID` | |
| Source Instance ID | String | `accountKey.sourceInstanceID` | |
| Source Key | String | `accountKey.sourceKey` | |
| Source Type | String | `accountKey.sourceType` | |


+++

+++  B2B Opportunity Person dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Expected Revenue | Double | `expectedRevenue.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Amount | Double | `opportunityAmount.amount` | Behavior: **[!UICONTROL Count values]** |
| Opportunity Stage - Closed Book | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Closed - Booked` |
| Opportunity Stage - Prospect | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Prospect` |
| Opportunity Stage - Qualification | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Opportunity Qualification` |
| Opportunity Stage - Solution Definition | String | `opportunityStage` | **[!UICONTROL Set include/exclude values]**<br/>**[!UICONTROL Case sensitive]**<br/>Match: **[!UICONTROL If all criteria are met]**<br/>Criteria: **[!UICONTROL Equals]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Closed Flag | Boolean | `isClosed` | |
| Company ID | String | `opportunityID` | |
| Forecast Category | String | `forecastCategoryName` | |
| Last Activity Date | Date-time | `lastActivityDate` | Date-time format: **[!UICONTROL Day]** |
| Lead Source | String | `leadSource` | |
| Opportunity Name | String | `opportunityName` | | 
| Opportunity Status | String | `opportunityStage` | |
| Won Flag | Boolean | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign Member dataset

### Metrics

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Bounced | Long | *_organizationID*`.campaignBounced` | Behavior: **[!UICONTROL Count values]** |
| Clicked | Long | *_organizationID*`.campaignClicked` | Behavior: **[!UICONTROL Count values]** |
| Opened | Long | *_organizationID*`.CampaignOpened` | Behavior: **[!UICONTROL Count values]** |
| Sent | Long | *_organizationID*`.campaignSent` | Behavior: **[!UICONTROL Count values]** |
| Subscribed | Long | *_organizationID*`.campaignSubscribed` | Behavior: **[!UICONTROL Count values]** |
| Webinar Registrations | Long | *_organizationID*`.Registrations` | Behavior: **[!UICONTROL Count values]** |

{style="table-layout:auto"}

### Dimensions

| Component Name | Schema data type | Schema path | Configuration |
|---|---|---|---|
| Campaign ID | String | `campaignID` | |
| Campaign Member ID | String | `campaignMemberID` | |
| Campaign Member Status | String | `memberStatus` | |
| Campaign Member Status Reason | String | `memberStatusReason` | |
| Created Date | Date-time | `extSourceSystemAudit.createdDate` | Date-time format: **[!UICONTROL Day]** |
| First Responded Date | String | `firstRespondedDate` | Date-time format: **[!UICONTROL Day]** |
| Has Reached Success | Boolean | `hasReachedSuccess` | |
| Has Responded | Boolean | `hasResponded` | |
| Last Status | String | `lastStatus` | |
| Last Updated Date | Date-time | `extSourceSystemAudit.lastUpdatedDate` | Date-time format: **[!UICONTROL Day]** |
| Membership Date | Date-time | `membershipDate` | Date-time format: **[!UICONTROL Day]** |
| Nurture Cadence | String | `nurtureCadence` | |
| Nurture Track Name | String | `nurtureTrackName` | |
| Person ID | String | `personID` | |
| Reached Success Date | Date-time | `reachedSuccessDate` | Date-time format: **[!UICONTROL Day]** |
| Webinar Registration ID | String | `webinarRegistrationID` | |
| Webinar Registration URL | String | `webinarConfirmationUrl` | |
| isExhausted | Boolean | isExhausted | |

{style="table-layout:auto"}

+++

+++ B2B Marketing List Member dataset

### Metrics

### Dimensions

+++

-->

## 工作区

通过在数据视图中正确定义组件，您现在可以在Workspace项目中构建特定的B2B报告和可视化图表。

以下是依赖于上述连接和数据视图的示例项目。

![示例项目](assets/sample-project.png)

<!-- See the descriptions for each visualization for more details.

+++ Example project

![Visualizations](assets/visualizations.png)

+++
-->
