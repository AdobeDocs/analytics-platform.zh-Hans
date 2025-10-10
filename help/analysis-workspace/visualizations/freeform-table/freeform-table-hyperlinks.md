---
title: 创建超链接
description: 了解如何在Analysis Workspace的自由格式表中为维度项目创建超链接。
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '1599'
ht-degree: 97%

---

# 创建超链接

您可以为维度项创建超链接，使其在 Analysis Workspace 中的自由格式表中可点击。

为以下类型的维度项创建超链接时此功能特别有用：

* 具有 URL 值的维度项（例如，“页面 URL”维度）。

* 包含具有 URL 值细分的维度项（例如，具有“页面 URL”维度细分的“页面名称”维度）。

* 具有作为 URL 一部分的值的维度项或细分（例如，作为 URL 一部分的“页面名称”维度）。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在自由格式表中创建超链接](https://video.tv.adobe.com/v/3445797/?quality=12&learn=on&captions=chi_hans){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


## 创建超链接

为一个或多个维度项创建超链接时，请考虑以下事项：

* 您创建的超链接存储在 Analysis Workspace 项目内的自由格式表中。在另一个表或另一个项目中使用相同维度或维度项时，超链接不会保留。

* 如果更改自由格式表的数据视图，则为表中的维度或维度项创建的任何超链接仍然可用。此功能假定该维度仍然存在于数据视图中。

* 创建超链接时，不会检查 URL 的有效性。如果您

   * 创建具有无效 URL 的超链接，或者
   * 创建引用没有 URL 值的维度项的超链接（通过直接引用维度项或使用 `$value` 或 `$breakdown` 变量），

  那么单击超链接的用户会看到一条错误消息，指示该 URL 无效。

* 为单个维度项创建的超链接会覆盖在该维度上创建的超链接。

* [下载的 PDF 文件中](/help/analysis-workspace/export/download-send.md)的超链接不起作用。

要为一个或多个维度项创建超链接：

1. 在 Analysis Workspace 中的自由格式表中，执行以下操作之一：

   * **为单个维度项创建超链接：**&#x200B;右键单击表格中要创建超链接的维度项，然后选择&#x200B;[!UICONTROL **创建超链接**]。

      1. 打开维度项的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **创建超链接**]。

         [!UICONTROL **创建超链接**]&#x200B;对话框会显示。您要为其创建超链接的维度项的名称将显示在对话框中。

         ![为单个项目创建超链接的对话框](assets/hyperlink-dialog-single.png)

   * **为维度列中的所有维度项创建超链接：**&#x200B;右键单击维度列标题中的维度名称，然后选择&#x200B;[!UICONTROL **为所有维度项创建超链接**]。

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **为所有维度项创建超链接**]。

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         [!UICONTROL **为所有维度项创建超链接**]&#x200B;对话框会显示。您要为其创建超链接的维度的名称将显示在对话框中。

         ![创建超链接对话框](assets/hyperlink-dialog-multiple.png)

1. 从以下选项中进行选择：

   * [!UICONTROL **使用维度项的值作为 URL**]：对于具有 URL 值的维度项（例如“页面 URL”维度），选择此选项。

     例如，如果您使用的是“页面 URL”维度，其中每个维度项的值都是 URL，则选择此选项会创建指向该 URL 的超链接。

   * [!UICONTROL **创建自定义 URL**]：指定静态或动态自定义 URL。选择此选项可以为没有 URL 值的维度项创建超链接。

     例如：您使用的是“页面名称”维度，其中每个维度项的值是页面的名称（而不是完整的 URL）。然后选择此选项，以指定一个超链接作为维度项的链接。

     如果您想为多个维度项创建动态 URL，您可以在自定义 URL 中使用 `$value` 和 `$breakdown` 变量。有关详细信息，请观看下方的表格。

     要创建自定义 URL，请指定以下信息：

     | 字段 | 描述 |
     |---------|----------|
     | [!UICONTROL **自定义 URL**] | 指定要用于超链接的自定义 URL。必须以完全限定的 URL 形式输入 URL。例如：<https://www.example.com><p>您创建的自定义 URL 可以是静态的，也可以是动态的：</p> <ul><li>**静态 URL：**&#x200B;当您希望所有维度项都链接到同一 URL 时，您可以为单个维度项或所有维度项指定一个静态 URL。例如：`https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**动态 URL：**&#x200B;如果您想为多个维度项或维度列中的所有维度项创建唯一的超链接，则可以创建一个动态 URL。<p>要使自定义 URL 动态化，您可以在 URL 中加入一个变量，以根据维度的值或细分维度的值更改 URL。</p><p>使用变量时，任何包含在 URL 中无效的字符（如空格）的维度项都会进行 URL 编码。</p><p>可用的变量如下：（**注释**：虽然您可以在同一个 URL 中使用这些变量，但单独使用它们的情况更常见。）</p> <ul><li>**`$value`：**&#x200B;允许您将维度项的值插入到您指定的 URL 中。 <p>假设您想要为自由格式表中的所有页面名称维度项创建超链接，其中每个维度项的值都是网页 URL 的一部分。在这种情况下，您可以构建一个针对每个维度项动态调整的单个自定义 URL。<br/>例如：`https://company-name.com/browse/product#\$value`</p><p>当此自定义 URL 应用于值为“ProductY”和“ProductZ”的页面名称维度项时，所生成的超链接将如下所示：<br/>`https://company-name.com/browse/product#ProductY` 和 <br/>`https://company-name.com/browse/product#ProductZ` </p><p>![在超链接中使用值](assets/table-hyperlinks-vaule.png)</p><p>**提示**：在自定义 URL 字段中仅添加 `$value` 变量，与在创建 URL 时选择&#x200B;[!UICONTROL **使用维度项的值**]&#x200B;选项的效果相同。</p></li><li>**`$breakdown`：**&#x200B;允许您将细分维度项的值插入到您指定的 URL 中。使用 `$breakdown`，您可以在报告中使用具有便于用户使用的名称的维度（例如“产品名称”维度）。并根据可能不太便于用户使用的细分维度（如产品 ID 或页面 URL 维度）生成超链接。<p>在引用细分维度时，对于给定的维度项，通常只会有一个细分项。如果给定维度项有多个细分项，则 URL 中会使用第一个细分项的值。如果没有列出细分项，则该 URL 无效。细分项的排序顺序与表格的排序顺序相同。</p><p>您可以在&#x200B;[!UICONTROL **细分维度**]&#x200B;字段中指定细分维度。</p> <p>考虑下面为&#x200B;[!UICONTROL **细分维度**]&#x200B;字段描述的示例场景。</p></li></ul> |
     | [!UICONTROL **细分维度（可选）**] | 开始键入要使用的划分维度的名称，然后从下拉菜单中选择该名称。 <p>如果在此字段中选择了一个细分维度，则必须在&#x200B;[!UICONTROL **自定义 URL**] 字段中指定的 URL 中使用 `$breakdown` 变量来引用它。</p><p>假设您想要为自由格式表中的所有“产品名称”维度项创建超链接。每个“产品名称”维度项均包含一个“产品 ID”维度的细分。</p></p>在这种情况下，您可以为每个“产品名称”维度创建超链接，利用“产品 ID”细分维度的值，将用户引导至产品页面。 </p><p>在&#x200B;[!UICONTROL **自定义 URL**] 字段中指定的自定义 URL 末尾添加 `$breakdown` 变量。例如：</p><p>`https://company-name.com/browse/product/$breakdown`</p>将此自定义 URL 应用于您的产品名称维度项（具有值为“ProductY”和“ProductZ”的细分维度项）时，生成的超链接如下所示：<br/>`https://company-name.com/browse/product/ProductY` 和 <br/>`https://company-name.com/browse/product/ProductZ`</p><p>然后，您要在&#x200B;[!UICONTROL **细分维度**]&#x200B;字段中选择产品 ID 维度 </p><p>![在超链接中使用细分](assets/table-hyperlinks-breakdown.png)</p> |

1. 选择&#x200B;[!UICONTROL **创建**]。

   查看自由格式表的用户会看到超链接的维度项。单击维度项时，用户将被带到单独的浏览器选项卡中的超链接页面。

   <!-- add screenshot of a table with hyperlinks.-->

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。

## 编辑超链接

您可以编辑自由格式表中的维度或维度项上创建的超链接。

1. 在 Analysis Workspace 中的自由格式表中，执行以下操作之一：

   * **编辑单个维度项的超链接：**

      1. 打开维度项的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **编辑超链接**]。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **编辑维度列中所有维度项的超链接：**

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;**[!UICONTROL 为所有维度项编辑超链接]**。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. 从右键菜单中选择&#x200B;[!UICONTROL **编辑所有维度项的超链接**]。

   [!UICONTROL **编辑维度项的超链接**]&#x200B;对话框会显示。

1. 有关编辑超链接的配置选项的信息，请参阅以上[为一个或多个维度项创建超链接](#create-hyperlinks-for-one-or-more-dimension-items)部分中的“第 3 步”，然后在您完成更新后，选择&#x200B;[!UICONTROL **应用**]。

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。

## 移除超链接

您可以移除为自由格式表中的维度项创建的超链接。

>[!NOTE]
>
>在自由格式表中，如果删除包含超链接的维度，则在将同一维度添加回自由格式表时，这些超链接将不会保留。

要移除维度项的超链接：

1. 在 Analysis Workspace 中的自由格式表中，执行以下操作之一：

   * **从单个维度项中移除超链接：**

      1. 打开维度项的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **移除超链接**]。
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **移除维度列中所有维度项的超链接：**

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;**[!UICONTROL 为所有维度项移除超链接]**。

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   如果您选择了单个维度项，则会从单个维度项中移除超链接。或者，如果您选择了维度列标题中的维度名称，则会从所有维度项中移除。

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。
