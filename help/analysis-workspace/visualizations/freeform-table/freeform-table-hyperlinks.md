---
title: 在自由格式表中创建超链接
description: 了解如何在Analysis Workspace的自由格式表中为维度项目创建超链接
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# 在自由格式表中创建超链接

您可以为维度项目创建超链接，以使它们可在Analysis Workspace的自由格式表中点击。

在为以下类型的维度项目创建超链接时，此功能特别有用：

* Dimension具有URL值的项目（例如，页面URL维度）。

* 包含具有URL值的划分的Dimension项目（例如，具有页面URL维度划分的页面名称维度）。

* Dimension其值属于URL的项目或划分（例如，属于URL的“页面名称”维度）。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在自由格式表中创建超链接](https://video.tv.adobe.com/v/3430411/?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## 创建超链接

为一个或多个维度项目创建超链接时，请考虑以下事项：

* 您创建的超链接存储在自由格式表的Analysis Workspace项目中。 在另一个表或其他项目中使用相同的维度或维度项时，超链接不会持久保留。

* 如果更改自由格式表的数据视图，则为表中的维度或维度项目创建的任何超链接仍然可用。 此功能假定数据视图中仍存在该维度。

* 创建超链接时，不会检查URL的有效性。 如果您

   * 创建包含无效URL的超链接，或者
   * 创建引用没有URL值的维度项目的超链接（通过直接引用维度项目或使用`$value`或`$breakdown`变量），

  随后，单击超链接的用户会看到一条错误消息，说明URL无效。

* 为单个维度项目创建的超链接会覆盖在维度上创建的超链接。

* 超链接在[下载的PDF文件](/help/analysis-workspace/export/download-send.md)中不起作用。

要为一个或多个维度项目创建超链接：

1. 在Analysis Workspace的自由格式表中，执行以下操作之一：

   * **为单个维度项创建超链接：**&#x200B;在要为其创建超链接的表内右键单击该维度项，然后选择&#x200B;[!UICONTROL **创建超链接**]。

      1. 打开维度项目的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **创建超链接**]。

         将显示&#x200B;[!UICONTROL **创建超链接**]&#x200B;对话框。 要为其创建超链接的维度项目的名称将显示在对话框中。

         ![为单个项目对话框创建超链接](assets/hyperlink-dialog-single.png)

   * **为维度列中的所有维度项创建超链接：**&#x200B;右键单击维度列标题中的维度名称，然后选择&#x200B;[!UICONTROL **为所有维度项创建超链接**]。

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **为所有维度项创建超链接**]。

         <!-- Do we really need a screenshot ![Create hyperlink for a dimension](assets/hyperlink-multiple-add.png) -->

         将显示&#x200B;[!UICONTROL **为所有维度项**]&#x200B;创建超链接对话框。 要为其创建超链接的维度的名称将显示在对话框中。

         ![创建超链接对话框](assets/hyperlink-dialog-multiple.png)

1. 从以下选项中进行选择：

   * [!UICONTROL **将维度项的值用作URL**]：为具有URL值的维度项（如页面URL维度）选择此选项。

     例如，如果您使用的是页面URL维度，其中每个维度项目的值都是一个URL，则选择此选项将创建指向该URL的超链接。

   * [!UICONTROL **创建自定义URL**]：指定静态或动态自定义URL。 选择此选项可以为没有URL值的维度项目创建超链接。

     例如：您使用的是“页面名称”维度，其中每个维度项目的值是页面的名称（而不是完整的URL）。 然后，选择此选项可指定要用作维度项目的链接的超链接。

     如果要为多个维度项目创建动态URL，可以在自定义URL中使用`$value`和`$breakdown`变量。 有关更多信息，请参阅下表。

     要创建自定义URL，请指定以下信息：

     | 字段 | 描述 |
     |---------|----------|
     | [!UICONTROL **自定义URL**] | 指定要用于超链接的自定义URL。 URL必须作为完全限定的URL输入。 例如：<https://www.example.com><p>您创建的自定义URL可以是静态或动态：</p> <ul><li>**静态URL：**&#x200B;如果希望单个维度项链接至同一URL，您可以为单个维度项或所有维度项指定静态URL。 例如：`https://wiki.internal.company_name/page_name#item_definition`</p></li><li>**动态URL：**&#x200B;如果要为多个维度项或维度列中的所有维度项创建唯一的超链接，可以创建动态URL。<p>要使自定义URL成为动态变量，可以在URL中包含一个变量，以根据维度的值或划分维度的值更改URL。</p><p>使用变量时，任何包含在URL中无效字符（例如空格）的维度项目都将进行URL编码。</p><p>以下变量可用： （**注意**：虽然可以在同一URL中使用这些变量，但通常单独使用这些变量。）</p> <ul><li>**`$value`：**&#x200B;允许您将维度项的值插入到您指定的URL中。 <p>假设您要为自由格式表中的所有“页面名称”维度项目创建超链接，其中每个维度项目的值都是网页URL的一部分。 在这种情况下，您可以构建一个自定义URL，以动态调整每个维度项目。 <br/>例如：`https://company-name.com/browse/product#\$value`</p><p>当此自定义URL应用于值为“ProductY”和“ProductZ”的“页面名称”维度项时，生成的超链接将如下所示：<br/>`https://company-name.com/browse/product#ProductY`和<br/>`https://company-name.com/browse/product#ProductZ` </p><p>![在超链接中使用值](assets/table-hyperlinks-vaule.png)</p><p>**提示**：仅将`$value`变量添加到“自定义URL”字段中，与创建URL时选择&#x200B;[!UICONTROL **使用维度项的值**]&#x200B;选项相同。</p></li><li>**`$breakdown`：**&#x200B;允许您将划分维度项的值插入到您指定的URL中。 通过`$breakdown`，您可以在报表中使用具有用户友好名称的维度（如产品名称维度）。 并且根据对用户不那么友好的划分维度（例如产品ID或页面URL维度）生成超链接。<p>在引用划分维度时，通常给定维度项目只具有一个划分项目。 如果给定维度项目有多个划分项目，则在URL中使用第一个划分项目的值。 如果未列出任何划分项目，则URL无效。 对划分项目应用的排序顺序与对表应用的排序顺序相同。</p><p>在下面的&#x200B;[!UICONTROL **划分维度**]&#x200B;字段中指定划分维度。</p> <p>考虑以下&#x200B;[!UICONTROL **划分维度**]&#x200B;字段描述的示例场景。</p></li></ul> |
     | [!UICONTROL **划分维度（可选）**] | 开始键入要使用的划分维度的名称，然后从下拉列表中选择该名称。 <p>如果在此字段中选择划分维度，则必须使用在&#x200B;[!UICONTROL **自定义URL**]&#x200B;字段中指定的URL中的`$breakdown`变量引用它。</p><p>假设您要为自由格式表中的所有“产品名称”维度项目创建超链接。 每个产品名称维度项都包含产品ID维度的细分。</p></p>在这种情况下，您可以为每个产品名称维度创建超链接，以便使用产品ID划分维度的值将用户引导至产品页面。 </p><p>将`$breakdown`变量添加到您在&#x200B;[!UICONTROL **自定义URL**]&#x200B;字段中指定的自定义URL的末尾。 例如：</p><p>`https://company-name.com/browse/product/$breakdown`</p>将此自定义URL应用于产品名称维度项目（具有值为“ProductY”和“ProductZ”的划分维度项目）时，生成的超链接如下所示：<br/>`https://company-name.com/browse/product/ProductY`和<br/>`https://company-name.com/browse/product/ProductZ`</p><p>然后，在&#x200B;[!UICONTROL **划分维度**]&#x200B;字段中选择产品ID维度 </p><p>![在超链接中使用划分](assets/table-hyperlinks-breakdown.png)</p> |

1. 选择&#x200B;[!UICONTROL **创建**]。

   查看自由格式表的用户会看到超链接的维度项目。 单击维度项目时，用户将被带入单独的浏览器选项卡中的超链接页面。

   <!-- add screenshot of a table with hyperlinks.-->

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。

## 编辑超链接

您可以编辑在自由格式表中针对维度或维度项目创建的超链接。

1. 在Analysis Workspace的自由格式表中，执行以下操作之一：

   * **编辑单个维度项目的超链接：**

      1. 打开维度项目的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **编辑超链接**]。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a single dimension item](assets/hyperlink-single-edit.png)-->

   * **编辑维度列中所有维度项的超链接：**

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;**[!UICONTROL 编辑所有维度项目的超链接]**。

     <!-- Do we really need a screenshot? ![Edit hyperlink for a dimension](assets/hyperlink-dimension-edit.png)-->

1. 从右键单击菜单中选择&#x200B;[!UICONTROL **编辑所有维度项目的超链接**]。

   将显示&#x200B;[!UICONTROL **维度项**]&#x200B;的“编辑超链接”对话框。

1. 有关用于编辑超链接的配置选项的信息，请参阅上面[为一个或多个维度项目创建超链接](#create-hyperlinks-for-one-or-more-dimension-items)部分中的步骤3，然后在完成更新后选择&#x200B;[!UICONTROL **应用**]。

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。

## 删除超链接

您可以删除为自由格式表中的维度项目创建的超链接。

>[!NOTE]
>
>在自由格式表中，如果删除包含超链接的维度，则在将同一维度重新添加到自由格式表中时，超链接将不会保留。

要从维度项目中删除超链接，请执行以下操作：

1. 在Analysis Workspace的自由格式表中，执行以下操作之一：

   * **从单个维度项中删除超链接：**

      1. 打开维度项目的上下文菜单。
      1. 从上下文菜单中选择&#x200B;[!UICONTROL **删除超链接**]。
         <!-- Do we really need a screenshot? ![Remove hyperlink from a single dimension item](assets/hyperlink-single-remove.png)-->

   * **从维度列中的所有维度项中删除超链接：**

      1. 从维度列标题打开上下文菜单。
      1. 从上下文菜单中选择&#x200B;**[!UICONTROL 删除所有维度项目的超链接]**。

     <!-- Do we really need a screenshot? [Remove hyperlink from a dimension](assets/hyperlink-dimension-remove.png)-->



   如果您选择了单个维度项目，则会从单个维度项目中删除超链接。 或者，如果您在维度列标题中选择了维度名称，则从所有维度项中删除。

1. [保存项目](/help/analysis-workspace/build-workspace-project/save-projects.md)以保存更改。
