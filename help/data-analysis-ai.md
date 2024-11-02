---
description: 如何向Customer Journey Analytics文档提出数据分析问题
title: Customer Journey Analytics中的数据分析AI助手
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e18d8facbd54ae65d158ce2c72f47709ef988f8f
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 4%

---


# Customer Journey Analytics中的数据分析AI助手 — Alpha

Data Analysis AI Assistant是一个智能的上下文感知会话代理，可帮助您更快、更高效地回答Customer Journey Analytics中有关Analysis Workspace数据的问题。

该助手会查看数据视图中的所有数据，包括不同类型的量度和组件，并将您的提示转换为此分析的正确维度、量度和日期范围。 您无需熟悉数据视图组件，然后以最佳组合拖放这些组件来回答您的问题，只需在AI助手中键入问题即可。

## Alpha版本的作用域内与作用域外功能

### 范围内的功能

| 支持的功能 | 描述 |
| --- | --- |
| **生成并更新可视化图表** | 生成自由格式表和相关的可视化图表（例如折线图、条形图、圆环图等）。<p>示例：*从2月到5月，跨SKU的利润是多少？* |
| **支持的可视化图表类型** | <ul><li>线形图</li><li>多行</li><li>自由格式表</li><li>条形图</li><li>圆环图</li><li>摘要数字</li></ul> |
| **范围外提示检测** | 如果提交超出范围的提示（如“导出此项目”），助理将通过告知您问题超出范围来进行响应。 |
| **澄清问题** | 如果您提出的问题，没有足够上下文可供AI助手回答或过于宽泛，则AI助手会用一个澄清问题和/或建议的选项进行响应。 示例： <p>**组件**<ul><li>量度：*您指的是哪个“收入”量度？*</li><li>Dimension： *您要关注以下“地区”中的哪一个？*</li><li>筛选器：*您要应用哪个“帐户”筛选器？*</li><li>日期范围： *对于“上个月”，您是指“上个月”还是“最近30天”？*</li></ul>**Dimension项目**：您指的是哪个“商店名称”？ (例如，Store #5274、Store #2949等) |
| **多圈** | AI Assistant使用上一个提示的上下文对提示进行响应，允许用户更新可视化并询问后续问题。 示例：*改为向我显示从3月到4月的数据。* |
| **反馈** | <ul><li>竖起大拇指</li><li>拇指朝下</li><li>标志</li></ul> |

### 超出范围的功能

| 不支持的功能 | 描述 |
| --- | --- |
| **内联摘要或响应** | AI助手无法在聊天边栏中以用户提示的摘要答案进行内联响应。范围外提示示例：<ul><li>*给我上一个提示的见解摘要。*</li><li>*从折线图可视化图表摘要突出显示内容。*</li></ul> |
| **澄清问题** | 澄清问题仅限于组件和维度项目。 AI Assistant无法阐明数据视图、可视化图表、数据粒度、比较、范围等。 如果不澄清问题，助理将默认使用您最可能要求的内容。 如果它返回意外的可视化或数据粒度，则您随后可以使用多轮/更新功能来调整可视化图表和数据。 |
| **Workspace操作/功能** | 除了构建和更新可视化图表之外，AI助手无法为Workspace中的用户执行操作。 例如，它不能执行以下任何操作：<ul><li>上下文操作UI按钮（添加到图表、新面板、新表）</li><li>共享</li><li>导出</li><li>下载</li><li>管理用户首选项</li><li>策划</li><li>管理数据视图</li><li>Analytics功能板应用程序</li><li>归因</li></ul> |
| **不支持的可视化图表类型** | <ul><li>流量</li><li>流失</li><li>同类群组表</li><li>面积图，栈叠的面积图</li><li>堆叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图、栈叠的水平条形图</li><li>关键量度摘要</li><li>散点图</li><li>概要变化</li><li>文本</li><li>树状图</li><li>维恩图</li></ul> |
| **解释性和可验证性** | 对AI助手如何生成响应的透明描述或引用，并为您提供一种确认答案是否正确的方法。 |

## Customer Journey AnalyticsUI中的功能访问

[Alpha是否需要此分区？]

以下参数控制对数据分析AI助手功能的访问：

* **解决方案访问**： Data Analysis AI Assistant可供Analysis Prime和Ultimate客户使用Customer Journey Analytics。 在Adobe Analytics中不可用。

Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform应用程序中也提供了此功能。

* **合同访问权限**：如果您无法使用AI助手，请联系您组织的管理员或Adobe客户代表。 在您的组织能够使用Data Analysis AI Assistant之前，您必须同意某些与GenAI相关的法律条款。

* **权限**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 报表工具] **[!UICONTROL AI Assistant：数据分析]**&#x200B;权限确定对此工具的访问权限。 [产品配置文件管理员](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中执行这些步骤：
   1. 导航到&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品配置文件]**
   1. 选择要为其提供[!UICONTROL AI助手：产品知识]访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**。
   1. 选择![编辑](/help/assets/icons/Edit.svg)以编辑&#x200B;**[!UICONTROL 报告工具]**。
   1. 选择![AddCircle](/help/assets/icons/AddCircle.svg)以将&#x200B;**AI助手：数据分析**&#x200B;添加到&#x200B;**[!UICONTROL 包含的权限项]**。

      ![添加权限](assets/ai-assistant-permissions.png)。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

有关详细信息，请参阅[访问控制](/help/technotes/access-control.md#access-control)。

## 访问和使用数据分析AI助手

1. 转到此链接以在Labs IMS组织（暂存中）中打开Workspace，然后使用您的Adobe ID登录。

1. 在项目页面顶部的横幅中单击&#x200B;**[!UICONTROL 空白项目]**&#x200B;以打开一个新的空白项目。

1. 单击右上角的AI助手聊天图标。

   ![AI助手图标](/help/assets/ai-asst-icon.png)

1. 在底部的&#x200B;**[!UICONTROL 询问Customer Journey Analytics]**&#x200B;对话框中，在AI助手中询问数据分析问题。

### 示例 1

例如，假设您对您的企业在7月份收到的订单感兴趣。

1. 输入“Show orders in July（在7月显示订单）”。

   ![AI提示](/help/assets/ai-asst-prompt1.png)

1. AI Assistant现在通过查看数据视图中的数据（包括量度和组件）来收集见解。 它将提示转换为正确的维度、量度和数据范围。

   如您所见，它自动生成了一个折线图和一个自由格式表，其中显示了7月份的订单。

   ![提示答案 — 折线图和自由格式表](/help/assets/ai-asst-result.png)

### 示例 2

接下来，您需要查看收入在不同地区的比较情况。

1. 在提示窗口中，输入“按区域显示收入”。

2. AI足够智能，能够理解“地区”的意思是“客户地区”。 该报表会生成一个条形图，其中按地区显示收入的情况最好：

   ![条形图](/help/assets/ai-asst-result2.png)

### 示例 3

现在，我们来了解一下按产品类别划分的收入。

1. 在提示窗口中，输入“按产品类别显示收入”。

2. 再次重申，数据分析AI助手会选取最适合的可视化图表（在本例中为&#x200B;**[!UICONTROL 圆环图]**&#x200B;可视化图表）来回答问题。

   ![圆环图](/help/assets/ai-asst-result3.png)

### 示例 4

最后，您想知道哪个SKU最有利可图，以及在何处投资营销资源。

1. 在提示窗口中，询问“从2月到5月，SKU的利润是多少？”

1. 简单的&#x200B;**[!UICONTROL 条形图]**&#x200B;提供了最简洁的答案：

   ![条形图](/help/assets/ai-asst-result4.png)

## 示例数据分析提示

以下是常见提示的一些示例，以及AI助手用于响应这些提示的可视化图表。

| 示例提示 | 预期可视化图表 |
| --- | --- |
| 显示[个月]的利润 | 线形图<p>默认情况下，在特定时间范围内请求趋势或量度会返回折线图可视化图表。 |
| [月]的订单趋势 | 线形图 |
| 在[月]内按地区显示收入 | 条形图 |
| 按产品类别分列的收入份额 | 圆环图 |
| 按星期几的订单，从1月到5月 | 条形图 |
| 按性别显示从3月到6月的订单 | 条形图 |
| 从2月到5月，跨SKU的利润如何 | 条形图 |
| [月]内按商店名称列出的收入 | 条形图 |
| 按[月]的利润计算，我的前10个SKU是什么？ | 条形图 |
| 按月份划分的购买比例 | 圆环图 |
| [个月]的总利润 | 摘要数字<p>如果要求提供特定时间范围内的量度“总计”，应当会返回“摘要数字”可视化图表。 |


## 提示最佳实践

待定

## Alpha测试期望并请求反馈

提出每个问题后，请仔细查看助理提供的答案。 在提供反馈之前全面评估生成的可视化图表至关重要。

评估答案：提供的答案是否正确？

如果助理在聊天边栏中做出响应：评估文本响应。

* 如果显示了可视化图表/图表：评估可视化图表。 对于您的问题，它是否为适当/预期的可视化图表？

* 如果显示了自由格式表：评估自由格式表。 自由格式表数据是否正确？ 是否在请求时划分数据？ 应用的过滤器是您请求还是期望的过滤器？

* 如果给出了一般性错误消息表明问题超出范围，请根据您的提示提供反馈，以判断您认为超出范围的消息是否合适。 你的提示真的在范围之内吗？

对于每次响应，根据响应情况向上或向下拇指

在按下/按上/下拇指选择后，请选择相关的多选反馈框。 如果要提供其他反馈，请在打开的文本框中添加注释。

## 问题和联系

电子邮件`taylorb@adobe.com` （下午）
在AlphaSlack频道中发送问题和反馈： #aep-cja-ai-assistant-testers ???


