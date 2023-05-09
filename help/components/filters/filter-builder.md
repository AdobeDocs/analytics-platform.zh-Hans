---
description: 过滤器生成器提供了一个画布，用于拖放量度Dimension、过滤器和事件，以根据容器层次结构逻辑、规则和运算符过滤访客。 通过使用该集成开发工具，您可以生成和保存简单或复杂的过滤器，以确定跨访问和页面点击的访客属性和操作。
title: 构建过滤器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 36%

---

# 过滤器生成器

的 [!UICONTROL 过滤器生成器] 允许您构建简单或复杂的过滤器，以确定跨访问和页面点击的访客属性和操作。 它提供了一个画布，用于拖放量度维度、事件或其他过滤器，以便根据层次结构逻辑、规则和运算符过滤访客。

有关如何创建仅应用于所创建项目的快速过滤器的信息，请参阅 [快速过滤器](/help/components/filters/quick-filters.md).

## 访问过滤器生成器

您可以通过以下任一方式访问过滤器生成器：

* **Analytics顶部导航**:单击 **[!UICONTROL Analytics]** > **[!UICONTROL 组件]** > **[!UICONTROL 过滤器]**.
* **[!UICONTROL Analysis Workspace]**:在Analysis Workspace中打开项目，选择 **[!UICONTROL +组件]** > **[!UICONTROL 创建过滤器]**.
* **[!UICONTROL Reports &amp; Analytics]**:单击 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]**，打开现有报表，然后单击 **过滤器** 图标，然后单击 **[!UICONTROL 添加]**.
* **[!UICONTROL Report Builder]**: [在Report Builder中添加或编辑过滤器](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=zh-Hans).

## 生成器标准概述 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以添加规则定义和容器以定义过滤器。 (有关访问过滤器生成器的信息，请参阅 [访问过滤器生成器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 标题]**:命名过滤器。
1. **[!UICONTROL 描述]**:为过滤器提供描述。
1. **[!UICONTROL 标记]**: [标记过滤器](/help/components/filters/manage-filters.md) 您可以通过从现有标记列表中选取标记或创建新标记来创建。
1. **[!UICONTROL 定义]**:这里是你 [构建和配置过滤器](/help/components/filters/filters-overview.md)、添加规则，以及嵌套和排列容器。
1. **[!UICONTROL 显示]**：（顶部容器选择器。）允许您选择顶级 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 人员], [!UICONTROL 会话], [!UICONTROL 事件])。 默认的顶级容器是事件容器。
1. **[!UICONTROL 选项]**：（齿轮）图标

   * **[!UICONTROL +添加容器]**:用于向过滤器定义中添加新容器（在顶级容器下）。
   * **[!UICONTROL 排除]**:用于通过排除一个或多个维度、过滤器或量度来定义过滤器。

1. **[!UICONTROL 维度]**：从维度列表中拖放的组件（橙色侧栏）。
1. **[!UICONTROL 运算符]**：您可以使用选定的运算符比较和约束值。
1. **[!UICONTROL 值]**:为维度、过滤器或量度输入或选择的值。
1. **[!UICONTROL 归因模型]**:这些模型仅可用于维度，它们确定要筛选的维度值。 Dimension模型在顺序过滤器中特别有用。

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
1. **[!UICONTROL 值]**:为维度、过滤器或量度输入或选择的值。
1. **[!UICONTROL X]**:（删除）用于删除过滤器定义的这一部分。
1. **[!UICONTROL Experience Cloud发布]**:将Adobe Analytics过滤器发布到Experience Cloud后，您可以将该过滤器用于 [!DNL Audience Manager] 和其他激活渠道。 [了解详情...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 受众库]**:Adobe的受众服务可管理如何将访客数据转换为受众筛选器。 因此，创建和管理受众与创建和使用过滤器类似，只是前者增加了一项将受众过滤器共享到Experience Cloud的功能。 [了解详情...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜索]**:搜索维度、过滤器或量度列表。
1. **[!UICONTROL 维度]**：（列表）单击标题可展开。
1. **[!UICONTROL 指标]**：单击标题可展开。
1. **[!UICONTROL 过滤器]**:单击标题可展开。
1. **[!UICONTROL 数据视图选择器]**:允许您选择保存此过滤器的报表包。 您仍然可以在所有数据视图中使用过滤器。
1. **[!UICONTROL 过滤器预览]**:用于预览关键量度，以查看您是否具有有效的过滤器以及过滤器的广泛程度。 表示在应用此过滤器时，您可能会看到的数据集的划分。 显示3个同心圆和一个列表，以显示的匹配数和百分比 [!UICONTROL 事件], [!UICONTROL 人员]和 [!UICONTROL 会话] ，用于针对数据集运行过滤器。 在您创建过滤器定义或对其进行更改后，此图表会立即更新。
1. **[!UICONTROL 产品兼容性]**:提供Adobe Analytics产品(Analysis Workspace、 [!UICONTROL Reports &amp; Analytics]、Data warehouse)。 大多数过滤器与所有产品都兼容。 但是，并非所有运算符和维度都与所有Analytics产品兼容，尤其是 [data warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). 在对过滤器定义进行更改后，此图表会立即更新。
1. **[!UICONTROL 保存]** 或 **[!UICONTROL 取消]**:保存或取消过滤器。 单击 **[!UICONTROL 保存]**，您将转到过滤器管理器，您可以在此处管理过滤器。

嵌入了日期范围的过滤器在Analysis Workspace与 [!UICONTROL Reports &amp; Analytics]:在工作区中，嵌入了日期范围的过滤器会覆盖面板日期范围。 相比之下， [!UICONTROL Reports &amp; Analytics] 提供报表日期范围和过滤器嵌入日期范围的交集。

## 构建过滤器 {#build-filters}

1. 只需将Dimension、过滤器或量度事件从左窗格拖至 [!UICONTROL 定义] 字段。

   ![](assets/drag_n_drop_dimension.png)

1. 从下拉菜单中，设置[运算符](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hans)。
1. 输入或选择所选项目的值。
1. 如果需要，可使用“**[!UICONTROL And]**”、“**[!UICONTROL Or]**”或“**[!UICONTROL Then]**”规则添加其他容器。
1. 放置容器并设置规则后，在右上角的验证图表中查看过滤器的结果。 验证器指示与您创建的过滤器匹配的页面查看次数、访问次数和独特访客的百分比和绝对数量。
1. 在 **[!UICONTROL 标记]**, [标记](/help/components/filters/manage-filters.md) 容器，方法是选择现有标记或创建新标记。
1. 单击 **[!UICONTROL 保存]** 来保存过滤器。

   您将转到 [过滤器管理器](/help/components/filters/manage-filters.md)，您可以在此处通过多种方式标记、共享和管理过滤器。

## 添加容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[生成容器框架](/help/components/filters/filters-overview.md)，然后在其中放置逻辑规则和运算符。

1. 单击 **[!UICONTROL 选项>添加容器]**.

   新 [!UICONTROL **事件**] 容器打开时不显示 [!UICONTROL **事件**] （页面查看）已识别。

   ![](assets/new_container.png)

1. 根据需要更改容器类型。
1. 将Dimension、过滤器或事件从左窗格拖到容器中。
1. 继续通过定义顶部的顶级“**[!UICONTROL 选项]** > **[!UICONTROL 添加容器]**”按钮添加新容器，或者从容器中添加容器以嵌套逻辑。

   **或者**

   选择一个或多个规则，然后单击“**[!UICONTROL 选项]** > **[!UICONTROL 通过选择添加容器]**”。这会将您的选择转换为单独的容器。

## 使用日期范围 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以构建包含滚动日期范围的过滤器，以回答有关持续促销活动或事件的问题。

例如，您可以轻松构建一个过滤器，其中包含“过去60天中购买过产品的用户”。

创建会话容器，并在其中添加 [!UICONTROL 最近60天] 时间范围和量度 [!UICONTROL 订单大于或等于1]，使用AND运算符。

以下是有关在过滤器中使用滚动日期范围的视频：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆叠筛选器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

堆叠过滤器的工作方式是：使用“and”运算符组合每个过滤器中的条件，然后应用组合的条件。 可以直接在工作区项目中或在过滤器生成器中完成此操作。

例如，堆叠“手机用户”过滤器和“美国地理位置”过滤器将只返回美国移动电话用户的数据。

将这些过滤器视为可包含在过滤器库中的构建基块或模块，供用户视需要使用。 这样，您就可以显着减少所需的过滤器数量。 例如，假定您有40个过滤器：

* 20 个用于不同国家/地区的移动电话用户（US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等）
* 20 个用于不同国家/地区的平板电脑用户（US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等）

通过使用过滤器堆叠，您可以将过滤器计数减少到22个，并根据需要进行堆叠。 您需要创建以下过滤器：

* 移动用户一个过滤器
* 平板电脑用户的一个过滤器
* 20个针对不同地理位置的过滤器

>[!NOTE]
>
>堆叠两个过滤器时，默认使用AND语句联接。 无法更改为 OR 语句。

1. 转到过滤器生成器。

1. 为过滤器提供标题和描述。

1. 单击 **[!UICONTROL 显示过滤器]** 以在左侧导航中显示过滤器列表。

1. 将要堆叠的过滤器拖到过滤器定义画布上。

1. 选择&#x200B;[!UICONTROL **保存**]。

## 过滤器模板 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

过滤器模板可用于常见的过滤器用例，如“首次访问”或“从移动设备访问”。 它们可在工作区项目和过滤器生成器中用作新过滤器的构建基块。

模板由 Adobe“A”徽标表示。以下列出了模板示例：

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 模板名称 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 放弃购物车 </td> 
   <td colname="col2">查看向购物车添加了物品但没有订购任何货物的访客的数据。在过滤器定义中，容器为访问。 此顺序过滤器的规则为 <p> 购物车加货不为空 </p> <p>Then </p> <p>订单等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 第一次访问 </td> 
   <td colname="col2">查看最多访问一 [1] 次的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>访问次数等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非顾客 </td> 
   <td colname="col2">查看未参与订购事件的访客的数据。在过滤器定义中，容器为“访客”。 此过滤器使用排除逻辑。 规则为 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非单页面访问（非跳出） </td> 
   <td colname="col2">查看多次访问的访客的数据。在过滤器定义中，容器为“访客”。 此过滤器使用排除逻辑。 规则为 <p>单次访问不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付费搜索 </td> 
   <td colname="col2">查看源自付费搜索的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>付费搜索等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顾客 </td> 
   <td colname="col2">查看参与订购事件的访客的数据。在过滤器定义中，容器为“访客”。 规则为 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回访 </td> 
   <td colname="col2">查看至少访问一次的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>访问次数大于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 单页面访问量 </td> 
   <td colname="col2"> 查看包含某个页面值的访问数据，可以提交该次访问过程中的多个页面查看。过滤器中包含具有退出链接事件的单页面访问量。 在过滤器定义中，容器为访问。 规则为 <p>单个页面访问次数等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查看的产品未添加到购物车 </td> 
   <td colname="col2">查看浏览了产品但未添加到购物车的访客的数据。在过滤器定义中，容器为访问。 此顺序过滤器的规则为 <p>产品查看不为空 </p> <p>Then </p> <p> 购物车加货等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自促销活动的访问量 </td> 
   <td colname="col2">查看通过促销活动引荐的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>跟踪代码不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自移动设备的访问量 </td> 
   <td colname="col2">查看使用移动设备的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>移动设备不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自免费搜索的访问量 </td> 
   <td colname="col2">查看非源自付费搜索的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>付费搜索等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自非移动设备的访问量 </td> 
   <td colname="col2">查看非使用移动设备的访客的数据。在过滤器定义中，容器为访问。 此过滤器使用排除逻辑。 规则为 <p>移动设备类型等于手机 </p> <p>或 </p> <p>移动设备类型等于平板电脑 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自手机的访问量 </td> 
   <td colname="col2">查看使用手机的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>设备类型等于手机。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自搜索引擎的访问量 </td> 
   <td colname="col2">查看通过搜索引擎引荐的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>反向链接类型等于搜索引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 社交网站访问量 </td> 
   <td colname="col2">查看通过社交网站反向链接的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>反向链接类型等于“社交网络”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自平板电脑的访问量 </td> 
   <td colname="col2">查看使用平板电脑的访客的数据。在过滤器定义中，容器为访问。 规则为 <p>设备类型等于平板电脑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用访客 ID Cookie 的访问量 </td> 
   <td colname="col2">查看需要永久性 Cookie 的网站上访客的数据。在过滤器定义中，容器为访问。 规则为 <p>永久性 Cookie 等于 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>