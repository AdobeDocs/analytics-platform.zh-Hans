---
description: 篩選器產生器提供的畫布可拖放量度Dimension、篩選器和事件，以便根據容器階層邏輯、規則和運運算元來篩選訪客。 此整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨瀏覽和事件的訪客屬性和動作。
title: 构建过滤器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 35%

---

# 篩選產生器

此 [!UICONTROL 篩選產生器] 可讓您建立簡單或複雜的篩選器，用於識別跨造訪和事件的訪客屬性和動作。 它提供畫布來拖放量度維度、事件或其他篩選器，以便根據階層邏輯、規則和運運算元來篩選訪客。

如需如何建立僅套用至建立篩選條件之專案的快速篩選條件的相關資訊，請參閱 [快速篩選](/help/components/filters/quick-filters.md).

## 存取篩選產生器

您可以透過下列任何方式存取「篩選產生器」：

* **Analytics頂端導覽**：按一下 **[!UICONTROL 分析]** > **[!UICONTROL 元件]** > **[!UICONTROL 篩選器]**.
* **[!UICONTROL Analysis Workspace]**：在Analysis Workspace中開啟專案後，選取 **[!UICONTROL +元件]** > **[!UICONTROL 建立篩選器]**.
* **[!UICONTROL Reports &amp; Analytics]**：按一下 **[!UICONTROL 分析]** > **[!UICONTROL 報表]**，開啟現有報表並按一下 **篩選** 圖示並按一下「 」 **[!UICONTROL 新增]**.
* **[!UICONTROL Report Builder]**： [在Report Builder中新增或編輯篩選器](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=zh-Hans).

## 產生器條件概觀 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以新增規則定義和容器來定義篩選器。 (如需有關存取篩選產生器的資訊，請參閱 [存取篩選產生器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 標題]**：為篩選器命名。
1. **[!UICONTROL 說明]**：提供篩選的說明。
1. **[!UICONTROL 標籤]**： [標籤篩選器](/help/components/filters/manage-filters.md) 您是從現有標籤清單中挑選標籤或建立新標籤來建立。
1. **[!UICONTROL 定義]**：這裡是您 [建置和設定篩選器](/help/components/filters/filters-overview.md)，新增規則、巢狀內嵌及排序容器。
1. **[!UICONTROL 显示]**：（顶部容器选择器。）可讓您選取頂層 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 個人]， [!UICONTROL 工作階段]， [!UICONTROL 事件])。 預設的頂層容器為「事件」容器。
1. **[!UICONTROL 选项]**：（齿轮）图标

   * **[!UICONTROL +新增容器]**：可讓您新增容器（在頂層容器下）至篩選定義。
   * **[!UICONTROL 排除]**：可讓您透過排除一或多個維度、篩選器或量度來定義篩選器。

1. **[!UICONTROL 维度]**：从维度列表中拖放的组件（橙色侧栏）。
1. **[!UICONTROL 运算符]**：您可以使用选定的运算符比较和约束值。
1. **[!UICONTROL 值]**：您針對維度、篩選器或量度所輸入或選取的值。
1. **[!UICONTROL 歸因模型]**：這些模型僅適用於維度，可決定要篩選的維度值。 Dimension模型在循序篩選器中特別有用。

   * **[!UICONTROL 重复]**（默认）：包含维度的实例和保留值。
   * **[!UICONTROL 实例]**：包含维度的实例。
   * **[!UICONTROL 非重复实例]**：包含维度的唯一实例（非重复）。这是排除重复实例时在“流量”中应用的模型。

   ![](assets/attribution-models.jpg)

   **範例：eVar1 = A的事件篩選器**

   | 示例 | A | A | A（保留） | B | A | C |
   |---|---|---|---|---|---|---|
   | 重复 | X | X | X | - | X | - |
   | 实例 | X | X | - | - | X | - |
   | 非重复实例 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**：在容器或规则之间分配 [!UICONTROL AND/OR/THEN] 运算符。THEN運運算元可讓您 [定義循序篩選器](/help/components/filters/filters-overview.md).
1. **[!UICONTROL 指标]**：（绿色侧栏）从指标列表中拖放的指标。
1. **[!UICONTROL 比较]**&#x200B;运算符：您可以使用选定的运算符比较和约束值。
1. **[!UICONTROL 值]**：您針對維度、篩選器或量度所輸入或選取的值。
1. **[!UICONTROL X]**：（刪除）可用來刪除這部分篩選定義。
1. **[!UICONTROL Experience Cloud發佈]**：將Adobe Analytics篩選器發佈至Experience Cloud，可讓您在中的行銷活動使用該篩選器 [!DNL Audience Manager] 和其他啟用管道中的。 [了解详情...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 對象庫]**：Adobe的受眾服務可管理將訪客資料轉譯為受眾篩選器的工作。 因此，建立和管理對象類似於建立和使用篩選器，再加上可與Experience Cloud共用對象篩選器的功能。 [了解详情...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜尋]**：搜尋維度、篩選器或量度清單。
1. **[!UICONTROL 维度]**：（列表）单击标题可展开。
1. **[!UICONTROL 指标]**：单击标题可展开。
1. **[!UICONTROL 篩選器]**：按一下標題可展開。
1. **[!UICONTROL 資料檢視選擇器]**：可讓您選取要將此篩選器儲存哪個報表套裝底下。 您仍可在所有資料檢視中使用該篩選器。
1. **[!UICONTROL 篩選器預覽]**：可讓您預覽關鍵量度，以檢視您是否具備有效的篩選器以及篩選器的作用範圍。 代表資料集的劃分，您可預期資料集將會顯示您是否套用此篩選器。 顯示3個同心圓和一個清單，用以顯示相符專案的數目和百分比 [!UICONTROL 事件]， [!UICONTROL 個人]、和 [!UICONTROL 工作階段] 用於針對資料集執行的篩選。 此圖表會在您建立或變更篩選定義後立即更新。
1. **[!UICONTROL 產品相容性]**：提供哪些Adobe Analytics產品(Analysis Workspace、 [!UICONTROL Reports &amp; Analytics]，Data Warehouse)，與您建立的篩選器相容。 大部分篩選器都與所有產品相容。 不過，並非所有運運算元和維度都與所有Analytics產品相容，特別是 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). 在您變更篩選器定義後，此圖表會立即更新。
1. **[!UICONTROL 儲存]** 或 **[!UICONTROL 取消]**：儲存或取消篩選器。 按一下 **[!UICONTROL 儲存]**，系統就會將您帶至「篩選器管理器」，讓您管理篩選器。

包含內嵌日期範圍的篩選器在Analysis Workspace中的運作方式持續與 [!UICONTROL Reports &amp; Analytics]：在工作區中，包含內嵌日期範圍的篩選器會覆寫面板日期範圍。 對比之下， [!UICONTROL Reports &amp; Analytics] 會提供報表日期範圍與篩選器內嵌日期範圍的交集。

## 构建过滤器 {#build-filters}

1. 只需將Dimension、篩選器或量度事件從左窗格拖曳至 [!UICONTROL 定義] 欄位。

   ![](assets/drag_n_drop_dimension.png)

1. 从下拉菜单中，设置[运算符](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hans)。
1. 输入或选择所选项目的值。
1. 如果需要，可使用“**[!UICONTROL And]**”、“**[!UICONTROL Or]**”或“**[!UICONTROL Then]**”规则添加其他容器。
1. 放置容器並設定規則後，可在右上角的驗證圖表中檢視篩選結果。 驗證器會指出符合您建立之篩選器的頁面檢視、造訪和不重複訪客的百分比和絕對數量。
1. 下 **[!UICONTROL 標籤]**， [標籤](/help/components/filters/manage-filters.md) 容器，方法是選取現有標籤或建立新標籤。
1. 按一下 **[!UICONTROL 儲存]** 以儲存篩選。

   您會被帶到 [篩選器管理器](/help/components/filters/manage-filters.md)，您可在此透過多種方式標籤、共用及管理您的篩選器。

## 添加容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[生成容器框架](/help/components/filters/filters-overview.md)，然后在其中放置逻辑规则和运算符。

1. 按一下 **[!UICONTROL 選項>新增容器]**.

   新 [!UICONTROL **事件**] 容器開啟，但不包含 [!UICONTROL **事件**] （頁面檢視）已識別。

   ![](assets/new_container.png)

1. 根据需要更改容器类型。
1. 將Dimension、篩選器或事件從左窗格拖曳至容器。
1. 继续通过定义顶部的顶级“**[!UICONTROL 选项]** > **[!UICONTROL 添加容器]**”按钮添加新容器，或者从容器中添加容器以嵌套逻辑。

   **或者**

   选择一个或多个规则，然后单击“**[!UICONTROL 选项]** > **[!UICONTROL 通过选择添加容器]**”。这会将您的选择转换为单独的容器。

## 使用日期范围 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以建立包含滾動日期範圍的篩選器，以回答與持續性促銷活動或事件有關的問題。

例如，您可以輕鬆建立包含「過去60天內購買過一次的人」的篩選器。

您可以建立工作階段容器，並在其中新增 [!UICONTROL 過去60天] 時間範圍和量度 [!UICONTROL 訂單大於或等於1]，且使用AND運運算元。

以下是有關在篩選中使用滾動式日期範圍的影片：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆叠筛选器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

棧疊篩選的運作方式是使用&#39;and&#39;運運算元結合每個篩選中的條件，然後套用結合的條件。 您可以直接在Workspace專案中或在篩選產生器中完成此作業。

例如，棧疊「行動電話使用者」篩選器和「美國地理」篩選器只會傳回美國行動電話使用者的資料。

將這些篩選器視為建置區塊或模組，您可將其納入篩選器程式庫中，讓使用者在他們認為合適的時候使用。 如此一來，您就可以大幅減少所需的篩選器數量。 例如，假設您有40個篩選器：

* 20 个用于不同国家/地区的移动电话用户（US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等）
* 20 个用于不同国家/地区的平板电脑用户（US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等）

透過使用篩選棧疊，您可以將篩選計數減少到22個，並視需要加以棧疊。 您需要建立下列篩選器：

* 適用於行動使用者的單一篩選器
* 平板電腦使用者適用一個篩選器
* 適用於不同地理位置的20個篩選器

>[!NOTE]
>
>將兩個篩選器棧疊在一起時，預設會使用AND陳述式加以連結。 无法更改为 OR 语句。

1. 前往篩選產生器。

1. 提供篩選的標題和說明。

1. 按一下 **[!UICONTROL 顯示篩選器]** 以在左側導覽中開啟篩選器清單。

1. 將您要棧疊的篩選器拖曳至篩選器定義畫布。

1. 选择&#x200B;[!UICONTROL **保存**]。

## 篩選範本 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

篩選範本是針對常見的篩選使用案例而提供的，例如「首次造訪」或「來自行動裝置的造訪」。 它們可在Workspace專案中和篩選器產生器中作為新篩選器的建置組塊。

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
   <td colname="col2">查看向购物车添加了物品但没有订购任何货物的访客的数据。在「篩選器定義」中，容器為「造訪」。 此循序篩選器的規則為 <p> 购物车加货不为空 </p> <p>Then </p> <p>订单等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 第一次访问 </td> 
   <td colname="col2">查看最多访问一 [1] 次的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>访问次数等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非顾客 </td> 
   <td colname="col2">查看未参与订购事件的访客的数据。在篩選定義中，容器為「訪客」。 此篩選器使用排除邏輯。 规则为 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非单页面访问（非跳出） </td> 
   <td colname="col2">查看多次访问的访客的数据。在篩選定義中，容器為「訪客」。 此篩選器使用排除邏輯。 规则为 <p>单次访问不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付费搜索 </td> 
   <td colname="col2">查看源自付费搜索的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>付费搜索等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顾客 </td> 
   <td colname="col2">查看参与订购事件的访客的数据。在篩選定義中，容器為「訪客」。 规则为 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回访 </td> 
   <td colname="col2">查看至少访问一次的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>访问次数大于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 单页面访问量 </td> 
   <td colname="col2"> 查看包含某个页面值的访问数据，可以提交该次访问过程中的多个页面查看。包含退出連結事件的單頁造訪次數會納入篩選器中。 在「篩選器定義」中，容器為「造訪」。 规则为 <p>单个页面访问次数等于 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查看的产品未添加到购物车 </td> 
   <td colname="col2">查看浏览了产品但未添加到购物车的访客的数据。在「篩選器定義」中，容器為「造訪」。 此循序篩選器的規則為 <p>产品查看不为空 </p> <p>Then </p> <p> 购物车加货等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自促销活动的访问量 </td> 
   <td colname="col2">查看通过促销活动引荐的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>跟踪代码不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自移动设备的访问量 </td> 
   <td colname="col2">查看使用移动设备的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>移动设备不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自免费搜索的访问量 </td> 
   <td colname="col2">查看非源自付费搜索的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>付费搜索等于 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自非移动设备的访问量 </td> 
   <td colname="col2">查看非使用移动设备的访客的数据。在「篩選器定義」中，容器為「造訪」。 此篩選器使用排除邏輯。 规则为 <p>移动设备类型等于手机 </p> <p>或 </p> <p>移动设备类型等于平板电脑 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自手机的访问量 </td> 
   <td colname="col2">查看使用手机的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>设备类型等于手机。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自搜索引擎的访问量 </td> 
   <td colname="col2">查看通过搜索引擎引荐的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>反向链接类型等于搜索引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 社交网站访问量 </td> 
   <td colname="col2">查看通过社交网站反向链接的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>反向链接类型等于“社交网络”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自平板电脑的访问量 </td> 
   <td colname="col2">查看使用平板电脑的访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>设备类型等于平板电脑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用访客 ID Cookie 的访问量 </td> 
   <td colname="col2">查看需要永久性 Cookie 的网站上访客的数据。在「篩選器定義」中，容器為「造訪」。 规则为 <p>永久性 Cookie 等于 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>