---
title: 对非重复值维度计数
description: 在Customer Journey Analytics的各种BI工具中，计算BI扩展的不同值维度用例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 0%

---

# 对非重复值维度计数


在此使用案例中，您希望获取2023年1月期间报告的不同数量的产品名称。

+++ Customer Journey Analytics

要报告产品名称的非重复计数，请在Customer Journey Analytics中设置一个计算量度，**[!UICONTROL 标题]** `Product Name (Count Distinct)`和&#x200B;**[!UICONTROL 外部ID]** `product_name_count_distinct`。

![Customer Journey Analytics产品名称（Distincr计数）计算量度](../assets/cja-calc-metric-distinct-count-product-names.png)

然后，您可以在用例的示例&#x200B;**[!UICONTROL 计算不同Dimension值]**&#x200B;面板中使用该量度：

![Customer Journey Analytics非重复计数值](../assets/cja-count-distinct-dimension-values.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>请确保已验证[连接是否成功，可以列出数据视图，并为要为其尝试此用例的BI工具使用数据视图](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

1. 为确保日期范围适用于所有可视化图表，请将&#x200B;**[!UICONTROL daterangeday]**&#x200B;从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格拖放到此页上的&#x200B;**[!UICONTROL 筛选器]**&#x200B;上。
   1. 从该页面上的&#x200B;**[!UICONTROL 筛选器中选择]** daterangeday is (All)****。
   1. 选择&#x200B;**[!UICONTROL 高级筛选]**&#x200B;作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 当值]** **[!UICONTROL 在]** `1/1/2023` **[!UICONTROL 和]** **[!UICONTROL 在]** `2/1/2023`之前或之后时显示项。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

1. 在&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中：
   1. 选择&#x200B;**[!UICONTROL datarangeday]**。
   1. 选择&#x200B;**[!UICONTROL sum cm_product_name_count_distinct]**，它是Customer Journey Analytics中定义的计算指标。

1. 若要将垂直条形图修改为表，请确保已选定该图表，并从&#x200B;**[!UICONTROL 可视化]**&#x200B;窗格中选择&#x200B;**[!UICONTROL 表]**。

   您的Power BI桌面应该如下所示。

   ![Power BI桌面多个非重复计数表](../assets/uc7-powerbi-table.png)

1. 选择表可视化图表。 从上下文菜单中，选择&#x200B;**[!UICONTROL 复制]** > **[!UICONTROL 复制视觉对象]**。
1. 使用&#x200B;**[!UICONTROL ctrl-v]**&#x200B;粘贴可视化图表。 可视化图表的精确副本与原始副本重叠。 将其移动到报表区域的右侧。
1. 若要将复制的可视化图表从表修改为卡片，请从&#x200B;**[!UICONTROL 可视化图表]**&#x200B;中选择&#x200B;**[!UICONTROL 卡片]**。

   您的Power BI桌面应该如下所示。

   ![Power BI桌面多个非重复计数表](../assets/uc7-powerbi-final.png)

或者，您可以使用Power BI中的不同计数功能。

1. 选择&#x200B;**[!UICONTROL product_name]**&#x200B;维度。
1. 对&#x200B;**[!UICONTROL 列]**&#x200B;中的&#x200B;**[!UICONTROL product_name]**&#x200B;维度应用&#x200B;**[!UICONTROL Count (Distinct)]**&#x200B;函数。

   ![非重复Power BI计数](../assets/uc7-powerbi-alternative.png)



>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**，然后选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**，然后选择`01/01/2023` - `31/1/2023`。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。
   1. 将&#x200B;**[!UICONTROL Cm Product Name Count Distinct]**&#x200B;拖至&#x200B;**[!UICONTROL 行]**。 该值更改为&#x200B;**[!UICONTROL SUM(Cm Product Name Count Distinct)]**。 此字段是您在Customer Journey Analytics中定义的计算指标。
   1. 将&#x200B;**[!UICONTROL Daterangeday]**&#x200B;拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁边。 选择&#x200B;**[!UICONTROL Daterangeday]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL Day]**。
   1. 若要将折线图可视化图表修改为表格，请从&#x200B;**[!UICONTROL 显示我]**&#x200B;中选择&#x200B;**[!UICONTROL 文本表格]**。
   1. 从工具栏中选择&#x200B;**[!UICONTROL 交换行和列]**。
   1. 从&#x200B;**[!UICONTROL 适合]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 适合宽度]**。

      您的Tableau桌面应该如下所示。

      ![Tableau Desktop Multiple Dimension排名过滤器](../assets/uc7-tableau-data.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Card`。

1. 确保您已选择&#x200B;**[!UICONTROL 卡片]**&#x200B;视图。
1. 选择&#x200B;**[!UICONTROL DAY(Daterangeday)]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 月]**。 值更改为&#x200B;**[!UICONTROL MONTH(Daterangeday)]**。
1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;中选择&#x200B;**[!UICONTROL SUM(Cm Product Name Count Distinct)]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 格式]**。
1. 若要更改字体大小，请在&#x200B;**[!UICONTROL Format SUM(CM Product Name Count Distinct)]**&#x200B;窗格中，选择&#x200B;**[!UICONTROL 默认值]**&#x200B;内的&#x200B;**[!UICONTROL 字体]**，然后选择字体大小为&#x200B;**[!UICONTROL 72]**。
1. 若要对齐数字，请选择&#x200B;**[!UICONTROL 对齐]**&#x200B;旁边的&#x200B;**[!UICONTROL 自动]**，并将&#x200B;**[!UICONTROL 水平]**&#x200B;设置为居中。
1. 若要使用整数，请选择&#x200B;**[!UICONTROL 数字]**&#x200B;旁边的&#x200B;**[!UICONTROL 123.456]**，然后选择&#x200B;**[!UICONTROL 数字（自定义）]**。 将&#x200B;**[!UICONTROL 小数位]**&#x200B;设置为`0`。

   您的Tableau桌面应该如下所示。

   ![Tableau Desktop Multiple Dimension排名过滤器](../assets/uc7-tableau-card.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL 卡片]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图的&#x200B;**[!UICONTROL 卡片]**&#x200B;工作表下。

   您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

   ![Tableau桌面功能板1](../assets/uc7-tableau-final.png)


或者，您可以使用Tableau Desktop中的非重复计数功能。

1. 使用&#x200B;**[!UICONTROL 产品名称]**，而不是&#x200B;**[!UICONTROL Cm产品名称计数Distinct]**。
1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;中的&#x200B;**[!UICONTROL 产品名称]**&#x200B;上应用&#x200B;**[!UICONTROL 度量]** > **[!UICONTROL 计数（非重复）]**。

   ![非重复表格计数](../assets/uc7-tableau-alternative.png)


>[!TAB Looker]

1. 在Looker的&#x200B;**[!UICONTROL 浏览]**&#x200B;界面中，确保您拥有干净的设置。 如果不是，请选择![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 删除字段和筛选器]**。
1. 选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;下的&#x200B;**[!UICONTROL +筛选器]**。
1. 在&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;对话框中：
   1. 选择&#x200B;**[!UICONTROL ‣抄送数据视图]**
   1. 从字段列表中，选择&#x200B;**[!UICONTROL 日‣间范围日期]**，然后选择&#x200B;**[!UICONTROL 日期范围日期]**。
      ![Looker筛选器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc数据视图日期范围日期]**&#x200B;筛选器，因为&#x200B;**[!UICONTROL 在]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 之前]** **[!UICONTROL 2023/02/01]**&#x200B;的范围内。
1. 从左边栏中的&#x200B;**[!UICONTROL ‣ Cc数据视图]**&#x200B;部分：
   1. 选择&#x200B;**[!UICONTROL 日期范围日期]**，然后选择&#x200B;**[!UICONTROL 日期]**。
   1. 从&#x200B;**[!UICONTROL 产品名称]**&#x200B;上的&#x200B;**⋮更多**&#x200B;上下文菜单中选择&#x200B;**[!UICONTROL 聚合非重复计数]**‣。
      ![Looker产品名称上下文菜单](../assets/uc7-looker-count-distinct.png)
1. 选择&#x200B;**[!UICONTROL 运行]**。
1. 选择‣**[!UICONTROL 可视化图表]**&#x200B;并从工具栏中选择6︎⃣以显示单值可视化图表。

您应该会看到如下所示的可视化图表和表格。

![非重复查找器计数](../assets/uc7-looker-result.png)


>[!TAB Jupyter笔记本]

1. 在新单元格中输入以下语句。

   ```
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. 执行单元格。 您应该会看到类似于以下屏幕快照的输出。

   ![Jupyter笔记本结果](../assets/uc7-jupyter-results.png)


>[!TAB RStudio]

1. 在新块中输入以下介于` ```{r} `和` ``` `之间的语句。

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. 运行块。 您应该会看到类似于以下屏幕快照的输出。

   ![RStudio结果](../assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++

