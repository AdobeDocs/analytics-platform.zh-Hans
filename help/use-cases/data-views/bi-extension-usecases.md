---
title: Customer Journey Analytics中BI扩展的用例
description: 多个用例说明了如何在Customer Journey Analytics的各种BI工具中使用BI扩展
solution: Customer Journey Analytics
feature: Data Views
role: User
hide: true
hidefromtoc: true
source-git-commit: d65171873f68835de0628b95158f01713eaacb6b
workflow-type: tm+mt
source-wordcount: '2575'
ht-degree: 1%

---

# BI扩展用例

本文提供了多个用例，说明如何跨不同的BI工具使用BI扩展的功能。

已记录以下用例：

1. [连接并列出数据视图](#connect-and-list-data-views)。
1. [每日趋势](#daily-trend)。
1. [小时趋势](#hourly-trend)。
1. [每月趋势](#monthly-trend)。
1. [单个维度排名](#single-dimension-ranked)。
1. [多个维度排名](#multiple-dimension-ranked)。
1. [计算不同的维度值](#count-distinct-dimension-values)。
1. [使用日期范围名称进行筛选](#use-date-range-names-to-filter)。
1. [使用筛选器名称来筛选](#use-filter-names-to-filter)。
1. [使用维度值筛选](#use-dimension-values-to-filter)。
1. [排序](#sort)。
1. [限制](#limits)。
1. [是否拼合](#to-flatten-or-not)。
1. [Dimension和度量转换](#dimension-and-metric-transformations)。
1. [可视化图表和交互](#visualizations-and-interactions)。

对于每个用例，**详细信息**&#x200B;部分中的以下BI工具都有相关说明：

* Power BI台式机(2.136.1478.0版64位（2024年9月）)
* Tableau台式机(2024.1.5版(20241.24.0705.0334) 64位)

该说明引用了一个名为&#x200B;**[!UICONTROL public.cc_data_view]**&#x200B;的示例数据视图、两个示例维度（**[!UICONTROL 产品名称]**&#x200B;和&#x200B;**[!UICONTROL 产品类别]**）和两个示例量度（**[!UICONTROL 购买]**&#x200B;和&#x200B;**[!UICONTROL 购买收入]**）。 按照相关说明进行操作，并根据需要修改特定环境的这些示例对象。


## 连接并列出数据视图

此用例设置从BI工具到Customer Journey Analytics的连接，并列出可用于成功测试连接的数据视图。

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

1. 从Experience Platform查询服务UI访问所需的凭据和参数。

   1. 导航到您的Experience Platform沙盒。
   1. 从左边栏中选择![查询](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查询]**。
   1. 在&#x200B;**[!UICONTROL 查询]**&#x200B;界面中选择&#x200B;**[!UICONTROL 凭据]**&#x200B;选项卡。
   1. 从&#x200B;**[!UICONTROL 数据库]**&#x200B;下拉菜单中选择`prod:cja`。

      ![查询服务凭据](assets/queryservice-credentials.png)

1. 打开Power BI桌面。
1. 从主界面中选择&#x200B;**[!UICONTROL 从其他源获取数据]**。
1. 在&#x200B;**[!UICONTROL 获取数据]**对话框中：
   ![PowerBI PostgreSQL数据库](assets/powerbi-postgresql.png)
   1. 搜索并选择&#x200B;**[!UICONTROL PostgreSQL数据库]**。
   1. 选择&#x200B;**[!UICONTROL 连接]**。
1. 在&#x200B;**[!UICONTROL PostgreSQL数据库]**对话框中：
   ![PowerBI桌面服务器和数据库设置](assets/powerbi-serverdatabase.png)
   1. 使用![复制](/help/assets/icons/Copy.svg)从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;中复制并粘贴&#x200B;**[!UICONTROL 主机]**&#x200B;和&#x200B;**[!UICONTROL 端口]**&#x200B;值，用`:`隔开，作为&#x200B;**[!UICONTROL 服务器]**&#x200B;的值。 例如：`examplecompany.platform-query.adobe.io:80`。
   1. 使用![复制](/help/assets/icons/Copy.svg)从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;中复制并粘贴&#x200B;**[!UICONTROL 数据库]**&#x200B;值。 将`?FLATTEN`添加到您粘贴的值。 例如，`prod:cja?FLATTEN`。
   1. 选择&#x200B;**[!UICONTROL DirectQuery]**&#x200B;作为[!UICONTROL 数据连接模式]。
   1. 选择&#x200B;**[!UICONTROL 确定]**。
1. 在&#x200B;**[!UICONTROL PostgreSQL数据库]** - **[!UICONTROL 数据库]**对话框中：
   ![PowerBI桌面用户和密码](assets/powerbi-userpassword.png)
   1. 使用![复制](/help/assets/icons/Copy.svg)从&#x200B;**[!UICONTROL 用户名]**&#x200B;和&#x200B;**[!UICONTROL 密码]**&#x200B;字段中的Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;面板中复制&#x200B;**[!UICONTROL 用户名]**&#x200B;和&#x200B;**[!UICONTROL 密码]**&#x200B;值。 如果您使用的是[不会过期的凭据](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect)，请使用不会过期的凭据的密码。
   1. 确保&#x200B;**[!UICONTROL 选择要将这些设置应用到]**&#x200B;的级别的下拉菜单设置为您之前定义的&#x200B;**[!UICONTROL 服务器]**。
   1. 选择&#x200B;**[!UICONTROL 连接]**。
1. 在&#x200B;**[!UICONTROL 导航器]**对话框中，将检索数据视图。 此检索可能需要一些时间。 检索后：
   ![Power BIDestkop服务器加载数据](assets/powerbi-navigator-load.png)
   1. 从左侧面板的列表中选择&#x200B;**[!UICONTROL public.cc_data_view]**。
   1. 选择&#x200B;**[!UICONTROL 加载]**。
1. 一段时间后，可用的量度和维度会显示在&#x200B;**[!UICONTROL 数据]**窗格中。
   ![Power BIDestkop服务器数据已加载](assets/powerbi-navigator-loaded.png)


>[!TAB Tableau桌面]

1. 从Experience Platform查询服务UI访问所需的凭据和参数。

   1. 导航到您的Experience Platform沙盒。
   1. 从左边栏中选择![查询](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查询]**。
   1. 在&#x200B;**[!UICONTROL 查询]**&#x200B;界面中选择&#x200B;**[!UICONTROL 凭据]**&#x200B;选项卡。
   1. 从&#x200B;**[!UICONTROL 数据库]**&#x200B;下拉菜单中选择`prod:cja`。

      ![查询服务凭据](assets/queryservice-credentials.png)

1. 打开Tableau。
1. 从&#x200B;**[!UICONTROL To a Server]**&#x200B;下的左边栏中选择&#x200B;**[!UICONTROL PostgreSQL]**。 如果不可用，请选择&#x200B;**[!UICONTROL 更多……]**，然后从&#x200B;**[!UICONTROL 安装的连接器]**&#x200B;中选择&#x200B;**[!UICONTROL PostgreSQL]**。
   ![Tableau连接器](assets/tableau-connectors.png)
1. 在&#x200B;**[!UICONTROL PostgreSQL]**&#x200B;对话框的&#x200B;**[!UICONTROL 常规]**选项卡中：
   ![Tableau登录对话框](assets/tableau-signin.png)
   1. 使用![复制](/help/assets/icons/Copy.svg)将&#x200B;**[!UICONTROL 主机]**&#x200B;从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;复制并粘贴到&#x200B;**[!UICONTROL 服务器]**。
   1. 使用![复制](/help/assets/icons/Copy.svg)将&#x200B;**[!UICONTROL 端口]**&#x200B;从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;复制并粘贴到&#x200B;**[!UICONTROL 端口]**。
   1. 使用![复制](/help/assets/icons/Copy.svg)将&#x200B;**[!UICONTROL 数据库]**&#x200B;从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;复制并粘贴到&#x200B;**[!UICONTROL 数据库]**。 将`%3FFLATTEN`添加到您粘贴的值。 例如：`prod:cja%3FFLATTEN`。
   1. 从&#x200B;**[!UICONTROL 身份验证]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 用户名和密码]**。
   1. 使用![复制](/help/assets/icons/Copy.svg)将&#x200B;**[!UICONTROL 用户名]**&#x200B;从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;复制并粘贴到&#x200B;**[!UICONTROL 用户名]**。
   1. 使用![复制](/help/assets/icons/Copy.svg)将&#x200B;**[!UICONTROL 密码]**&#x200B;从Experience Platform **[!UICONTROL 查询]** **[!UICONTROL 过期凭据]**&#x200B;复制并粘贴到&#x200B;**[!UICONTROL 密码]**。 如果您使用的是[不会过期的凭据](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect)，请使用不会过期的凭据的密码。
   1. 确保已选中&#x200B;**[!UICONTROL Require SSL]**。
   1. 选择&#x200B;**[!UICONTROL 登录]**。

   在Tableau Desktop验证连接时，您会看到&#x200B;**[!UICONTROL 处理请求]**&#x200B;对话框。
1. 在主窗口中，您会在左侧窗格的Data Source视图中看到：
   * **[!UICONTROL 连接]**&#x200B;下的连接名称。
   * **[!UICONTROL 数据库]**&#x200B;下的数据库名称。
   * **[!UICONTROL 表]**下的表列表。
     ![已连接Tableau](assets/tableau-connected.png)
   1. 将&#x200B;**[!UICONTROL cc_data_view]**&#x200B;条目拖放到显示&#x200B;**[!UICONTROL 将表]**&#x200B;拖放到此处的主视图中。
1. 主窗口现在显示&#x200B;**[!UICONTROL cc_data_view]**数据视图的详细信息。
   ![已连接Tableau](assets/tableau-validation.png)

>[!ENDTABS]

+++


## 每日趋势

在此使用案例中，您要显示一个表格和简单的折线图可视化图表，其中显示2023年1月1日至2023年1月31日期间发生次数的每日趋势。

+++ 详细信息

>[!PREREQUISITES]
>
>请确保已验证[成功连接，并且可以为要尝试此用例的BI工具列出数据视图](#connect-and-list-data-views)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

1. 在&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中：
   1. 选择&#x200B;**[!UICONTROL daterangeday]**&#x200B;维度。
   1. 选择&#x200B;**[!UICONTROL 发生次数]**&#x200B;量度。

   您会看到一个显示当月发生次数的表。 为了获得更好的可见性，请放大表可视化图表。

1. 在&#x200B;**[!UICONTROL 筛选器]**&#x200B;窗格中：

   1. 从此视觉对象上的&#x200B;**[!UICONTROL 筛选器中选择**[!UICONTROL  daterangeday is (All)]**]**。
   1. 选择&#x200B;**[!UICONTROL 高级筛选]**&#x200B;作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 当值]** **[!UICONTROL 位于或晚于]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 位于]** `1/2/2023.`时显示项您可以使用日历图标挑选日期。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

   您会看到使用应用的&#x200B;**[!UICONTROL daterangeday]**&#x200B;过滤器更新的表。

1. 在&#x200B;**[!UICONTROL 可视化图表]**&#x200B;窗格中：

   1. 选择&#x200B;**[!UICONTROL 折线图]**&#x200B;可视化图表。

   使用与表相同的数据时，折线图可视化图表会替换表。

   ![Power BI桌面用例2日期范围筛选器](assets/uc2-pbi-filter-daterange.png)

1. 在折线图可视化图表上：

   1. 选择![更多](/help/assets/icons/More.svg)。
   1. 从上下文菜单中，选择&#x200B;**[!UICONTROL 显示为表]**。

   主视图已更新以显示折线图可视化图表和表格。

   ![Power BI桌面用例2最终每日趋势可视化图表](assets/uc2-pbi-filter-final.png)

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并指定句点`01/01/2023` - `01/02/2023`。

      ![Tableau桌面筛选器](assets/uc2-tableau-filter.png)

   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖放&#x200B;**[!UICONTROL Daterangeday]**，并将条目拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁边的字段中。
      * 从&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL Day]**，以便将该值更新为&#x200B;**[!UICONTROL DAY(Daterangeday)]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 发生次数]**，并将条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。
      * 值会自动转换为&#x200B;**[!UICONTROL SUM（发生次数）]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的工作表1视图应如下所示。

      ![Tableau桌面图形](assets/uc2-tableau-graph.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Graph`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 确保已选择&#x200B;**[!UICONTROL 数据]**&#x200B;工作表。 在“数据”视图中：
   1. 选择右上角的&#x200B;**[!UICONTROL 向我显示]**&#x200B;并选择&#x200B;**[!UICONTROL 文本表]**（左上角可视化图表）以将数据视图的内容修改为表。
   1. 将&#x200B;**[!UICONTROL DAY(Daterangeday)]**&#x200B;从&#x200B;**[!UICONTROL 列]**&#x200B;拖到&#x200B;**[!UICONTROL 行]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的&#x200B;**[!UICONTROL 数据]**&#x200B;视图应如下所示。

      ![Tableau桌面数据](assets/uc2-tableau-data.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL Graph]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 图形]**&#x200B;工作表下的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中。
   1. 选择视图中的&#x200B;**[!UICONTROL 数据]**&#x200B;工作表，并将&#x200B;**[!UICONTROL 整个视图]**&#x200B;修改为&#x200B;**[!UICONTROL 固定宽度]**。

      您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

      ![Tableau桌面功能板1](assets/uc2-tableau-dashboard.png)

>[!ENDTABS]

+++


## 每小时趋势

在此使用案例中，您要显示一个表格和简单的折线图可视化图表，其中显示2023年1月1日每小时发生次数的趋势。

+++ 详细信息

>[!PREREQUISITES]
>
>请确保已验证[成功连接，并且可以为要尝试此用例的BI工具列出数据视图](#connect-and-list-data-views)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

![警报](/help/assets/icons/Alert.svg)Power BI **不**&#x200B;了解如何处理日期时间列，因此不支持&#x200B;**[!UICONTROL daterangehour]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute]**&#x200B;等维度。

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并指定句点`01/01/2023` - `02/01/2023`。

      ![Tableau桌面筛选器](assets/uc3-tableau-filter.png)

   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖放&#x200B;**[!UICONTROL Daterangehour]**，并将条目拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁边的字段中。
      * 从&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL More]** > **[!UICONTROL Hours]**，以便将该值更新为&#x200B;**[!UICONTROL HOUR(Daterangeday)]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 发生次数]**，并将条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。
      * 值会自动转换为&#x200B;**[!UICONTROL SUM（发生次数）]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的工作表1视图应如下所示。

      ![Tableau桌面图形](assets/uc3-tableau-graph.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Graph`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 确保已选择&#x200B;**[!UICONTROL 数据]**&#x200B;工作表。 在“数据”视图中：
   1. 选择右上角的&#x200B;**[!UICONTROL 向我显示]**&#x200B;并选择&#x200B;**[!UICONTROL 文本表]**（左上角可视化图表）以将数据视图的内容修改为表。
   1. 将&#x200B;**[!UICONTROL HOUR(Daterangeday)]**&#x200B;从&#x200B;**[!UICONTROL 列]**&#x200B;拖到&#x200B;**[!UICONTROL 行]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的&#x200B;**[!UICONTROL 数据]**&#x200B;视图应如下所示。

      ![Tableau桌面数据](assets/uc3-tableau-data.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL Graph]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 图形]**&#x200B;工作表下的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中。
   1. 选择视图中的&#x200B;**[!UICONTROL 数据]**&#x200B;工作表，并将&#x200B;**[!UICONTROL 整个视图]**&#x200B;修改为&#x200B;**[!UICONTROL 固定宽度]**。

      您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

      ![Tableau桌面功能板1](assets/uc3-tableau-dashboard.png)


>[!ENDTABS]

+++


## 每月趋势

在此使用案例中，您希望显示一个表格和简单的折线图可视化图表，以显示2023年1月1日至2024年1月1日发生次数的每月趋势。

+++ 详细信息

>[!PREREQUISITES]
>
>请确保已验证[成功连接，并且可以为要尝试此用例的BI工具列出数据视图](#connect-and-list-data-views)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

1. 在&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中：
   1. 选择&#x200B;**[!UICONTROL daterangemonth]**&#x200B;维度。
   1. 选择&#x200B;**[!UICONTROL 发生次数]**&#x200B;量度。

   您会看到一个显示当月发生次数的表。 为了获得更好的可见性，请放大表可视化图表。

1. 在&#x200B;**[!UICONTROL 筛选器]**&#x200B;窗格中：

   1. 从此视觉对象上的&#x200B;**[!UICONTROL 筛选器中选择**[!UICONTROL  daterangemonth is (All)]**。]**
   1. 选择&#x200B;**[!UICONTROL 高级筛选]**&#x200B;作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 当值]** **[!UICONTROL 位于或晚于]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 位于]** `1/1/2024.`时显示项您可以使用日历图标挑选日期。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

   您会看到使用应用的&#x200B;**[!UICONTROL daterangeday]**&#x200B;过滤器更新的表。

1. 在&#x200B;**[!UICONTROL 可视化图表]**&#x200B;窗格中：

   1. 选择&#x200B;**[!UICONTROL 折线图]**&#x200B;可视化图表。

   使用与表相同的数据时，折线图可视化图表会替换表。

   ![Power BI桌面用例2日期范围筛选器](assets/uc4-pbi-filter-daterange.png)

1. 在折线图可视化图表上：

   1. 选择![更多](/help/assets/icons/More.svg)。
   1. 从上下文菜单中，选择&#x200B;**[!UICONTROL 显示为表]**。

   主视图已更新以显示折线图可视化图表和表格。

   ![Power BI桌面用例2最终每日趋势可视化图表](assets/uc4-pbi-filter-final.png)

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目，并将该条目放到&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架上。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;并指定句点`01/01/2023` - `01/01/2024`。

      ![Tableau桌面筛选器](assets/uc4-tableau-filter.png)

   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖放&#x200B;**[!UICONTROL Daterangeday]**，并将条目拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁边的字段中。
      * 从&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL MONTH]**，以便将该值更新为&#x200B;**[!UICONTROL MONTH(Daterangeday)]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中的&#x200B;**[!UICONTROL 表（*度量值名称*）]**&#x200B;列表中拖放&#x200B;**[!UICONTROL 发生次数]**，并将条目拖放到&#x200B;**[!UICONTROL 行]**&#x200B;旁边的字段中。
      * 值会自动转换为&#x200B;**[!UICONTROL SUM（发生次数）]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的工作表1视图应如下所示。

      ![Tableau桌面图形](assets/uc4-tableau-graph.png)

1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 复制]**&#x200B;以创建第二个工作表。
1. 从&#x200B;**[!UICONTROL 工作表1]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Graph`。
1. 从&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;选项卡上下文菜单中选择&#x200B;**[!UICONTROL 重命名]**&#x200B;以将工作表重命名为`Data`。
1. 确保已选择&#x200B;**[!UICONTROL 数据]**&#x200B;工作表。 在“数据”视图中：
   1. 选择右上角的&#x200B;**[!UICONTROL 向我显示]**&#x200B;并选择&#x200B;**[!UICONTROL 文本表]**（左上角可视化图表）以将数据视图的内容修改为表。
   1. 将&#x200B;**[!UICONTROL MONTH(Daterangeday)]**&#x200B;从&#x200B;**[!UICONTROL 列]**&#x200B;拖到&#x200B;**[!UICONTROL 行]**。
   1. 从工具栏的下拉菜单中将&#x200B;**[!UICONTROL Standard]**&#x200B;修改为&#x200B;**[!UICONTROL 整个视图]**。

      您的&#x200B;**[!UICONTROL 数据]**&#x200B;视图应如下所示。

      ![Tableau桌面数据](assets/uc4-tableau-data.png)

1. 选择&#x200B;**[!UICONTROL 新建仪表板]**&#x200B;选项卡按钮（位于底部）以创建新的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图。 在&#x200B;**[!UICONTROL 功能板1]**&#x200B;视图中：
   1. 将&#x200B;**[!UICONTROL Graph]**&#x200B;工作表从&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中，该视图显示&#x200B;*在此处放置工作表*。
   1. 将&#x200B;**[!UICONTROL 数据]**&#x200B;工作表从&#x200B;**[!UICONTROL 图形]**&#x200B;工作表下的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图中。
   1. 选择视图中的&#x200B;**[!UICONTROL 数据]**&#x200B;工作表，并将&#x200B;**[!UICONTROL 整个视图]**&#x200B;修改为&#x200B;**[!UICONTROL 固定宽度]**。

      您的&#x200B;**[!UICONTROL 仪表板1]**&#x200B;视图应如下所示。

      ![Tableau桌面功能板1](assets/uc4-tableau-dashboard.png)

>[!ENDTABS]

+++


## 单个维度排名

用例摘要

+++ 详细信息

>[!PREREQUISITES]
>
>请确保已验证[成功连接，并且可以为要尝试此用例的BI工具列出数据视图](#connect-and-list-data-views)。
>

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++


## 多个维度排名

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++


## 对非重复维度值计数

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 使用日期范围名称进行筛选

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 使用筛选器名称进行筛选

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 使用维度值进行筛选

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 排序

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 限制

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 是否扁平化

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## Dimension和量度转换

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++



## 可视化和交互

用例摘要

+++ 详细信息

>[!BEGINTABS]

>[!TAB Power BI桌面]

步骤

>[!TAB Tableau桌面]

步骤

>[!ENDTABS]

+++


