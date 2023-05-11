---
title: SQL Connector
description: 了解如何使用查询服务、Power BI和/或表格来使用SQL Connector访问数据视图。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 4205995fdc54e4d7626f17de79573751a5c63d26
workflow-type: tm+mt
source-wordcount: '2879'
ht-degree: 2%

---

# SQL Connector

{{release-limited-testing}}

的 [!DNL Customer Journey Analytics (CJA) SQL Connector] 启用对的SQL访问 [数据视图](./data-views.md) 在CJA中定义。 您的Power BI工程师和分析人员可能更熟悉数据、表格或其他业务智能和可视化工具（进一步称为BI工具）。 现在，他们可以基于CJA用户在创建其Analysis Workspace项目时所使用的相同数据视图来创建报表和功能板。

Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn) 是用于Experience Platform数据湖中可用数据的SQL接口。 使用 [!DNL CJA SQL Connector] 启用，其功能 [!DNL Query Service] 扩展后，您的CJA数据视图将作为 [!DNL Query Service] 会话。 因此，使用 [!DNL Query Service] 由于其PostgresSQL接口可以无缝地从这项扩展功能中受益。

主要优势包括：

- 无需在BI工具本身中重新创建CJA数据视图的等效表示形式。 <br/>请参阅 [数据视图](data-views.md) 有关数据视图功能的更多信息，以了解必须重新创建哪些内容。<br/>

- 在BI工具与CJA之间的报告和分析方面更加一致。

- 将CJA数据与BI工具中已有的其他数据源合并。

## 先决条件

要使用此功能，您必须

- 启用 [!UICONTROL CJA SQL Connector] 在您的Experience Platform组织中。

- 配置相关产品配置文件、用户组和/或个人用户的功能。<br/>
用户必须有权访问：
   - Experience Platform查询服务、
   - CJA工作区项目和
   - 要使用的CJA数据视图。

- 使用在未过期的凭据上过期，将BI工具连接到CJA SQL Connector。 请参阅 [凭据指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 有关设置过期凭据或未过期凭据的详细信息。


## 使用情况

使用 [!DNL CJA SQL Connector] 功能中，您可以直接使用SQL，也可以使用特定BI工具中提供的拖放体验。

### SQL

您可以使用查询编辑器或标准PostgresSQL命令行界面(CLI)客户端直接在SQL语句中使用该功能。

+++ 查询编辑器

在Experience PlatformUI中：

1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从 **[!UICONTROL **&#x200B;数据管理&#x200B;**]** 中。

2. 选择 ![创建查询](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;创建查询&#x200B;**]**.

3. 要执行查询，请键入SQL语句并选择 ![播放](assets/Smock_Play_18_N.svg) 按钮（或按SHIFT + ENTER）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查找并复制PostgresSQL凭据：

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(下 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 来访问Advertising Cloud的帮助。

   3. 要复制连接字符串，请使用 ![复制](assets/Smock_Copy_18_N.svg) 在 **[!UICONTROL ** PSQL命令&#x200B;**]** 中。

2. 打开PostgresSQL CLI。

3. 要登录并开始执行查询，请将连接字符串粘贴到PostgresSQL CLI中。

+++

请参阅 [查询编辑器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 以了解更多信息。


### BI工具

目前，CJA SQL Connector支持Power BI和表格。

+++ Power BI

1. 在Adobe Experience Platform UI中，查找PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(下 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 来访问Advertising Cloud的帮助。

   3. 使用 ![复制](assets/Smock_Copy_18_N.svg) 复制每个Postgres凭据参数([!UICONTROL 主机], [!UICONTROL 端口], [!UICONTROL 数据库], [!UICONTROL 用户名]等)。

2. 在Power BI中：

   1. 在主窗口中，选择 **[!UICONTROL **&#x200B;获取数据&#x200B;**]** 中。

   2. 选择 **[!UICONTROL **&#x200B;更多……**]** 中。

   3. 在 **获取数据** 屏幕，搜索 `PostgresSQL` ，然后选择 **[!UICONTROL ** PostgresSQL数据库&#x200B;**]** 列表。

   4. 在 **[!UICONTROL **&#x200B;出口SQL数据库&#x200B;**]** 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本。

      2. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] in **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本。

         添加 `?FLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此其内容如下所示 `prod:all?FLATTEN` 例如。 请参阅 [扁平化嵌套数据结构以与第三方BI工具一起使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

      3. 提示时 **[!UICONTROL **&#x200B;数据连接&#x200B;**]** 模式，选择 **[!UICONTROL ** DirectQuery **]** 以确保正确扁平化数据结构。

      4. 系统会提示您输入 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 和 **[!UICONTROL **&#x200B;密码&#x200B;**]**. 使用Experience Platform查询中的等效参数 [!UICONTROL 凭据].
   5. 成功登录后，CJA数据视图表会显示在Power BI的 **[!UICONTROL **&#x200B;导航器&#x200B;**]**. 数据视图表使用 `dv_` 以他们的名字。


   6. 选择要使用的数据视图表，然后选择 **[!UICONTROL **&#x200B;加载&#x200B;**]**.

   与一个或多个选定表格关联的所有维度和量度都显示在右侧窗格中，可在您的可视化中使用。

   请参阅 [将Power BI连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 以了解更多信息。

+++

+++表格

1. 在Experience PlatformUI中，查找PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(下 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 来访问Advertising Cloud的帮助。

   3. 使用 ![复制](assets/Smock_Copy_18_N.svg) 复制每个Postgres凭据参数([!UICONTROL 主机], [!UICONTROL 端口], [!UICONTROL 数据库], [!UICONTROL 用户名]等)。

2. 在表格中：

   1. 选择 **[!UICONTROL **&#x200B;更多&#x200B;**]** 从 **[!UICONTROL **&#x200B;到服务器&#x200B;**]** 中。

   2. 选择 **[!UICONTROL ** PostgresSQL **]** 列表。

   3. 在 [!UICONTROL PostgresSQL] 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本。

      2. 粘贴 **[!UICONTROL **&#x200B;端口&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;端口&#x200B;**]** 文本。

      3. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本。

         添加 `%3FFLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此其内容如下所示 `prod:all%3FFLATTEN` 例如。 请参阅 [扁平化嵌套数据结构以与第三方BI工具一起使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

      4. 选择 **[!UICONTROL **&#x200B;用户名和密码&#x200B;**]** 从 **[!UICONTROL **&#x200B;身份验证&#x200B;**]** 列表。

      5. 粘贴 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;用户名&#x200B;**]** 文本。

      6. 粘贴 **[!UICONTROL **&#x200B;密码&#x200B;**]** 来自Experience Platform查询的参数 [!UICONTROL 凭据] into **[!UICONTROL **&#x200B;密码&#x200B;**]** 文本。

      7. 选择 **[!UICONTROL **&#x200B;登录&#x200B;**]**.
   4. CJA数据视图在 **[!UICONTROL **&#x200B;表&#x200B;**]** 列表。 数据视图表的前缀为 `dv_`.

   5. 在画布上拖动要使用的表。

   您现在可以处理数据视图表中的数据，以构建报表和可视化图表。

   请参阅 [将表格连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 以了解更多信息。

+++

请参阅 [将客户端连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 以了解各种可用工具的概述和更多信息。

## 功能

默认情况下，您的数据视图具有从其友好名称生成的表安全名称。 例如，名为的数据视图 [!UICONTROL 我的Web数据] 具有视图名称 `dv_my_web_data`.

如果要将数据视图ID用作表名称，可以添加可选 `CJA_USE_IDS` 在连接时将设置为数据库名称。 例如， `prod:all?CJA_USE_IDS` 显示数据视图，其名称如 `dv_ABC123`.

### 数据管理

Customer Journey Analytics中与数据管理相关的设置继承自Adobe Experience Platform。 CJA 和 Adobe Experience Platform 数据管理之间的集成允许标记敏感 CJA 数据和实施隐私政策。

在 Experience Platform 使用的数据集上创建的隐私标签和策略可以在 CJA 数据视图工作流中显示。 因此，使用CJA SQL Connector查询的数据在不遵守定义的隐私标签和策略时会显示相应的警告或错误。

### 列出数据视图

在标准PostgreSQL CLI中，您可以使用 `\dv`

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

### 嵌套与扁平化

默认情况下，数据视图的架构使用嵌套结构，就像原始XDM架构一样。 该集成还支持 `FLATTEN` 选项。 您可以使用此选项强制对数据视图（以及会话中的任何其他表）的架构进行扁平化处理。 拼合允许在不支持结构化架构的BI工具中更轻松地使用。 请参阅 [在查询服务中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

### 支持的SQL

请参阅 [查询服务SQL引用](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以获取有关支持哪种类型SQL的完整引用。

有关模式和示例的概述，请参阅下面的模式表。

+++模式

| 模式 | 示例 |
|---|---|
| 架构发现 | <pre>从dv1中选择* ，其中1=0</pre> |
| 排名/划分 | <pre>选择DIM1, SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>GROUP BY dim1</pre><pre>选择DIM1, SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\`和<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>选择DIM1, SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\`和<br/>  和(dim2 = &#39;A&#39;或DIM3 IN(&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING子句 | <pre>选择DIM1, SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>GROUP BY dim1<br/>m1>100</pre> |
| 非重复，顶部 <br/>维度值 | <pre>选择DISTINCT DIM1 FROM dv1</pre><pre>选择DIM1 AS dv1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>GROUP BY dim1</pre><pre>选择DIM1 AS dv1<br/>从dv1<br/>其中， \&#39;timestamp\` >= &#39;2022-01-01&#39; AND \&#39;timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>按总和排序(metric1)<br/>限制15</pre> |
| 量度总计 | <pre>选择SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\</pre> |
| 多维度<br/>划分<br/>和顶部显示 | <pre>选择DIM1、dim2、SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>GROUP BY dim1, dim2</pre><pre>选择DIM1、dim2、SUM(metric1)AS m1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>按1、2分组<br/>按1、2排序</pre><pre>选择DISTINCT DIM1, dim2<br/>从dv1</pre> |
| 子选择：<br/>其他结果<br/>过滤 | <pre>SELECT dim1, m1<br/>从(<br/>  选择DIM1, SUM(metric1)AS m1<br/>  从dv1<br/>  其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\</br>  GROUP BY dim1<br/>)<br/>其中，dim1 in(&#39;A&#39;, &#39;B&#39;)</pre> |
| 子选择：<br/>加入<br/>数据集未在<br/>CJA | <pre>选择b.key、a.dim1、a.m1<br/>从(<br/>  选择DIM1, SUM(metric1)AS m1<br/>  从dv1<br/>  其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>  GROUP BY dim1<br/>)a<br/>a.dim1 = b.key上的LEFT JOIN查找b</pre> |
| 子选择：<br/>跨渠道查询<br/>data-views | <pre>选择键，总和(m1)AS总计<br/>从(<br/>  选择DIM1作为键，SUM(metric1)AS m1<br/>  从dv1<br/>  其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>  GROUP BY dim1<br/><br/>  并集<br/><br/>  选择DIM2作为键，SUM(m1)AS m1<br/>  从dv2<br/>  其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>  GROUP BY dim2<br/>按键分组<br/>订单总额</pre> |
| 子选择： <br/>分层源， <br/>过滤， <br/>和聚合 | 使用子选项分层：<br><pre>选择ROWS.dim1, SUM(rows.m1)AS total<br/>从(<br/>  选择\_.dim1,\_.m1<br/>  从(<br/>    从dv1中选择\*<br/>    其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>  )\_<br/>  其中，\_.dim1 in(&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>)行<br/>按1分组<br/>订单总额</pre><br/>使用CTE的层：<br/><pre>行为(<br/>  使用\_ AS(<br/>    选择*从数据区<br/>    其中，“2021-01-01”和“2021-02-01”之间的\`timestamp\<br/>  )<br/>  选择_.item，_.units FROM _<br/>  其中_.item不为NULL<br/>)<br/>选择ROWS.item， SUM(rows.units)AS units<br/>(“A”、“B”、“C”)中的ROWS.item<br/>按行.item分组</pre> |
| 选择<br/>量度之前<br/> 或与<br/>维度 | <pre>选择SUM(metric1)AS m1, dim1<br/>从dv1<br/>其中，“2022-01-01”和“2022-01-02”之间的\`timestamp\<br/>按2分组</pre> |

{style="table-layout:auto"}

+++

### 维度

您可以选择默认可用或在数据视图中定义的任何维度。 您可以按维度的ID来选择维度。

### 度量

可供选择的量度包括：

- 默认可用的任何量度，

- 在数据视图中定义，

- 与用户有权访问的数据视图兼容的计算量度。

您可以通过其ID来选择量度，该ID封装在 `SUM(metric)` 表达式，就像使用其他SQL源一样。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 以获取发生次数量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 来计算维度的近似非重复值。 请参阅 [计数区别](#counting-distincts).

- [内联计算](#inline-calculations) 来快速组合量度和/或对量度进行数学运算。

#### 计数区别

由于CJA工作方式的基本性质，您唯一可以获得精确独特计数的维度是 `adobe_personid` 维度。 以下SQL语句 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 返回默认访客量度的值，该值是不同人员的计数。 对于其他维度，会返回非重复近似计数。

#### 条件量度

您可以嵌入 `IF` 或 `CASE` 子句 `SUM` 或 `COUNT` 函数添加特定于所选量度的附加过滤。 添加这些子句与将过滤器应用到工作区报表表中的量度列类似。

示例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 内联计算

您可以将其他量度表达式应用到 `SELECT` 而不是在计算量度中定义数学。 下表列出了支持的表达式类型。

| 运算符或函数 | 详细信息 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、减、乘、除和取模/余数 |
| `-X` 或 `+X` | 更改X为量度表达式的符号或量度 |
| `PI()` | π常数 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`和 `TANH` | 一元数学函数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二进制数学函数 |

{style="table-layout:auto"}

### 特殊列

**时间戳**

的 `timestamp` 特殊列用于提供查询的日期范围。 日期范围可以使用 `BETWEEN` 表达式或一对 `timestamp` `>`, `>=`, `<`, `<=` 检查 `AND`一起拼了。
的 `timestamp` 为可选参数，如果未提供完整范围，则使用默认值：

- 如果仅提供最小值(`timestamp > X` 或 ` timestamp >= X`)，范围从X到现在。

- 如果仅提供最大值(`timestamp < X` 或 `timestamp <= X`)，范围为X-30天到X。

- 如果未提供任何内容，则范围为“现在–30天”到“现在”。

时间戳范围会在RankedRequest中转换为日期范围全局过滤器。
时间戳字段还可用于Date-Time函数中以解析、截断事件时间戳。

**日期范围**

的 `daterange` 特殊列的工作方式类似于  `timestamp`，但过滤时间限制为整天。 的 `daterange` 也是可选的，且其默认范围与相同 `timestamp`.
的 `daterange` 字段，也可以在日期时间函数中使用来解析和截断事件日期。

**filterId**

的 `filterId` 特殊列是可选列，用于将外部定义的过滤器应用到查询。 将外部定义的过滤器应用到查询与在工作区的面板上拖动过滤器类似。 可以提供多个过滤器ID `AND`-Ing theres。

### WHERE子句

WHERE子句分三步处理：

1. 从 `timestamp` 特殊字段。

2. 查找任何外部定义的 `filterId`要包含在过滤中。

3. 将其余表达式转换为临时过滤器。

处理通过解析 `AND`s `WHERE` 子句。 每个顶级 `AND`ed表达式必须与上述任一值匹配。 比 `AND`s，或者，如果 `WHERE` 子句使用 `OR`作为临时过滤器处理。

### 订购依据

默认情况下，查询会按第一个选定量度的降序排序结果。 您可以通过指定 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`. 如果您使用 `ORDER BY`，您必须指定 `ORDER BY` 在第一个选定量度上。

您还可以使用 `-` （减）。 下面两个语句的顺序相同：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支持

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [CAST（列AS类型）](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 当前不支持类型转换，但不会引发任何错误。 的 `CAST` 函数时，会将其忽略。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 将时间字符串解析为时间戳，以在 `WHERE` 子句。 |
| [TO_TIMESTAMP(timeString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 将时间字符串解析为时间戳，以在 `WHERE` 子句，或者为该时间字符串提供格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 将日期字符串解析为时间戳，以在 `WHERE` 子句。 |
| [TO_DATE(dateString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 将日期字符串解析为时间戳，以在 `WHERE` 子句，或者为该日期字符串提供格式。 |

{style="table-layout:auto"}

### Dimension功能支持

这些函数可用于 `SELECT`, `WHERE` 子句或条件量度中的。

**字符串函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在传递的字段上生成动态维度标识。 |

{style="table-layout:auto"}

**日期时间函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [YEAR（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [MONTH（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAY（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAYOFWEEK（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 由于您需要的编号不是友好名称，因此请使用项目ID而不是值。 |
| [DAYOFYEAR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [WEEK（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [QUARTER（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [HOUR（日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 由于您需要的编号不是友好名称，因此请使用项目ID而不是值。 |
| [MINUTE（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [EXTRACT（part FROM date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在传递的字段上生成动态维度标识。 由于您需要的编号不是友好名称，因此请对此函数的某些部分使用项目ID而不是值。<br/>支持的部件包括：<br> — 关键词： `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/> — 字符串：  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`或 `'MINUTE'`. |
| [DATE_PART（part、date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在传递的字段上生成动态维度标识。 由于您需要的编号不是友好名称，因此请对此函数的某些部分使用项目ID而不是值。<br/>支持的字符串部分包括： `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`或 `'MINUTE'`. |
| [DATE_TRUNC（粒度、日期或日期 — 时间）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在传递的字段上生成动态维度标识。<br/>支持的字符串粒度包括： `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`或 `'MINUTE'`. |

{style="table-layout:auto"}

