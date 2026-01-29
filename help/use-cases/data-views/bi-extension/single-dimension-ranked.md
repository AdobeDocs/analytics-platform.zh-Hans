---
title: 单个Dimension排名
description: 在Customer Journey Analytics的各种BI工具中，BI扩展的单维度排名用例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 1%

---

# 单个维度排名


在此使用案例中，您希望显示一个表格和简单的条形图可视化图表，其中显示产品名称在2023年的购买和购买收入。

+++ Customer Journey Analytics

用例的&#x200B;**[!UICONTROL 单个Dimension排名]**&#x200B;面板示例：

![Customer Journey Analytics单个维度排名可视化图表](../assets/cja-single-dimension-ranked.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>请确保已验证[连接是否成功，可以列出数据视图，并为要为其尝试此用例的BI工具使用数据视图](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

1. 在&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中：
   1. 选择&#x200B;**[!UICONTROL 日期范围]**。
   1. 选择&#x200B;**[!UICONTROL 产品名称]**。
   1. 选择&#x200B;**[!UICONTROL sum purchase_revenue]**。
   1. 选择&#x200B;**[!UICONTROL 购买总和]**。

   您会看到一个空表，其中仅显示选定元素的列标题。 为了获得更好的可见性，请放大可视化图表。

1. 在&#x200B;**[!UICONTROL 筛选器]**&#x200B;窗格中：

   1. 从该视觉对象上的&#x200B;**[!UICONTROL 筛选器中选择]**&#x200B;日期范围是（全部）**&#x200B;**。
   1. 选择&#x200B;**[!UICONTROL 相对日期]**&#x200B;作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 当值]** **[!UICONTROL 在最后]** `1` **[!UICONTROL 日历年]**&#x200B;内时显示项。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

   您会看到使用应用的&#x200B;**[!UICONTROL 日期范围]**&#x200B;筛选器更新的表。

1. 在&#x200B;**[!UICONTROL 可视化图表]**&#x200B;窗格中：

   1. 使用![CrossSize75](/help/assets/icons/CrossSize75.svg)从&#x200B;**[!UICONTROL 列]**&#x200B;中删除&#x200B;**[!UICONTROL 日期范围]**。
   1. 将&#x200B;**[!UICONTROL Sum of purchases_revenue]**&#x200B;拖放到&#x200B;**[!UICONTROL 列]**&#x200B;中的&#x200B;**[!UICONTROL Sum of purchases]**&#x200B;下。

1. 在“表”可视化图表上：

   1. 选择&#x200B;**[!UICONTROL Sum of purchase_revenue]**&#x200B;以按降序采购收入顺序对产品名称排序。 您的Power BI桌面应该如下所示。

   ![Power BI桌面用例5表状态](../assets/uc5-pbi-table.png)

1. 在&#x200B;**[!UICONTROL 筛选器]**&#x200B;窗格中：

   1. 选择&#x200B;**[!UICONTROL product_name is (All)]**。
   1. 将&#x200B;**[!UICONTROL 筛选器类型]**&#x200B;设置为&#x200B;**[!UICONTROL 前N]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 按值]**&#x200B;显示项目&#x200B;**&#x200B;**&#x200B;前`10` **&#x200B;**。
   1. 将&#x200B;**[!UICONTROL purchase_revenue]**&#x200B;拖放到&#x200B;**[!UICONTROL By值]**&#x200B;中&#x200B;**[!UICONTROL 在此处添加数据字段]**。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

   您会看到该表与Analysis Workspace中的自由格式表可视化图表同步更新了购买收入值。

1. 在&#x200B;**[!UICONTROL 可视化图表]**&#x200B;窗格中：

   1. 选择&#x200B;**[!UICONTROL 折线图和栈叠柱状图]**&#x200B;可视化图表。

   使用与表相同的数据时，折线图和栈叠式柱状图可视化会替换表。

1. 将&#x200B;**[!UICONTROL 购买]**&#x200B;拖放到&#x200B;**[!UICONTROL 可视化图表]**&#x200B;窗格中的&#x200B;**[!UICONTROL 行Y轴]**&#x200B;上。

   更新了折线图和栈叠式柱状图。 您的Power BI桌面应该如下所示。

   ![Power BI桌面用例5图表](../assets/uc5-pbi-chart.png)

1. 在折线图和栈叠式柱状图可视化图表上：

   1. 选择![更多](/help/assets/icons/More.svg)。
   1. 从上下文菜单中，选择&#x200B;**[!UICONTROL 显示为表]**。

   主视图已更新以显示折线图可视化图表和表格。

   ![Power BI桌面用例2最终每日趋势可视化图表](../assets/uc5-pbi-final.png)

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并指定句点`01/01/2023` - `31/12/2023`。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。

      ![Tableau桌面筛选器](../assets/uc5-tableau-filter.png)

   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 产品名称]**，并将该条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 购买]**，并将条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。 该值会自动转换为&#x200B;**[!UICONTROL SUM（购买）]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 购买收入]**，并将条目拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁的字段中，该字段来自&#x200B;**[!UICONTROL SUM（购买）]**。 该值会自动转换为&#x200B;**[!UICONTROL SUM（采购收入）]**。
   1. 要按降序排列两个图表，请将鼠标悬停在&#x200B;**[!UICONTROL 采购收入]**&#x200B;标题上并选择排序图标。
   1. 要限制图表中的条目数，请在&#x200B;**[!UICONTROL 行]**&#x200B;中选择&#x200B;**[!UICONTROL SUM(Purchase Revenue)]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 筛选器]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[Purchase Revenue\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 值范围]**&#x200B;并输入相应的值。 例如： `1,000,000` - `2,000,000`。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。
   1. 若要将两个条形图转换为双组合图，请在&#x200B;**[!UICONTROL 行]**&#x200B;中选择&#x200B;**[!UICONTROL SUM（购买）]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 双轴]**。 条形图转换为散点图。
   1. 要将散点图修改为条形图，请执行以下操作：
      1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;区域中选择&#x200B;**[!UICONTROL SUM（购买）]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 行]**。
      1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;区域中选择&#x200B;**[!UICONTROL SUM(Purchase Revenue)]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 栏]**。

   您的Tableau桌面应该如下所示。

   ![Tableau桌面图形](../assets/uc5-tableau-graph.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Graph`。
1. 确保已选择&#x200B;**[!UICONTROL 数据]**&#x200B;工作表。
   1. 选择右上角的&#x200B;**[!UICONTROL 向我显示]**&#x200B;并选择&#x200B;**[!UICONTROL 文本表]**（左上角可视化）以将两个图表的内容修改为表格。
   1. 若要按降序对采购收入排序，请将指针悬停在表中的&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;上，然后选择![SortOrderDown](/help/assets/icons/SortOrderDown.svg)。
   1. 从&#x200B;**[!UICONTROL 适合]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 整个视图]**。

   您的Tableau桌面应该如下所示。

   ![Tableau桌面数据](../assets/uc5-tableau-data.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL Graph]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 图形]**&#x200B;工作表下的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中。
   1. 选择视图中的&#x200B;**[!UICONTROL 数据]**&#x200B;工作表，并将&#x200B;**[!UICONTROL 整个视图]**&#x200B;修改为&#x200B;**[!UICONTROL 固定宽度]**。

   您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

   ![Tableau桌面功能板1](../assets/uc5-tableau-dashboard.png)



>[!TAB Looker]

1. 在Looker的&#x200B;**[!UICONTROL 浏览]**&#x200B;界面中，确保您拥有干净的设置。 如果不是，请选择![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 删除字段和筛选器]**。
1. 选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;下的&#x200B;**[!UICONTROL +筛选器]**。
1. 在&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;对话框中：
   1. 选择&#x200B;**[!UICONTROL ‣抄送数据视图]**
   1. 从字段列表中，选择&#x200B;**[!UICONTROL 日‣间范围日期]**，然后选择&#x200B;**[!UICONTROL 日期范围日期]**。
      ![Looker筛选器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc数据视图日期范围日期]**&#x200B;筛选器，因为&#x200B;**[!UICONTROL 在]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 之前]** **[!UICONTROL 2024/01/01]**&#x200B;的范围内。
1. 从左边栏中的&#x200B;**[!UICONTROL ‣ Cc数据视图]**&#x200B;部分，选择&#x200B;**[!UICONTROL 产品名称]**。
1. 在左边栏的&#x200B;**[!UICONTROL ‣自定义字段]**&#x200B;部分中：
   1. 从&#x200B;**[!UICONTROL +添加]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 自定义度量值]**。
   1. 在&#x200B;**[!UICONTROL 创建自定义度量值]**&#x200B;对话框中：
      1. 从&#x200B;**[!UICONTROL 要度量]**&#x200B;的字段下拉菜单中选择&#x200B;**[!UICONTROL 购买收入]**。
      1. 从&#x200B;**[!UICONTROL 度量值类型]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Sum]**。
      1. 输入&#x200B;**[!UICONTROL 名称]**&#x200B;的自定义字段名称。 例如：`Purchase Revenue`。
      1. 选择&#x200B;**[!UICONTROL 字段详细信息]**&#x200B;选项卡。
      1. 从&#x200B;**[!UICONTROL 格式]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 小数]**，并确保以`0`小数&#x200B;**[!UICONTROL 输入]**。
         ![Looker自定义量度字段](../assets/uc5-looker-customfield.png)
      1. 选择&#x200B;**[!UICONTROL 保存]**。
   1. 从&#x200B;**[!UICONTROL +添加]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 自定义度量值]**。 在&#x200B;**[!UICONTROL 创建自定义]**&#x200B;度量值对话框中：
      1. 从&#x200B;**[!UICONTROL 要度量]**&#x200B;的字段下拉菜单中选择&#x200B;**[!UICONTROL 购买]**。
      1. 从&#x200B;**[!UICONTROL 度量值类型]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Sum]**。
      1. 输入&#x200B;**[!UICONTROL 名称]**&#x200B;的自定义字段名称。 例如：`Sum of Purchases`。
      1. 选择&#x200B;**[!UICONTROL 字段详细信息]**&#x200B;选项卡。
      1. 从&#x200B;**[!UICONTROL 格式]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 小数]**，并确保以`0`小数&#x200B;**[!UICONTROL 输入]**。
      1. 选择&#x200B;**[!UICONTROL 保存]**。
   1. 这两个字段都会自动添加到数据视图。
1. 选择&#x200B;**[!UICONTROL +筛选器]**&#x200B;以添加其他&#x200B;**[!UICONTROL 筛选器]**&#x200B;并限制数据。
1. 在&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL ‣自定义字段]**，然后选择&#x200B;**[!UICONTROL 购买收入]**。
1. 进行适当的选择并输入建议值，以使筛选器显示为&#x200B;**[!UICONTROL 介于]** `1000000` **[!UICONTROL 和]** `2000000`之间。
1. 选择&#x200B;**[!UICONTROL 运行]**。
1. 选择‣**[!UICONTROL 可视化图表]**&#x200B;以显示折线图可视化图表。
1. 选择&#x200B;**[!UICONTROL 可视化图表]**&#x200B;中的&#x200B;**[!UICONTROL 编辑]**&#x200B;以更新可视化图表。 在弹出的对话框中：
   1. 选择&#x200B;**[!UICONTROL 系列]**&#x200B;选项卡。
   1. 向下滚动以查看&#x200B;**[!UICONTROL 购买]**&#x200B;并将&#x200B;**[!UICONTROL 类型]**&#x200B;更改为&#x200B;**[!UICONTROL 行]**。
   1. 选择&#x200B;**[!UICONTROL Y]**&#x200B;选项卡。
   1. 将&#x200B;**[!UICONTROL 购买]**&#x200B;从&#x200B;**[!UICONTROL 左1]**&#x200B;容器拖动到显示&#x200B;**[!UICONTROL *将系列拖动到此处以创建新的左轴&#x200B;*]**。 此操作创建&#x200B;**[!UICONTROL &#x200B; Left 2 &#x200B;]**&#x200B;容器。
      ![Looker可视化图表配置](../assets/uc5-looker-visualization.png)
   1. 选择![编辑](/help/assets/icons/CrossSize75.svg)旁边的&#x200B;**[!UICONTROL CrossSize75]**&#x200B;以隐藏弹出对话框

您应该会看到如下所示的可视化图表和表格。

![Looker结果每日趋势](../assets/uc5-looker-result.png)


>[!TAB Jupyter笔记本]

1. 在新单元格中输入以下语句。

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. 执行单元格。 您应该会看到类似于以下屏幕快照的输出。

   ![Jupyter笔记本结果](../assets/uc5-jupyter-results.png)


>[!TAB RStudio]

1. 在新块中输入以下介于` ` ``{r} `和` `` ` `之间的语句。

   ```R
   library(tidyr)
   
   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. 运行块。 您应该会看到类似于以下屏幕快照的输出。

   ![RStudio结果](../assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

