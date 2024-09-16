---
description: 创建、编辑或删除警报。
title: 警报管理器 (Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 640624ab017d8fc0e7b942c2f00c71cf255c4296
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 7%

---

# 管理警报

您可以在警报管理器中管理现有警报。 您可以对警报执行各种管理任务，如标记、重命名、删除等。

警报管理器的结构非常类似于[筛选器管理器](/help/components/filters/manage-filters.md)和[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)。

## 创建警报

要从警报管理器创建警报，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 警报]**&#x200B;以访问Customer Journey Analytics中的警报管理器。

   ![](assets/alert-manager.png)

1. 选择&#x200B;[!UICONTROL **添加**]（如果没有任何现有警报，则选择&#x200B;[!UICONTROL **新建警报**]）。

1. 继续[创建警报](/help/components/c-intelligent-alerts/alert-builder.md)，了解有关创建警报的更多详细信息。

## 管理现有警报

要在警报管理器中管理现有警报，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 警报]**&#x200B;以访问Customer Journey Analytics中的警报管理器。

   ![](assets/alert-manager.png)

1. 选择要管理的一个或多个警报。

   ![](assets/alert-manager-tasks.png)

1. 在操作栏中，选择以下任一选项：

   | 操作 | 功能 |
   |---------|----------|
   | [!UICONTROL **标记**] | 将标记应用于警报。 这有助于您组织警报以方便使用。 |
   | [!UICONTROL **删除**] | 删除警报。 |
   | [!UICONTROL **重命名**] | 重命名警报。 |
   | [!UICONTROL **批准**] | 将警报标记为已批准。 |
   | [!UICONTROL **Copy**] | 创建警报的副本（重复）。 |
   | [!UICONTROL **禁用**] | 禁用当前启用的警报。 |
   | [!UICONTROL **启用**] | 启用当前已禁用的警报。 |
   | [!UICONTROL **续订**] | 更新警报到期日期。 这会将过期日期延长一年的时间（从选择此选项之日算起，而不考虑原始过期日期）。 |
   | [!UICONTROL **导出到 CSV**] | 将警报导出到.CSV文件。 |

## 编辑警报

要编辑现有警报，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 警报]**&#x200B;以访问Adobe Analytics中的警报管理器。

   ![](assets/alert-manager.png)

1. 在&#x200B;[!UICONTROL **标题和描述**]&#x200B;列中选择警报名称。

1. 根据需要编辑警报。

   以下是编辑警报时可以执行的一些操作：

   * 将警报添加到其他报表包
   * 更改所有者
   * 更新过滤器
   * 更新到期日期

1. 编辑警报，然后选择&#x200B;[!UICONTROL **保存**]。

## 配置列

通过配置显示的列，可以配置在“警报管理器”中为每个警报显示的信息。

要在警报管理器中配置可见列，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL 警报]**。

1. 在警报管理器中，选择&#x200B;**自定义列**&#x200B;图标![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在警报管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 标题和描述 | 这些值在警报生成器中提供。 要编辑标题和描述，请选择标题链接以打开警报生成器。 |
   | 收藏 | 在每个警报旁边显示星形图标，允许您将警报标记为收藏。<!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | 类型 | 显示警报是Analytics数据警报还是服务器调用使用情况警报。 |
   | 已启用 | 显示警报当前是启用还是禁用。 |
   | 报表包 | 指示警报上次保存在哪个报表包中。 |
   | 所有者 | 指示警报的所有者。 如果您不是管理员，则只能看到您拥有的警报或与您共享的警报。 |
   | 标记 | 显示应用到警报的标记，这些标记由您自己或与您共享该警报的人添加。 |
   | 过期日期 | 显示警报设置为到期的日期和时间。 |
   | 修改日期 | 指示上次修改警报的日期。 |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->

## 警报疑难解答

对警报问题进行故障诊断时，请提供JID（作业实例ID）编号以Adobe支持。 JID号位于您收到的警报电子邮件通知的底部。

![通知电子邮件](assets/alerts-email.PNG)