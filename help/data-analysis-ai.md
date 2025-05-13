---
description: 如何向Customer Journey Analytics文档提出数据分析问题
title: 在Customer Journey Analytics中使用Data Insights代理可视化数据
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: f3f3b34c904c1aeba3fbd07218f323ccd81974d4
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 3%

---

# 在Customer Journey Analytics中使用Data Insights Agent可视化数据

{{release-limited-testing}}

>[!AVAILABILITY]
>
>在2025年11月30日之前，Data Insights Agent适用于符合条件的Customer Journey Analytics客户。 在该日期之后，如果要继续使用Data Insights Agent，则需要许可证。 请联系您的Adobe客户团队以获得许可流程方面的帮助。

Data Insights Agent可从Customer Journey Analytics中的AI助手访问，是一个创新型人工智能会话代理，可快速高效地回答有关您数据的问题。 它使用数据视图中的组件并使用实际数据在Analysis Workspace中构建相关可视化图表。

使用Data Insights Agent在Analysis Workspace中解答以数据为中心的问题，可以节省您原本要在Analysis Workspace中手动构建可视化并熟悉数据视图组件所花费的无数时间。

AI助手中的![数据分析代理](assets/cja-ai-asst-da.gif)

## 范围内功能与范围外功能



### 范围内的功能

| 支持的功能 | 描述 |
| --- | --- |
| **生成并更新可视化图表** | 生成自由格式表和相关的可视化图表（例如折线图、条形图、圆环图等）。<p>示例：*从2月到5月，跨SKU的利润是多少？* |
| **支持的可视化图表类型** | <ul><li>线形图</li><li>多行</li><li>自由格式表</li><li>条形图</li><li>环形图</li><li>摘要数字</li></ul> |
| **范围外提示检测** | 如果您提交了一个超出范围的提示（如“导出此项目”），Data Insights Agent会通过告知您问题超出范围来进行响应。 |
| **澄清问题** | 如果您提的问题没有足够上下文可供Data Insights Agent回答，或者过于宽泛，Data Insights Agent会用一个澄清问题或建议的选项进行响应。 示例： <p>**组件**<ul><li>量度：*您指的是哪个“收入”量度？*</li><li>Dimension：*您想关注以下“地区”中的哪一个？*</li><li>区段： *您要应用哪个“帐户”区段？*</li><li>日期范围： *对于“上个月”，您是指“上个月”还是“最近30天”？*</li></ul>**Dimension项目**：您指的是哪个“商店名称”？ (例如，存储#5274、存储#2949等。) |
| **多圈** | Data Insights Agent会使用之前任何提示中的上下文来响应提示，以便用户更新可视化图表和提出后续问题。 示例： <ul><li>提示1：*从3月开始的趋势事件。*</li><li>提示2： *改为向我显示从3月到4月的数据*</li></ul> |
| **可验证性** | 通过生成的自由格式表和数据可视化，可以验证数据的可验证性和正确性。 例如，如果用户在上月&#x200B;*询问*&#x200B;趋势订单，您可以确认在新生成的面板、数据可视化和自由格式表中选择了正确的量度（“订单”）和日期范围（“上个月”）。 |
| **反馈** | <ul><li>竖起大拇指</li><li>拇指朝下</li><li>标志</li></ul> |

### 超出范围的功能

| 不支持的功能 | 描述 |
| --- | --- |
| **内联摘要或响应** | Data Insights Agent无法在聊天边栏中以用户提示的摘要答案进行内联响应。 范围外提示示例：<ul><li>*给我上一个提示的见解摘要。*</li><li>*从折线图可视化图表摘要突出显示内容。*</li></ul> |
| **澄清问题** | 澄清问题仅限于组件和维度项目。 Data Insights Agent无法阐明数据视图、可视化图表、数据粒度、比较和范围等内容。 当澄清无法使用的问题时，代理将默认为您最可能要求的内容。 如果它返回意外的可视化或数据粒度，您随后可以使用多圈/更新功能调整可视化图表和数据。 |
| **Workspace操作/功能** | 除了构建和更新可视化图表之外，Data Insights Agent无法为Workspace中的用户执行任何操作。 例如，它不能执行以下任何操作：<ul><li>上下文操作UI按钮（添加到图表、新面板、新表）</li><li>共享</li><li>导出</li><li>下载</li><li>管理用户首选项</li><li>策划</li><li>管理数据视图</li><li>Analytics功能板应用程序</li><li>归因</li></ul> |
| **不支持的可视化图表类型** | <ul><li>流量</li><li>流失</li><li>同类群组表</li><li>面积图，栈叠的面积图</li><li>堆叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图、栈叠的水平条形图</li><li>关键量度摘要</li><li>散点图</li><li>概要变化</li><li>文本</li><li>树状图</li><li>维恩图</li></ul> |

## 在Customer Journey Analytics中管理对Data Insights Agent的访问权限

以下参数可管理对Customer Journey Analytics中Data Insights Agent的访问：

* **解决方案访问权限**： Data Insights Agent可供Customer Journey Analytics Prime和Ultimate客户使用。 在Adobe Analytics中不可用。

* **合同访问权限**：如果您无法在AI助手中使用Data Insights Agent，请联系贵组织的管理员或Adobe帐户团队。 在贵组织可以使用Data Insights Agent之前，您必须同意与创作AI相关的某些法律条款。

* **权限**：必须先在[!UICONTROL Adobe Admin Console]中授予必要的权限，用户才能访问Data Insights Agent。

  要授予权限，[产品配置文件管理员](https://helpx.adobe.com/cn/enterprise/using/manage-product-profiles.html)必须在[!UICONTROL Admin Console]中完成以下步骤：
   1. 在&#x200B;**[!UICONTROL Admin Console]**&#x200B;中，选择&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡以查看&#x200B;**[!UICONTROL 所有产品和服务]**&#x200B;页面。
   1. 选择&#x200B;**[!UICONTROL Customer Journey Analytics]**。
   1. 在&#x200B;**[!UICONTROL 产品配置文件]**&#x200B;选项卡上，选择要为其提供[!UICONTROL AI助手：产品知识]访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。

      Admin Console中的![权限选项卡](assets/ai-assistant-permissions-tab.png)

   1. 在提供的表中的&#x200B;**[!UICONTROL 报告工具]**&#x200B;行中，选择编辑图标![编辑](/help/assets/icons/Edit.svg)。
   1. 滚动到或搜索&#x200B;**[!UICONTROL AI助手：产品知识]**，然后选择此权限旁边的加号图标![AddCircle](/help/assets/icons/AddCircle.svg)。

      **[!UICONTROL AI助手：产品知识]**&#x200B;权限已添加到&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;列。

      ![添加权限](assets/ai-assistant-permissions.png)。

   1. 选择&#x200B;**[!UICONTROL 数据视图工具]**&#x200B;选项卡，然后选择&#x200B;**[!UICONTROL Data Insights Agent]**&#x200B;权限旁边的加号图标![AddCircle](/help/assets/icons/AddCircle.svg)。

      **[!UICONTROL Data Insights Agent]**&#x200B;权限已添加到&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;列。

      ![添加权限](assets/ai-assistant-permissions-dataviewtools.png)。

   1. 选择&#x200B;**[!UICONTROL 数据视图]**&#x200B;选项卡以选择要为Data Insights Agent启用的数据视图。

      >[!IMPORTANT]
      >
      >Data Insights Agent可以引用所包含的数据视图，而引用数据视图的时间与您在Admin Console中启用这些视图的同一天。

   1. 搜索或滚动到要启用的数据视图，然后选择每个数据视图名称旁边的加号图标![AddCircle](/help/assets/icons/AddCircle.svg)。

      您添加的每个数据视图都显示在&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;列中。

      ![添加权限](assets/ai-assistant-permissions-dataviews.png)。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存权限。

  有关访问控制的详细信息，请参阅[访问控制](/help/technotes/access-control.md#access-control)。

## 在AI助手中访问Data Insights Agent

1. 转到[experience.adobe.com](https://experience.adobe.com/)并使用Adobe ID登录。

2. 从Experience Cloud主页中选择&#x200B;**Customer Journey Analytics**。

3. 在项目页面顶部的横幅中选择&#x200B;**[!UICONTROL 空白项目]**&#x200B;以打开一个新的空白项目。

4. 请确保为面板选择的数据视图是已启用与Data Insights Agent一起使用的数据视图，如[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)中所述。

5. 选择页面右上角的AI Assistant聊天图标。

   如果您看不到聊天图标，请联系您的管理员，以便管理员在Admin Console中启用以下功能：

   * 报告工具： **[!UICONTROL AI助手：产品知识]**

   * 数据视图工具： **[!UICONTROL Data Insights Agent]**

   有关其他详细信息，请参阅[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)。

   ![AI助手图标](/help/assets/ai-asst-icon.png)

6. 在页面底部的&#x200B;**[!UICONTROL 关于Customer Journey Analytics]**&#x200B;对话框中，使用Data Insights Agent提出数据可视化问题。

   有关更多信息，请参阅以下示例。

### 示例 1

例如，假设您对您的企业在7月份收到的订单感兴趣。

**提示：**&#x200B;输入&#x200B;*“7月份的趋势订单”。*

![AI提示](/help/assets/ai-asst-prompt1.png)

**响应：** Data Insights Agent通过查看数据视图中的数据（包括量度和组件）来收集见解。 它会将提示转换为数据范围内正确的维度和量度。

如您所见，它会自动生成一个线形图和一个自由格式表来显示7月的订单。

![提示答案 — 折线图和自由格式表](/help/assets/ai-asst-result.png)

### 示例 2

接下来，您需要查看收入在不同地区的比较情况。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按地区显示收入”*。

**响应：** Data Insights Agent智能地理解了“地区”的意思，即“客户地区”。 该报表会生成一个条形图，其中按地区显示收入的情况最好：

![条形图](/help/assets/ai-asst-result2.png)

### 示例 3

接下来，除了按地区了解收入之外，您还需要按地区查看利润数据。 您可以要求Data Insights Agent更新最新的可视化图表和自由格式表，而不是重复之前的提示。

**提示：**&#x200B;在提示窗口中，键入&#x200B;*“添加利润”*。

**响应：** **[!UICONTROL 条形]**&#x200B;图表仍提供最简洁的答案，但利润指标已添加为自由格式表中的列：

![条形图](/help/assets/ai-asst-result4.png)

### 示例 4

最后，我们来了解一下按产品类别划分的收入。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按产品类别列出的收入比例”。*

**响应：**&#x200B;同样，Data Insights Agent选择最合适的可视化图表（在本例中为&#x200B;**[!UICONTROL 圆环图]**&#x200B;可视化图表）来回答问题。

![环形图](/help/assets/ai-asst-result3.png)

## 示例数据可视化提示

以下是常见提示的一些示例以及Data Insights Agent用于响应这些提示的可视化图表。

| 示例提示 | 预期可视化图表 |
| --- | --- |
| 显示[个月]的利润 | 线形图<p>默认情况下，在特定时间范围内请求趋势或量度会返回折线图可视化图表。 |
| [月]的订单趋势 | 线形图 |
| 在[月]内按地区显示收入 | 条形图 |
| 按产品类别分列的收入份额 | 环形图 |
| 按星期几的订单，从1月到5月 | 条形图 |
| 按性别显示从3月到6月的订单 | 条形图 |
| 从2月到5月，跨SKU的利润如何 | 条形图 |
| [月]内按商店名称列出的收入 | 条形图 |
| 按[月]的利润计算，我的前10个SKU是什么？ | 条形图 |
| 按月份划分的购买比例 | 环形图 |
| [个月]的总利润 | 摘要数字<p>如果要求提供特定时间范围内的量度“总计”，应当会返回“摘要数字”可视化图表。 |


## 提示最佳实践

Data Insights Agent会处理每个用户提示提供的上下文，并尝试以自由格式表形式智能地响应最合适的可视化和组件。

响应可能会因提示中使用的具体字词和短语而异，语言的细微变化可能会导致不同的结果。

要获得最佳结果，请考虑以下准则：

* **具体：**&#x200B;包含精确术语以缩小响应范围。 以下是一个特定提示示例：“上月在加利福尼亚的销售额”

* **使用清晰的量度、维度和区段：**&#x200B;添加特定的量度（如“收入”）、维度（如“网站名称”）、区段(如“iPhone用户”)和日期范围（如“过去三个月”）有助于Data Insights Agent关注正确的数据。

* **直接提问：**&#x200B;使用措辞提问可让Data Insights Agent更轻松地提供清晰、相关的见解。 下面是一个在提示中直接提出问题的示例：“按产品类别列出的今年平均收入是多少？”

请查看下表，了解可在Data Insights Agent的提示中使用的示例术语和短语，以及可期待的响应类型。

这些示例旨在帮助您了解特定字词或结构如何影响Data Insight Agent的输出，从而确保更精确、更有价值的洞察。 Data Insights Agent使用创作AI，因此可视化图表或选定的数据可能会在类似提示中略有不同。

| 预期结果 | 术语和短语示例 |
| --- | --- |
| 概要数字可视化 | <ul><li>合计</li></ul> |
| 比较组件 | <ul><li>比较</li><li>对比</li><li>对比度</li><li>每周</li><li>月同比</li><li>季度环比</li><li>年份</li></ul> |
| 圆环图可视化图表 | <ul><li>比例</li><li>共享</li><li>分布</li><li>百分比</li><li>贡献</li><li>部分</li><li>部分</li></ul> |
| 折线图可视化图表 | <ul><li>趋势</li><li>在[时间范围]内的[指标]</li></ul> |
| 条形图可视化 | <ul><li>[Dimension]的[指标]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->

