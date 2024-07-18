---
description: 过滤器生成器提供了一个画布以将指标Dimension、过滤器和事件拖放到其中，从而根据容器层次结构逻辑、规则和运算符过滤人员。 通过使用该集成开发工具，您可以生成并保存简单或复杂的过滤器，以确定跨访问和事件的人员属性和操作。
title: 构建过滤器
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: e1f1e37293f1a18616b11fea685d372ec499c407
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 20%

---

# 过滤器生成器

通过[!UICONTROL 筛选器生成器]，可生成简单或复杂的筛选器，这些筛选器可标识跨访问和事件的人员属性和操作。 它提供了一个画布以将指标维度、事件或其他过滤器拖放到其中，从而根据层次结构逻辑、规则和运算符筛选人员。

有关如何创建仅应用于创建快速筛选器的项目的信息，请参阅[快速筛选](/help/components/filters/quick-filters.md)。

## 访问过滤器生成器

您可以通过以下任意方式访问过滤器生成器：

* **顶部导航**：单击&#x200B;**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 组件]** > **[!UICONTROL 筛选器]**。
* **[!UICONTROL Analysis Workspace]**：在Analysis Workspace中打开一个项目，选择&#x200B;**[!UICONTROL +组件]** > **[!UICONTROL 创建筛选器]**。
* **[!UICONTROL Report Builder]**： [使用Report Builder](/help/report-builder/work-with-filters.md)中的筛选器。

## 生成器条件概述 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以添加规则定义和容器以定义过滤器。 （有关访问筛选器生成器的信息，请参阅[访问筛选器生成器](#access-the-filter-builder)。）

![筛选器生成器显示本节所述的新筛选器选项。](assets/segment_builder_ui_2.png)

| UI 元素 | 描述 |
| --- | --- |
| **[!UICONTROL 标题]** | 命名过滤器 |
| **[!UICONTROL 描述]** | 提供过滤器的详细说明。 |
| **[!UICONTROL 标记]** | [通过从现有标记列表中选取标记或创建新标记来标记您创建的过滤器](/help/components/filters/manage-filters.md)。 |
| **[!UICONTROL 定义]** | 在这里，您可以[生成和配置过滤器](/help/components/filters/filters-overview.md)、添加规则、嵌套和排列容器。 |
| **[!UICONTROL 包含]** | （顶部容器选择器。） 允许您选择顶级[容器](/help/components/filters/filters-overview.md)（[!UICONTROL 人员]，[!UICONTROL 会话]，[!UICONTROL 事件]）。 默认的顶级容器为“事件”容器。 |
| **[!UICONTROL 选项]** | （齿轮）图标 | <ul><li>**[!UICONTROL +添加容器]**：用于向筛选器定义添加新容器（在顶级容器下）。</li><li>**[!UICONTROL 排除]**：允许您通过排除一个或多个维度、过滤器或量度来定义过滤器。</li></ul> |
| **[!UICONTROL 维度]** | 从Dimension列表中拖放的组件（橙色侧栏）。 |
| **[!UICONTROL 运算符]** | 您可以使用选定的运算符比较和约束值。 （等于、不等于、包含、包含全部等） |
| **[!UICONTROL 值]** | 为维度、过滤器或量度输入或选择的值。 |
| **[!UICONTROL 归因模型]** | 这些模型仅适用于维度，它们确定要过滤的维度值。 Dimension模型在连续过滤器中特别有用。<ul><li>**[!UICONTROL 重复]**（默认）：包含维度的实例和保留值。</li><li>**[!UICONTROL 实例]**：包含维度的实例。</li><li>**[!UICONTROL 非重复实例]**：包含维度的唯一实例（非重复）。这是排除重复实例时在“流量”中应用的模型。</li></ul>有关示例，请参阅下面的“归因模型”部分。 |
| **[!UICONTROL And/Or/Then]** | 在容器或规则之间分配 [!UICONTROL AND/OR/THEN] 运算符。THEN运算符允许您[定义顺序筛选器](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL 量度]** | （绿色侧栏）从指标列表中拖放的指标。 |
| **[!UICONTROL X]** | （删除）用于删除此部分过滤器定义。 |
| **[!UICONTROL 从筛选器创建受众]** | 通过从过滤器创建受众，可将该过滤器与Adobe Experience Platform共享以供激活。 [了解详情...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL 搜索组件]** | 搜索维度、过滤器或量度列表。 |
| **[!UICONTROL 维度]** | （列表）可包含在过滤器中的维度列表。 单击标题可展开。 |
| **[!UICONTROL 指标]** | 可包含在过滤器中的量度列表。 单击标题可展开。 |
| **[!UICONTROL 过滤器]** | 可包含在筛选器中的现有筛选器列表。 单击标题可展开。 |
| **[!UICONTROL 数据视图选择器]** | 允许您选择保存此过滤器的报表包。 您仍然可以在所有数据视图中使用过滤器。 |
| **[!UICONTROL 筛选器预览]** | 允许您预览关键量度，以查看您的过滤器是否有效以及该过滤器的作用范围。 表示预计将看到是否应用此筛选器的数据集的划分方式。 显示3个同心圆和一个列表，以针对数据集运行过滤器时显示[!UICONTROL 人员]、[!UICONTROL 会话]和[!UICONTROL 报告运行]的匹配数量和百分比。<p>此图表将在您创建或更改筛选器定义后立即更新。 |
| **[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 取消]** | 保存或取消过滤器。 单击&#x200B;**[!UICONTROL 保存]**&#x200B;后，将转到过滤器管理器，您可以在其中管理过滤器。 |

## 构建过滤器 {#build-filters}

1. 只需将Dimension、筛选器或量度事件从左窗格拖到[!UICONTROL 定义]字段。

   ![](assets/drag_n_drop_dimension.png)

1. 从下拉菜单中，设置[运算符](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hans)。
1. 输入或选择所选项目的值。
1. 如果需要，可使用“**[!UICONTROL And]**”、“**[!UICONTROL Or]**”或“**[!UICONTROL Then]**”规则添加其他容器。
1. 放置容器并设置规则后，可在右上角的验证图表中查看筛选器的结果。 验证器指示与您创建的过滤器匹配的页面查看次数、访问次数和独特访客的百分比和绝对数量。
1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;下，[标记](/help/components/filters/filters-tag.md)容器，方法是选择现有标记或创建新标记。
1. 单击&#x200B;**[!UICONTROL 保存]**&#x200B;以保存筛选器。

   您将转到[筛选器管理器](/help/components/filters/manage-filters.md)，在此处，可以通过多种方式标记、共享和管理筛选器。

## 添加容器 {#containers}

您可以[生成容器框架](/help/components/filters/filters-overview.md)，然后在其中放置逻辑规则和运算符。

1. 单击&#x200B;**[!UICONTROL 选项>添加容器]**。

   打开新的&#x200B;[!UICONTROL **Event**]&#x200B;容器，但未识别&#x200B;[!UICONTROL **Event**] （页面查看）。

   ![](assets/new_container.png)

1. 根据需要更改容器类型。
1. 将Dimension、筛选器或事件从左窗格拖动到容器。
1. 继续通过定义顶部的顶级“**[!UICONTROL 选项]** > **[!UICONTROL 添加容器]**”按钮添加新容器，或者从容器中添加容器以嵌套逻辑。

   **或者**

   选择一个或多个规则，然后单击“**[!UICONTROL 选项]** > **[!UICONTROL 通过选择添加容器]**”。这会将您的选择转换为单独的容器。

## 使用日期范围 {#date-ranges}

您可以构建包含滚动日期范围的过滤器，以获取有关持续促销活动或事件问题的解答。

例如，您可以轻松构建一个过滤器，包含“过去60天内购买过产品的用户”。

您可以创建一个会话容器，并在其中添加[!UICONTROL 最近60天]时间范围和量度[!UICONTROL 订单大于或等于1]（使用AND运算符）。

以下是一段关于在过滤器中使用滚动日期范围的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆叠筛选器 {#stack}

栈叠筛选器的工作方式是使用“and”运算符组合每个筛选器中的条件，然后应用该组合条件。 可以直接在Workspace项目中或在筛选器生成器中完成此操作。

例如，栈叠“移动电话用户”过滤器和“美国地区”过滤器将只返回美国的移动电话用户的数据。

您可以将这些过滤器视为构建块或模块，并将其包含在过滤器库中，以便用户酌情使用。 这样，您就可以显着减少所需的过滤器数量。 例如，假设您有40个过滤器：

* 20 个用于不同国家/地区的移动电话用户（US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等）
* 20 个用于不同国家/地区的平板电脑用户（US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等）

通过使用过滤器栈叠，您可以将过滤器数量减少到22个，然后根据需要进行栈叠。 您需要创建以下过滤器：

* 适用于移动用户的单一筛选器
* 一个适用于平板电脑用户的过滤器
* 适用于不同地理区域的20个过滤器

>[!NOTE]
>
>栈叠两个筛选器时，默认使用AND语句联接。 无法更改为 OR 语句。

1. 转到过滤器生成器。

1. 提供过滤器的标题和描述。

1. 单击&#x200B;**[!UICONTROL 显示筛选器]**&#x200B;以在左侧导航中显示筛选器列表。

1. 将要栈叠的筛选器拖到筛选器定义画布上。

1. 选择&#x200B;[!UICONTROL **保存**]。

## 归因模型 {#attribution}

![](assets/attribution-models.jpg)

**示例：eVar1 = A**&#x200B;的事件筛选器

| 示例 | A | A | A（保留） | B | A | C |
|---|---|---|---|---|---|---|
| 重复 | X | X | X | - | X | - |
| 实例 | X | X | - | - | X | - |
| 非重复实例 | X | - | - | - | X | - |
