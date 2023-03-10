---
source-git-commit: 176816969032143750dcde64db223e73efd19165
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 75%

---
# 片段

## 发布的有限测试阶段 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能发布](/help/release-notes/releases.md)。

## 发布的有限测试阶段部分 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本部分描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能发布](/help/release-notes/releases.md)。

## 数据词典过滤条件 {#dd-filter-criteria}

1. （可选）选择&#x200B;**过滤**&#x200B;图标![，即“数据词典过滤”图标](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png)，然后选择以下任一过滤器选项过滤组件列表：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **已批准**] | 仅显示标记为由管理员批准的组件。 |
   | [!UICONTROL **收藏夹**] | 仅显示收藏夹列表中的组件。有关将组件添加到收藏夹列表的信息，请参阅[组件概览](/help/components/overview.md)。 |
   | [!UICONTROL **维度**] | 仅显示维度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **量度**] | 仅显示量度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **筛选器**] | 仅显示属于筛选器的组件。 （当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。）<!--this is Filters in CJA--> |
   | [!UICONTROL **日期范围**] | 仅显示日期范围的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **显示所有**] | 显示所有组件。此选项仅适用于管理员。 |
   | [!UICONTROL **未批准**] | 仅显示未标记为由管理员批准的组件。作为管理员，这有助于确定需要您审阅和批准的组件。此选项仅适用于管理员。 |
   | [!UICONTROL **缺少描述**] | 仅显示在“描述”字段中尚未描述的组件。此选项仅适用于管理员。 |
   | [!UICONTROL **显示重复项**] | 仅显示与所选报告包中的另一个组件具有相同标签或相同描述的组件。其中包括您创建的组件和 Adobe 提供的组件。标签或描述必须完全匹配才能显示为重复项。此选项仅适用于管理员。 |
   | [!UICONTROL **没有最近的数据**] | 仅显示在过去 90 天内未收集任何数据的组件。此选项仅适用于管理员。 |
   | [!UICONTROL **由 Adobe 创建**] <!-- I don't see this option--> | 仅显示由 Adobe 创建的组件。不会显示由管理员或您组织中的其他用户创建的组件。 |

   {style="table-layout:auto"}

## “数据词典”组件信息 {#dd-component-information}

| 选项 | 函数 |
|---------|----------|
| [!UICONTROL **已批准**] | <p>表示该组件已获管理员审阅和批准。</p><p>管理员会看到&#x200B;[!UICONTROL **取消批准**]&#x200B;选项。选择此选项会为用户将组件标记为“未批准”。</p> |
| [!UICONTROL **未批准**] | <p>表示该组件尚未获得管理员审阅和批准。</p><p>管理员会看到&#x200B;[!UICONTROL **批准**]&#x200B;选项。 选择此选项会为用户将组件标记为“已批准”。</p> |
| [!UICONTROL **描述**] | 描述组件的预期功能。（此信息由 Analytics 管理员添加，如[添加组件描述](/help/components/add-component-descriptions.md)中所述。） |
| [!UICONTROL **常常与以下组件一同使用**] | <p>显示最常与您正在查看的组件一起使用的组件。</p><p>最多可显示5种主要组件类型中的5种组件：量度、计算量度、Dimension、过滤器和日期范围。</p><p>此列表基于过去 90 天的数据。只列出您有权限查看的组件。</p><p>管理员可以策划用户在此部分中看到的组件，方法是在 [!UICONTROL **始终包括**] 和 [!UICONTROL **始终排除**] 下拉字段。 在组织用户看到的组件之前，请首先应用 **全部显示** 筛选以确保您看到的所有组件未与您共享，而这些组件可能已由其他管理员添加。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **如同**] | <p>显示与您正在查看的组件具有相似标签的组件。</p><p>最多可显示5种主要组件类型中的5种组件：量度、计算量度、Dimension、过滤器和日期范围。</p><p>只列出您有权限查看的组件。</p><p>报告包中的任何重复组件都将显示在此处。Analytics 管理员应识别并移除所有重复的组件，如[监视数据词典运行状况](/help/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理员可以策划用户在此部分中看到的组件，方法是在 [!UICONTROL **始终包括**] 和 [!UICONTROL **始终排除**] 下拉字段。 在组织用户看到的组件之前，请首先应用 **全部显示** 筛选以确保您看到的所有组件未与您共享，而这些组件可能已由其他管理员添加。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：** 目前， **类似于** 部分仅包含您创建的组件，而不包含Adobe提供的组件。 Adobe提供的组件将添加到未来版本中。</p> |
| [!UICONTROL **标记**] | 显示应用于组件的所有标记。具有管理员访问权限的用户可以在编辑组件时添加标记。 |
| [!UICONTROL **组件类型**] | 列出组件的类型，即Dimension、量度、过滤器或日期范围。 |
| [!UICONTROL **创建者**] | 显示创建组件的用户名称。 |
| [!UICONTROL **预览**] | 显示组件在 Analysis Workspace 中的外观预览。 |
| [!UICONTROL **上次修改日期**] | 显示上次修改组件的日期。查看过滤器、量度、计算量度和日期范围时，将显示此部分。 |

{style="table-layout:auto"}