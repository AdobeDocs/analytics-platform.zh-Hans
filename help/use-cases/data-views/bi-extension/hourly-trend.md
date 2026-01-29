---
title: 每小时趋势
description: Customer Journey Analytics中各种BI工具中BI扩展的每小时趋势用例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 每小时趋势


## 每小时趋势

在此使用案例中，您要显示一个表格和简单的折线图可视化图表，其中显示2023年1月1日发生次数（事件）的每小时趋势。

+++ Customer Journey Analytics

用例的&#x200B;**[!UICONTROL 每小时趋势]**&#x200B;面板示例：

![Customer Journey Analytics小时趋势可视化图表](../assets/cja_hourly_trend.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>请确保已验证[连接是否成功，可以列出数据视图，并为要为其尝试此用例的BI工具使用数据视图](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **不**&#x200B;了解如何处理日期时间字段，因此不支持&#x200B;**[!UICONTROL daterangehour]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute]**&#x200B;等维度。

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并指定句点`01/01/2023` - `02/01/2023`。

      ![Tableau桌面筛选器](../assets/uc3-tableau-filter.png)

   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖放&#x200B;**[!UICONTROL Daterangehour]**，并将条目拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁边的字段中。
      * 从&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL More]** > **[!UICONTROL Hours]**，以便将该值更新为&#x200B;**[!UICONTROL HOUR(Daterangeday)]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 发生次数]**，并将条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。 该值会自动转换为&#x200B;**[!UICONTROL SUM（发生次数）]**。
   1. 从工具栏的&#x200B;**[!UICONTROL 适应]**&#x200B;下拉菜单将&#x200B;**[!UICONTROL 标准]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的Tableau桌面应该如下所示。

      ![Tableau桌面图形](../assets/uc3-tableau-graph.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Graph`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 确保已选择&#x200B;**[!UICONTROL 数据]**&#x200B;工作表。 在&#x200B;**[!UICONTROL 数据]**&#x200B;视图中：
   1. 选择右上角的&#x200B;**[!UICONTROL 向我显示]**&#x200B;并选择&#x200B;**[!UICONTROL 文本表]**（左上角可视化图表）以将数据视图的内容修改为表。
   1. 将&#x200B;**[!UICONTROL HOUR(Daterangeday)]**&#x200B;从&#x200B;**[!UICONTROL 列]**&#x200B;拖到&#x200B;**[!UICONTROL 行]**。
   1. 从工具栏的&#x200B;**[!UICONTROL 适应]**&#x200B;下拉菜单将&#x200B;**[!UICONTROL 标准]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的Tableau桌面应该如下所示。

      ![Tableau桌面数据](../assets/uc3-tableau-data.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL Graph]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 图形]**&#x200B;工作表下的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中。
   1. 选择视图中的&#x200B;**[!UICONTROL 数据]**&#x200B;工作表，并将&#x200B;**[!UICONTROL 整个视图]**&#x200B;修改为&#x200B;**[!UICONTROL 固定宽度]**。

      您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

      ![Tableau桌面功能板1](../assets/uc3-tableau-dashboard.png)


>[!TAB Looker]


1. 在Looker的&#x200B;**[!UICONTROL 浏览]**&#x200B;界面中，确保您拥有干净的设置。 如果不是，请选择![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 删除字段和筛选器]**。
1. 选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;下的&#x200B;**[!UICONTROL +筛选器]**。
1. 在&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;对话框中：
   1. 选择&#x200B;**[!UICONTROL ‣抄送数据视图]**
   1. 从字段列表中，选择&#x200B;**[!UICONTROL 日‣间范围日期]**，然后选择&#x200B;**[!UICONTROL 日期范围日期]**。
      ![Looker筛选器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc数据视图日期范围日期]**&#x200B;筛选器，因为&#x200B;**[!UICONTROL 在]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 之前]** **[!UICONTROL 2023/01/02]**&#x200B;的范围内。
1. 从左边栏中的&#x200B;**[!UICONTROL 抄送数据视图]**&#x200B;部分，
   1. 从‣**[!UICONTROL DIMENSIONS]**&#x200B;的列表中选择&#x200B;**[!UICONTROL Daterangehour Date]**，然后选择&#x200B;**[!UICONTROL Time]**。
   1. 在左边栏（底部）中选择&#x200B;**[!UICONTROL MEASURES]**&#x200B;下的&#x200B;**[!UICONTROL 计数]**。
1. 选择&#x200B;**[!UICONTROL 运行]**。
1. 选择‣**[!UICONTROL 可视化图表]**&#x200B;以显示折线图可视化图表。

您应该会看到如下所示的可视化图表和表格。

![Looker结果每日趋势](../assets/uc3-looker-result.png)


>[!TAB Jupyter笔记本]

1. 在新单元格中输入以下语句。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. 执行单元格。 您应该会看到类似于以下屏幕快照的输出。

   ![Jupyter笔记本结果](../assets/uc3-jupyter-results.png)


>[!TAB RStudio]

1. 在新块中输入以下介于` ` ``{r} `和` `` ` `之间的语句。

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. 运行块。 您应该会看到类似于以下屏幕快照的输出。

   ![RStudio结果](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
