---
description: 如何提出 Customer Journey Analytics 文档的数据分析问题
title: 使用 Customer Journey Analytics 中的 Data Insights 代理将数据可视化
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: e82179f3436dc6b66ebe3f2f9b11986cadd135d9
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 36%

---

# 在Customer Journey Analytics中使用Data Insights Agent可视化数据

{{release-limited-testing}}

>[!AVAILABILITY]
>
>在2025年11月30日之前，Data Insights Agent适用于符合条件的Customer Journey Analytics客户。 在该日期之后，如果要继续使用Data Insights Agent，则需要许可证。 请联系您的Adobe客户团队以获得许可流程方面的帮助。

Data Insights Agent可从Customer Journey Analytics中的AI助手访问，是一个创新型人工智能会话代理，可快速高效地回答有关您数据的问题。 它使用来自数据视图的组件和您的实际数据在 Analysis Workspace 中构建相关的可视化图表。

使用Data Insights Agent在Analysis Workspace中解答以数据为中心的问题，可以节省您原本要在Analysis Workspace中手动构建可视化并熟悉数据视图组件所花费的无数时间。

![AI 助手中的 Data Insights 代理](assets/cja-ai-asst-da.gif)

## 范围内功能与范围外功能

| 功能 | 范围 | 超出范围 |
| --- | --- | --- |
| **可视化类型** | <ul><li>线形图</li><li>多条折现图</li><li>自由格式表</li><li>条形图</li><li>环形图</li><li>摘要数字</li></ul> | <ul><li>流量</li><li>流失</li><li>同类群组表</li><li>面积图，堆叠面积图</li><li>堆叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图，横向堆叠条形图</li><li>关键量度摘要</li><li>散点图</li><li>摘要变化</li><li>文本</li><li>树状图</li><li>维恩图</li></ul> |
| **Workspace操作和代理功能** | <ul><li>构建和更新可视化图表<p>生成自由格式表和相关联的可视化图表（例如线形图、条形图、圆环图等）。<p>例如，*从2月到5月，跨SKU的利润是多少？*</p></li><li>提出跟进问题</li><li>响应上下文中的任何先前提示中的提示<p>例如：</p> <ul><li>提示词 1：*3 月的趋势事件。*</li><li>提示词 2：*请改为显示 3 月至 4 月的数据*</li></ul> </li><li>范围外提示检测<p>如果您提交了一个超出范围的提示，如&#x200B;*导出此项目*，Data Insights Agent会通知您问题超出范围，从而做出响应。</p></li></ul> | <ul><li>上下文操作 UI 按钮（添加到图表、新面板、新表格）</li><li>共享</li><li>导出</li><li>下载</li><li>管理用户偏好设置</li><li>策划</li><li>管理数据视图</li><li>Analytics 功能板应用程序</li><li>归因</li><li>内联摘要或响应<p>Data Insights Agent无法在聊天边栏中以用户提示的摘要答案进行内联响应。 范围外提示的示例包括：*给我上一个提示的见解摘要*&#x200B;和&#x200B;*总结折线图可视化图表的亮点。*</p></li></ul> |
| **澄清问题** | 如果您提的问题没有足够上下文可供Data Insights Agent回答，或者过于宽泛，Data Insights Agent会用一个澄清问题或建议的选项进行响应。 <p>以下澄清性问题是组件相关问题的示例：</p><ul><li>量度：*您指的是哪个“收入”量度？*</li><li>维度：*您想关注以下哪一个“地区”？*</li><li>区段：*您想应用哪个“帐户”区段？*</li><li>日期范围：*您所说的“上个月”是指过去的整个月还是过去 30 天？*</li></ul><p>以下澄清问题是与维度项目相关的一个问题的示例：</p> <ul><li>你是指哪个“商店名称”？ （例如，商店 #5274、商店 #2949 等。）</li></ul> | 澄清问题仅限于组件和维度项。Data Insights Agent无法阐明数据视图、可视化图表、数据粒度、比较和范围等内容。 当澄清无法使用的问题时，代理将默认使用您最可能要求的内容。 如果它返回意外的可视化图表或数据粒度，您可以提出后续问题或调整可视化图表和数据。 |
| **数据可验证性和正确性** | 通过查看生成的自由格式表和数据可视化图表，可以确认数据的可验证性和正确性。 <p>例如，如果您要求Data Insights Agent显示上个月&#x200B;*的*&#x200B;趋势订单，则可以确认在新生成的面板、数据可视化图表和自由格式表中选择了正确的指标（“订单”）和日期范围（“上个月”）。 | Data Insights Agent不会通过通知您添加了哪些组件或可视化图表来进行响应。</p> |
| **反馈机制** | <ul><li>拇指向上</li><li>拇指向下</li><li>标记</li></ul> |  |


## 在Customer Journey Analytics中管理对Data Insights Agent的访问权限

以下参数可管理对Customer Journey Analytics中Data Insights Agent的访问：

* **解决方案访问权限**： Data Insights Agent可供Customer Journey Analytics Prime和Ultimate客户使用。 它在 Adobe Analytics 中不可用。

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

1. 前往 [experience.adobe.com](https://experience.adobe.com/) 并使用您的 Adobe ID 登录。

2. 从 Experience Cloud 主页选择 **Customer Journey Analytics**。

3. 在项目页面顶部的横幅中选择&#x200B;**[!UICONTROL 空白项目]**，打开一个新的空白项目。

4. 请确保为面板选择的数据视图是已启用与Data Insights Agent一起使用的数据视图，如[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)中所述。

5. 选择页面右上角的 AI 助手聊天图标。

   如果您看不到聊天图标，请联系您的管理员，他们可以在管理控制台中启用以下功能：

   * 报告工具： **[!UICONTROL AI助手：产品知识]**

   * 数据视图工具： **[!UICONTROL Data Insights Agent]**

   有关其他详细信息，请参阅[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)。

   ![AI 助手图标](/help/assets/ai-asst-icon.png)

6. 在页面底部的&#x200B;**[!UICONTROL 关于Customer Journey Analytics]**&#x200B;对话框中，使用Data Insights Agent提出数据可视化问题。

   有关更多信息，请参阅以下示例。

### 示例 1

例如，假设您对您的企业 7 月份收到的订单感兴趣。

**提示词：**&#x200B;输入&#x200B;*“7 月份订单趋势。”*

![AI 提示词](/help/assets/ai-asst-prompt1.png)

**响应：** Data Insights Agent通过查看数据视图中的数据（包括量度和组件）来收集见解。 它将提示词转换成数据范围内的合适的维度和量度。

您可以看到，它自动生成了一个线形图和一个自由格式表来显示 7 月的订单。

![对提示词的回答——线形图和自由格式表](/help/assets/ai-asst-result.png)

### 示例 2

接下来，您想了解不同地区的收入比较。

**提示词：**&#x200B;在提示词窗口中输入&#x200B;*“按地区显示收入。”*

**响应：** Data Insights Agent智能地理解了“地区”的意思，即“客户地区”。 它会生成一个能最佳显示各地区收入的条形图：

![条形图](/help/assets/ai-asst-result2.png)

### 示例 3

接下来，除了按地区了解收入之外，您还需要按地区查看利润数据。 您可以要求Data Insights Agent更新最新的可视化图表和自由格式表，而不是重复之前的提示。

**提示词：**&#x200B;在提示词窗口中输入&#x200B;*“添加利润。”*

**回答：**&#x200B;**[!UICONTROL 条形]**&#x200B;图仍然提供了最简洁的回答，而利润量度被添加到自由格式表中成为一列：

![条形图](/help/assets/ai-asst-result4.png)

### 示例 4

最后我们来看看按产品类别划分的收入。

**提示词：**&#x200B;在提示词窗口中输入&#x200B;*“按产品类别划分的收入比例”。*

**响应：**&#x200B;同样，Data Insights Agent选择最合适的可视化图表（在本例中为&#x200B;**[!UICONTROL 圆环图]**&#x200B;可视化图表）来回答问题。

![环形图](/help/assets/ai-asst-result3.png)

## 数据可视化图表提示词示例

以下是常见提示的一些示例以及Data Insights Agent用于响应这些提示的可视化图表。

| 提示词示例 | 预期的可视化图表 |
| --- | --- |
| 显示[各月]的利润 | 线形图<p>默认情况下，询问特定时间范围内的趋势或量度时会返回一个可视化线性图。 |
| [各月]订单趋势 | 线形图 |
| 显示[各月]各地区的收入 | 条形图 |
| 按产品类别划分的收入比例 | 环形图 |
| 1 月至 5 月一周中各天的订单 | 条形图 |
| 显示 3 月到 6 月不同性别的订单 | 条形图 |
| 2 月到 5 月各 SKU 的利润是多少 | 条形图 |
| [各月]按商店名称划分的收入 | 条形图 |
| 按[月]利润计算，我的前 10 名 SKU 是哪些？ | 条形图 |
| 一年中各月的购买比例 | 环形图 |
| [月]总利润 | 摘要数字<p>询问特定时间范围内某个量度的“总数”应该返回一个摘要数字可视化图表。 |


## 提示词最佳实践

Data Insights Agent会处理每个用户提示提供的上下文，并尝试以自由格式表形式智能地响应最合适的可视化和组件。

回答可能会因提示词中使用的具体单词和短语而有所不同，语言的细微变化可能会导致不同的结果。

为了获得最佳结果，请考虑以下原则：

* **具体：**&#x200B;包含精确术语以缩小响应范围。 以下是一个特定提示示例：“上月在加利福尼亚的销售额”

* **使用清晰的量度、维度和区段：**&#x200B;添加特定的量度（如“收入”）、维度（如“网站名称”）、区段(如“iPhone用户”)和日期范围（如“过去三个月”）有助于Data Insights Agent关注正确的数据。

* **直接提问：**&#x200B;使用措辞提问可让Data Insights Agent更轻松地提供清晰、相关的见解。 下面是一个在提示中直接提出问题的示例：“按产品类别列出的今年平均收入是多少？”

请查看下表，了解可在Data Insights Agent的提示中使用的示例术语和短语，以及可期待的响应类型。

这些示例旨在帮助您了解特定字词或结构如何影响Data Insight Agent的输出，从而确保更精确、更有价值的洞察。 Data Insights Agent使用创作AI，因此可视化图表或选定的数据可能会在类似提示中略有不同。

| 期望的结果 | 术语和短语示例 |
| --- | --- |
| 摘要数字可视化图表 | <ul><li>合计</li></ul> |
| 比较组件 | <ul><li>比较</li><li>VS</li><li>对比度</li><li>每周</li><li>月度环比</li><li>季度环比</li><li>年度同比</li></ul> |
| 环形图可视化图表 | <ul><li>比例</li><li>份额</li><li>分布</li><li>百分比</li><li>贡献</li><li>部分</li><li>部分</li></ul> |
| 线形图可视化图表 | <ul><li>趋势</li><li>[时间范围]内的[量度]</li></ul> |
| 条形图可视化图表 | <ul><li>按[维度]的[量度]</li></ul> |

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

