---
description: 在 Analysis Workspace for Customer Journey Analytics 中使用快速过滤器。
title: 快速过滤器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 41%

---

# 快速过滤器

快速篩選器可讓您輕鬆探索指定專案中的資料，而不需在中建立更複雜的元件清單篩選器。 [篩選產生器](/help/components/filters/create-filters.md).

建立快速篩選時，請考量下列事項：

* 快速篩選只適用於建立所在的專案。 此类过滤器在其他项目中不可用，无法共享给其他用户。 
* 最多允許3個規則。
* 不支援巢狀容器或循序規則。

以下影片示範如何使用快速濾鏡。 (注意：本影片使用「快速區段」一詞而非「快速篩選」。 不過，功能是相同的。)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 创建快速过滤器 {#create}

Analysis Workspace中的任何使用者都可以建立快速篩選。

若要建立快速篩選：

1. 選擇下列其中一個方法，開始建立快速篩選：

   * **臨機（拖放）：** 從左側邊欄中，將元件拖曳至 **篩選** 圖示中，然後選取 **編輯** 圖示可調整篩選器。

      ![編輯臨時篩選](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > 建立快速篩選隨選（拖放）時，請考量下列事項：
      > * 不支援下列元件型別：計算量度和維度，以及無法建立篩選器的量度。
      > * 為了取得完整的維度和事件，Analysis Workspace會建立「存在」事件篩選器。 示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
      > * 如果将“未指定”或“无”拖入过滤器放置区域，则它自动转换为“不存在”过滤器，以使其在筛选时受到正确对待。



   * **使用篩選圖示：** 在自由格式表格中，選取 **篩選** 圖示來識別。

      ![区段过滤器](assets/quick-seg1.png)

1. 調整下列任一設定：

   | 设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 名称] | 过滤器的默认名称为该过滤器中的规则名称的组合。 可以将过滤器重命名为更友好的名称。 |
   | [!UICONTROL 包括/排除] | 可在过滤器定义中包括或排除组件，但不得既包括又排除。 |
   | [!UICONTROL “点击”/“访问”/“访客”容器] | 快速过滤器仅包括一个[过滤器容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，从中可在过滤器中包括（或从过滤器中排除）某个维度/指标/日期范围。[!UICONTROL 访客]包含访客在不同的访问和页面查看间专属的总体数据。 通过[!UICONTROL 访问]容器可设置规则，允许您根据访问划分访客的数据，而通过[!UICONTROL 点击]容器可根据个别页面查看划分访客信息。默认容器为[!UICONTROL 点击]。 |
   | [!UICONTROL 组件]（维度/量度/日期范围） | 通过添加组件（维度、量度、日期范围或维度值）可定义最多 3 条规则。有 3 种方法可以找到正确的组件：<ul><li>開始輸入，然後快速篩選產生器就會自動找到合適的元件。</li><li>使用下拉列表查找组件。</li><li>从左边栏中拖放组件。</li></ul> |
   | [!UICONTROL 运算符] | 使用下拉菜单查找标准运算符和[!UICONTROL 非重复计数]运算符。请参阅[过滤器运算符](operators.md)。 |
   | 加号 (+) | 添加另一条规则。 |
   | AND/OR 限定符 | 可将“AND”或“OR”限定符添加到规则，但不得在单个过滤器定义中混用“AND”和“OR”。 |
   | [!UICONTROL 应用] | 将此过滤器应用于面板。如果篩選不包含任何資料，系統會詢問您是否要繼續。 |
   | [!UICONTROL 打开生成器] | 打开过滤器生成器。 在篩選產生器中儲存或套用篩選後，將無法再考慮「快速篩選」。 它成为组件列表过滤器库的一部分。 <p>若要讓元件可在您的所有專案中和左側欄中使用，請選取選項 [!UICONTROL **將此篩選器設為可用於所有專案，並將其新增至您的元件清單**].</p><p>如需詳細資訊，請參閱區段 [將快速篩選儲存為元件清單篩選](#save-a-quick-filter-as-a-component-list-filter) 本文章內容。</p><p>**注意：** 僅限在中擁有篩選器建立許可權的使用者。 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools?lang=zh-Hans) 可以開啟「篩選產生器」。</p> |
   | [!UICONTROL 取消] | 取消此快速篩選（不要套用它）。 |
   | [!UICONTROL 日期范围] | 该验证器使用面板日期范围执行其数据查找。但在快速过滤器中应用的任何日期范围都将取代面板顶部的面板日期范围。 |
   | 预览（右上角） | 让您查看您的过滤器是否有效以及该过滤器的作用范围。 代表您套用此篩選器時可預期看到的資料集劃分。 您可能会收到一条通知，表明此过滤器没有数据。在这种情况下，可继续操作或更改过滤器定义。 |

1. 選取 [!UICONTROL **套用**] 以儲存變更。

## 編輯快速篩選 {#edit}

1. 暫留在您要編輯的快速篩選上，然後選取 **編輯** 圖示。

   ![編輯臨時篩選](assets/filter-adhoc-edit.png)

1. 编辑过滤器定义或过滤器名称。
1. 選取 [!UICONTROL **套用**] 以儲存變更。

## 將快速篩選儲存為元件清單篩選 {#save}

>[!IMPORTANT]
>
> 儲存快速篩選時，請考量下列事項：
> 
> * 若要儲存快速篩選，您需要 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools?lang=zh-Hans).
> 
> * 儲存或套用篩選後，無法在快速篩選產生器中編輯它。 您必須改用一般篩選產生器。


您可以選擇將快速篩選儲存為元件清單篩選。 元件清單篩選器的優點包括：

* 所有Workspace專案的可用性
* 支援更複雜的篩選器以及循序篩選器

您可以從快速篩選產生器或儲存篩選 [!UICONTROL 篩選產生器].

### 儲存在快速篩選產生器中 {#save2}

1. 套用快速篩選後，將滑鼠懸停在其上並選取資訊(「i」)圖示。
1. 選取 **[!UICONTROL 使其可用於所有專案並新增至您的元件清單]**.
1. （可选）为过滤器重命名。
1. 选择&#x200B;**[!UICONTROL 保存]**。

   此篩選器現在會顯示在左側欄的元件清單中。 另請注意，篩選器的側邊欄會從淺藍色變更為深藍色，這表示在快速篩選產生器中無法再編輯或開啟它。

### 儲存在篩選產生器中 {#save3}

1. 套用快速篩選後，將滑鼠懸停在其上並選取資訊(「i」)圖示。
1. 选择&#x200B;**[!UICONTROL 保存过滤器]**
1. （可選）重新命名篩選器，然後選取 [!UICONTROL **套用**].

   返回「工作區」，並注意篩選器的側邊欄會從淺藍色變更為深藍色，表示不能再在快速篩選產生器中編輯或開啟它。 通过保存它，它就成为组件列表的一部分。

   ![过滤器组件列表](assets/quick-seg4.png)

套用篩選後，您可以選擇將其新增至篩選元件清單，並使其可用於所有專案。

1. 将光标悬停在保存的过滤器上并选择铅笔图标。

1. 選取 [!UICONTROL **開啟產生器**].

1. 在过滤器生成器的顶部，注意此对话框：

   ![过滤器对话框](assets/project-only-filter-dialog.png)

1. 選取旁邊的核取方塊 **[!UICONTROL 將此篩選器設為可用於所有專案，並將其新增至您的元件清單。]**

1. 选择&#x200B;**[!UICONTROL 保存]**。

   所有项目的过滤器组件列表中现在都显示该过滤器。还可与组织中的其他人员[共享该过滤器](/help/components/filters/manage-filters.md)。

## 快速篩選範例

下列篩選範例結合了維度和量度：

![过滤器定义示例](assets/quick-seg2.png)

