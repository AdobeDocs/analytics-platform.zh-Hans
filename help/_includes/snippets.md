---
source-git-commit: 901ddcd814c71504ff056d91fd25445d94a6f56e
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 70%

---
# 片段

## 发布的有限测试阶段 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。如需Customer Journey Analytics發行程式的相關資訊，請參閱 [Customer Journey Analytics功能發行](/help/release-notes/releases.md).

## 发布的有限测试阶段部分 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本部分描述的功能处于发布的有限测试阶段，因此可能在您的环境中尚不可用。当该功能正式发布时，将删除此说明。如需Customer Journey Analytics發行程式的相關資訊，請參閱 [Customer Journey Analytics功能發行](/help/release-notes/releases.md).

## 数据词典过滤条件 {#dd-filter-criteria}

1. （可选）选择&#x200B;**过滤**&#x200B;图标![，即“数据词典过滤”图标](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然后选择以下任一过滤器选项过滤组件列表：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **已批准**] | 仅显示标记为由管理员批准的组件。 |
   | [!UICONTROL **收藏夹**] | 仅显示收藏夹列表中的组件。有关将组件添加到收藏夹列表的信息，请参阅[组件概览](/help/components/overview.md)。 |
   | [!UICONTROL **维度**] | 仅显示维度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **量度**] | 仅显示量度的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **筛选器**] | 僅顯示屬於篩選器的元件。 （当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。）<!--this is Filters in CJA--> |
   | [!UICONTROL **日期范围**] | 仅显示日期范围的组件。（当您首次访问数据词典时，此选项也可在&#x200B;[!UICONTROL **快速过滤**]&#x200B;选项卡中使用。） |
   | [!UICONTROL **显示所有**] | 显示所有组件。仅管理员有此选项可用。 |
   | [!UICONTROL **未批准**] | 仅显示未标记为由管理员批准的组件。作为管理员，这有助于确定需要您审阅和批准的组件。仅管理员有此选项可用。 |
   | [!UICONTROL **缺少描述**] | 仅显示在“描述”字段中尚未描述的组件。仅管理员有此选项可用。 |
   | [!UICONTROL **显示重复项**] | 僅顯示與所選資料檢視中其他元件具有相同名稱或相同說明的元件。 其中包括您创建的组件和 Adobe 提供的组件。名稱或說明必須完全相符，才能顯示為重複專案。 此选项仅适用于管理员。 |
   | [!UICONTROL **没有最近的数据**] | 仅显示在过去 90 天内未收集任何数据的组件。仅管理员有此选项可用。 |
   | [!UICONTROL **由 Adobe 创建**] <!-- I don't see this option--> | 仅显示由 Adobe 创建的组件。不会显示由管理员或您组织中的其他用户创建的组件。 |

   {style="table-layout:auto"}

## “数据词典”组件信息 {#dd-component-information}

| 选项 | 函数 |
|---------|----------|
| [!UICONTROL **已批准**] | <p>表示该组件已获管理员审阅和批准。</p><p>管理员会看到&#x200B;[!UICONTROL **取消批准**]&#x200B;选项。选择此选项会为用户将组件标记为“未批准”。</p> |
| [!UICONTROL **未批准**] | <p>表示该组件尚未获得管理员审阅和批准。</p><p>管理员会看到&#x200B;[!UICONTROL **批准**]&#x200B;选项。 选择此选项会为用户将组件标记为“已批准”。</p> |
| [!UICONTROL **描述**] | 描述组件的预期功能。（此信息由 Analytics 管理员添加，如[添加组件描述](/help/components/add-component-descriptions.md)中所述。） |
| [!UICONTROL **常常与以下组件一同使用**] | <p>显示最常与您正在查看的组件一起使用的组件。</p><p>5種主要元件型別中會顯示最多5種元件：量度、計算量度、Dimension、篩選器和日期範圍。</p><p>此列表基于过去 90 天的数据。其中仅列出您有权查看的组件。</p><p>管理员可通过在&#x200B;[!UICONTROL **始终包括**]&#x200B;和&#x200B;[!UICONTROL **始终排除**]&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您組織使用者看到的元件之前，請先套用 **全部顯示** 篩選以確保您看到任何未與您共用，且可能由其他管理員新增的元件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **类似于**] | <p>显示与您正在查看的组件名称类似的组件。</p><p>5種主要元件型別中會顯示最多5種元件：量度、計算量度、Dimension、篩選器和日期範圍。</p><p>其中仅列出您有权查看的组件。</p><p>資料檢視中的任何重複元件都會顯示在這裡。 Analytics 管理员应识别并删除所有重复的组件，如[监视数据词典运行状况](/help/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理员可通过在&#x200B;[!UICONTROL **始终包括**]&#x200B;和&#x200B;[!UICONTROL **始终排除**]&#x200B;下拉字段中选择所需的组件而编排用户可在此部分中看到的组件。在您組織使用者看到的元件之前，請先套用 **全部顯示** 篩選以確保您看到任何未與您共用，且可能由其他管理員新增的元件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：****类似于**&#x200B;部分当前仅包括您创建的组件，而不包括 Adobe 提供的组件。将在未来的版本中添加 Adobe 提供的组件。</p> |
| [!UICONTROL **标记**] | 显示应用于组件的所有标记。具有管理员访问权限的用户可以在编辑组件时添加标记。 |
| [!UICONTROL **组件类型**] | 列出它的元件型別，包括Dimension、量度、篩選器或日期範圍。 |
| [!UICONTROL **创建者**] | 显示创建组件的用户名称。 |
| [!UICONTROL **预览**] | 显示组件在 Analysis Workspace 中的外观预览。 |
| [!UICONTROL **上次修改日期**] | 显示上次修改组件的日期。檢視篩選器、量度、計算量度和日期範圍時，會顯示此區段。 |

{style="table-layout:auto"}

## 元件排序選項 {#components-sort-options}

| 选项 | 函数 |
|---------|----------|
| [!UICONTROL **建议**] | 將元件與建議置於清單頂端的元件進行排序。 您或組織中其他人最常使用且最近使用的元件，會在清單中顯示在較高位置。 |
| [!UICONTROL **按字母顺序**] | 依字母順序排序元件。 |
| [!UICONTROL **類別**] | 根據元件型別（維度、量度、區段、日期範圍）來排序元件。 |

{style="table-layout:auto"}

