---
title: 管理过滤器
description: 了解如何管理Customer Journey Analytics中的筛选器
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# 管理过滤器


您可以从中央的[!UICONTROL 筛选器]管理界面[共享](filters-share.md)、[筛选器](filters-filter.md)、[标记](filters-tag.md)、[批准](filters-approve.md)、重命名、[复制](filters-copy.md)、删除、导出筛选器并将筛选器标记为[收藏](filters-favorite.md)。 要管理过滤器，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 筛选器]**。


>[!NOTE]
>
>您在特定Workspace项目中创建的快速筛选器不会出现在[!UICONTROL 筛选器]管理器中，除非您将该筛选器设置为对所有项目都可用。
>

## 筛选器管理器

过滤器管理器具有以下界面元素：

![筛选器接口](assets/filters-manager.png)

### 过滤器列表

过滤器列表会➊显示您拥有的所有过滤器、已设定到您所有项目的范围以及已与您共享的过滤器。 该列表具有以下列：

| 栏目 | 描述 |
| --- | --- | 
| ![星形大纲](/help/assets/icons/StarOutline.svg) | 选择支持![星型](/help/assets/icons/Star.svg)或取消支持![星型大纲](/help/assets/icons/StarOutline.svg)筛选器。 查看[将筛选器标记为收藏](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL 标题和描述]** | 要编辑筛选器，请选择标题链接，这将打开[筛选器生成器](filter-builder.md)。 通过![共享](/help/assets/icons/ShareAlt.svg)指示共享筛选器。 |
| **[!UICONTROL 数据视图]** | 此过滤器应用于的数据视图。 |
| **[!UICONTROL 所有者]** | 筛选器的所有者。 作为用户，您只会看到自己拥有的过滤器或与您共享的注释。 |
| **[!UICONTROL 标记]** | 此过滤器的标记。 |
| **[!UICONTROL 共享对象]** | 您与多少个人或组共享该过滤器。 选择以打开&#x200B;**[!UICONTROL 共享组件]**&#x200B;对话框。 有关详细信息，请参阅[共享筛选器](filters-share.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改过滤器的日期和时间。 |
| **[!UICONTROL 用于]** | 显示过滤器当前的使用位置以及在每个区域中使用过滤器的次数。 <p>例如，如果筛选器在40个项目和2个警报中使用，则此列的值显示为&#x200B;[!UICONTROL **42个组件**]。</p> <p>选择此列中的值可查看使用过滤器的位置的细分(例如，[!UICONTROL **项目(40)**]，[!UICONTROL **移动记分卡(2)**])。 此外，您还可以查看正在使用筛选器的项目列表。 例如，查看正在使用它们的项目的列表，选择&#x200B;[!UICONTROL **项目(40)**]&#x200B;链接。</p><p>以下每个区域均显示了该区域中正在使用的过滤器实例数：</p>  <ul><li>[!UICONTROL **项目**]<p>包含已在筛选器生成器](/help/components/filters/filter-builder.md#)中创建[且可用于所有项目的筛选器。</p></li><li>[!UICONTROL **临时组件**]<p>包含已[创建为快速筛选器](/help/components/filters/quick-filters.md)的筛选器，并且仅在单个项目中可用。</p></li><li>[!UICONTROL **计划项目**]</li><li>[!UICONTROL **移动记分卡**]</li><li>[!UICONTROL **批注**]</li><li>[!UICONTROL **计算量度**]</li><li>[!UICONTROL **Report Builder**]<p>选择此选项可下载包含以下数据列的CSV文件：</p><ul><li>Report Builder名称</li><li>上次访问</li><li>上次访问的IMS用户ID</li><li>上次访问的用户名</li></ul></li></ul><p>此信息可帮助您确定组件是否对贵组织中的用户有用、组件的使用位置以及是否需要删除或修改组件。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息仅供系统管理员使用。</li><li>默认情况下，[!UICONTROL **Used in**]&#x200B;列不显示。 使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)配置此列的显示。</li><li>此信息不包括API或Data Warehouse的使用情况。</li><li>如果此列中没有给定组件的数据，但该组件具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，则表示该组件可能未保存便已在分析中使用。</li><li>使用情况信息从 2023 年 9 月开始提供。</li></ul><p>您可以将[数据字典](/help/components/data-dictionary/data-dictionary-overview.md)与此信息一起使用，以帮助您跟踪和更好地了解组织中如何使用组件。</p> |
| **[!UICONTROL 上次使用]** | 上次使用该过滤器的时间。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要显示的列。

### 操作栏

您可以使用操作栏对筛选器执行操➋作。 操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![添加圆圈](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[筛选器生成器](filter-builder.md)添加另一个筛选器。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 在列表中未选择筛选器时，使用此搜索字段搜索筛选器。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标签]** | 标记所选过滤器。 在&#x200B;**[!UICONTROL 标记筛选器]**&#x200B;对话框中，选择或取消选择所选筛选器的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选筛选器的标记。 有关详细信息，请参阅[标记筛选器](/help/components/filters/filters-tag.md)。 |
| ![共享](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共享]** | 共享所选的过滤器。 在&#x200B;**[!UICONTROL 共享筛选器]**&#x200B;对话框中，您可以![搜索](/help/assets/icons/Search.svg) *搜索个人或组*，也可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选筛选器的共享详细信息。 有关详细信息，请参阅[共享筛选器](filters-share.md)。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除所选的过滤器。 系统会提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 重命名]** | 重命名单个选定的筛选器。 选中后，可以内联重命名筛选器。 |
| ![复选标记Circle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 批准]** | 批准所选过滤器。 有关详细信息，请参阅[批准筛选器](filters-approve.md)。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 复制所选过滤器。 已创建具有相同名称和后缀`(Copy)`的新筛选器。 |
| ![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]** | 将筛选器导出到`Filters List.csv`文件。 |

### 活动筛选栏

筛选器栏➌显示从筛选器面板应用于筛选器列表（如果有）的活动筛选器。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速删除筛选器。 如果指定了多个筛选器，则可以使用&#x200B;**[!UICONTROL 删除所有]**&#x200B;来删除所有筛选器。

### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板筛选筛选器➍列表。 过滤器面板显示过滤器的类型和遵循特定过滤器的过滤器数量。 选择![筛选器](/help/assets/icons/Filter.svg)以切换筛选器面板的显示。

有关详细信息，请参阅[筛选筛选器列表](filters-filter.md)。
