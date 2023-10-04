---
title: 筛选器管理器
description: 了解如何管理 Customer Journey Analytics 中的过滤器
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 27%

---

# 筛选器管理器

过滤器管理器提供了许多种管理过滤器的方式，如共享、标记、批准、复制、删除和标记为收藏。

过滤器管理器会显示您拥有的所有过滤器以及与您共享的所有过滤器。 管理员级别的用户可以查看组织内的所有过滤器。此概述介绍了过滤器管理器的用户界面和功能。

![](assets/filter-manager-ui.png)

## 访问过滤器管理器

1. 在Customer Journey Analytics中，选择 **[!UICONTROL 组件]** 选项卡，然后选择 **[!UICONTROL 过滤器]**.

## 筛选器管理器中的可用操作

在过滤器管理器中，您可以：

* [筛选筛选器列表](/help/components/filters/filters-filter.md)

* [将过滤器标记为收藏](/help/components/filters/filters-favorite.md)

* [批准过滤器](/help/components/filters/filters-approve.md)

* [标记过滤器](/help/components/filters/filters-tag.md)

* [共享过滤器](/help/components/filters/filters-share.md)

* 将过滤器导出到CSV文件。

* [复制筛选器](/help/components/filters/filters-copy.md)

* 删除筛选器

## 配置列

通过配置显示的列，可以配置过滤器管理器中为每个过滤器显示的信息。

要在过滤器管理器中配置可见列，请执行以下操作：

1. 在Customer Journey Analytics中，选择 **[!UICONTROL 组件]** 选项卡，然后选择 **[!UICONTROL 文件管理器]**.

1. 在过滤器管理器中，选择 **自定义列** 图标 ![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在过滤器管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 标题和描述 | 这些值在筛选器生成器中提供。 要编辑标题和描述，请选择标题链接以打开过滤器生成器。 |
   | 收藏 | 在每个筛选器旁边显示星形图标，以使您可以将筛选器标记为收藏。 有关更多信息，请参阅 [将过滤器标记为收藏](/help/components/filters/filters-favorite.md). |
   | 数据视图 | 此列指示上次将过滤器保存到的数据视图。 |
   | 所有者 | 指示过滤器的所有者。如果您不是管理员，则只能看到您拥有的过滤器或与您共享的过滤器。 |
   | 标记（在列选择器中未选择，因此列不显示） | 应用到过滤器的标记，这些标记由您自己或与您共享该过滤器的人添加。 |
   | 共享对象 | 列出您与其共享该过滤器的个人或组（仅限管理员）或所有人（仅限管理员）。 <p>当您或与您共享某个过滤器时，该过滤器名称旁边会显示一个共享图标。</p> |
   | 修改日期 | 显示上次修改过滤器的日期。 |
   | 用在 | 显示过滤器当前使用的组件数。 <p>例如，如果过滤器在40个项目和2个警报中使用，则此列的值显示为 [!UICONTROL **42个组件**].</p> <p>选择此列中的值可查看在其中使用该过滤器的划分(例如， [!UICONTROL **项目(40)**]， [!UICONTROL **警报(2)**])。</p><p>过滤器可用于以下任何组件类型：</p> <ul><li>计算量度</li><li>项目</li><li>计划项目</li></ul><p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。</p><p>此信息不包括API、Report Builder或Data Warehouse的使用情况。</p><p>您可以使用 [数据字典](/help/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。</p><p>此 [!UICONTROL **使用位置**] 默认情况下不显示列。 [配置列](#configure-columns) 以显示。</p> |
   | 上次使用时间 | 显示上次在以下任意组件类型中使用过滤器的日期： <ul><li>计算量度</li><li>项目</li><li>计划项目</li><li>过滤器</li></ul> <p>此信息可帮助您确定组件是否对组织中的用户有价值，或者是否应将其删除。</p><p>此信息不包括API或Report Builder的使用情况。</p><p>您可以使用 [数据字典](/help/components/data-dictionary/data-dictionary-overview.md) 以及此信息，以帮助您跟踪并更好地了解组织中如何使用组件。 |

   {style="table-layout:auto"}
