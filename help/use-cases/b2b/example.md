---
title: 示例B2B项目
description: 了解如何设置、配置和报告B2B数据
solution: Customer Journey Analytics
feature: Use Cases
hide: true
hidefromtoc: true
source-git-commit: ec2778396f5090fb2ce71a991aa7a7bcaa913762
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 15%

---

# 示例B2B项目

本文通过示例说明如何在Customer Journey Analytics中设置、配置和报告B2B数据。

## 连接

定义您的连接以包含Experience Platform中的所有相关B2B数据集。 这包括Experience Platform中的典型B2B设置所需的重要查找数据集。 请参阅 [添加帐户级别的数据作为查询数据集](b2b.md) 以了解更多信息。

可以考虑添加到连接的数据集：

| 数据集 | 架构 | 架构类型 | 基类 | 描述 |
|---|---|---|---|---|
| B2B活动数据集 | B2B活动模式 | 事件 | XDM ExperienceEvent | ExperienceEvent是所发生情况的事实记录，包括时间点和所涉及的个人身份。 ExperienceEvents可以是显式的（可直接观察的人类行为）或隐式的（在没有直接人类行为的情况下引发），并且无需聚合或解释即可记录。 它们对于时域分析至关重要，因为它们允许观察和分析给定时间段内发生的变化，并比较多个时间段以跟踪趋势。 |
| B2B人员数据集 | B2B人员模式 | 用户档案 | XDM 个人资料 | XDM个人资料形成已识别和部分识别的个人的属性和兴趣的单一表示。 识别度较低的用户档案可能仅包含匿名行为信号，如浏览器Cookie，而识别度较高的用户档案可能包含详细的个人信息，如姓名、出生日期、位置和电子邮件地址。 随着用户档案的发展，它成为个人信息、身份信息、联系人详细信息和个人通信偏好设置的强大存储库。 |
| B2B营销活动成员数据集 | B2B营销活动成员架构 | 查询 | XDM商业营销活动成员 | XDM商业营销活动成员是一个标准体验数据模型(XDM)类，它描述了与商业营销活动关联的联系人或商机。 |
| B2B帐户数据集 | B2B帐户架构 | 查询 | XDM业务帐户 | XDM业务帐户是一个标准体验数据模型(XDM)类，可捕获业务帐户的最低要求属性。 |
| B2B帐户人员关系数据集 | B2B帐户人员关系架构 | 查询 | XDM业务帐户人员关系 | XDM业务帐户人员关系是一个标准体验数据模型(XDM)类，可捕获与业务帐户关联的人员的最低要求属性。 |
| B2B Opportunity数据集 | B2B机会架构 | 查询 | XDM商业机会 | XDM业务机会是一个标准体验数据模型(XDM)类，可捕获业务机会的最低要求属性。 |
| B2B机会人员关系数据集 | B2B机会人员关系架构 | 查询 | XDM业务机会人员关系 | XDM业务机会人员关系是一个标准体验数据模型(XDM)类，可捕获与业务机会关联的人员的最低要求属性。 |
| B2B Campaign数据集 | B2B营销活动模式 | 查询 | XDM商业营销活动 | XDM商业营销活动是一个标准体验数据模型(XDM)类，可捕获商业营销活动的最低要求属性。 |
| B2B营销列表数据集 | B2B营销列表架构 | 查询 | XDM营销列表 | XDM业务营销列表是一个标准体验数据模型(XDM)类，可捕获营销列表的最低要求属性。 营销列表允许您优先考虑最有可能购买您的产品的潜在客户。 |
| B2B营销列表成员数据集 | B2B营销列表成员架构 | 查询 | XDM营销列表成员 | XDM业务营销列表成员是一个标准的体验数据模型(XDM)类，它描述了与营销列表关联的成员、人员或联系人。 |

查找架构、配置文件架构和事件架构之间的关系在Experience Platform内的B2B设置中定义。 请参阅中的架构 [Real-time Customer Data Platform B2B版本](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/schemas/b2b.html?lang=en) 和 [在Real-time Customer Data Platform B2B版本中定义两个架构之间的多对一关系](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/relationship-b2b.html?lang=en) 以了解更多详细信息。

![B2B架构之间的关系](assets/classes.png)

对于添加到连接的每个查找数据集，必须使用“编辑数据集”对话框中的键和匹配键显式定义与事件数据集的关系。 例如：

![键 — 匹配键](assets/key-matchingkey.png)


下表提供了 [!UICONTROL 人员ID]， [!UICONTROL 键]、和 [!UICONTROL 匹配键] 每个数据集的值。


| 数据集 | 人员 ID | 键 | 匹配键（在事件数据集中） |
|---|---|---|---|
| B2B活动数据集 | `personKey.sourceKey` | | |
| B2B人员数据集 | `b2b.personKey.sourceKey` | | |
| B2B帐户数据集 | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B Opportunity数据集 | | `accountKey.sourceKey` | *_organizationID*`.interactions.accountKey.sourceKey` |
| B2B Campaign数据集 | | `campaignKey.sourceKey` | *_organizationID*`.interactions.campaignKey.sourceKey` |
| B2B营销列表数据集 | | `listKey.sourceKey` | `listOperations.listKey.sourceKey` |

{style="table-layout:auto"}


在表中 *_organizationID*`.interaction.*`，是指您添加到B2B活动架构以定义与B2B帐户和B2B机会架构的关系的自定义字段组。 此 `listOperations.listKey.sourceKey` 指的是添加到B2B活动架构的“添加到列表”字段组，用于跟踪人员添加到特定列表的时间。

请参阅 [添加和配置数据集](../../connections/create-connection.md) 有关如何配置数据集设置的更多信息。


## 数据视图

要在构建工作区项目时访问相关的B2B维度和量度，您必须相应地定义数据视图。

本节提供了有关在定义 [组件](../../data-views/create-dataview.md#components) 数据视图中的B2B数据集。

为每个组件提供了名称、架构类型、架构路径，以及有关配置的详细信息（如果适用）。

+++ B2B活动数据集

### 量度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 添加到营销活动 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `leadOperation.addToCampaign` |
| 添加到机会 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `opportunityEvent.addToOpportunity` |
| 应用程序已关闭 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `application.close` |
| 应用程序启动 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `application.launch` |
| 营销活动流 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** ` leadOperation.changeCampaignStream` |
| 结账 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.checkouts` |
| 转化商机 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `leadOperation.convertLead` |
| 电子邮件已点击 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `directMarketing.emailClicked` |
| 电子邮件已送达 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `directMarketing.emailDelivered` |
| 电子邮件已打开 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `directMarketing.emailOpened` |
| 已发送电子邮件 | 字符串 | 事件类型 | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `directMarketing.emailSent` |
| 电子邮件已取消订阅 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `directMarketing.emailUnsubscribed` |
| 表单已填写 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `web.formFilledOut` |
| 已开始表单 | 字符串 | `web.fillOutForm.webFormName` | |
| 商机 | 字符串 | 事件类型 | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `leadOperation.newLead` |
| 机会已更新 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `opportunityEvent.opportunityUpdated` |
| 价格 | 双精度 | *_organizationID*`.interactions.products.price` |  |
| 优先级 | 整数 | `leadOperation.changeScore.priority` |  |
| 生产列表添加 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.productListAdds.value` |
| 生产列表打开 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.productListOpens.value` |
| 生产视图 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.productViews.value` |
| 购买 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.purchases.value` |
| 从机会中移除 | 字符串 | `eventType` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `opportunityEvent.removeFromOpportunity` |
| 保存留待后用 | 字符串 | 事件类型 | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `commerce.productViews.value` |

{style="table-layout:auto"}


### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 帐户密钥（源密钥） | 字符串 | *_organizationID*`.Interactions.accountKey.sourceKey` | |
| 转化状态 | 字符串 | `leadOperation.convertLead.convertedStatus` | |
| 事件类型 | 字符串 | `eventType` | |
| 表单名称 | 字符串 | `leadOperation.newLead.formName` | |
| 标识符 | 字符串 | `_id` | |
| 已发送通知 | 布尔值 | `leadOperation.convertLead.isSentNotificationEmail` | |
| 关键字 | 字符串 | `search.keywords` | |
| 列表Id | 字符串 | `listOperations.listID` | |
| 列表名称 | 字符串 | `leadOperation.newLead.listName` | |
| 页面名称 | 字符串 | `web.webPageDetails.name` | |
| 人员密钥（源密钥） | 字符串 | `personKey.sourceKey` | |
| 制作者 | 字符串 | productedBy | |
| 产品名称 | 字符串 | *_organizationID*`.Interactions.products.name` | |
| 角色 | 字符串 | `opportunityEvent.role` | |
| 时间戳 | 日期时间 | `timestamp` | 日期时间格式： **[!UICONTROL 天]** |
| URL | 字符串 | `web.webPageDetails.URL` | |
| Web窗体名称 | 字符串 | `web.fillOutForm.webFormName` | |
| 产品URL | 字符串 | *_organizationID*`.Interactions.products.url` | |

{style="table-layout:auto"}

+++


+++ B2B人员数据集


### 量度

没有量度组件被定义为此数据集的一部分。


### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 上次活动日期 | 日期时间 | `extSourceSystemAudit.lastActivityDate` | 日期时间格式： **[!UICONTROL 天]** |
| 人员 ID | 字符串 | `personID` | |

{style="table-layout:auto"}

+++


+++  B2B Opportunity数据集

### 量度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 预期收入 | 双精度 | `expectedRevenue.amount` | 行为： **[!UICONTROL 值计数]** |
| 机会金额 | 双精度 | `opportunityAmount.amount` | 行为： **[!UICONTROL 值计数]** |
| 机会阶段 — 已关闭的帐簿 | 字符串 | `opportunityStage` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `Closed - Booked` |
| 机会阶段 — 潜在客户 | 字符串 | `opportunityStage` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `Prospect` |
| 机会阶段 — 资格 | 字符串 | `opportunityStage` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `Opportunity Qualification` |
| 机会阶段 — 解决方案定义 | 字符串 | `opportunityStage` | **[!UICONTROL 设置包括/排除值]**<br/>**[!UICONTROL 区分大小写]**<br/>匹配：**[!UICONTROL &#x200B;如果满足所有条件]**<br/>标准： **[!UICONTROL 等于]** `Solution Definition and Validation` |

{style="table-layout:auto"}


### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 已关闭标志 | 布尔值 | `isClosed` | |
| 公司标识 | 字符串 | `opportunityID` | |
| 预测类别 | 字符串 | `forecastCategoryName` | |
| 上次活动日期 | 日期时间 | `lastActivityDate` | 日期时间格式： **[!UICONTROL 天]** |
| 商机来源 | 字符串 | `leadSource` | |
| 机会名称 | 字符串 | `opportunityName` | |
| 机会状态 | 字符串 | `opportunityStage` | |
| 赢单标志 | 布尔值 | `isWon` | |

{style="table-layout:auto"}

+++


+++ B2B Campaign数据集

### 量度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 促销活动成本 | 双精度 | `actualCost.amount` | |

{style="table-layout:auto"}


### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 促销活动 ID | 字符串 | `campaignID` | |
| 营销活动名称 | 字符串 | `campaignName` | |
| 促销活动开始日期 | 日期时间 | `campaignStartDate` | 日期时间格式： **[!UICONTROL 天]** |
| 渠道名称 | 字符串 | `channelName` | |
| 父营销活动ID | 字符串 | `parentCampaignID` | |

{style="table-layout:auto"}

+++



+++ B2B帐户数据集

### 量度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 年收入 | 双精度 | `accountOrganization.annualRevenue.amount` | |
| 员工数 | 整数 | `accountOrganization.numberOfEmployees` | |

{style="table-layout:auto"}


### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 帐户标识符 | 字符串 | `accountID` | |
| 帐户类型 | 字符串 | `accountType` | |
| 城市 | 字符串 | `accountBillingAddress.city` | |
| 国家/地区 | 字符串 | `accountBillingAddress.country` | |
| 行业 | 字符串 | `accountOrganization.industry` | |
| 区域 | 字符串 | `accountBillingAddress.region` | |
| 源 ID | 字符串 | `accountKey.sourceID` | |
| 源实例ID | 字符串 | `accountKey.sourceInstanceID` | |
| 源密钥 | 字符串 | `accountKey.sourceKey` | |
| 源类型 | 字符串 | `accountKey.sourceType` | |

{style="table-layout:auto"}

+++


+++ B2B营销活动成员数据集

### 量度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 已退回 | 长型 | *_organizationID*`.campaignBounced` | 行为： **[!UICONTROL 值计数]** |
| 已点击 | 长型 | *_organizationID*`.campaignClicked` | 行为： **[!UICONTROL 值计数]** |
| 已打开 | 长型 | *_organizationID*`.CampaignOpened` | 行为： **[!UICONTROL 值计数]** |
| 已发送 | 长型 | *_organizationID*`.campaignSent` | 行为： **[!UICONTROL 值计数]** |
| 已订阅 | 长型 | *_organizationID*`.campaignSubscribed` | 行为： **[!UICONTROL 值计数]** |
| 网络研讨会注册 | 长型 | *_organizationID*`.Registrations` | 行为： **[!UICONTROL 值计数]** |

{style="table-layout:auto"}

### 维度

| 组件名称 | 架构数据类型 | 架构路径 | 配置 |
|---|---|---|---|
| 促销活动 ID | 字符串 | `campaignID` | |
| 营销活动成员ID | 字符串 | `campaignMemberID` | |
| 营销活动成员状态 | 字符串 | `memberStatus` | |
| 营销活动成员状态原因 | 字符串 | `memberStatusReason` | |
| 创建日期 | 日期时间 | `extSourceSystemAudit.createdDate` | 日期时间格式： **[!UICONTROL 天]** |
| 首次响应日期 | 字符串 | `firstRespondedDate` | 日期时间格式： **[!UICONTROL 天]** |
| 已取得成功 | 布尔值 | `hasReachedSuccess` | |
| 已响应 | 布尔值 | `hasResponded` | |
| 上次状态 | 字符串 | `lastStatus` | |
| 上次更新日期 | 日期时间 | `extSourceSystemAudit.lastUpdatedDate` | 日期时间格式： **[!UICONTROL 天]** |
| 成员资格日期 | 日期时间 | `membershipDate` | 日期时间格式： **[!UICONTROL 天]** |
| 培养节奏 | 字符串 | `nurtureCadence` | |
| 培养轨迹名称 | 字符串 | `nurtureTrackName` | |
| 人员 ID | 字符串 | `personID` | |
| 已达到成功日期 | 日期时间 | `reachedSuccessDate` | 日期时间格式： **[!UICONTROL 天]** |
| 网络研讨会注册ID | 字符串 | `webinarRegistrationID` | |
| 网络研讨会注册URL | 字符串 | `webinarConfirmationUrl` | |
| isExhausted | 布尔值 | isExhausted | |

{style="table-layout:auto"}

+++

<!--
### B2B Marketing List Member dataset

The B2B Marketing List Member dataset contains member of marketing lists.

-->

## 工作区

通过正确定义的组件，您现在可以在工作区项目中构建特定的B2B可视化图表。

以下是依赖于上述连接和数据视图的示例项目。 有关更多详细信息，请参阅每个可视化图表的描述。

+++ 示例项目

![可视化图表](assets/visualizations.png)

+++

