---
description: 如何向Customer Journey Analytics文档提出数据分析问题
title: 在Customer Journey Analytics中使用Data Insights代理可视化数据
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: bc0573b2d75a18aaaac4f5d171579e9763f2f8e0
workflow-type: tm+mt
source-wordcount: '1703'
ht-degree: 3%

---

# 在Customer Journey Analytics中使用Data Insights代理可视化数据

数据分析代理是Customer Journey Analytics中的AI助手的一部分，它是一个创新型人工智能会话代理，可快速高效地回答有关您数据的问题。 它使用数据视图中的组件并使用实际数据在Analysis Workspace中构建相关可视化图表。

使用Data Insights代理在Analysis Workspace中回答以数据为中心的问题，可以节省您原本要在Analysis Workspace中手动构建可视化并熟悉数据视图组件所花费的无数时间。

AI助手中的![数据分析代理](assets/cja-ai-asst-da.gif)

## Alpha版本的范围内与范围外功能

### Alpha内置功能

| 支持的功能 | 描述 |
| --- | --- |
| **生成并更新可视化图表** | 生成自由格式表和相关的可视化图表（例如折线图、条形图、圆环图等）。<p>示例：*从2月到5月，跨SKU的利润是多少？* |
| **支持的可视化图表类型** | <ul><li>线形图</li><li>多行</li><li>自由格式表</li><li>条形图</li><li>圆环图</li><li>摘要数字</li></ul> |
| **范围外提示检测** | 如果您提交了一个超出范围的提示，如“导出此项目”，助理会告知您问题超出范围。 |
| **澄清问题** | 如果您提的问题没有足够上下文可供数据分析代理回答，或者过于宽泛，数据分析代理会使用澄清问题或建议的选项进行响应。 示例： <p>**组件**<ul><li>量度：*您指的是哪个“收入”量度？*</li><li>Dimension：*您想关注以下“地区”中的哪一个？*</li><li>筛选器：*您要应用哪个“帐户”筛选器？*</li><li>日期范围： *对于“上个月”，您是指“上个月”还是“最近30天”？*</li></ul>**Dimension项目**：您指的是哪个“商店名称”？ (例如，存储#5274、存储#2949等。) |
| **多圈** | 数据分析代理使用任何之前提示中的上下文对提示做出响应，允许用户更新可视化图表并询问后续问题。 示例： <ul><li>提示1：*从3月开始的趋势事件。*</li><li>提示2： *改为向我显示从3月到4月的数据*</li></ul> |
| **可验证性** | 通过生成的自由格式表和数据可视化，可以验证数据的可验证性和正确性。 例如，如果用户在上月&#x200B;*询问*&#x200B;趋势订单，您可以确认在新生成的面板、数据可视化和自由格式表中选择了正确的量度（“订单”）和日期范围（“上个月”）。 |
| **反馈** | <ul><li>竖起大拇指</li><li>拇指朝下</li><li>标志</li></ul> |

### 范围外的Beta功能

| 不支持的功能 | 描述 |
| --- | --- |
| **内联摘要或响应** | 数据分析代理无法在聊天边栏中以用户提示的摘要答案进行内联响应。 范围外提示示例：<ul><li>*给我上一个提示的见解摘要。*</li><li>*从折线图可视化图表摘要突出显示内容。*</li></ul> |
| **澄清问题** | 澄清问题仅限于组件和维度项目。 数据分析代理无法明确数据视图、可视化图表、数据粒度、比较和范围等内容。 当无法使用澄清问题时，助理将默认使用您最可能要求的内容。 如果它返回意外的可视化或数据粒度，您随后可以使用多圈/更新功能调整可视化图表和数据。 |
| **Workspace操作/功能** | 除了构建和更新可视化图表之外，数据分析代理无法对Workspace中的用户执行操作。 例如，它不能执行以下任何操作：<ul><li>上下文操作UI按钮（添加到图表、新面板、新表）</li><li>共享</li><li>导出</li><li>下载</li><li>管理用户首选项</li><li>策划</li><li>管理数据视图</li><li>Analytics功能板应用程序</li><li>归因</li></ul> |
| **不支持的可视化图表类型** | <ul><li>流量</li><li>流失</li><li>同类群组表</li><li>面积图，栈叠的面积图</li><li>堆叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图、栈叠的水平条形图</li><li>关键量度摘要</li><li>散点图</li><li>概要变化</li><li>文本</li><li>树状图</li><li>维恩图</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## AI助手中的访问和数据分析代理

1. 转到[experience.adobe.com](https://experience.adobe.com/)并使用Adobe ID登录。

2. 从Experience Cloud主页中选择&#x200B;**Customer Journey Analytics**。

3. 在项目页面顶部的横幅中选择&#x200B;**[!UICONTROL 空白项目]**&#x200B;以打开一个新的空白项目。

4. 确保为面板选择的数据视图与为Beta测试启用数据分析代理的数据视图相同。

   如果您不确定，请联系Beta Slack渠道。

5. 选择页面右上角的AI Assistant聊天图标。

   如果您看不到聊天图标，请联系您的管理员，以便管理员在Admin Console中启用以下功能：

   * **[!UICONTROL AI助手：产品知识]**

   * **[!UICONTROL AI助手：数据分析]**

   有关其他详细信息，管理员可以看到[这些说明](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access)。

   ![AI助手图标](/help/assets/ai-asst-icon.png)

6. 在页面底部的&#x200B;**[!UICONTROL 关于Customer Journey Analytics]**&#x200B;对话框中，在AI助手中询问数据可视化问题。

   有关更多信息，请参阅以下示例。

### 示例 1

例如，假设您对您的企业在7月份收到的订单感兴趣。

**提示：**&#x200B;输入&#x200B;*“7月份的趋势订单”。*

![AI提示](/help/assets/ai-asst-prompt1.png)

**响应：** AI Assistant中的数据分析代理通过查看数据视图中的数据（包括量度和组件）来收集分析。 它会将提示转换为数据范围内正确的维度和量度。

如您所见，它会自动生成一个线形图和一个自由格式表来显示7月的订单。

![提示答案 — 折线图和自由格式表](/help/assets/ai-asst-result.png)

### 示例 2

接下来，您需要查看收入在不同地区的比较情况。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按地区显示收入”*。

**响应：** AI Assistant中的数据分析代理智能地理解了“区域”的含义，即“客户区域”。 该报表会生成一个条形图，其中按地区显示收入的情况最好：

![条形图](/help/assets/ai-asst-result2.png)

### 示例 3

接下来，除了按地区了解收入之外，您还需要按地区查看利润数据。 您可以要求AI助手更新最新的可视化图表和自由格式表，而不是重复之前的提示。

**提示：**&#x200B;在提示窗口中，键入&#x200B;*“添加利润”*。

**响应：** **[!UICONTROL 条形]**&#x200B;图表仍提供最简洁的答案，但利润指标已添加为自由格式表中的列：

![条形图](/help/assets/ai-asst-result4.png)

### 示例 4

最后，我们来了解一下按产品类别划分的收入。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按产品类别列出的收入比例”。*

**响应：**&#x200B;同样，AI Assistant中的数据分析代理选择最合适的可视化图表（在本例中为&#x200B;**[!UICONTROL 圆环图]**&#x200B;可视化图表）来回答问题。

![圆环图](/help/assets/ai-asst-result3.png)

## 示例数据可视化提示

以下是常见提示和数据分析代理用于响应这些提示的一些可视化图表示例。

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

数据分析代理会处理每个用户提示提供的上下文，并尝试以自由格式表形式智能地响应最合适的可视化和组件。

响应可能会因提示中使用的具体字词和短语而异，语言的细微变化可能会导致不同的结果。

要获得最佳结果，请考虑以下准则：

* 具体说明：包含确切的术语以缩小响应范围。 以下是一个特定提示示例：“上月在加利福尼亚的销售额”

* 使用清晰的量度和过滤器：添加特定量度（如“收入”）、维度（如“网站名称”）、过滤器(如“iPhone用户”)和日期范围（如“过去三个月”），可帮助数据分析代理重点关注正确的数据。

* 提出直接问题：用措辞直接表示问题更便于数据见解代理提供清晰、相关的见解。 下面是一个在提示中直接提问的示例：“按产品类别列出的今年平均收入是多少？”

请查看下表，了解可在AI助手中的数据分析代理的提示中使用的术语和短语示例，以及可期待的响应类型。

这些示例旨在帮助您了解特定词语或结构如何影响AI助理的输出，从而确保更精确、更有价值的见解。 AI Assistant中的数据分析代理使用创作AI，因此可视化图表或选定的数据可能会在相似提示中略有不同。

| 预期结果 | 术语和短语示例 |
| --- | --- |
| 概要数字可视化 | <ul><li>合计</li></ul> |
| 比较组件 | <ul><li>比较</li><li>对比</li><li>对比度</li><li>每周</li><li>月同比</li><li>季度环比</li><li>年份</li></ul> |
| 圆环图可视化图表 | <ul><li>比例</li><li>共享</li><li>分布</li><li>百分比</li><li>贡献</li><li>部分</li><li>部分</li></ul> |
| 折线图可视化图表 | <ul><li>趋势</li><li>在[时间范围]内的[指标]</li></ul> |
| 条形图可视化 | <ul><li>[Dimension]的[指标]</li></ul> |

## Beta测试客户期望并请求反馈

提出每个问题后，请仔细查看助理提供的答案。 在提供反馈之前全面评估生成的可视化图表至关重要。

在AI助手中评估来自数据分析代理的响应时，请考虑以下事项：

* 聊天边栏响应或模板：评估助理提供的文本响应。 根据提示的上下文，响应是否合适？

* 可视化图表：评估可视化图表。 对于您的问题，它是适当的还是预期的可视化图表？还是预期的可视化图表会不同？

* 自由格式表：评估自由格式表。 自由格式表数据是否正确？ 是否在请求时划分数据？ 应用的过滤器是您请求还是期望的过滤器？

* 错误消息/超出范围：如果提供了一般错误消息，指出问题超出范围，请提供反馈，说明您的提示是否认为超出范围的消息合适。 你的提示真的在范围之内吗？

**对于每个响应，根据响应给出竖起或竖起的缩略图。**

在向上或向下拇指选择后，请选择相关的多选反馈框。 如果要提供其他反馈，请在打开的文本框中添加注释。

## 问题和联系

* 在Alpha Slack渠道中发送问题和反馈： #cja-assistant-data-alpha
