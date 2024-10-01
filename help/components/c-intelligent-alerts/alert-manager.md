---
description: 创建、编辑或删除警报。
title: 管理警报
feature: Workspace Basics
role: User, Admin
source-git-commit: bd58af0680fc9524453e072ecb60e3ada72ce634
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 4%

---

# 管理警报


您可以从集中[!UICONTROL 警报]管理界面筛选、标记、删除、重命名、复制、启用、禁用续订和导出警报。 要管理警报，请执行以下操作：

* 在主界面中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 警报]**。

警报管理器的结构非常类似于[筛选器管理器](/help/components/filters/manage-filters.md)和[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)。


## 警报管理器

警报管理器具有以下界面元素：

![筛选器接口](assets/alerts-manager.png)

### 警报列表

警报列表会➊显示您拥有的所有警报、已覆盖到您所有项目的警报以及与您共享的警报。 该列表具有以下列：

| 栏目 | 描述 |
|---|---|
| ![星形大纲](/help/assets/icons/StarOutline.svg) | 选择支持![Star](/help/assets/icons/Star.svg)或取消支持![StarOutline](/help/assets/icons/StarOutline.svg)警报。 |
| **[!UICONTROL 标题和描述]** | 要编辑警报，请选择标题链接，这将打开[警报生成器](alert-builder.md#alert-builder)。 |
| **[!UICONTROL 类型]** | 显示警报是Customer Journey Analytics数据警报还是Server call usage警报。 |
| **[!UICONTROL 已启用]** | 指示警报是启用还是禁用。 |
| **[!UICONTROL 数据视图]** | 此警报应用于的数据视图。 |
| **[!UICONTROL 所有者]** | 警报的所有者。 如果您不是管理员，则只能看到您拥有的警报或与您共享的警报。 |
| **[!UICONTROL 标记]** | 此警报的标记。 |
| **[!UICONTROL 到期日期]** | 警报设置为到期的日期和时间。 |
| **[!UICONTROL 修改日期]** | 上次修改警报的日期和时间。 |

<!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要显示的列。

### 操作栏

您可以使用操作栏➋对警报执行操作。 操作栏包含以下操作：

| 操作 | 描述 |
|---|---|
| ![添加圆圈](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]** | 使用[警报生成器](alert-builder.md#alert-builder)添加另一个警报。 |
| ![搜索](/help/assets/icons/Search.svg) [!UICONTROL *按标题搜索*] | 在列表中未选择警报时，使用此搜索字段搜索警报。 |
| ![标签](/help/assets/icons/Label.svg) **[!UICONTROL 标签]** | 标记所选警报。 在&#x200B;**[!UICONTROL 标记警报]**&#x200B;对话框中，选择或取消选择所选警报的标记。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存选定警报的标记。 |
| ![删除](/help/assets/icons/Delete.svg) **[!UICONTROL 删除]** | 删除所选警报。 系统会提示您进行确认。 |
| ![编辑](/help/assets/icons/Edit.svg)**[!UICONTROL 重命名]** | 重命名单个选定警报。 选中后，可以内联重命名警报。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 复制所选警报。 创建的新警报具有相同的名称和后缀`(Copy)`。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 启用]**&#x200B;或&#x200B;**[!UICONTROL 禁用]** | 启用或禁用所选警报。 |
| ![刷新](/help/assets/icons/Refresh.svg) **[!UICONTROL 续订]** | 更新警报到期日期。 过期日期从选择此选项之日起延长1年，与原始过期日期无关。 |
| ![文件CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 导出到CSV]** | 将警报导出到`Alerts List.csv`文件。 |


### 活动筛选栏

过滤器栏➌显示从过滤器面板应用于警报列表（如果有）的活动过滤器。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速删除筛选器。 如果指定了多个筛选器，则可以使用&#x200B;**[!UICONTROL 删除所有]**&#x200B;来删除所有筛选器。


### 过滤器面板

您可以使用![筛选器](/help/assets/icons/Filter.svg) **[!UICONTROL 筛选器]**&#x200B;左侧面板筛选警报列表➍。 过滤器面板显示过滤器的类型和遵循特定过滤器的警报数。

{{filterspanel}}


#### 标记过滤器部分

{{tagfiltersection}}


#### 数据视图过滤器部分

{{dataviewfiltersection}}


#### “所有者”过滤器部分

{{ownerfiltersection}}


#### 已启用状态筛选器部分

{{enabledstatusfiltersection}}


#### 键入筛选器部分

{{typefiltersection}}


#### 其他筛选器筛选器部分

{{otherfiltersfiltersection}}



## 编辑警报

您可以编辑警报

* 在[[!UICONTROL 警报]列表](#alerts-list)中，选择警报的标题。

您使用[警报生成器](alert-builder.md#alert-builder)编辑警报。

## 警报疑难解答

对警报问题进行故障诊断时，请提供JID（作业实例ID）编号以Adobe支持。 JID号位于您收到的警报电子邮件通知的底部。

![通知电子邮件](assets/alerts-email.PNG)
