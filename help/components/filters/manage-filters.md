---
title: 管理区段
description: 了解如何在Customer Journey Analytics中管理区段
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 33%

---

# 管理区段


您可以从中央的[!UICONTROL 区段]管理界面[共享](filters-share.md)、[区段](filters-filter.md)、[标记](filters-tag.md)、[批准](filters-approve.md)、重命名、[复制](filters-copy.md)、删除、导出区段并将区段标记为[收藏](filters-favorite.md)。 要管理区段，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 区段]**。


>[!NOTE]
>
>您在特定Workspace项目中所创建的快速区段不会显示在[!UICONTROL 区段]管理器中，除非您已将区段设置为对所有项目都可用。
>

## 区段管理器

区段管理器具有以下界面元素：

![区段接口](assets/filters-manager.png)

### 区段列表

区段列表会➊显示您拥有的所有区段、已覆盖到您的所有项目的区段以及与您共享的区段。 该列表具有以下各列：

| 列 | 描述 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 选择支持![星形](/help/assets/icons/Star.svg)或取消支持![星形轮廓](/help/assets/icons/StarOutline.svg)区段。 查看[将区段标记为收藏](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL 标题和描述]** | 要编辑区段，请选择标题链接，这会打开[区段生成器](filter-builder.md)。 共享区段以![共享](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 数据视图]** | 此区段应用于的数据视图。 |
| **[!UICONTROL 所有者]** | 区段的所有者。 作为用户，您只能看到自己拥有的区段或与您共享的注释。 |
| **[!UICONTROL 标记]** | 此区段的标记。 |
| **[!UICONTROL 共享对象]** | 您与多少个人或组共享了区段。 选择以打开&#x200B;**[!UICONTROL 分享组件]**&#x200B;对话框。有关详细信息，请参阅[共享区段](filters-share.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改区段的日期和时间。 |
| **[!UICONTROL 用在]** | 显示区段当前的使用位置以及在每个区域中使用它们的次数。 <p>例如，如果该区段在40个项目和2个警报中使用，则此列的值显示为&#x200B;[!UICONTROL **42个组件**]。</p> <p>选择此列中的值可查看使用区段的细分(例如，[!UICONTROL **项目(40)**]、[!UICONTROL **移动记分卡(2)**])。 此外，您还可以查看正在使用区段的项目列表。 例如，要查看正在使用它们的项目列表，请选择&#x200B;[!UICONTROL **项目（40）**]&#x200B;链接。</p><p>以下每个区域均显示了该区域中正在使用的区段实例数：</p>  <ul><li>[!UICONTROL **项目**]<p>包含[在区段生成器](/help/components/filters/filter-builder.md#)中创建并且可用于所有项目的区段。</p></li><li>[!UICONTROL **临时组件**]<p>包含[创建为快速区段](/help/components/filters/quick-filters.md)的区段，并且仅在单个项目中可用。</p></li><li>[!UICONTROL **计划项目**]</li><li>[!UICONTROL **移动记分卡**]</li><li>[!UICONTROL **注释**]</li><li>[!UICONTROL **计算量度**]</li><li>[!UICONTROL **Report Builder**]<p>选择此选项会下载包含以下列数据的 CSV 文件：</p><ul><li>Report Builder 名称</li><li>上次访问时间</li><li>上次访问的 IMS 用户 ID</li><li>上次访问的用户名称</li></ul></li></ul><p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息仅供系统管理员使用。</li><li>默认情况下，[!UICONTROL **用于**]&#x200B;列不显示。使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 来配置此列的显示。</li><li>此信息不包括 API 或 Data Warehouse 的使用情况。</li><li>如果此列中没有给定组件的数据，但该组件具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，则该组件可能已在分析中使用但尚未保存。</li><li>使用情况信息从 2023 年 9 月开始提供。</li></ul><p>可以结合[数据字典](/help/components/data-dictionary/data-dictionary-overview.md)和这些信息，帮助您跟踪并更好地了解组织中组件的使用情况。</p> |
| **[!UICONTROL 上次使用]** | 区段的上次使用时间。 |

使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 指定您想要显示的列。

### 操作栏

您可以使用操作栏➋对区段执行操作。 该操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[区段生成器](filter-builder.md)添加另一个区段。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 在列表中未选择区段时，使用此搜索字段搜索区段。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标记]** | 标记选定的区段。 在&#x200B;**[!UICONTROL 标记区段]**&#x200B;对话框中，选择或取消选择选定区段的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选区段的标记。 有关详细信息，请参阅[标记区段](/help/components/filters/filters-tag.md)。 |
| ![共享](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共享]** | 共享选定的区段。 在&#x200B;**[!UICONTROL 共享区段]**&#x200B;对话框中，您可以![搜索](/help/assets/icons/Search.svg) *搜索个人或组*，也可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选区段的共享详细信息。 有关详细信息，请参阅[共享区段](filters-share.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除选定的区段。 系统将提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 重命名]** | 重命名单个选定的区段。 选中后，可以内联重命名区段。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 批准]** | 批准选定的区段。 有关详细信息，请参阅[批准区段](filters-approve.md)。 |
| ![复制](/help/assets/icons/Copy.svg)  **[!UICONTROL 复制]** | 复制选定的区段。 已创建具有相同名称和后缀`(Copy)`的新区段。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出为 CSV]** | 将区段导出到`Segments List.csv`文件。 |

### 活动过滤器栏

过滤器栏➌显示从过滤器面板应用于区段列表（如果有）的活动区段。 您可以使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 快速移除过滤器。如果指定了多个筛选器，则可以使用&#x200B;**[!UICONTROL 删除所有]**&#x200B;来删除所有筛选器。

### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板筛选区段列表➍。 过滤器面板显示过滤器的类型和遵循特定过滤器的区段数。 选择![筛选器](/help/assets/icons/Filter.svg)切换筛选器面板的显示。

有关详细信息，请参阅[筛选区段列表](filters-filter.md)。
