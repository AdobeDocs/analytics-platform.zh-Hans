---
title: SQL连接器
description: 了解如何使用Query Service、Power BI和/或Tableau通过SQL Connector访问数据视图。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 2%

---

# SQL连接器

{{release-limited-testing}}

此 [!DNL Customer Journey Analytics (CJA) SQL Connector] 允许通过SQL访问 [数据视图](./data-views.md) 您在CJA中定义的属性。 您的数据工程师和分析人员可能更熟悉Power BI、Tableau或其他商业智能和可视化工具（进一步称为BI工具）。 他们现在可以基于CJA用户在创建其Analysis Workspace项目时所用的相同数据视图创建报告和仪表板。

Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn) 是Experience Platform数据湖中可用数据的SQL接口。 使用 [!DNL CJA SQL Connector] 已启用，的功能 [!DNL Query Service] 扩展了以将CJA数据视图作为表或视图查看 [!DNL Query Service] 会话。 因此，使用 [!DNL Query Service] 因为其PostgresSQL接口可从此扩展功能中无缝受益。

主要优势包括：

- 无需在BI工具本身中重新创建CJA数据视图的等效表示形式。 <br/>参见 [数据视图](data-views.md) 有关数据视图功能的更多信息，以了解必须重新创建的内容。<br/>

- 提高BI工具和CJA之间报告和分析的一致性。

- 将CJA数据与BI工具中已有的其他数据源相结合。

## 先决条件

要使用此功能，您必须

- 启用 [!UICONTROL CJA SQL Connector] 在您的Experience Platform组织中。

- 配置相关产品配置文件、用户组和/或个人用户的功能。<br/>
用户必须有权访问：
   - Experience Platform查询服务，
   - CJA工作区项目，以及
   - 他们要使用的CJA数据视图。

- 使用过期凭据将BI工具连接到CJA SQL Connector。 三 [凭据指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 提供有关设置过期凭据或非过期凭据的更多信息。

参见 [访问控制](../admin/cja-access-control.md) 有关更多信息，请参阅“CJA管理”部分。


## 使用情况

要使用 [!DNL CJA SQL Connector] 功能上，您可以直接使用SQL，也可以使用特定BI工具中提供的拖放体验。

### SQL

您可以使用查询编辑器或标准PostgresSQL命令行界面(CLI)客户端直接在SQL语句中使用功能。

+++ 查询编辑器

在Experience PlatformUI中：

1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 起始日期 **[!UICONTROL **&#x200B;数据管理&#x200B;**]** 在左边栏中。

2. 选择 ![创建查询](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;创建查询&#x200B;**]**.

3. 要执行查询，请键入您的SQL语句并选择 ![播放](assets/Smock_Play_18_N.svg) 按钮（或按SHIFT + ENTER）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查找并复制您的PostgresSQL凭据：

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏（在下） **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 要复制连接字符串，请使用 ![复制](assets/Smock_Copy_18_N.svg) 在 **[!UICONTROL ** PSQL命令&#x200B;**]** 部分。

2. 打开PostgresSQL CLI。

3. 要登录并开始执行查询，请将连接字符串粘贴到PostgresSQL CLI中。

+++

参见 [查询编辑器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 了解更多信息。


### BI工具

目前，Power BI和Tableau支持CJA SQL连接器。

+++ Power BI

1. 在Adobe Experience Platform UI中，查找您的PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏（在下） **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 使用 ![复制](assets/Smock_Copy_18_N.svg) 复制每个Postgres凭据参数([!UICONTROL 主机]， [!UICONTROL 端口]， [!UICONTROL 数据库]， [!UICONTROL 用户名]Power BI 、及其他)的任意值。

2. 在Power BI：

   1. 在主窗口中，选择 **[!UICONTROL **&#x200B;获取数据&#x200B;**]** 从顶部工具栏中。

   2. 选择 **[!UICONTROL **&#x200B;更多……**]** 在左边栏中。

   3. 在 **获取数据** 屏幕，搜索 `PostgresSQL` 并选择 **[!UICONTROL ** PostgresSQL数据库&#x200B;**]** 从名单上。

   4. 在 **[!UICONTROL ** PostgressSQL数据库&#x200B;**]** 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本字段。

      2. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 在 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本字段。

         添加 `?FLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此它显示为 `prod:all?FLATTEN` 例如。 参见 [拼合嵌套数据结构以与第三方BI工具一起使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 了解更多信息。

      3. 提示输入时 **[!UICONTROL **&#x200B;数据连接&#x200B;**]** 模式，选择 **[!UICONTROL ** Directquery **]** 以确保数据结构正确拼合。

      4. 系统会提示您输入 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 和 **[!UICONTROL **&#x200B;密码&#x200B;**]**. 使用Experience Platform查询中的等效参数 [!UICONTROL 凭据].
   5. 成功登录后，CJA数据视图表会显示在Power BI的 **[!UICONTROL **&#x200B;导航器&#x200B;**]**. 数据视图表使用进行标识 `dv_` 以他们的名义。


   6. 选择要使用的数据视图表，然后选择 **[!UICONTROL **&#x200B;加载&#x200B;**]**.

   与一个或多个选定表关联的所有维度和量度都会显示在右侧窗格中，并准备好用于可视化图表中。

   参见 [将Power BI连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 了解更多信息。

+++

+++表格

1. 在Experience PlatformUI中，查找PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏（在下） **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 使用 ![复制](assets/Smock_Copy_18_N.svg) 复制每个Postgres凭据参数([!UICONTROL 主机]， [!UICONTROL 端口]， [!UICONTROL 数据库]， [!UICONTROL 用户名]、和其他项)。

2. 在表格中：

   1. 选择 **[!UICONTROL **&#x200B;更多&#x200B;**]** 起始日期 **[!UICONTROL **&#x200B;到服务器&#x200B;**]** 在左边栏中。

   2. 选择 **[!UICONTROL ** PostgresSQL **]** 从名单上。

   3. 在 [!UICONTROL PostgresSQL] 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本字段。

      2. 粘贴 **[!UICONTROL **&#x200B;端口&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;端口&#x200B;**]** 文本字段。

      3. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本字段。

         添加 `%3FFLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此它显示为 `prod:all%3FFLATTEN` 例如。 参见 [拼合嵌套数据结构以与第三方BI工具一起使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 了解更多信息。

      4. 选择 **[!UICONTROL **&#x200B;用户名和密码&#x200B;**]** 起始日期 **[!UICONTROL **&#x200B;身份验证&#x200B;**]** 列表。

      5. 粘贴 **[!UICONTROL **&#x200B;用户名&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 文本字段。

      6. 粘贴 **[!UICONTROL **&#x200B;密码&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;密码&#x200B;**]** 文本字段。

      7. 选择 **[!UICONTROL **&#x200B;登录&#x200B;**]**.
   4. CJA数据视图在中显示为表 **[!UICONTROL **&#x200B;表&#x200B;**]** 列表。 数据视图表的前缀为 `dv_`.

   5. 拖动要在画布上使用的表。

   您现在可以使用数据视图表中的数据来构建报告和可视化图表。

   参见 [将Tableau连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 了解更多信息。

+++

参见 [将客户端连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 有关各种可用工具的概述和更多信息。

## 功能

默认情况下，数据视图具有从其友好名称生成的表安全名称。 例如，数据视图命名为 [!UICONTROL 我的Web数据] 具有视图名称 `dv_my_web_data`.

如果要使用数据视图ID作为表名，可以添加可选的 `CJA_USE_IDS` 设置为连接时的数据库名称。 例如， `prod:all?CJA_USE_IDS` 显示您的数据视图，其名称如下 `dv_ABC123`.

### 数据管理

Customer Journey Analytics中与数据治理相关的设置继承自Adobe Experience Platform。 CJA 和 Adobe Experience Platform 数据管理之间的集成允许标记敏感 CJA 数据和实施隐私政策。

在 Experience Platform 使用的数据集上创建的隐私标签和策略可以在 CJA 数据视图工作流中显示。 因此，当不符合定义的隐私标签和策略时，使用CJA SQL Connector查询的数据会显示相应的警告或错误。

### 列出数据视图

在标准PostgreSQL CLI中，您可以使用以下命令列出视图 `\dv`

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

默认情况下，数据视图的架构使用嵌套结构，就像原始XDM架构一样。 该集成还支持 `FLATTEN` 选项。 您可以使用此选项强制将数据视图（以及会话中的任何其他表）的架构扁平化。 拼合允许在不支持结构化架构的BI工具中更轻松地使用。 参见 [在查询服务中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 了解更多信息。

### 支持的SQL

参见 [查询服务SQL引用](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以了解有关支持的SQL类型的完整引用。

有关模式和示例的概述，请参阅下面的模式表。

+++模式

| 模式 | 示例 |
|---|---|
| 架构发现 | <pre>从dv1中选择*，其中1=0</pre> |
| 排名/细分 | <pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按dim1分组</pre><pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间，并且<br/>  filterId = &#39;12345&#39;<br/>按dim1分组</pre><pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间，并且<br/>  AND (dim2 = &#39;A&#39;或dim3 IN (&#39;X&#39;， &#39;Y&#39;， &#39;Z&#39;))<br/>按dim1分组</pre> |
| HAVING子句 | <pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按dim1分组<br/>拥有m1 > 100</pre> |
| Distinct，顶部 <br/>维度值 | <pre>从dv1中选择不同的DIM1</pre><pre>选择dim1 AS dv1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按dim1分组</pre><pre>选择dim1 AS dv1<br/>从dv1<br/>其中\&#39;timestamp\&#39; >= &#39;2022-01-01&#39;和\&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>按dim1分组<br/>ORDER BY SUM(metric1)<br/>限制15</pre> |
| 指标总计 | <pre>选择SUM(metric1)作为m1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间</pre> |
| 多维<br/>划分<br/>和顶级区别 | <pre>选择dim1、dim2、SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>GROUP BY dim1， dim2</pre><pre>选择dim1、dim2、SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按1、2分组<br/>排序方式1、2</pre><pre>选取DISTINCT dim1， dim2<br/>从dv1</pre> |
| 子选择：<br/>其他结果<br/>筛选 | <pre>选择dim1， m1<br/>从(<br/>  选择dim1，SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间</br>  按dim1分组<br/>)<br/>其中dim1位于(&#39;A&#39;， &#39;B&#39;)</pre> |
| 子选择：<br/>加入<br/>数据集不在<br/>CJA | <pre>选择b.key、a.dim1、a.m1<br/>从(<br/>  选择dim1，SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按dim1分组<br/>) a<br/>左连接查找b ON a.dim1 = b.key</pre> |
| 子选择：<br/>跨以下项查询<br/>数据视图 | <pre>SELECT键，SUM(m1) AS total<br/>从(<br/>  选择dim1 AS键，选择SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按dim1分组<br/><br/>  并集<br/><br/>  选择dim2 AS键，SUM(m1) AS m1<br/>  从dv2<br/>  其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按DIM2分组<br/>按键分组<br/>ORDER BY总计</pre> |
| 子选择： <br/>分层源， <br/>正在筛选， <br/>和聚合 | 使用子选择进行分层：<br><pre>SELECT rows.dim1， SUM(rows.m1) AS total<br/>从(<br/>  选择\_.dim1，\_.m1<br/>  从(<br/>    从dv1中选择\*<br/>    其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  ) \_<br/>  其中\_.dim1位于(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>)行<br/>按1分组<br/>ORDER BY总计</pre><br/>将CTE与以下内容结合使用的图层：<br/><pre>行为(<br/>  带有\_ AS (<br/>    SELECT * FROM data_ares<br/>    其中\&#39;时间戳\&#39;介于&#39;2021-01-01&#39;和&#39;2021-02-01&#39;之间<br/>  )<br/>  选择_.item 、_.units FROM _<br/>  其中_.item不为空<br/>)<br/>SELECT rows.item， SUM(rows.units) AS units<br/>FROM行，其中rows.item位于(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 选择<br/>指标先于<br/> 或与<br/>尺寸 | <pre>选择SUM(metric1) AS m1， dim1<br/>从dv1<br/>其中\&#39;时间戳\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按2分组</pre> |

{style="table-layout:auto"}

+++

### 维度

您可以选择默认可用的维或数据视图中定义的维。 通过维度的ID选择维度。

### 度量

可供选择的量度包括：

- 任何默认可用的量度，

- 在数据视图中定义，

- 与用户有权访问的数据视图兼容的计算指标。

您可以通过包裹在量度中的ID来选择量度 `SUM(metric)` 表达式，就像处理其他SQL源一样。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 以获取发生次数量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 以计算维度的近似非重复值。 有关详细信息，请参阅 [计数区别](#counting-distincts).

- [内联计算](#inline-calculations) 动态组合量度和/或对其进行数学运算。

#### 计数区别

由于CJA工作方式的根本性质，您唯一可以获得准确非重复计数的维度是 `adobe_personid` 维度。 以下SQL语句 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 返回默认人员量度的值，该量度是不同人员的计数。 对于其他维度，会返回近似的非重复计数。

#### 条件量度

您可以嵌入 `IF` 或 `CASE` 子句位于 `SUM` 或 `COUNT` 用于添加特定于选定量度的其他筛选的函数。 添加这些子句与将过滤器应用于Workspace报表中的量度列类似。

示例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 内联计算

您可以对中的量度表达式应用附加的 `SELECT` 而不是在计算量度中定义数学。 下表列出了支持的表达式类型。

| 运算符或函数 | 详细信息 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、减、乘、除和模数/余数 |
| `-X` 或 `+X` | 更改符号或指标，其中X是指标表达式 |
| `PI()` | π常数 |
| `POSITIVE`， `NEGATIVE`， `ABS`， `FLOOR`， `CEIL`， `CEILING`， `EXP`， `LN`， `LOG10`， `LOG1P`， `SQRT`， `CBRT`， `DEGREES`， `RADIANS`， `SIN`， `COS`， `TAN`， `ACOS`， `ASIN`， `ATAN`， `COSH`， `SINH`、和 `TANH` | 一元数学函数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二进制数学函数 |

{style="table-layout:auto"}

### 特殊列

**时间戳**

此 `timestamp` 特殊列用于提供查询的日期范围。 可以使用定义日期范围 `BETWEEN` 表达式或一对 `timestamp` `>`， `>=`， `<`， `<=` 支票 `AND`艾德在一起。
此 `timestamp` 是可选的，如果未提供完整范围，则使用默认值：

- 如果只提供最低值(`timestamp > X` 或 ` timestamp >= X`)，其范围是从X到现在。

- 如果只提供最大值(`timestamp < X` 或 `timestamp <= X`)，范围为X-30天到X。

- 如果未提供任何内容，则范围为从现在–30天到现在。

时间戳范围在RankingRequest中转换为日期范围全局过滤器。
时间戳字段还可用于日期时间函数，以解析、截断事件时间戳。

**日期范围**

此 `daterange` 特殊列的工作方式类似于  `timestamp`，但筛选时间限制为全天。 此 `daterange` 也是可选的，其默认范围与相同 `timestamp`.
此 `daterange` 字段还可以在日期时间函数中使用，以解析、截断事件日期。

**filterId**

此 `filterId` 特殊列是可选的，用于向查询应用外部定义的过滤器。 将外部定义的过滤器应用于查询，类似于将过滤器拖动到工作区中的面板上。 可以提供多个过滤器ID，方法是 `AND` — 他们。

### WHERE子句

WHERE子句分三个步骤处理：

1. 从以下位置查找日期范围： `timestamp` 特殊字段。

2. 查找任何外部定义的 `filterId`要包含在筛选中的。

3. 将剩余表达式转换为临时过滤器。

处理通过解析第一级来完成 `AND`s在 `WHERE` 子句。 每个顶级 `AND`ed表达式必须匹配以上任意一项。 比第一层更深入的东西 `AND`s，或者，如果 `WHERE` 子句用法 `OR`在顶层，作为临时过滤器处理。

### 排序方式

默认情况下，查询按第一个选择的量度以降序对结果进行排序。 您可以通过指定覆盖默认排序顺序 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`. 如果您使用 `ORDER BY`，您必须指定 `ORDER BY` 在第一个选定的量度上。

也可以使用反向该顺序 `-` （减）在指标前面。 以下两个语句的结果是相同的顺序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支持

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 当前不支持类型转换，但不会引发错误。 此 `CAST` 函数被忽略。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 将时间字符串解析为时间戳，以便在 `WHERE` 子句。 |
| [TO_TIMESTAMP(timeString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 将时间字符串解析为时间戳，以便在 `WHERE` 子句，可以选择为该时间字符串提供格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 将日期字符串解析为时间戳，以便在 `WHERE` 子句。 |
| [TO_DATE(dateString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 将日期字符串解析为时间戳，以便在 `WHERE` 子句（可选）为该日期字符串提供格式。 |

{style="table-layout:auto"}

### Dimension功能支持

这些函数可用于中的维度 `SELECT`， `WHERE` 子句中或条件量度中的。

**字符串函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在传递的字段上生成动态维度标识。 |

{style="table-layout:auto"}

**日期时间函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [YEAR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [MONTH（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAY（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAYOFWEEK（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 请使用项目ID而不是值，因为您需要的是编号而不是友好名称。 |
| [DAYOFYEAR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [WEEK（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [QUARTER（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [HOUR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 请使用项目ID而不是值，因为您需要的是编号而不是友好名称。 |
| [MINUTE（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是此函数某些部分的值，因为您需要编号而不是友好名称。<br/>支持的部件包括：<br> — 关键字： `YEAR`， `MONTH`， `DAYOFMONTH`， `DAYOFWEEK`， `DAYOFYEAR`， `WEEK`， `QUARTER`， `HOUR`， `MINUTE`.<br/> — 字符串：  `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_PART（part、date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是此函数某些部分的值，因为您需要编号而不是友好名称。<br/>支持的字符串部分包括： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_TRUNC（粒度、日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在传递的字段上生成动态维度标识。<br/>支持的字符串粒度包括： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |

{style="table-layout:auto"}

