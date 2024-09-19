---
description: 计算指标管理器提供了多种管理指标的方式，如共享、过滤、标记、批准、复制、删除和标记为收藏。
title: 计算指标管理器
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: e994a53934ae25802fb16e912d0fdee32d5ea524
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 12%

---

# 计算量度管理器

“计算量度”页面提供了许多种管理量度的方式，如共享、筛选、标记、批准、复制、删除和标记为收藏。

计算指标管理器会显示您拥有的所有过滤器以及与您共享的所有过滤器。 管理员级别的用户可以查看组织内的所有自定义指标。此概述介绍了计算指标管理器的用户界面和功能。

![显示可用筛选器的计算量度窗口。](assets/calc-metric-manager.png)

## 访问计算量度管理器

1. 在Customer Journey Analytics中，选择&#x200B;[!UICONTROL **组件**] > [!UICONTROL **计算量度**]。

## 计算量度管理器中的可用操作

在计算量度管理器中，您可以：

* [筛选计算量度](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [将计算量度标记为收藏内容](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [批准计算量度](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [标记计算量度](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [共享计算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* 将计算量度导出到CSV文件。

* [复制计算量度](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* 删除计算量度

## 配置列

通过配置显示的列，可以配置在计算量度管理器中为每个计算量度显示的信息。

要在计算量度管理器中配置可见列，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL 计算量度]**。

1. 在计算量度管理器中，选择&#x200B;**自定义列**&#x200B;图标![自定义列图标](assets/customize-columns-icon.png)，然后选择要显示在计算量度管理器中的列。

   以下列可供使用：

   | 列标题 | 描述 |
   |---|---|
   | 收藏 | 在每个计算量度旁边显示星形图标，以使您可将计算量度标记为收藏。 有关详细信息，请参阅[将计算量度标记为收藏](/help/components/calc-metrics/cm-workflow/cm-favorite.md)。 |
   | 标题和描述 | 这些值在计算量度生成器中提供。 要编辑标题和描述，请选择标题链接以打开计算指标生成器。 |
   | 报表包 | 指示指标上次保存在哪个报表包中。 |
   | 所有者 | 指示谁拥有该自定义指标。如果您不是管理员，则只能看到您拥有的指标或与您共享的指标。 |
   | 标记 | 显示应用到指标的标记，这些标记由您自己或与您共享计算指标的人添加。 |
   | 共享对象 | 列出您与之共享计算指标的个人或组（仅限管理员）或全部（仅限管理员）。 <p>共享计算指标时，计算指标名称旁边会显示一个共享图标。</p> |
   | 修改日期 | 指示上次修改自定义量度的日期。 |
   | 用在 | 显示当前使用计算量度的位置以及在每个区域中使用计算量度的次数。 <p>例如，如果计算量度在40个项目和2个警报中使用，则此列的值显示为&#x200B;[!UICONTROL **42个组件**]。 <p>选择此列中的值可查看在其中使用计算量度的细分(例如，[!UICONTROL **项目(40)**]、[!UICONTROL **移动记分卡(2)**])。 此外，您还可以查看正在使用计算量度的项目列表。 例如，要查看正在使用它们的项目的列表，请选择&#x200B;[!UICONTROL **项目(40)**]&#x200B;链接。</p><p>以下每个区域均显示该区域内正在使用的计算量度实例数：</p> <ul><li>[!UICONTROL **项目**]<p>包含[在计算量度生成器](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects)中创建并且可用于所有项目的计算量度。</p></li><li>[!UICONTROL **临时组件**]<p>包含[创建为快速计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)且仅在单个项目中可用的计算量度。</p></li><li>[!UICONTROL **计划项目**]</li><li>[!UICONTROL **移动记分卡**]</li><li>[!UICONTROL **批注**]</li><li>[!UICONTROL **Report Builder**]<p>选择此选项可下载包含以下数据列的CSV文件：</p><ul><li>Report Builder名称</li><li>上次访问</li><li>上次访问的IMS用户ID</li><li>上次访问的用户名</li></ul><p>在查看Report Builder信息时，使用情况信息自2024年9月起可用。</p></li></ul><p>此信息可帮助您确定组件是否对组织中的用户有用、组件的使用位置以及是否需要删除或修改它。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息仅供系统管理员使用。</li><li>默认情况下，[!UICONTROL **Used in**]&#x200B;列不显示。 [配置列](#configure-columns)以显示它。</li><li>如果某个计算量度在其定义中包含另一个计算量度，则该计算量度的任何使用均不会显示在&#x200B;[!UICONTROL **Used in**]&#x200B;列中。 如果计算度量包含在另一类型组件（如筛选器）的定义中，则使用情况显示在&#x200B;[!UICONTROL **Used in**]&#x200B;列中。</li><li>此信息不包括API或Data Warehouse的使用情况。</li><li>如果此列中没有给定组件的数据，但它具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，则表示该组件可能未保存便已在分析中使用。</li><li>使用情况信息从 2023 年 9 月开始提供。</li></ul><p>您可以将[数据字典](/help/components/data-dictionary/data-dictionary-overview.md)与此信息一起使用，以帮助您跟踪和更好地了解组织中如何使用组件。</p> |
   | 上次使用时间 | 显示计算指标上次在以下任意组件类型中使用的日期： <ul><li>计算量度</li><li>项目</li><li>计划项目</li></ul> <p>此信息可帮助您确定组件是否对组织中的用户有价值，或者是否应将其删除。</p><p>查看本列时请考虑以下事项：</p><ul><li>此信息不包括API、Report Builder或Data Warehouse的使用情况。</li><li>对于某些组件，如果上次在2023年9月之前使用该组件，则此列可能不包含数据。</li><li>此信息仅供系统管理员使用。</li></ul><p>您可以将[数据字典](/help/components/data-dictionary/data-dictionary-overview.md)与此信息一起使用，以帮助您跟踪和更好地了解组织中如何使用组件。 |

   {style="table-layout:auto"}
