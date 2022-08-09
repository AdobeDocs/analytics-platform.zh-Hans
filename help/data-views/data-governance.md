---
title: CJA支持Adobe Experience Platform数据管理
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# CJA支持Adobe Experience Platform数据管理

CJA与 [Adobe Experience Platform数据管理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 允许为敏感CJA数据设置标签并强制执行隐私政策。

在CJA数据视图工作流中，可以显示在由Experience Platform使用的数据集上创建的隐私标签和策略。 这些标签可阻止或警告从敏感字段创建量度和/或维度的用户。

此外，在从CJA导出数据（通过报表、导出、API等）时，会添加警告或标签，以通知用户报表包含需要以特定方式处理的敏感信息。

此集成使您能够更轻松地管理法规遵从性。 贵组织中的数据管理员可以设置策略以限制使用。 因此，您的CJA用户可以更自信地使用数据，因为他们知道数据符合数据管理者定义的策略。

## Adobe Experience Platform标签和政策

在Experience Platform中创建数据集时，您可以创建 [数据使用标签](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) ，用于数据集中的部分或全部元素。 迄今为止，CJA中尚未公开这些标签。 在此版本中，您可以在CJA中查看这些标签。 CJA特别感兴趣的是C8标签，该标签显示“数据不能用于测量贵组织的网站或应用程序”。

标签本身并不意味着强制使用这些数据。 这就是政策的用途。 您可以通过 [策略服务API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform。

策略有两个组成部分：数据标签和营销操作，数据消费者可在受限数据使用策略的上下文中执行此操作。 在CJA中，定义了两个Adobe [营销行动](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) 很重要：

* Analytics — 将数据用于分析目的，例如测量、分析和报告贵组织网站或应用程序的消费者使用情况。

* 将此数据导出到Adobe环境之外，例如将数据导出到第三方。

将标签和营销操作与策略绑定，然后打开策略。 该策略将标签和营销操作标记为：强制执行此限制。 CJA中显示了两个Adobe定义的策略：

* Analytics策略
* 下载策略

## 在CJA数据视图中查看数据标签

在Experience Platform中创建的数据标签在数据视图用户界面的三个位置显示：

| 位置 | 描述 |
| --- | --- |
| 架构字段上的“信息”按钮 | 单击此按钮可指示当前应用于字段的数据使用标签：<p>![](assets/data-label-left.png) |
| 下方的右边栏 [组件设置](/help/data-views/component-settings/overview.md) | 此处列出了所有数据使用情况标签：<p>![](assets/data-label-right.png) |
| 将数据标签添加为列 | 您可以将数据标签作为列添加到数据视图的“已包括组件”列中。 只需单击列选择器图标，然后选择数据使用情况标签：<p>![](assets/data-label-column.png) |

### 在CJA中过滤“数据管理”标签

在数据视图编辑器中，单击左侧跟踪中的过滤器图标，然后按数据管理标签过滤数据视图组件：

![](assets/filter-labels.png)

### 在CJA中过滤数据管理策略

您可以检查是否开启了阻止将某些CJA数据视图元素用于分析或导出目的的策略。

再次单击左边栏中的过滤器图标，在“数据管理”下单击策略：

![](assets/filter-policies.png)

如果打开策略，则那些与其关联的某些数据标签（如C8）的架构字段将无法用于CJA工作区中的分析或下载（如通过电子邮件或共享pdf）目的。

请注意

* 不允许将它们添加到数据视图。 这些字段在左边栏架构字段列表中将灰显。
* 无法保存已阻止其中字段的数据视图。


