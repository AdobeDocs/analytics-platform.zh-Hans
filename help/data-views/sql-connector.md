---
title: SQL Connector
description: 了解如何使用 Query Service、Power BI 和/或 Tableau 通过 SQL Connector 访问数据视图。
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: 1b03689820c91a823cd7cf8ff42e3f5ee46083e5
workflow-type: ht
source-wordcount: '2938'
ht-degree: 100%

---

# SQL Connector

{{release-limited-testing}}

{{select-package}}

通过 [!DNL Customer Journey Analytics SQL Connector]，SQL 可访问您在 Customer Journey Analytics 中定义的[数据视图](./data-views.md)。您的数据工程师和分析师可能更熟悉 Power BI、Tableau 或其他商业智能和可视化工具（也称为 BI 工具）。他们现在可以基于 Customer Journey Analytics 用户在创建 Analysis Workspace 项目时使用的相同数据视图来创建报告和仪表板。

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn) 是 Experience Platform 数据湖中可用数据的 SQL 接口。启用 [!DNL Customer Journey Analytics SQL Connector] 后，[!DNL Query Service]的功能将得到扩展，以便在[!DNL Query Service]会话中以表或视图的形式查看 Customer Journey Analytics 数据视图。因此，将[!DNL Query Service]用作其 PostgresSQL 接口的商业智能工具可以无缝地从这项扩展的功能中受益。

主要好处是：

- 无需在 BI 工具中重新创建 Customer Journey Analytics 数据视图的等效表示形式。<br/>有关数据视图功能的更多信息，请参阅[数据视图](data-views.md)，从而了解必须重新创建的内容。<br/>

- BI 工具和 Customer Journey Analytics 之间的报告和分析具有更高的一致性。

- 将 Customer Journey Analytics 数据与 BI 工具中已有的其他数据源结合起来。

## 先决条件

要使用此功能，您必须：

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 针对相关产品配置文件、用户组和/或个人用户配置此功能。<br/>
用户必须有权访问：
   - Experience Platform Query Service，
   - Customer Journey Analytics Workspace 项目，以及
   - 要使用的 Customer Journey Analytics 数据视图。

- 使用过期凭据或不过期凭据将 BI 工具连接到 Customer Journey Analytics SQL Connector。[凭据指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=zh-Hans)提供了有关如何设置过期凭据或不过期凭据的更多信息。

请参阅“Customer Journey Analytics 管理”部分中的[访问控制](../admin/cja-access-control.md)以了解更多信息。


## 使用情况

要使用 [!DNL Customer Journey Analytics SQL Connector] 功能，您可以直接使用 SQL，也可以使用特定 BI 工具中提供的拖放体验。

### SQL

您可以通过查询编辑器或标准 PostgresSQL 命令行界面 (CLI) 客户端直接在 SQL 语句中使用此功能。

+++ 查询编辑器

在 Experience Platform UI 中：

1. 在左边栏中的&#x200B;**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;中，选择&#x200B;**[!UICONTROL **&#x200B;查询&#x200B;**]**。

2. 选择![创建查询](assets/Smock_AddCircle_18_N.svg)**[!UICONTROL **&#x200B;创建查询&#x200B;**]**。

3. 要执行查询，请键入 SQL 语句并选择![播放](assets/Smock_Play_18_N.svg)按钮（或按 Shift + Enter）。

+++


+++ PostgresSQL CLI

1. 在 Experience Platform UI 中，找到并复制您的 PostgresSQL 凭据：

   1. 从左边栏中（**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;下），选择&#x200B;**[!UICONTROL **&#x200B;查询&#x200B;**]**。

   2. 从顶部栏中选择&#x200B;**[!UICONTROL **&#x200B;凭据&#x200B;**]**。

   3. 要复制连接字符串，请使用 **[!UICONTROL ** PSQL 命令&#x200B;**]**&#x200B;部分中的![复制](assets/Smock_Copy_18_N.svg)。

2. 打开 PostgresSQL CLI。

3. 要登录并开始执行查询，请将连接字符串粘贴到 PostgresSQL CLI 中。

+++

有关更多信息，请参阅[查询编辑器 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=zh-Hans)。


### BI 工具

目前，仅 Power BI 和 Tableau 能够支持和测试 Customer Journey Analytics SQL Connector。其他使用 PSQL 接口的 BI 工具也能工作，但尚未获得正式支持。

+++ Power BI

1. 在 Adobe Experience Platform UI 中，查找 PostgresSQL 凭据的详细信息。

   1. 从左边栏中（**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;下），选择&#x200B;**[!UICONTROL **&#x200B;查询&#x200B;**]**。

   2. 从顶部栏中选择&#x200B;**[!UICONTROL **&#x200B;凭据&#x200B;**]**。

   3. 如果需要，使用![复制](assets/Smock_Copy_18_N.svg)在 Power BI 中复制每个 Postgres 凭据参数（[!UICONTROL 主机]、[!UICONTROL 端口]、[!UICONTROL 数据库]、[!UICONTROL 用户名] 等）。

2. 在 Power BI 中：

   1. 在主窗口中，从顶部工具栏中选择&#x200B;**[!UICONTROL **&#x200B;获取数据&#x200B;**]**。

   2. 选择左边栏中的&#x200B;**[!UICONTROL **&#x200B;更多...**]**。

   3. 在&#x200B;**获取数据**&#x200B;屏幕中，搜索 `PostgresSQL`，并从列表中选择 **[!UICONTROL ** PostgresSQL 数据库&#x200B;**]**。

   4. 在 **[!UICONTROL ** PostgressSQL 数据库&#x200B;**]**&#x200B;对话框中：

      1. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;主机&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;服务器&#x200B;**]**&#x200B;文本字段中。

      2. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;文本字段中。

         将 `?FLATTEN` 添加到&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;参数，例如，使其显示内容为 `prod:cja?FLATTEN`。有关更多信息，请参阅[扁平化处理嵌套数据结构以用于第三方 BI 工具](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=zh-Hans)。

      3. 在系统提示输入&#x200B;**[!UICONTROL **&#x200B;数据连接&#x200B;**]**&#x200B;模式时，选择 **[!UICONTROL ** DirectQuery **]** 以确保适当地扁平化处理数据结构。

      4. 系统会提示您输入&#x200B;**[!UICONTROL **&#x200B;用户名&#x200B;**]**&#x200B;和&#x200B;**[!UICONTROL **&#x200B;密码&#x200B;**]**。使用 Experience Platform 查询[!UICONTROL 凭据]中的等效参数。


   5. 成功登录后，Customer Journey Analytics 数据视图表将显示在 Power BI 的&#x200B;**[!UICONTROL **&#x200B;导航器&#x200B;**]**&#x200B;中。数据视图表由其名称中使用的 `dv_` 标识。


   6. 选择要使用的数据视图表，然后选择&#x200B;**[!UICONTROL **&#x200B;加载&#x200B;**]**。

   与一个或多个选定表关联的所有维度和量度都显示在右窗格中，可供您在可视化图表中使用。

   有关更多信息，请参阅[将 Power BI 连接到 Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=zh-Hans)。

+++

+++Tableau

1. 在 Experience Platform UI 中，查找 PostgresSQL 凭据的详细信息。

   1. 从左边栏中（**[!UICONTROL **&#x200B;数据管理&#x200B;**]**&#x200B;下），选择&#x200B;**[!UICONTROL **&#x200B;查询&#x200B;**]**。

   2. 从顶部栏中选择&#x200B;**[!UICONTROL **&#x200B;凭据&#x200B;**]**。

   3. 如果需要，使用![复制](assets/Smock_Copy_18_N.svg)在 Tableau 中复制每个 Postgres 凭据参数（[!UICONTROL 主机]、[!UICONTROL 端口]、[!UICONTROL 数据库]、[!UICONTROL 用户名] 等）。

2. 在 Tableau 中：

   1. 从左边栏中的&#x200B;**[!UICONTROL **&#x200B;至服务器&#x200B;**]**&#x200B;中选择&#x200B;**[!UICONTROL **&#x200B;更多&#x200B;**]**。

   2. 从列表中选择 **[!UICONTROL ** PostgresSQL **]**。

   3. 在 [!UICONTROL PostgresSQL] 对话框中：

      1. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;主机&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;服务器&#x200B;**]**&#x200B;文本字段中。

      2. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;端口&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;端口&#x200B;**]**&#x200B;文本字段中。

      3. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;文本字段中。

         将 `%3FFLATTEN` 添加到&#x200B;**[!UICONTROL **&#x200B;数据库&#x200B;**]**&#x200B;参数，例如，使其显示内容为 `prod:cja%3FFLATTEN`。有关更多信息，请参阅[扁平化处理嵌套数据结构以用于第三方 BI 工具](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=zh-Hans)。

      4. 从&#x200B;**[!UICONTROL **&#x200B;身份验证&#x200B;**]**&#x200B;列表中选择&#x200B;**[!UICONTROL **&#x200B;用户名和密码&#x200B;**]**。

      5. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;用户名&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;用户名&#x200B;**]**&#x200B;文本字段中。

      6. 将 Experience Platform 查询[!UICONTROL 凭据]中的&#x200B;**[!UICONTROL **&#x200B;密码&#x200B;**]**&#x200B;参数粘贴到&#x200B;**[!UICONTROL **&#x200B;密码&#x200B;**]**&#x200B;文本字段中。

      7. 选择&#x200B;**[!UICONTROL **&#x200B;登录&#x200B;**]**。

   4. Customer Journey Analytics 数据视图显示为&#x200B;**[!UICONTROL **&#x200B;表&#x200B;**]**&#x200B;列表中的表。数据视图表的前缀为 `dv_`。

   5. 将要使用的表拖动到画布上。

   您现在可以使用数据视图表中的数据来构建报告和可视化图表。

   有关更多信息，请参阅[将 Tableau 连接到 Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=zh-Hans)。

+++

请参阅[将客户端连接到 Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=zh-Hans)，大致了解各种可用工具及其详细信息。

## 功能

默认情况下，您的数据视图具有从其友好名称生成的表安全名称。例如，名为[!UICONTROL 我的 Web 数据]的数据视图的视图名称为 `dv_my_web_data`。

如果要使用数据视图 ID 作为表名称，可以在连接时将可选的 `CJA_USE_IDS` 设置添加到数据库名称。例如，`prod:all?CJA_USE_IDS` 显示具有 `dv_ABC123` 等名称的数据视图。

### 数据管理

Customer Journey Analytics 中与数据管理相关的设置继承自 Adobe Experience Platform。Customer Journey Analytics 和 Adobe Experience Platform 数据管理之间的集成允许标记敏感的 Customer Journey Analytics 数据和实施隐私政策。

在 Experience Platform 使用的数据集上创建的隐私标签和政策可以在 Customer Journey Analytics 数据视图工作流中显示。因此，在未遵循定义的隐私标签和政策时，使用 Customer Journey Analytics SQL Connector 查询的数据会显示相应的警告或错误。

### 列出数据视图

在标准 PostgreSQL CLI 中，可以使用 `\dv` 列出视图

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### 嵌套与扁平化处理

默认情况下，数据视图架构使用嵌套结构，就像原始 XDM 架构一样。该集成还支持 `FLATTEN` 选项。您可以使用此选项实施要扁平化处理的数据视图（以及会话中的任何其他表）的架构。通过扁平化处理，可以更轻松地在不支持结构化架构的 BI 工具中使用。有关更多信息，请参阅[在 Query Service 中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=zh-Hans)。

### 支持的 SQL

有关支持的 SQL 类型的完整参考，请参阅 [Query Service SQL 参考](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=zh-Hans)。

有关可使用的 SQL 示例，请见下表。

+++ 示例

| 模式 | 示例 |
|---|---|
| 架构发现 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| 排名/细分 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING 子句 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 顶部区别<br/>维度值 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 量度总计 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| 多维度<br/>细分<br/>和顶部区别 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| 子选择：<br/>附加结果<br/>过滤 | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| 子选择：<br/>与<br/>未在<br/>Customer Journey Analytics 中的数据集联接 | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| 子选择：<br/>跨数据视图<br/>查询 | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| 子选择：<br/>分层来源，<br/>过滤<br/>和聚合 | 使用子选择进行分层：<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>使用 CTE WITH 的层：<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 选择<br/>量度位于维度之前<br/>或与维度<br/>混合的情况 | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### 维度

您可以选择默认可用或在数据视图中定义的任何维度。可通过维度 ID 选择维度。

### 量度

可选择的量度为：

- 默认情况下可用的任何量度，

- 数据视图中定义的量度，

- 与用户有权访问的数据视图兼容的计算量度。

可通过包含在 `SUM(metric)` 表达式中的量度 ID 选择量度，就像处理其他 SQL 源一样。

您可以使用：

- `SELECT COUNT(*)` 或 `COUNT(1)` 获取发生次数量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 对某个维度的近似不同值计数。有关详细信息，请参阅[非重复计数](#counting-distincts)。

- [内联计算](#inline-calculations)，动态组合量度并/或对它们进行数学运算。

#### 非重复计数

由于 Customer Journey Analytics 工作方式的基本特性，您可以获得准确的不同计数的唯一维度是 `adobe_personid` 维度。以下 SQL 语句返回默认人员量度的值，即不同人员的计数：`SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)`。对于其他维度，返回近似的非重复计数。

#### 条件量度

可以将 `IF` 或 `CASE` 子句嵌入 `SUM` 或 `COUNT` 函数中，以添加特定于选定量度的其他过滤。添加这些子句类似于将过滤器应用于 Workspace 报告表中的量度列。

示例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 内联计算

您可以在 `SELECT` 中应用其他量度表达式，而不是在计算量度中定义数学。下表列出了支持的表达式的类型。

| 运算符或函数 | 详细信息 |
|---|---|
| `+`、`-`、`*`、`/` 和 `%` | 加、减、乘、除和模数/余数 |
| `-X` 或 `+X` | 更改符号或量度，其中 X 是量度表达式 |
| `PI()` | π 常量 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、`ASIN`、`ATAN`、`COSH`、`SINH` 和 `TANH` | 一元数学函数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二元数学函数 |

{style="table-layout:auto"}

### 特殊列

**时间戳**

`timestamp` 特殊列用于提供查询的日期范围。可使用 `BETWEEN` 表达式或 `timestamp` `>`、`>=`、`<`、`<=` 检查 `AND` 对来定义日期范围。
`timestamp` 是可选的，如果未提供完整范围，则使用默认值：

- 如果仅提供最小值（`timestamp > X` 或 ` timestamp >= X`），则范围为从 X 到当前日期。

- 如果仅提供最大值（`timestamp < X` 或 `timestamp <= X`），则范围为 X-30 天到 X。

- 如果未提供任何内容，则范围为从当前日期的前 30 天到当前日期。

时间戳范围将转换为 RankedRequest 中的 date-range 全局过滤器。
时间戳字段也可以在 Date-Time 函数中用于解析、截断事件时间戳。

**日期范围**

`daterange` 特殊列的工作方式与 `timestamp` 的类似，但是过滤仅限于完整天。`daterange` 也是可选的，并具有与 `timestamp` 相同的范围默认值。
`daterange` 字段也可以在 Date-Time 函数中用于解析、截断事件日期。

**filterId**

`filterId` 特殊列是可选的，用于将外部定义的过滤器应用于查询。将外部定义的过滤器应用于查询类似于将过滤器拖动到 Workspace 中的面板上。可使用 `AND` 将多个过滤器 ID 联接来提供这些 ID。

### WHERE 子句

通过三个步骤处理 WHERE 子句：

1. 从 `timestamp` 特殊字段中查找日期范围。

2. 查找要包含在过滤中的任何外部定义的 `filterId`。

3. 将剩余的表达式转变为临时过滤器。

通过解析 `WHERE` 子句中的 `AND` 的第一层来进行处理。每个采用 `AND` 的顶层表达式必须与上述某个表达式匹配。比 `AND` 的第一层更深入的任何项目（或在 `WHERE` 子句在顶层使用 `OR` 时）将处理为临时过滤器。

### ORDER BY

默认情况下，查询按第一个选定量度以降序顺序对结果进行排序。可以通过指定 `ORDER BY ... ASC` 或 `ORDER BY ... DESC` 来覆盖默认排序顺序。如果使用的是 `ORDER BY`，则必须在第一个选定量度上指定 `ORDER BY`。

还可以在量度前面使用 `-`（减号）来颠倒顺序。下面的两个语句都将产生相同的顺序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般函数支持

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 虽然当前不支持类型转换，但不会引发错误。`CAST` 函数将被忽略。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 将时间字符串解析为时间戳以在 `WHERE` 子句中使用。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 将时间字符串解析为时间戳以在 `WHERE` 子句中使用，（可选）并提供该时间字符串的格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 将日期字符串解析为时间戳以在 `WHERE` 子句中使用。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 将日期字符串解析为时间戳以在 `WHERE` 子句中使用，（可选）并提供该日期字符串的格式。 |

{style="table-layout:auto"}

### 维度函数支持

这些函数可用于 `SELECT`、`WHERE` 子句或条件量度中的维度。

**String 函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在传入字段上生成动态维度标识。 |

{style="table-layout:auto"}

**Date-Time 函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [YEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [MONTH(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [DAY(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [DAYOFWEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在传入字段上生成动态维度标识。使用项目 ID 而不是值，因为您需要的是数字而不是友好名称。 |
| [DAYOFYEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [WEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [QUARTER(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [HOUR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在传入字段上生成动态维度标识。使用项目 ID 而不是值，因为您需要的是数字而不是友好名称。 |
| [MINUTE(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在传入字段上生成动态维度标识。 |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在传入字段上生成动态维度标识。对此函数的某些部分使用项目 ID 而不是值，因为您需要的是数字而不是友好名称。<br/>支持的部分为：<br>- 关键词：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 字符串：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [DATE_PART(part, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在传入字段上生成动态维度标识。对此函数的某些部分使用项目 ID 而不是值，因为您需要的是数字而不是友好名称。<br/>支持的字符串部分为：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [DATE_TRUNC(granularity, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在传入字段上生成动态维度标识。<br/>支持的字符串粒度为：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |

{style="table-layout:auto"}
