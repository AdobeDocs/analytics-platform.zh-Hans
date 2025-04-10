---
title: 创建并发布受众
description: 了解如何从 Customer Journey Analytics 发布受众
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: dab355e2934689afc06b9228ac5caf357b4ae4e6
workflow-type: tm+mt
source-wordcount: '1973'
ht-degree: 18%

---

# 创建并发布受众 {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="刷新频率"
>abstract="了解如何实现受众会员资格的重新评估。<br/>一次性受众仅会评估一次。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="受众限制"
>abstract="根据刷新频率，刷新受众会受到限制。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="刷新回顾时段"
>abstract="定义从今天开始评估受众的回顾天数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="受众规模限制"
>abstract="受众不得超过 2 000 万会员。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="已包括命名空间"
>abstract="该受众的身份标识由以下命名空间组成。"

<!-- markdownlint-enable MD034 -->




本主题讨论如何在Adobe Experience Platform中创建并将在Customer Journey Analytics中识别的受众发布到[实时客户个人资料](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/profile/home)，以实现客户定位和个性化。

请阅读此[概述](/help/components/audiences/audiences-overview.md)，以了解Customer Journey Analytics受众的概念。

## 创建和发布受众 {#create}

1. 要创建并发布受众，请执行以下操作之一：

   | 创建方法 | 详细信息 |
   | --- | --- |
   | 从&#x200B;**[!UICONTROL 受众]**&#x200B;界面中 | 从Customer Journey Analytics主菜单中选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 受众]**。 此时将显示“受众”界面。 选择&#x200B;**[!UICONTROL 创建受众]**，将打开[!UICONTROL 受众生成器]。 |
   | 从Analysis Workspace中的可视化图表 | Analysis Workspace中的许多可视化图表都允许您使用上下文菜单创建受众。 例如，您可以从[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中项目的上下文菜单或在[历程画布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)中的节点中选择&#x200B;**[!UICONTROL 创建受众]**。<p>使用此方法时会使用您选择的维度或维度项目预填充受众生成器中的过滤器。</p><p>通过以下可视化图表，可使用右键单击菜单创建受众：</p><ul><li>[同类群组表](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[流](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[历程画布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[维恩图](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**注意：**&#x200B;受众不能包含计算量度。 如果尝试创建的受众包含计算量度，则该计算量度不会包含在受众定义中。</p> |
   | 通过过滤器创建/编辑 UI | 选中显示&#x200B;**[!UICONTROL 从此过滤器创建受众]**&#x200B;的框。使用此方法时会预填充过滤器。 有关详细信息，请参阅[创建筛选器](/help/components/filters/create-filters.md)。 |

   {style="table-layout:auto"}

1. 使用[受众生成器](#audience-builder)生成受众。

1. 使用[日期预览](#data-preview)面板解释数据。

1. 选择&#x200B;**[!UICONTROL [!UICONTROL 查看样本ID]]**&#x200B;以查看此受众中的ID示例。 在&#x200B;**[!UICONTROL 示例ID]**&#x200B;对话框中，您可以使用![搜索](/help/assets/icons/Search.svg) [!UICONTROL *搜索示例ID*]&#x200B;来搜索示例ID。

1. 仔细检查受众配置并选择&#x200B;**[!UICONTROL 发布]**。
您会收到一条关于受众已发布的确认消息。 发布只需一两分钟，该受众就会出现在Experience Platform中。

1. 在同一条消息中选择&#x200B;**[!UICONTROL 在AEP中查看受众]**，您将转到Adobe Experience Platform中的[区段UI](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview)。 有关详细信息，请参阅下文。

## 受众生成器

配置这些设置以定义或更新受众。

![下一节中介绍的创建受众倾斜设置的屏幕截图。](assets/create-audience.png)

| 设置 | 描述 |
| --- | --- |
| ![数据](/help/assets/icons/Data.svg) | 选择用于创建受众的数据视图。 |
| **[!UICONTROL 名称]** | 受众的名称。 例如，`Really Interested in Potential Car Buyers` |
| **[!UICONTROL 标记]** | 出于组织目的而要分配给受众的任何标记。 您可以选择一个或多个预先存在的标记或输入新标记。 |
| **[!UICONTROL 描述]** | 受众的描述，用于区分其他受众。 例如，`Build an audience of really interested potential car buyers` |
| **[!UICONTROL 刷新频率]** | 您刷新受众所要采用的频率。<p/>您可以选择 <ul><li>**[!UICONTROL 一次]**&#x200B;受众：一个无需刷新的受众（默认）。 例如，此选项可能有助于特定的一次性营销活动。<br/>您必须指定&#x200B;**[!UICONTROL 一次性日期范围]**。 您可以使用![日历](/help/assets/icons/Calendar.svg)输入日期范围。</li><li>正在刷新受众。 您可以从下列选项中进行选择：<ul><li>**[!UICONTROL 每4小时]**&#x200B;秒：每4小时刷新的受众。</li><li>**[!UICONTROL 每日]**：每天刷新的受众</li><li>**[!UICONTROL 每周]**：每周刷新的受众。</li><li>**[!UICONTROL 每月]**：每月刷新的受众</li></ul></li>要刷新受众，您必须指定：<ul><li>**[!UICONTROL 刷新回顾窗口]**。 定义从今天开始评估受众的回顾天数。 您可以从选项中进行选择或定义自定义时间。 最长为90天。</li><li>**[!UICONTROL 过期日期]**：定义受众何时停止刷新。 您可以使用![日历](/help/assets/icons/Calendar.svg)选择日期。 默认值为创建日期开始 1 年。即将过期的受众的处理方式与即将过期的计划报表的处理方式类似。 管理员会在受众过期前一个月收到一封电子邮件。</li></ul> 请注意，根据您的Customer Journey Analytics权限，受众刷新限制为75到150次。</li></ul> |
| **[!UICONTROL 过滤器]** | 过滤器是受众的主要输入。从左侧![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 筛选器]**&#x200B;面板将一个或多个筛选器拖放到筛选器区域。 您可以使用![搜索](/help/assets/icons/Search.svg) [!UICONTROL *搜索筛选器*]&#x200B;来搜索筛选器。 您最多可以添加 20 个过滤器。筛选器可以与&#x200B;**[!UICONTROL And]**&#x200B;或&#x200B;**[!UICONTROL Or]**&#x200B;运算符相连。<p>从Analysis Workspace中的可视化图表(例如自由格式表或历程画布)创建受众时，应用于面板或列的任何过滤器都会保留。 您可以删除任何自动应用的过滤器。</p> |
| **[!UICONTROL 数据预览]** | 选择![信息](/help/assets/icons/Info.svg)以显示或隐藏所选日期范围的[数据预览](#data-preview)。 |

## 数据预览

数据预览面板提供以下信息。

| 元素 | 描述 |
| --- | --- |
| **[!UICONTROL 总人数]** | 该受众中总人数的汇总。最大规模为2000万人。 如果您的受众超过2000万人，则必须先缩小受众规模，然后才能发布。 |
| **[!UICONTROL 受众规模限制]** | 用于显示受众距离2000万这一限制有多远的可视化图表。 |
| **[!UICONTROL 预计会返回的受众]** | 您可以使用此值重新定位此受众中会返回您的网站、移动应用程序或其他渠道的人员。<p>您可以为可能返回的估计客户数选择时间范围（**[!UICONTROL Next 7天]**、**[!UICONTROL Next 2周]**&#x200B;或&#x200B;**[!UICONTROL Next month]**）。 |
| **[!UICONTROL 预计会返回]** | 该数字为您提供了所选时间范围内回访客户的估计数量。 此数字是使用此受众的历史客户流失率预测的。 |
| **[!UICONTROL 预览量度]** | 您可以选择特定量度，以查看该量度的数据如何基于您定义的受众。  每个预览量度会根据受众显示量度的总计。 以及基于受众的量度在量度总数中所占的百分比，如数据视图所定义。 例如，381人（您选择的量度）是受众定义的结果，相当于数据视图中可用总人数的5%。 您可以选择数据视图中可用的任何量度。 |
| **[!UICONTROL 命名空间包含]** | 与受众中的人关联的特定命名空间。例如 ECID、CRM ID、电子邮件地址等。 |
| **[!UICONTROL 沙盒]** | 受众所在的 [Experience Platform sandbox](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home) 沙盒。当您将此受众发布到Platform时，您只能在此沙盒的范围内处理受众。 |

{style="table-layout:auto"}

## 创建和发布受众后会发生什么？ {#after-audience-created}

在Customer Journey Analytics中创建并发布受众后，该受众即会在Experience Platform中使用。 仅当您的组织设置为进行流式分段时，才会创建Adobe Experience Platform流式区段。

* Platform中的受众与Customer Journey Analytics受众共享相同的名称和描述。 该名称将附加有Customer Journey Analytics受众ID，以确保受众是唯一的。
* 对Customer Journey Analytics中的受众名称或描述所做的任何更改都会反映在Experience Platform中。
* 如果在Customer Journey Analytics中删除了某个受众，则该受众将继续在Experience Platform中可用，直到受众的个人资料成员资格过期为止。 对于一次性受众，配置文件成员资格将在420天后过期，对于定期受众，配置文件成员资格将在16天后过期。

## 延迟注意事项 {#latency}

在受众发布之前、期间和之后的多个时间点，可能会出现延迟。 以下是对可能出现的延迟情况的概述。

![受众发布的延迟，如本节所述。](assets/latency-diagram.svg)

|  | 延迟点 | 延迟持续时间 |
| --- | --- | --- |
| 未显示 | Adobe Analytics到Analytics源连接器(A4T) | 最多 30 分钟 |
| 1 | 将数据摄取到数据湖（从Analytics源连接器或其他源） | 最多 90 分钟 |
| 2 | 将数据从Experience Platform数据湖摄取到Customer Journey Analytics | 最多 90 分钟 |
| 3 | 将受众发布到实时客户个人资料，包括自动创建流区段，并允许区段准备好接收数据。 | 几秒钟 |
| 4 | 受众的刷新频率 | <ul><li>一次性刷新（延迟小于 5 分钟）</li><li>每 4 小时、每天、每周、每月刷新一次（延迟与刷新率密切相关） |
| 5 | 在Adobe Experience Platform中创建目标：激活新区段 | 1-2 小时 |

{style="table-layout:auto"}

## 在Experience Platform中使用Customer Journey Analytics受众 {#audiences-aep}

Customer Journey Analytics会从已发布的受众中获取所有命名空间和ID组合，并将它们流式传输到Real-Time Customer Data Platform中。 Customer Journey Analytics根据配置连接时选择作为[!UICONTROL 人员ID]的内容，将受众发送到设置了主身份的Experience Platform。

然后，Real-Time Customer Data Platform会检查每个命名空间/ID组合，并查找可能包含该组合的配置文件。 轮廓其实就是由所链接的命名空间、ID 和设备组成的集群。如果它找到配置文件，则会将命名空间和ID作为区段成员资格属性添加到此配置文件中的其他ID。 例如，可以跨其所有设备和渠道定位<user@adobe.com>。 如果未找到相关的轮廓，则会创建一份新的轮廓。

要在Platform中查看Customer Journey Analytics受众，请执行以下操作：

1. 在左侧面板中展开&#x200B;**[!UICONTROL 客户]**，然后选择&#x200B;**[!UICONTROL 受众]**。<!-- is there a folder called "Customer Journey Analytics? -->

1. 选择&#x200B;**[!UICONTROL 浏览]**&#x200B;选项卡。

1. 要查找您从Customer Journey Analytics发布的受众，请执行以下任一操作：

   左侧面板中的![受众选项](assets/aep-audiences.png)

   * 按&#x200B;**[!UICONTROL Origin]**&#x200B;列对表进行排序，以查看将&#x200B;[!UICONTROL **Customer Journey Analytics**]&#x200B;显示为源的受众。

   * 筛选&#x200B;**[!UICONTROL 原点]**&#x200B;上的![筛选器](/help/assets/icons/Filter.svg)并选择&#x200B;**[!UICONTROL Customer Journey Analytics]**。

   * 使用![搜索](/help/assets/icons/Search.svg)搜索字段。

有关在Platform中使用受众的更多信息，请参阅Experience Platform文档的[区段生成器UI指南](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder)中的[受众](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder)部分。

<!---### Understand discrepancies in audience counts between Customer Journey Analytics and Real-Time Customer Data Platform

Discrepancies in audience counts may occur between Customer Journey Analytics and Real-Time Customer Data Platform. The points below provide a detailed explanation of these differences:

![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)

**Probabilistic versus deterministic counts**

The methodology by which audience membership numbers are being calculated differs between the two apps, as described below.

*  **Customer Journey Analytics**: The **[!UICONTROL Total People]** metric in Customer Journey Analytics is an estimated value. This means that the count is an estimate based on the rules of the audience and it can change between refresh intervals.
*  **Real-Time Customer Data Platform**: The count in Real-Time Customer Data Platform is deterministic, based on daily evaluation jobs, and fixed at the time the audience finishes publishing into the audience portal. 

**Publishing interval and rate**

Audiences publish to Real-Time Customer Data Platform at a rate of 1500 records per second (RPS). For example, an audience of 20 million members will take approximately 3.7 hours to fully publish (20M / 1500 RPS / 3600 seconds per hour). During this time, differences in audience membership between the two apps are likely.

**Profile fragmentation**

If profiles imported from Customer Journey Analytics already exist in Real-Time Customer Data Platform, they are not counted as new profiles. This can lead to lower-than-expected profile counts in Real-Time Customer Data Platform.

**Batch versus streaming audiences**

Customer Journey Analytics audiences are not included in the daily batch evaluation job and remain fixed until the next publish interval. In contrast, other batch audiences in Real-Time Customer Data Platform are re-evaluated every 24 hours.

### Key takeaways to remember

* **Estimated counts in Customer Journey Analytics**: Understand that the **[!UICONTROL Total People]** count in Customer Journey Analytics is an estimate and can vary due to streaming data and identity behaviors.
* **Deterministic counts in Real-Time Customer Data Platform**: The count in Real-Time Customer Data Platform is fixed and does not change until the next publish interval.
* **Profile Fragmentation**: Be aware that existing profiles in Real-Time Customer Data Platform may not contribute to new profile counts when importing from Customer Journey Analytics.

By clearly differentiating these aspects, you can better understand and manage your audience data across Customer Journey Analytics and Real-Time Customer Data Platform.--->

## 常见问题解答 {#faq}

关于受众发布的常见问题。

+++**如果用户不再是Customer Journey Analytics中的受众成员，会发生什么情况？**

在这种情况下，系统会从Customer Journey Analytics向Experience Platform发送退出事件。

+++

+++**如果删除Customer Journey Analytics中的受众会发生什么情况？**

删除Customer Journey Analytics受众后，该受众不再显示在Experience Platform UI中。 但是，与该受众关联的用户档案不会在Experience Platform中删除。

+++

+++**如果Real-Time Customer Data Platform中不存在相应的配置文件，是否会创建新的配置文件？**

是的，会的。

+++

+++**Customer Journey Analytics是将受众数据作为管道事件还是作为同样发送到数据湖的平面文件发送？**

Customer Journey Analytics通过pipeline将数据流式传输到Real-Time Customer Data Platform中，并且这些数据还会收集到数据湖的系统数据集中。

+++

+++**Customer Journey Analytics发送了哪些标识？**

在[连接设置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection)中指定的任何标识/命名空间对。 具体而言，用户选择要用作人员ID的字段时的步骤。

+++

+++**选择什么 ID 作为主要身份标识？**

请参阅上面的内容。每个Customer Journey Analytics人员只发送一个身份。

+++

+++**Real-Time Customer Data Platform是否也处理Customer Journey Analytics消息？ Customer Journey Analytics能否通过受众共享将身份添加到配置文件身份图？**

否。由于每人只发送一个身份，因此Real-Time Customer Data Platform将不会使用任何图形边缘。

+++

+++**在一天中的哪个时间进行每日、每周和每月的刷新？ 每周的哪一天进行刷新？**

刷新时间基于原始受众的发布时间和锚点到当天时间（以及星期或月）。

+++

+++**是否可以配置每日、每周和每月刷新时间？**

否，用户无法配置刷新时间。

+++


## 后续步骤

* 若要管理该受众，请转到[管理 UI](/help/components/audiences/manage.md)。
