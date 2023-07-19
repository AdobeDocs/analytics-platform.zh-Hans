---
description: 过滤器生成器提供了一个画布以将指标Dimension、过滤器和事件拖放到画布上，从而根据容器层次结构逻辑、规则和运算符过滤人员。 通过这个集成的开发工具，您可以构建和保存简单或复杂的过滤器，以确定跨访问和事件的人员属性和操作。
title: 构建过滤器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: d045ecf73f7e15940510b764814fb853222e88cc
workflow-type: tm+mt
source-wordcount: '1396'
ht-degree: 22%

---

# 过滤器生成器

此 [!UICONTROL 筛选器生成器] 可让您构建简单或复杂的过滤器，用于标识跨访问和事件的人员属性和操作。 它提供了一个画布以将指标维度、事件或其他过滤器拖放到其中，从而根据层次结构逻辑、规则和运算符筛选人员。

有关如何创建仅应用于在其中创建筛选器的项目的快速筛选器的信息，请参阅 [快速过滤器](/help/components/filters/quick-filters.md).

## 访问过滤器生成器

您可以通过以下任意方式访问过滤器生成器：

* **顶部导航**：单击 **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 组件]** > **[!UICONTROL 筛选器]**.
* **[!UICONTROL Analysis Workspace]**：在Analysis Workspace中打开一个项目后，选择 **[!UICONTROL +组件]** > **[!UICONTROL 创建筛选器]**.
* **[!UICONTROL Report Builder]**： [在Report Builder中使用筛选器](/help/report-builder/work-with-filters.md).

## 生成器标准概述 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以添加规则定义和容器以定义过滤器。 (有关访问过滤器生成器的信息，请参阅 [访问过滤器生成器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 标题]**：命名过滤器。
1. **[!UICONTROL 描述]**：提供对过滤器的描述。
1. **[!UICONTROL 标记]**： [标记过滤器](/help/components/filters/manage-filters.md) 您可通过从现有标记列表中选取标记或创建新标记来进行创建。
1. **[!UICONTROL 定义]**：这是您所在的位置 [生成和配置过滤器](/help/components/filters/filters-overview.md)，添加规则，以及嵌套和排序容器。
1. **[!UICONTROL 显示]**：（顶部容器选择器。）允许您选择顶级 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 人员]， [!UICONTROL 会话]， [!UICONTROL 事件])。 默认的顶级容器是事件容器。
1. **[!UICONTROL 选项]**：（齿轮）图标

   * **[!UICONTROL +添加容器]**：用于向筛选器定义添加新容器（在顶级容器下）。
   * **[!UICONTROL 排除]**：用于通过排除一个或多个维度、过滤器或量度来定义过滤器。

1. **[!UICONTROL 维度]**：从维度列表中拖放的组件（橙色侧栏）。
1. **[!UICONTROL 运算符]**：您可以使用选定的运算符比较和约束值。
1. **[!UICONTROL 值]**：为维度、过滤器或量度输入或选择的值。
1. **[!UICONTROL 归因模型]**：这些模型仅适用于维度，它们确定要过滤的维度值。 Dimension模型在顺序过滤器中特别有用。

   * **[!UICONTROL 重复]**（默认）：包含维度的实例和保留值。
   * **[!UICONTROL 实例]**：包含维度的实例。
   * **[!UICONTROL 非重复实例]**：包含维度的唯一实例（非重复）。这是排除重复实例时在“流量”中应用的模型。

   ![](assets/attribution-models.jpg)

   **示例：eVar1 = A的事件过滤器**

   | 示例 | A | A | A（保留） | B | A | C |
   |---|---|---|---|---|---|---|
   | 重复 | X | X | X | - | X | - |
   | 实例 | X | X | - | - | X | - |
   | 非重复实例 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**：在容器或规则之间分配 [!UICONTROL AND/OR/THEN] 运算符。THEN运算符允许您 [定义顺序过滤器](/help/components/filters/filters-overview.md).
1. **[!UICONTROL 指标]**：（绿色侧栏）从指标列表中拖放的指标。
1. **[!UICONTROL 比较]**&#x200B;运算符：您可以使用选定的运算符比较和约束值。
1. **[!UICONTROL 值]**：为维度、过滤器或量度输入或选择的值。
1. **[!UICONTROL X]**：（删除）用于删除此部分过滤器定义。
1. **[!UICONTROL Experience Cloud发布]**：将Adobe Analytics过滤器发布到Experience Cloud后，您可以将该过滤器用于中的营销活动 [!DNL Audience Manager] 和其他激活渠道中的。 [了解详情...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 受众库]**：Adobe的受众服务可管理将人员数据转换为受众过滤器的过程。 因此，创建和管理受众与创建和使用过滤器类似，只是前者增加了一项将受众过滤器共享到Experience Cloud的功能。 [了解详情...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜索]**：搜索维度、过滤器或量度列表。
1. **[!UICONTROL 维度]**：（列表）单击标题可展开。
1. **[!UICONTROL 指标]**：单击标题可展开。
1. **[!UICONTROL 筛选器]**：单击标题可展开。
1. **[!UICONTROL 数据视图选择器]**：用于选择保存此筛选器的报表包。 您仍然可以在所有数据视图中使用筛选器。
1. **[!UICONTROL 筛选器预览]**：用于预览关键量度，以确定是否具有有效的过滤器以及过滤器的作用范围。 表示预计会看到是否应用此筛选器的数据集的划分方式。 显示3个同心圆和一个列表，用于显示匹配的数量和百分比 [!UICONTROL 事件]， [!UICONTROL 人员]、和 [!UICONTROL 会话] 针对数据集运行的过滤器。 此图表会在您创建或更改筛选器定义后立即更新。
1. **[!UICONTROL 产品兼容性]**：提供哪些Adobe Analytics产品(Analysis Workspace、 [!UICONTROL Reports &amp; Analytics]，Data warehouse)，与您创建的过滤器兼容。 大多数过滤器与所有产品都兼容。 但是，并非所有运算符和维度都与所有Analytics产品兼容，特别是 [data warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). 在对筛选器定义进行更改后，将立即更新此图表。
1. **[!UICONTROL 保存]** 或 **[!UICONTROL 取消]**：保存或取消过滤器。 单击后 **[!UICONTROL 保存]**，您将转到过滤器管理器，可以在其中管理过滤器。

嵌入了日期范围的过滤器在Analysis Workspace中的操作仍然有所不同，与 [!UICONTROL Reports &amp; Analytics]：在工作区中，嵌入了日期范围的过滤器会覆盖面板日期范围。 相比之下， [!UICONTROL Reports &amp; Analytics] 为您提供报表日期范围和筛选器的嵌入日期范围的交集。

## 构建过滤器 {#build-filters}

1. 只需将Dimension、过滤器或量度事件从左窗格拖动到 [!UICONTROL 定义] 字段。

   ![](assets/drag_n_drop_dimension.png)

1. 从下拉菜单中，设置[运算符](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hans)。
1. 输入或选择所选项目的值。
1. 如果需要，可使用“**[!UICONTROL And]**”、“**[!UICONTROL Or]**”或“**[!UICONTROL Then]**”规则添加其他容器。
1. 放置容器并设置规则后，可在右上角的验证图表中查看筛选器的结果。 验证器指示与您创建的过滤器匹配的页面查看次数、访问次数和独特访客的百分比和绝对数量。
1. 下 **[!UICONTROL 标记]**， [标记](/help/components/filters/manage-filters.md) 容器。
1. 单击 **[!UICONTROL 保存]** 以保存过滤器。

   您会被带到 [筛选器管理器](/help/components/filters/manage-filters.md)，您可以通过多种方式标记、共享和管理过滤器。

## 添加容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[生成容器框架](/help/components/filters/filters-overview.md)，然后在其中放置逻辑规则和运算符。

1. 单击 **[!UICONTROL 选项>添加容器]**.

   新 [!UICONTROL **事件**] 容器打开，但不包含 [!UICONTROL **事件**] （页面查看）已识别。

   ![](assets/new_container.png)

1. 根据需要更改容器类型。
1. 将Dimension、筛选器或事件从左窗格拖动到容器。
1. 继续通过定义顶部的顶级“**[!UICONTROL 选项]** > **[!UICONTROL 添加容器]**”按钮添加新容器，或者从容器中添加容器以嵌套逻辑。

   **或者**

   选择一个或多个规则，然后单击“**[!UICONTROL 选项]** > **[!UICONTROL 通过选择添加容器]**”。这会将您的选择转换为单独的容器。

## 使用日期范围 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以构建包含滚动日期范围的过滤器，以回答有关持续促销活动或事件的问题。

例如，您可以轻松构建一个包含“过去60天内购买过一次的人”的过滤器。

创建一个会话容器，并在其中添加 [!UICONTROL 最近60天] 时间范围和量度 [!UICONTROL 订单大于或等于1]，使用AND运算符。

以下是一段关于在过滤器中使用滚动日期范围的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆叠筛选器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

栈叠筛选器的工作方式是使用“and”运算符组合每个筛选器中的条件，然后应用组合条件。 可以直接在Workspace项目中或在过滤器生成器中完成此操作。

例如，栈叠“移动电话用户”过滤器和“美国地区”过滤器将只返回美国的移动电话用户的数据。

将这些过滤器视为构建块或模块，可将其包含在过滤器库中，以供用户酌情使用。 这样，您就可以显着减少所需的过滤器数量。 例如，假设您有40个过滤器：

* 20 个用于不同国家/地区的移动电话用户（US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等）
* 20 个用于不同国家/地区的平板电脑用户（US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等）

通过使用过滤器栈叠，您可以将过滤器数量减少到22个，然后根据需要栈叠它们。 您需要创建以下过滤器：

* 移动用户使用一个筛选器
* 一个适用于平板电脑用户的过滤器
* 适用于不同地理位置的20个过滤器

>[!NOTE]
>
>栈叠两个筛选器时，默认使用AND语句联接。 无法更改为 OR 语句。

1. 转到过滤器生成器。

1. 提供过滤器的标题和描述。

1. 单击 **[!UICONTROL 显示筛选器]** 以在左侧导航中显示过滤器列表。

1. 将要栈叠的筛选器拖到筛选器定义画布上。

1. 选择&#x200B;[!UICONTROL **保存**]。

