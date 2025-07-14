---
title: 创建并发布受众
description: 了解如何从 Customer Journey Analytics 发布受众
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: f3bd60d6a371a16e606d9af60e3359d8128a3c9f
workflow-type: tm+mt
source-wordcount: '2389'
ht-degree: 99%

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




该主题讨论了如何在 Adobe Experience Platform 中将在 Customer Journey Analytics 中识别的受众创建并发布到[实时客户轮廓](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/profile/home)，以实现客户定位和个性化。

阅读本[概述](/help/components/audiences/audiences-overview.md)，以了解 Customer Journey Analytics 受众的概念。

## 创建并发布受众 {#create}

1. 要创建并发布受众，请执行以下操作之一：

   | 创建方法 | 详细信息 |
   | --- | --- |
   | 从&#x200B;**[!UICONTROL 受众]**&#x200B;界面内 | 在 Customer Journey Analytics 菜单中，选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 受众]**。“受众”界面显现。选择&#x200B;**[!UICONTROL 创建受众]**，然后[!UICONTROL 受众生成器]将会打开。 |
   | 从 Analysis Workspace 的可视化功能 | Analysis Workspace 中的许多可视化功能允许您使用上下文菜单创建受众。例如，您可以从[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中的项目或[历程画布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)中的节点的上下文菜单中选择&#x200B;**[!UICONTROL 创建受众]**。<p>使用此方法时会在受众生成器中用您选择的维度或维度项预填充区段。</p><p>以下可视化功能可让您使用右键菜单创建受众：</p><ul><li>[同类群组表](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[流](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[历程画布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[地图&#x200B;](/help/analysis-workspace/visualizations/map.md#create-an-audience-from-the-map-visualization)<br/>**注意：**&#x200B;此可视化图表处于发行版的“有限测试”阶段，可能在您的环境中不可用。</li><li>[维恩图](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**注释：**&#x200B;受众不能包含计算量度。如果您尝试创建包含计算量度的受众，则受众定义不会包含该计算量度。</p> |
   | 从区段创建/编辑 UI | 勾选&#x200B;**[!UICONTROL 从这个区段创建受众]**&#x200B;的复选框。使用此方法可预填充区段。有关更多信息，请参阅[创建区段](/help/components/segments/seg-create.md)。 |

   {style="table-layout:auto"}

1. 使用[受众生成器](#audience-builder)构建受众。

1. 使用[日期预览](#data-preview)面板解释数据。

1. 选择&#x200B;**[!UICONTROL [!UICONTROL 查看示例 ID]]** 来查看此受众中的 ID 示例。在 **[!UICONTROL ID 示例]**&#x200B;对话框中，您可以使用![搜索](/help/assets/icons/Search.svg) [!UICONTROL *搜索 ID 示例*]&#x200B;来搜索 ID 示例。

1. 双击受众配置，然后选择&#x200B;**[!UICONTROL 发布]**。
您会收到一条受众已发布的确认消息。发布只需要一两分钟，这个受众就会出现在 Experience Platform 上。

1. 在同一条消息中选择&#x200B;**[!UICONTROL 在 AEP 中查看受众]**，即可进入 Adobe Experience Platform 中的 [Segment UI](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/segmentation/ui/overview)。有关详细信息，请参阅下文。

## 受众生成器

通过配置这些设置来定义或更新您的受众。

![创建受众的屏幕快照，其中显示下一节中描述的设置。](assets/create-audience.png)

| 设置 | 描述 |
| --- | --- |
| ![数据](/help/assets/icons/Data.svg) | 选择用于创建受众群体的数据视图。 |
| **[!UICONTROL 名称]** | 受众的名称。例如，`Really Interested in Potential Car Buyers` |
| **[!UICONTROL 标记]** | 出于组织目的而要分配给受众的任何标记。您可以选择一个或多个预先存在的标记，也可以输入一个新标记。 |
| **[!UICONTROL 描述]** | 对受众的描述，以区别于其他人。例如，`Build an audience of really interested potential car buyers` |
| **[!UICONTROL 刷新频率]** | 您刷新受众所要采用的频率。<p/>您可以选择 <ul><li>**[!UICONTROL 一次性]** 受众：无需刷新的受众（默认）。例如，该选项可能有助于特定的一次性营销活动。<br/>您必须指定一个&#x200B;**[!UICONTROL 一次性的日期范围]**。您可以使用![日程表](/help/assets/icons/Calendar.svg)来输入日期范围。</li><li>刷新的受众。您可以从下列选项中进行选择：<ul><li>**[!UICONTROL 每 4 小时]**：每 4 小时刷新一次的受众。</li><li>**[!UICONTROL 每日]**：每日刷新一次的受众</li><li>**[!UICONTROL 每周]**：每周刷新一次的受众。</li><li>**[!UICONTROL 每月]**：每月刷新一次的受众</li></ul></li>若要刷新观众，您必须指定：<ul><li>**[!UICONTROL 刷新回顾窗口]**。定义从今天开始评估受众的回顾天数。您可以从选项中进行选择或定义自定义时间。最长为 90 天。</li><li>**[!UICONTROL 到期日期]**：定义受众停止刷新的时间。您可以使用![日程表](/help/assets/icons/Calendar.svg)选择日期。默认值为创建日期开始 1 年。到期受众的处理方式与到期的计划报告类似。管理员会在受众到期前一个月收到一封电子邮件。</li></ul> 请注意，受众刷新次数限制为 75 到 150 次，具体取决于您的 Customer Journey Analytics 权限。</li></ul> |
| **[!UICONTROL 过滤器]** | 过滤器是受众的主要输入。将一个或多个区段从左侧![分段](/help/assets/icons/Segmentation.svg)**[!UICONTROL 区段]**&#x200B;面板拖放到区段区域。您可以使用![搜索](/help/assets/icons/Search.svg) [!UICONTROL *搜索区段*]&#x200B;来搜索区段。您最多可以添加 20 个区段。区段可以与 **[!UICONTROL And]** 或 **[!UICONTROL Or]** 运算符相连。<p>从 Analysis Workspace 中的可视化图表（例如自由格式表或“历程”画布）创建受众时，应用于面板或列的任何区段都会保留。您可以移除任何自动应用的区段。</p> |
| **[!UICONTROL 数据预览]** | 选择![信息](/help/assets/icons/Info.svg)可显示或隐藏所选日期范围的[数据预览](#data-preview)。 |

## 数据预览

数据预览面板提供以下信息。

| 元素 | 描述 |
| --- | --- |
| **[!UICONTROL 总人数]** | 该受众中总人数的汇总。最大规模为 2000 万人。如果您的受众超过 2000 万人，则必须先缩小受众规模，然后才能发布。 |
| **[!UICONTROL 受众规模限制]** | 显示该受众距离 2000 万人的限制还有多远的可视化内容。 |
| **[!UICONTROL 预计观众回访率]** | 您可以使用此值重新定位该受众中返回您的网站、移动应用程序或其他渠道的用户。<p>您可以为可能返回的估计客户数量选择时间范围（**[!UICONTROL 未来 7 天]**、**[!UICONTROL 未来 2 周]**&#x200B;或&#x200B;**[!UICONTROL 下个月]**）。 |
| **[!UICONTROL 预计会返回]** | 该数字为您提供了在您选择的时间范围内返回的客户的估计数量。这个数字是使用该受众的历史流失率预测的。 |
| **[!UICONTROL 预览量度]** | 您可以选择一个特定的量度，以查看该量度的数据是如何基于您定义的受众得出的。每个预览量度都会根据受众显示该量度的总数。以及数据视图定义的基于受众的量度占量度总数的百分比。例如，381 人（您选择的量度）是对受众定义的结果，其占数据视图中可用总人数的 5%。您可以选择数据视图中可用的任何量度。 |
| **[!UICONTROL 命名空间包含]** | 与受众中的人关联的特定命名空间。例如 ECID、CRM ID、电子邮件地址等。 |
| **[!UICONTROL 沙盒]** | 受众所在的 [Experience Platform sandbox](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home) 沙盒。当您将此受众发布到 Platform 时，您只能在这个沙盒的范围内使用该受众。 |

{style="table-layout:auto"}

## 创建和发布受众后会发生什么? {#after-audience-created}

在 Customer Journey Analytics 中创建并发布受众后，受众就可以在 Experience Platform 中使用，并可在[受众门户](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/segmentation/ui/audience-portal)中查看。受众不仅在 Experience Platform 中可用，也可以在其他 Experience Platform 应用程序中使用，如 Adobe Journey Optimizer。

只有您的组织设置了流式分段，才会创建 Adobe Experience Platform 流式区段。

在使用从 Customer Journey Analytics 发布到 Experience Platform 的受众时，请考虑以下事项：

* Experience Platform 中的受众与 Customer Journey Analytics 受众具有相同的名称和描述。该名称附加了 Customer Journey Analytics 受众 ID，以确保受众的唯一性。
* Customer Journey Analytics 中对受众名称或描述所做的任何更改都会反映在 Experience Platform 中。
* 如果在 Customer Journey Analytics 中删除了某个受众，则该受众仍可在 Experience Platform 中继续使用，直到该受众的轮廓会员资格到期。对于一次性观众，轮廓会员资格会在 420 天后到期；对于定期观众，轮廓会员资格会在 16 天后到期。

## 延迟注意事项 {#latency}

在受众发布之前、期间和之后的几个时间点，可能会出现延迟。以下是对可能出现的延迟情况的概述。

![本节所述的受众发布中的延迟。](assets/latency-diagram.svg)

|  | 延迟点 | 延迟持续时间 |
| --- | --- | --- |
| 未显示 | Adobe Analytics 至 Analytics 源连接器 (A4T) | 最多 30 分钟 |
| 1 | 数据摄入数据湖（从 Analytics 源连接器或其他来源） | 最多 90 分钟 |
| 2 | 将数据从 Experience Platform Data Lake 引入到 Customer Journey Analytics | 最多 90 分钟 |
| 3 | 受众发布到实时客户轮廓，包括自动创建流式区段，并可让区段准备好接收数据。 | 几秒钟 |
| 4 | 受众的刷新频率 | <ul><li>一次性刷新（延迟小于 5 分钟）</li><li>每 4 小时、每天、每周、每月刷新一次（延迟与刷新率密切相关） |
| 5 | 在 Adobe Experience Platform 中创建目标：激活新区段 | 1-2 小时 |

{style="table-layout:auto"}

## 在 Experience Platform 中使用 Customer Journey Analytics {#audiences-aep}

Customer Journey Analytics 可以从您发布的受众中获取所有的命名空间和 ID 组合，并将其流式传输到 Real-Time Customer Data Platform 中。Customer Journey Analytics 会将受众发送到 Experience Platform，并根据配置连接时选择的[!UICONTROL 人员 ID] 设置主要身份标识。

然后，Real-Time Customer Data Platform 会检查每个命名空间/ID 组合，并查找可能包含它的轮廓。轮廓其实就是由所链接的命名空间、ID 和设备组成的集群。如果它找到一份相关的轮廓，则会将命名空间和 ID 作为区段会员资格属性添加到此轮廓中的其他 ID。例如，<user@adobe.com> 可以成为所有设备和渠道的目标。如果未找到相关的轮廓，则会创建一份新的轮廓。

要在 Platform 中查看 Customer Journey Analytics 受众，请执行以下操作：

1. 在左侧面板中展开&#x200B;**[!UICONTROL 客户]**，然后选择&#x200B;**[!UICONTROL 受众]**。<!-- is there a folder called "Customer Journey Analytics? -->

1. 选择&#x200B;**[!UICONTROL 浏览]**&#x200B;选项卡。

1. 要找到您从 Customer Journey Analytics 发布的受众，请执行以下操作之一：

   ![左侧面板中的受众选项](assets/aep-audiences.png)

   * 按&#x200B;**[!UICONTROL 来源]**&#x200B;列对表格进行排序，以查看将 [!UICONTROL **Customer Journey Analytics**] 显示为来源的受众。

   * 按&#x200B;**[!UICONTROL 来源]**&#x200B;进行筛选![筛选](/help/assets/icons/Filter.svg)并选择 **[!UICONTROL Customer Journey Analytics]**。

   * 使用![搜索](/help/assets/icons/Search.svg)搜索字段。

有关在 Platform 中使用受众的更多信息，请参阅 Experience Platform 文档中的[区段生成器 UI 指南](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/segmentation/ui/segment-builder)中的[受众](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/segmentation/ui/segment-builder)部分。

### 了解受众数量的差异

Customer Journey Analytics 和 Real-Time Customer Data Platform 两者的受众数量可能会有差异。

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### 估计数量与确定数量

这两个应用程序计算受众会员数量的方法有所不同，详见下文所述。

* **Customer Journey Analytics**：Customer Journey Analytics 中的&#x200B;**[!UICONTROL 总人数]**&#x200B;量度是一个估计值。这意味着这是根据受众规则估计的数量，可能在刷新间隔之间发生变化。
* **Real-Time Customer Data Platform**：Real-Time Customer Data Platform 中的数量是确定的，基于每日评估工作，这个数值固定在受众门户中完成受众发布的这一刻。

#### 发布间隔和速度

受众以每秒 1500 条记录 (RPS) 的速度在 Real-Time Customer Data Platform 上发布。例如，拥有 2000 万会员的受众大约需要 3.7 小时才能完全发布（2000 万/1500 RPS/每小时 3600 秒）。在这个过程中，两个应用程序的受众会员可能会有所不同。

#### 轮廓碎片化

如果从 Customer Journey Analytics 导入的轮廓在 Real-Time Customer Data Platform 中已经存在，它们就不被视为新轮廓。这可能导致 Real-Time Customer Data Platform 中的轮廓数量低于预期。

#### 批量受众与流媒体受众

Customer Journey Analytics 受众不包括在每日批量评估作业中，直到下一个发布间隔之前都保持不变。与此不同，Real-Time Customer Data Platform 中的其他批量受众每 24 小时就会重新评估一次。

### 需要记住的关键要点

* **Customer Journey Analytics 中的估计数量**：了解 Customer Journey Analytics 中的&#x200B;**[!UICONTROL 总人数]**&#x200B;是一个估计值，可能会因流数据和身份标识行为而变化。
* **Real-Time Customer Data Platform 中的确定数量**：Real-Time Customer Data Platform 中的数量是固定的，直到下一个发布间隔之前都保持不变。
* **轮廓碎片化**：请注意，从 Customer Journey Analytics 导入轮廓的情况下，Real-Time Customer Data Platform 中现有的轮廓可能不会计入新的轮廓数量。

明确区分这几个方面，您就可以更好地了解和管理跨应用 Customer Journey Analytics 和 Real-Time Customer Data Platform 的受众数据。--->

## 常见问题解答 {#faq}

关于受众发布的常见问题。

+++**如果用户不再是 Customer Journey Analytics 中的受众，会发生什么？**

在这种情况下，系统会从 Customer Journey Analytics 将退出事件发送给 Experience Platform。

+++

+++**如果您在 Customer Journey Analytics 中删除受众，会发生什么情况？**

删除 Customer Journey Analytics 受众后，该受众将不会再在 Experience Platform UI 中显示。然而，与该受众相关的轮廓不会在 Experience Platform 中删除。

+++

+++**如果 Real-Time Customer Data Platform 中不存在相应的轮廓，是否会创建新的轮廓？**

是的，会的。

+++

+++**Customer Journey Analytics 是将受众数据作为管道事件发送，还是作为也进入数据湖的平面文件发送？**

Customer Journey Analytics 通过管道将数据流式传输至 Real-Time Customer Data Platform，并且这些数据也会被收集到数据湖中的系统数据集中。

+++

+++**Customer Journey Analytics 会发送哪些身份标识？**

[连接设置](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-connections/create-connection)中指定的身份标识/命名空间对。具体来说，这是用户选择要用作其“个人 ID”的字段时的步骤。

+++

+++**选择什么 ID 作为主要身份标识？**

请参阅上面的内容。每个 Customer Journey Analytics 人员仅发送一个身份标识。

+++

+++**Real-Time Customer Data Platform 是否也处理 Customer Journey Analytics 消息？Customer Journey Analytics 是否可以通过受众共享将身份标识添加到轮廓身份标识图中？**

否。每个人只发送一个身份标识，因此没有图形边缘可供 Real-Time Customer Data Platform 使用。

+++

+++**每日、每周和每月的刷新发生在一天中的什么时间？对于每周进行一次的刷新，一周中的哪一天会进行刷新？**

刷新的时间取决于原始受众的发布时间，并固定在一天中的那个时间（以及一周中的某天或一个月中的某天）。

+++

+++**可以配置每天、每周、每月的刷新时间吗？**

不可以，用户无法配置刷新时间。

+++


## 后续步骤

* 若要管理该受众，请转到[管理 UI](/help/components/audiences/manage.md)。
