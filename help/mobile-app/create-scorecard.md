---
description: 如何创建和共享 Analytics 功能板记分卡
title: 创建并共享记分卡
feature: Analytics Dashboards
role: User, Admin
exl-id: 12531600-7e88-4d56-a2a5-e5b346f91937
solution: Customer Journey Analytics
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '2701'
ht-degree: 98%

---

# 创建移动记分卡 {#create-a-mobile-scorecard}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="mobilescorecard_annotations"
>title="注释"
>abstract="可以在组件管理器或 Workspace 项目内部创建注释。"

<!-- markdownlint-enable MD034 -->


以下信息将指导 Customer Journey Analytics 数据策划人如何为执行用户配置和展示功能板。要开始操作，您可以观看 Analytics 功能板记分卡生成器视频：


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Createa 移动记分卡](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/dashboards/create-a-mobile-scorecard){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


>[!NOTE]
>
>此页面的 Analytics 记分卡屏幕快照获取自 Adobe Analytics UI 而非 Customer Journey Analytics。这些 UI 几乎完全相同。

Analytics 记分卡以平铺版面为执行用户显示关键数据可视化图表，如下所示：

![Analytics 记分卡示例，其中显示了对移动记分卡的演示](assets/intro_scorecard.png)

作为此记分卡的策划人，您可以使用记分卡生成器来配置要在执行用户的记分卡上显示的磁贴。您还可以配置在点按图块后，如何调整详细视图或细分。记分卡生成器界面如下所示：

![记分卡生成器，其中显示新的移动记分卡窗口。](assets/scorecard_builder.png)

要创建记分卡，您需要执行以下操作：

1. 访问 Workspace 中的[!UICONTROL 空白移动记分卡]模板。
2. 使用数据配置记分卡并将其保存。

## 访问[!UICONTROL 空白移动记分卡]模板 {#template}

您可以通过创建新项目或从“工具”菜单中访问[!UICONTROL 空白移动记分卡]模板。

### 创建新项目 {#create}

1. 打开 Customer Journey Analytics，然后单击&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡。
1. 在左边栏中点击&#x200B;**[!UICONTROL 项目]**。
1. 单击&#x200B;**[!UICONTROL 创建新项目]**&#x200B;并选择&#x200B;**[!UICONTROL 空白移动记分卡]**&#x200B;项目模板。
1. 单击&#x200B;**[!UICONTROL 创建]**。

![“所有模板”窗口，其中选中了“空白移动记分卡”。](assets/new_template.png)

### “工具”菜单

1. 从&#x200B;**[!UICONTROL 工具]**&#x200B;菜单中，选择 **[!UICONTROL Analytics 功能板（移动应用程序）]**。
1. 在后续显示的屏幕上，单击&#x200B;**[!UICONTROL 新建记分卡]**。

## 使用数据配置记分卡并将其保存 {#configure}

要实施记分卡模板，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 记分卡属性]**（位于右侧边栏）中，指定要使用其中数据的&#x200B;**[!UICONTROL 项目数据视图]**。

   ![新的移动记分卡窗口，其中突出显示数据视图选择](assets/properties_save.png)

1. 要向记分卡中添加新磁贴，从左侧面板中拖动量度并将其放至&#x200B;**[!UICONTROL 在此处拖放量度]**&#x200B;区域。您也可以使用类似的工作流程，在两个图块之间插入量度。

   ![新的移动记分卡窗口，其中有一个箭头指向记分卡中的量度（新 KPI）。](assets/build_list.png)


1. 从每个磁贴中，您可以访问一个详细视图，该视图显示有关量度的其他信息，例如，相关维度列表的排名最前的项目。

## 添加维度或量度 {#dimsmetrics}

要向量度中添加相关维度，请将左侧面板中的维度拖放到磁贴中。

例如，您可以通过将适当的维度（如本示例中的 **[!DNL Marketing Channel]**）拖放到图块上来将它添加到&#x200B;**[!UICONTROL 独特访客]**&#x200B;指标。维度细分显示在图块特定的&#x200B;**[!UICONTROL 属性]**&#x200B;的[!UICONTROL 深入分析]（细分）部分的下方。可向每个图块中添加多个维度。

![新的移动记分卡窗口，其中有一个从维度列表指向记分卡窗格的箭头。](assets/layer_dimensions.png)

## 应用区段 {#segments}

要将区段应用于单个磁贴，请将左侧面板中的某个区段直接拖放到磁贴的顶部。

如果要将区段应用于记分卡中的所有磁贴，请将区段拖放到记分卡的顶部。或者，您也可以在日期范围下方的区段菜单中选择区段，然后应用它们。您可以像在 Customer Journey Analytics Workspace 中那样[为记分卡配置和应用区段](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=zh-Hans)。

![区段下拉选择器突出显示已构建的区段](assets/segment_ui.png)

## 添加日期范围 {#dates}

通过选择日期范围下拉菜单来添加和移除可在记分卡中选择的日期范围组合。

![新的移动记分卡，其中突出显示昨天与上周同一天的对比情况](assets/new_score_card.png)

每个新记分卡都从 6 个日期范围组合开始，重点展示今天和昨天的数据。您可以单击 x 以移除不必要的日期范围，也可以单击铅笔图标以修改每个日期范围组合。

![新的移动记分卡，其中突出显示铅笔图标](assets/new_score_card2.png)

要创建或更改主要日期，请使用下拉菜单从可用日期范围中选择，或者将日期组件从右边栏拖放到放置区域中。

![新的移动记分卡，其中突出显示日期范围，并选择了主要日期/昨天](assets/new_score_card3.png)

要创建比较日期，您可以在下拉菜单中选择方便的预设以进行常用的时间比较。您还可以从右边栏拖放日期组件。

![新的移动记分卡，其中突出显示了日期范围，并将比较日期设置为所选的上周的同一天](assets/new_score_card4.png)

如果尚未创建您所需的日期范围，您可以单击日程表图标以创建一个新的日期范围。

![日程表图标](assets/new_score_card5.png)

这会将您带到日期范围生成器，您可以在其中创建和保存新的日期范围组件。

### 显示或隐藏比较日期范围 {#show-comparison-dates}

要包括比较日期范围，请切换&#x200B;**包括比较日期**&#x200B;设置。

![新的移动记分卡，其中突出显示昨天与前一天的对比情况，并包括比较日期](assets/include-comparison-dates.png)

默认情况下&#x200B;*启用*&#x200B;此设置。如果您不想查看比较日期，请将其切换为&#x200B;*关闭*。

![新的移动记分卡，其中突出显示昨天的情况，并包括比较日期](assets/no-comparison-dates.png)

## 应用可视化图表 {#viz}

Analytics 功能板提供了四种可视化图表，可让您洞察维度项和量度。通过更改磁贴的[!UICONTROL 属性]的[!UICONTROL 图表类型]来更改为其他可视化图表。只需选择正确的磁贴，然后更改图表类型。

![磁贴属性](assets/properties.png)

或者，单击左边栏中的[!UICONTROL 可视化图表]图标，并将正确的可视化图表拖放到磁贴上：

![可视化内容](assets/vizs.png)

### [!UICONTROL 摘要数字]

使用摘要数字可视化图表来突出显示项目中的大型重要数字。

![新的移动记分卡，其中具有摘要数字可视化图表，并突出显示了 13.3K 次访问](assets/summary-number.png)

### [!UICONTROL 环形图]

此可视化与饼图类似，将数据显示为整体的一部分。在比较总数的百分比时使用环形图。例如，您想查看哪个广告平台对独特访客总数做出了贡献：

![新的移动记分卡，其中显示环形图可视化](assets/donut-viz.png)

### [!UICONTROL 折线图]

此线形图可视化图表使用线条来表示指标，以显示一段时间内值的变化情况。线形图显示随时间变化的维度，但适用于任何可视化图表。在此示例中，您将对产品类别维度进行可视化。

![新的移动记分卡，其中显示线形图可视化](assets/line.png)

### [!UICONTROL 水平条形图]

此可视化图表显示了一些水平条形图，这些水平条形图表示一个或多个量度中的各种值。例如，要轻松查看您的最热门产品，请使用[!UICONTROL 水平条形图]作为您的首选可视化图表。

![新的移动记分卡，其中显示水平条](assets/horizontal.png)

## 命名记分卡 {#name}

要命名记分卡，请单击屏幕左上角的命名空间，然后输入新名称。

![Naming_Scorecards](assets/new_name.png)

### 删除[!UICONTROL 未指定]维度项 {#remove-dims}

如果要从数据中删除[!UICONTROL 未指定]维度项，请执行以下操作：

1. 选择正确的磁贴。
1. 在右边栏中的&#x200B;**[!UICONTROL 深入分析]**&#x200B;下，选择要删除其&#x200B;**[!UICONTROL 未指定]**&#x200B;项的维度项旁边的右箭头。

   ![带有指向维度名称旁边的右箭头的箭头的属性。](assets/unspecified.png)

1. 单击&#x200B;**[!UICONTROL 未指定]**&#x200B;旁边的图标以从报告中删除未指定数据。（您也可以删除任何其他维度项。）

## 查看和配置磁贴属性 {#tiles}

在记分卡生成器中单击某个磁贴时，右侧边栏将显示与该磁贴及其详细信息幻灯片关联的属性和特征。在此边栏中，可为该磁贴提供新的&#x200B;**标题**&#x200B;或通过应用区段而配置该磁贴。

![属性磁贴](assets/properties-tile-new.png)

## 查看详细信息幻灯片 {#view-detail-slides}

在单击某个磁贴时，将有一个动态弹出窗口显示如何在应用程序中为执行用户显示详细信息幻灯片。可添加维度以根据特定需求细分数据。如果尚未应用某个维度，则细分维度将为&#x200B;**小时**&#x200B;或&#x200B;**天**，具体取决于默认日期范围。

细分通过按维度项（如以下各项）细分各个量度而细化您的分析结果：

* 按广告平台（AMO ID）细分独特访客量度
* 按产品类别（零售）细分访问
* 按产品名称细分总收入

![Breakdown_view](assets/break_view.png)

添加到图块的每个维度将显示在应用程序详细视图的下拉菜单中。 然后，执行用户可以从下拉菜单中选取列出的选项。

## 自定义详细信息幻灯片 {#customize-detail-slide}

通过自定义详细信息幻灯片，与受众共享的信息可更有针对性。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自定义详细信息视图](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/visitor-id/stitching-enablement-and-validation){target="_blank"}以观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]

可修改每个详细信息幻灯片的布局，并添加文本以更好地解释最终用户可能在数据中看到的内容。还可以使用下拉菜单更改图表类型。

![自定义详细信息幻灯片](assets/custom-detail-slide.png)

### 更改幻灯片布局

更改幻灯片布局可强调最重要的信息。例如，可更改布局以仅显示图表或仅显示表格。要更改幻灯片布局，请选择预先设计的格式之一。

![幻灯片布局](assets/layout.png)

还可通过将可视化图表组件从左侧边栏拖放到画布上而更改幻灯片布局。每个详细信息幻灯片一次只能容纳两个可视化图表。

![幻灯片布局更改](assets/slide-layout-change.png)

### 将描述性文本添加到幻灯片

可添加文本以提供关于图表中包含的内容的有意义信息或关于数据的细微差别。

要将文本添加到详细信息幻灯片，请选择显示 `T` 符号的布局，或将文本可视化图表组件从左侧边栏拖放过来。在添加新的文本可视化图表或选择带有文本的幻灯片布局时，将自动打开文本编辑器。文本编辑器提供用于设置文本格式的所有标准选项。可应用段落、标题和副标题等文本样式，并可应用粗体和斜体字体。可两端对齐文本、添加带项目符号和编号的列表以及添加链接。编辑完毕后，选择文本编辑器右上角的最小化按钮以关闭它。要编辑已添加的文本，请选择铅笔图标以再次打开文本编辑器。

![幻灯片布局更改](assets/add-descriptive-text.png)

## 删除组件 {#remove}

同样，要删除应用于整个记分卡的组件，请单击记分卡上图块外的任意位置，然后通过单击将鼠标悬停在该组件上时显示的 **x** 而删除该组件，如下面对于&#x200B;**首次访问数**&#x200B;显示的那样：

![Remove_components](assets/new_remove.png)

## 创建数据故事 {#create-data-story}

数据故事是围绕中心主题或量度生成的辅助数据点、业务背景和相关量度的集合。

例如，如果您关注 Web 流量，则对您最重要的量度可能是访问量，但您也可能对新访客和独特访客感兴趣，并且您可能要查看按网页或流量来源设备类型细分的数据。通过移动记分卡项目中的数据故事，可重点介绍对您最重要的量度，同时用多张详细信息幻灯片讲述这些量度背后的整个故事。

观看视频以详细了解如何在 Analysis Workspace 中的移动记分卡项目中创建数据故事。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [移动记分卡的数据故事项目](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/dashboards/create-a-mobile-scorecard){target="_blank"}，观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]


**创建数据故事** {#data-story-create}

通过将多张详细信息幻灯片添加到磁贴而生成您的数据故事。

1. 从移动记分卡项目开始。
1. 选择要从其创建故事的磁贴。
   ![创建数据故事](assets/data-story1.png)
   ![创建数据故事图标](assets/create-data-story.png){width=".50%"}
1. 添加幻灯片以构建您的数据故事。默认生成您的第一张幻灯片。要添加新幻灯片，请将光标悬停在幻灯片上或单击幻灯片，然后选择可用的选项：
   * 点按 + 号以创建新幻灯片。
   * 点按复制图标以复制现有幻灯片。
1. 如果创建空白的幻灯片，请从左边栏拖放组件，或选择一种版面以自动为该幻灯片填入磁贴中的数据。
   ![创建数据故事](assets/data-story2.png)
要删除幻灯片，请点按垃圾桶图标。

### 自定义数据故事 {#customize-data-story}

通过数据故事，可自定义一切，以使您可共享要共享的信息并排除多余的一切。您可以自定义图块和单张幻灯片以添加区段、显示细分、更改版面、更改可视化图表。

**自定义磁贴**

1. 点按磁贴。所选磁贴加入蓝色轮廓，并且右侧面板显示该磁贴属性。
1. 更改标题、图表类型和其他磁贴选项。
1. 将组件拖动到磁贴上。
   ![创建数据故事](assets/data-story3.png)
在将可视化等组件拖放到磁贴上时，该组件将应用于所有数据故事幻灯片。
1. 要仅对标题应用更改，请按住 Shift 键以应用更改。
   ![创建数据故事](assets/data-story4.png)

>[!NOTE]
>幻灯片从磁贴继承组件，但磁贴不从幻灯片继承组件。

**自定义个别幻灯片**

可更改数据故事中个别幻灯片的可视化图表。例如，可将特定幻灯片的水平条形图变为圆环图。还可以更改版面。参阅[自定义详细信息幻灯片](#customize-detail-slide)。

### 预览数据故事 {#preview-data-story}

创建数据故事后，使用&#x200B;**预览**&#x200B;按钮可像应用程序用户那样查看数据故事并与之交互。有关预览数据故事的信息，请参阅[预览记分卡](#preview)

### 在磁贴和幻灯片之间导航 {#navigate-tiles-slides}

导航栏显示代表每张幻灯片上的内容的图标。如果您有大量幻灯片，可使用导航栏轻松导航到特定幻灯片。

要在磁贴和幻灯片之间移动，请点按导航栏。![创建数据故事](assets/data-story5.png)
![创建数据故事](assets/data-story-nav.png){width="45%"}

还可使用箭头键或选择组件并按住它移向屏幕左侧或右侧进行滚动以来回导航。

## 预览记分卡 {#preview}

您可以预览记分卡在 Adobe Analytics 功能板应用程序中发布后的外观和功能。

1. 在屏幕的右上角单击&#x200B;**[!UICONTROL 预览]**。

   ![预览记分卡](assets/preview.png)

1. 要查看记分卡在不同设备上的外观，请从[!UICONTROL 设备预览]下拉菜单中选择一个设备。

   ![设备预览](assets/device-preview.png)

1. 要与预览交互，您可以：

   * 单击左键以模拟在手机屏幕上点击。

   * 使用计算机的滚动功能模拟用手指滚动手机屏幕。

   * 单击并按住以模拟在手机屏幕上按住手指。此操作对于与详细视图中的可视化图表交互很有用。

## 共享记分卡 {#share}

要与执行用户共享记分卡，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 共享]**&#x200B;菜单，然后选择&#x200B;**[!UICONTROL 共享记分卡]**。

1. 在&#x200B;**[!UICONTROL 共享移动记分卡]**&#x200B;表单中，通过以下方式填写字段：

   * 提供记分卡的名称
   * 提供记分卡的说明
   * 添加相关标记
   * 指定记分卡的收件人

1. 单击&#x200B;**[!UICONTROL 共享]**。

![Share_Scorecards](assets/new_share.png)

共享记分卡后，收件人可在其 Analytics 功能板中访问该记分卡。如果您在记分卡生成器中对记分卡进行后续更改，则已共享的记分卡会自动更新以反映这些更改。然后，执行用户在其应用程序中刷新记分卡后，便可看到这些更改。

如果通过添加新组件来更新记分卡，则您可能需要再次共享记分卡（并选中&#x200B;**[!UICONTROL 共享嵌入的组件]**&#x200B;选项），以确保执行用户有权访问这些更改。

### 使用可共享链接共享记分卡

使用可共享链接可以轻松地在电子邮件、文档或短信应用程序中共享记分卡。可共享链接让收件人可以在他们的桌面或仪表板移动应用程序上打开记分卡。可共享深度链接使共享项目和提升利益相关者的参与变得更加容易。

使用可共享链接共享记分卡

1. 单击&#x200B;**[!UICONTROL 共享]**&#x200B;菜单，然后选择&#x200B;**[!UICONTROL 共享记分卡]**。

   ![Share_Scorecards](assets/share-scorecard.png)

1. 复制链接并将其粘贴到电子邮件、文档或 IM 应用程序中。

   当收件人使用桌面应用程序或浏览器打开链接时，移动记分卡项目将在工作区中打开。

   当收件人在移动设备上打开链接时，记分卡将直接在 Adobe Analytics 仪表板应用程序中打开。

   如果收件人尚未下载移动应用程序，他们将被引向 App Store 或 Google Play Store 中的应用程序列表，然后可以在那里下载。

