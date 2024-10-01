---
title: 管理注释
description: 如何在工作区中管理注释。
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 19d2130f4fae736a8553c1a3dd573706d4fb8083
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 6%

---

# 管理注释

您可以从中心[!UICONTROL 注释]管理界面共享、筛选、标记、批准、复制、删除注释并将注释标记为收藏。 要管理注释，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 注释]**。


>[!NOTE]
>
>您在特定Workspace项目内创建的注释不会出现在[!UICONTROL 注释]管理器中，除非您使注释对所有项目都可用。
>

## 注释管理器

注释管理器具有以下界面元素：

![注释界面](assets/annotations-manager.png)

### 注释列表

注释列表会➊显示您拥有的所有注释、已覆盖到您的所有项目的注释以及与您共享的注释。 该列表具有以下列：

| 栏目 | 描述 |
| --- | --- | 
| ![星形大纲](/help/assets/icons/StarOutline.svg) | 选择支持![Star](/help/assets/icons/Star.svg)或取消支持![StarOutline](/help/assets/icons/StarOutline.svg)注释。 |
| **[!UICONTROL 标题和描述]** | 在 Annotation Builder 中提供。要编辑标题和描述，请选择标题链接 — 打开[注释生成器](/help/components/annotations/create-annotations.md#annotation-builder)。 共享批注以![共享](/help/assets/icons/ShareLight.svg)表示。 |
| **[!UICONTROL 数据视图]** | 此注释应用于的数据视图。 |
| **[!UICONTROL 所有者]** | 注释的所有者。 作为用户，您只会看到自己拥有的注释或与您共享的注释。 |
| **[!UICONTROL 应用的日期范围]** | 此注释应用于的日期或日期范围。 |
| **[!UICONTROL 标记]** | 此注释的标记。 |
| **[!UICONTROL 共享对象]** | 您与其共享注释的个人或组。 选择以打开&#x200B;**[!UICONTROL 共享组件]**&#x200B;对话框。 |
| **[!UICONTROL 修改日期]** | 显示上次修改注释的日期和时间。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要显示的列。

### 操作栏

您可以使用操作栏对注释进➋行操作。 操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![添加圆圈](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[Annotation Builder](create-annotations.md#annotation-builder)添加另一个注释。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 在列表中未选择批注时，使用此搜索字段搜索批注。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标签]** | 标记选定的注释。 在&#x200B;**[!UICONTROL 标记组件]**&#x200B;对话框中，选择或取消选择所选批注的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存选定批注的标记。 |
| ![共享](/help/assets/icons/ShareLight.svg) **[!UICONTROL 共享]** | 共享所选批注。 在&#x200B;**[!UICONTROL 共享组件]**&#x200B;对话框中，您可以![搜索](/help/assets/icons/Search.svg) *搜索个人或组*，也可以选择&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存所选批注的共享详细信息。 有关更多详细信息，请参阅[共享注释](#share-annotations)。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除所选注释。 系统会提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 重命名]** | 重命名单个选定的注释。 选中后，可以内联重命名注释。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 复制所选注释。 创建具有相同名称和后缀的新注释（复制） |
| ![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]** | 将注释导出到`Annotations List.csv`文件。 |

### 活动筛选栏

筛选器栏➌显示活动的筛选器（如果有）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速删除筛选器。 如果指定了多个筛选器，则可以使用&#x200B;**[!UICONTROL 删除所有]**&#x200B;来删除所有筛选器。

### 过滤器面板

您可以使用&#x200B;**[!UICONTROL 筛选器]**&#x200B;左侧面板筛选批注➍。 过滤器面板显示过滤器的类型和遵循过滤器的注释数。 选择![筛选器](/help/assets/icons/Filter.svg)以切换筛选器面板的显示。

要筛选筛选器列表，请执行以下操作：

1. 选择![筛选器](/help/assets/icons/Filter.svg)以打开筛选器面板。 如果筛选器列表需要更多空间，您可以再次选择![筛选器](/help/assets/icons/Filter.svg)以关闭面板。
1. 您可以使用任何可用的[过滤部分](#filter-sections)来过滤注释。

   >[!INFO]
   >
   >*项目*&#x200B;引用了[批注列表](manage-annotations.md#annotations-list)中显示的批注项目。
   > 

#### 筛选区域

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[注释列表](manage-annotations.md#annotations-list)会根据您的筛选器配置自动更新。 您可以在[活动筛选器栏](manage-annotations.md#active-filter-bar)中查看配置的筛选器。


## 编辑注释

可通过两种方式编辑注释：

* 在Workspace项目中，使用[组件信息](/help/components/use-components-in-workspace.md#component-info)图标。

* 在[[!UICONTROL 注释]列表](#annotations-list)中，选择注释的标题。

您使用[Annotation Builder](/help/components/annotations/create-annotations.md#annotation-builder)编辑注释。

## 共享注释

以下内容适用于共享注释或使用与您共享的注释：

* 在与其他用户共享的项目中，将为这些用户显示仅用于项目的注释。 用户无法编辑或删除这些仅用于项目的注释。
* 如果保存注释并直接与用户共享注释，则该用户只有在具有管理员权限的情况下才能编辑和删除注释。

* 如果某个项目与您共享，则该项目中创建的注释仅会显示在该项目中。 如果注释直接与您共享，则该注释会显示在可以显示该注释的所有项目中。

## 注释和时区

所有注释都使用时间戳创建，但没有小时或时区信息。 在报告时，将使用为面板配置的数据视图的时区。
