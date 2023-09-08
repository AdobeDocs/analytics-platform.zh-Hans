---
title: SQL Connector
description: 了解如何使用Query Service、Power BI和/或Tableau通过SQL Connector访问数据视图。
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: 1b03689820c91a823cd7cf8ff42e3f5ee46083e5
workflow-type: tm+mt
source-wordcount: '2938'
ht-degree: 1%

---

# SQL Connector

{{release-limited-testing}}

{{select-package}}

此 [!DNL Customer Journey Analytics SQL Connector] 允许通过SQL访问 [数据视图](./data-views.md) 您已在Customer Journey Analytics中定义该参数。 您的数据工程师和分析人员可能更熟悉Power BI、Tableau或其他业务智能和可视化工具（进一步称为BI工具）。 他们现在可以根据Customer Journey Analytics用户在创建Analysis Workspace项目时所使用的相同数据视图创建报告和仪表板。

Adobe Experience Platform [查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn) 是Experience Platform的数据湖中可用数据的SQL接口。 使用 [!DNL Customer Journey Analytics SQL Connector] 已启用，的功能 [!DNL Query Service] 扩展了以表或视图的形式查看Customer Journey Analytics数据视图 [!DNL Query Service] 会话。 因此，使用 [!DNL Query Service] 因为其PostgresSQL接口可从此扩展功能中无缝受益。

主要优势包括：

- 无需在BI工具本身中重新创建Customer Journey Analytics数据视图的等效表示形式。 <br/>请参阅 [数据视图](data-views.md) 有关数据视图功能的更多信息，以了解必须重新创建的内容。<br/>

- 提高BI工具和Customer Journey Analytics之间报表和分析的一致性。

- 将Customer Journey Analytics数据与BI工具中已有的其他数据源相结合。

## 先决条件

要使用此功能，您必须

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 为相关的产品配置文件、用户组和/或个人用户配置功能。<br/>
用户必须有权访问：
   - Experience Platform查询服务，
   - Customer Journey Analytics工作区项目，以及
   - Customer Journey Analytics要使用的数据视图。

- 使用过期凭据将BI工具连接到Customer Journey AnalyticsSQL连接器。 三 [凭据指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 提供了有关设置过期凭据或不过期凭据的详细信息。

请参阅 [访问控制](../admin/cja-access-control.md) 有关更多信息，请参阅Customer Journey Analytics管理部分。


## 使用情况

要使用 [!DNL Customer Journey Analytics SQL Connector] 功能，您可以直接使用SQL，或使用特定BI工具中提供的拖放体验。

### SQL

您可以使用查询编辑器或标准的PostgresSQL命令行界面(CLI)客户端直接在SQL语句中使用这些功能。

+++ 查询编辑器

在Experience PlatformUI中：

1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从 **[!UICONTROL **&#x200B;数据管理&#x200B;**]** 在左边栏中。

2. 选择 ![创建查询](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;创建查询&#x200B;**]**.

3. 要执行查询，请键入您的SQL语句并选择 ![播放](assets/Smock_Play_18_N.svg) 按钮（或按SHIFT + ENTER）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查找并复制您的PostgresSQL凭据：

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(在 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 要复制连接字符串，请使用 ![复制](assets/Smock_Copy_18_N.svg) 在 **[!UICONTROL ** PSQL命令&#x200B;**]** 部分。

2. 打开PostgresSQL CLI。

3. 要登录并开始执行查询，请将连接字符串粘贴到PostgresSQL CLI中。

+++

请参阅 [查询编辑器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 以了解更多信息。


### BI工具

目前，仅支持Customer Journey AnalyticsSQL连接器并针对Power BI和Tableau进行测试。 其他使用PSQL接口的BI工具也可能正常工作，但尚未得到正式支持。

+++ Power BI

1. 在Adobe Experience Platform UI中，查找您的PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(在 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 在 Power BI 中，使用 ![ 副本 ](assets/Smock_Copy_18_N.svg) 复制每个 Postgres 凭据参数（ [!UICONTROL  主机 ] 、 [!UICONTROL  端口 ] 、 [!UICONTROL  数据库 ] 、 [!UICONTROL  用户名 ] 及其他）。

2. 在 Power BI 中：

   1. 在主窗口中，从顶部工具栏中选择 **[!UICONTROL ** &quot;获取数据 **]** &quot;。

   2. 在左侧的边栏中选择 **[!UICONTROL ** 更多 ... **]**

   3. 在 **获取数据** 屏幕，搜索 `PostgresSQL` 并选择 **[!UICONTROL ** PostgresSQL数据库&#x200B;**]** 从名单上。

   4. 在 **[!UICONTROL ** PostgressSQL数据库&#x200B;**]** 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本字段。

      2. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 在 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本字段。

         添加 `?FLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此它显示为 `prod:cja?FLATTEN` 例如。 请参阅 [拼合嵌套数据结构以用于第三方BI工具](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

      3. 提示输入时 **[!UICONTROL **&#x200B;数据连接&#x200B;**]** 模式，选择 **[!UICONTROL ** Directquery **]** 以确保数据结构正确扁平化。

      4. 系统会提示您输入 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 和 **[!UICONTROL **&#x200B;密码&#x200B;**]**. 使用Experience Platform查询中的等效参数 [!UICONTROL 凭据].


   5. 成功登录后，“Customer Journey Analytics数据视图”表将出现在Power BI的 **[!UICONTROL **&#x200B;导航器&#x200B;**]**. 数据视图表使用进行标识 `dv_` 以他们的名义。


   6. 选择要使用的数据视图表，然后选择 **[!UICONTROL **&#x200B;加载&#x200B;**]**.

   与一个或多个选定表关联的所有维度和量度都将显示在右侧窗格中，您可以在可视化图表中随时使用。

   请参阅 [将Power BI连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 以了解更多信息。

+++

+++Tableau

1. 在Experience PlatformUI中，查找您的PostgresSQL凭据的详细信息。

   1. 选择 **[!UICONTROL **&#x200B;查询&#x200B;**]** 从左边栏(在 **[!UICONTROL **&#x200B;数据管理&#x200B;**]**)。

   2. 选择 **[!UICONTROL **&#x200B;凭据&#x200B;**]** 从顶部栏中。

   3. 使用 ![复制](assets/Smock_Copy_18_N.svg) 复制每个Postgres凭据参数([!UICONTROL 主机]， [!UICONTROL 端口]， [!UICONTROL 数据库]， [!UICONTROL 用户名]、和其他项)。

2. 在表格中：

   1. 选择 **[!UICONTROL **&#x200B;更多&#x200B;**]** 从 **[!UICONTROL **&#x200B;到服务器&#x200B;**]** 在左边栏中。

   2. 选择 **[!UICONTROL ** PostgresSQL **]** 从名单上。

   3. 在 [!UICONTROL PostgresSQL] 对话框：

      1. 粘贴 **[!UICONTROL **&#x200B;主机&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;服务器&#x200B;**]** 文本字段。

      2. 粘贴 **[!UICONTROL **&#x200B;端口&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;端口&#x200B;**]** 文本字段。

      3. 粘贴 **[!UICONTROL **&#x200B;数据库&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 文本字段。

         添加 `%3FFLATTEN` 到 **[!UICONTROL **&#x200B;数据库&#x200B;**]** 参数，因此它显示为 `prod:cja%3FFLATTEN` 例如。 请参阅 [拼合嵌套数据结构以用于第三方BI工具](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

      4. 选择 **[!UICONTROL **&#x200B;用户名和密码&#x200B;**]** 从 **[!UICONTROL **&#x200B;身份验证&#x200B;**]** 列表。

      5. 粘贴 **[!UICONTROL **&#x200B;用户名&#x200B;**]** Experience Platform查询中的参数 [!UICONTROL 凭据] 到 **[!UICONTROL **&#x200B;用户名&#x200B;**]** 文本字段。

      6. 粘贴 **[!UICONTROL ** 密码 **]** 参数从 Experience Platform 查询 [!UICONTROL  凭据 ] 转换为 **[!UICONTROL ** 密码 **]** 文本字段。

      7. 选择 **[!UICONTROL ** 登录 **]** 。

   4. Customer Journey Analytics 数据查看显示为表格 **]** 列表中的 **[!UICONTROL ** 表格。数据视图表具有 `dv_` 前缀。

   5. 在画布上拖动要使用的表。

   您现在可以处理来自数据视图表的数据，以版本报表和可视化。

   请参阅 [将Tableau连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 以了解更多信息。

+++

请参阅 [将客户端连接到查询服务](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 有关各种可用工具的概述和更多信息。

## 功能

默认情况下，您的数据视图有一个从其友好名称生成的表安全名称。 例如，名为的数据视图 [!UICONTROL 我的Web数据] 具有视图名称 `dv_my_web_data`.

如果要使用数据视图ID作为表名，则可以添加可选的 `CJA_USE_IDS` 设置为连接时的数据库名称。 例如， `prod:all?CJA_USE_IDS` 显示其名称如下的数据视图 `dv_ABC123`.

### 数据管理

Customer Journey Analytics中与数据管理相关的设置继承自Adobe Experience Platform。 Customer Journey Analytics与Adobe Experience Platform数据管理之间的集成允许标记敏感Customer Journey Analytics数据和实施隐私政策。

在Experience Platform使用的数据集上创建的隐私标签和策略可以在Customer Journey Analytics数据视图工作流中显示。 因此，使用Customer Journey AnalyticsSQL Connector查询的数据在不遵循定义的隐私标签和策略时会显示相应的警告或错误。

### 列出数据视图

在标准PostgreSQL CLI中，您可以使用列出视图 `\dv`

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

### 嵌套与拼合

默认情况下，数据视图的架构使用嵌套结构，就像原始XDM架构一样。 该集成还支持 `FLATTEN` 选项。 您可以使用此选项强制将数据视图（以及会话中的任何其他表）的架构平面化。 拼合允许在不支持结构化架构的BI工具中更轻松地使用。 请参阅 [在查询服务中使用嵌套数据结构](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以了解更多信息。

### 支持的SQL

请参阅 [查询服务SQL引用](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以获取有关支持哪种SQL类型的完整引用。

有关可以使用的SQL的示例，请参见下表。

+++ 示例

| 模式 | 示例 |
|---|---|
| 架构发现 | <pre>从 dv1 中选择 *，其中 1 = 0</pre> |
| 排名/划分 | <pre>选择 dim1，SUM （metric1）作为 m1 <br/> ，dv1 <br/> 其中 &quot;2022-01-01&quot; 和 &quot;2022-01-02&quot; <br/> GROUP x dim1 之间的 \ &quot;时间戳 \&quot;</pre><pre>从 dv1 <br/> 中选择 dim1、SUM （metric1）作为 m1 <br/> ，其中 &quot;2022-01-01&quot; 和 &quot;2022-01-02&quot; 与 <br/> filterId = &quot;12345&quot; <br/> GROUP BY dim1</pre><pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间，并且<br/>  AND (dim2 = &#39;A&#39;或dim3 IN (&#39;X&#39;， &#39;Y&#39;， &#39;Z&#39;))<br/>按dim1分组</pre> |
| HAVING子句 | <pre>选择dim1，SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按dim1分组<br/>拥有m1 > 100</pre> |
| Distinct，顶部 <br/>维度值 | <pre>从dv1中选择DISTINCT dim1</pre><pre>选择dim1 AS dv1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按dim1分组</pre><pre>选择dim1 AS dv1<br/>从dv1<br/>其中\&#39;timestamp\&#39; >= &#39;2022-01-01&#39;和\&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>按dim1分组<br/>ORDER BY SUM(metric1)<br/>限制15</pre> |
| 指标总计 | <pre>选择SUM(metric1)作为m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间</pre> |
| 多维<br/>划分<br/>和顶级特性 | <pre>选择dim1、dim2、SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>GROUP BY dim1， dim2</pre><pre>选择dim1、dim2、SUM(metric1) AS m1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按1、2分组<br/>ORDER BY 1， 2</pre><pre>选择DISTINCT dim1， dim2<br/>从dv1</pre> |
| 子选择：<br/>其他结果<br/>筛选 | <pre>选择dim1， m1<br/>从(<br/>  选择dim1，SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间</br>  按dim1分组<br/>)<br/>其中dim1位于(&#39;A&#39;， &#39;B&#39;)</pre> |
| 子选择：<br/>加入<br/>数据集不在<br/>Customer Journey Analytics | <pre>选择b.key、a.dim1、a.m1<br/>从(<br/>  选择dim1，SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按dim1分组<br/>) a<br/>左连接查找b ON a.dim1 = b.key</pre> |
| 子选择：<br/>正在跨以下位置查询<br/>数据视图 | <pre>选择键，SUM(m1) AS total<br/>从(<br/>  选择dim1作为键，选择SUM(metric1) AS m1<br/>  从dv1<br/>  其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按dim1分组<br/><br/>  合并<br/><br/>  选择dim2 AS键，SUM(m1) AS m1<br/>  从dv2<br/>  其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  按dim2分组<br/>按键分组<br/>ORDER BY合计</pre> |
| 子选择： <br/>分层源， <br/>正在筛选， <br/>和聚合 | 使用子选择分层：<br><pre>选择rows.dim1， SUM(rows.m1) AS total<br/>从(<br/>  选择\_.dim1，\_.m1<br/>  从(<br/>    从dv1中选择\*<br/>    其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>  ) \_<br/>  其中\_.dim1位于(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>)行<br/>按1分组<br/>ORDER BY合计</pre><br/>将CTE与以下内容一起使用的图层：<br/><pre>行为(<br/>  带有\_ AS (<br/>    选择*从数据区(_A)<br/>    其中\&#39;timestamp\&#39;介于&#39;2021-01-01&#39;和&#39;2021-02-01&#39;之间<br/>  )<br/>  从_中选择_.item 、_.units<br/>  其中_.item不为空<br/>)<br/>SELECT rows.item， SUM(rows.units) AS units<br/>FROM行，其中rows.item位于(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 选择<br/>量度先于<br/> 或混合使用<br/>尺寸 | <pre>选择SUM(metric1) AS m1， dim1<br/>从dv1<br/>其中\&#39;timestamp\&#39;介于&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之间<br/>按2分组</pre> |

{style="table-layout:auto"}

+++

### 维度

您可以选择默认可用的维或数据视图中定义的维。 您可以按 ID 选择维度。

### 量度

可供选择的量度包括：

- 默认可用的任何量度，

- 在 data 视图中定义，

- 与用户有权访问的数据查看兼容的计算量度。

您可以通过包裹在中的指标ID来选择指标 `SUM(metric)` 表达式，就像处理其他SQL源一样。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 以获取发生次数量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 以计算维度的近似非重复值。 有关详细信息，请参阅 [计数区别](#counting-distincts).

- [内联计算](#inline-calculations) 动态组合量度和/或对其进行数学运算。

#### 计数区别

由于Customer Journey Analytics工作方式的基本性质，您可以获得准确非重复计数的唯一维度是 `adobe_personid` 维度。 以下SQL语句 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 返回默认人员量度的值，该量度是不同人员的计数。 对于其他维度，将返回近似非重复计数。

#### 条件量度

您可以嵌入 `IF` 或 `CASE` 中的子句 `SUM` 或 `COUNT` 函数，可添加特定于选定量度的其他筛选。 添加这些子句与将过滤器应用于Workspace报表中的量度列类似。

示例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 内联计算

您可以对中的量度表达式应用其他 `SELECT` 而不是在计算量度中定义数学。 下表列出了支持的表达式类型。

| 运算符或函数 | 详细信息 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、减、乘、除和模/余数 |
| `-X` 或 `+X` | 更改符号或指标，其中X是指标表达式 |
| `PI()` | π常数 |
| `POSITIVE`， `NEGATIVE`， `ABS`， `FLOOR`， `CEIL`， `CEILING`， `EXP`， `LN`， `LOG10`， `LOG1P`， `SQRT`， `CBRT`， `DEGREES`， `RADIANS`， `SIN`， `COS`， `TAN`， `ACOS`， `ASIN`， `ATAN`， `COSH`， `SINH`、和 `TANH` | 一元数学函数 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二进制数学函数 |

{style="table-layout:auto"}

### 特殊列

**时间戳**

此 `timestamp` 特殊列用于提供查询的日期范围。 可以使用定义日期范围 `BETWEEN` 表达式或一对 `timestamp` `>`， `>=`， `<`， `<=` 支票 `AND`艾德在一起。
此 `timestamp` 是可选的，如果未提供完整的范围，将使用默认值：

- 如果只提供最低值(`timestamp > X` 或 ` timestamp >= X`)，其范围是从X到现在。

- 如果只提供最大值(`timestamp < X` 或 `timestamp <= X`)，范围为X-30天到X。

- 如果未提供任何内容，则范围为现在–30天到现在。

时间戳范围会在RankedRequest中转换为日期范围全局过滤器。
时间戳字段还可用于日期时间函数以解析、截断事件时间戳。

**日期范围**

此 `daterange` 特殊列的工作方式类似于  `timestamp`，但筛选时间限制为全天。 此 `daterange` 也是可选的，其默认范围与相同 `timestamp`.
此 `daterange` 字段还可用于日期时间函数以解析、截断事件日期。

**filterId**

此 `filterId` 特殊列是可选的，用于向查询应用外部定义的过滤器。 将外部定义的过滤器应用于查询，类似于将过滤器拖动到工作区中的面板上。 可以提供多个过滤器ID `AND` — 他们。

### WHERE子句

WHERE子句分三个步骤处理：

1. 从以下位置查找日期范围： `timestamp` 特殊字段。

2. 查找任何外部定义的 `filterId`s以包含在筛选中。

3. 将剩余表达式转换为临时过滤器。

处理是通过解析第一级的 `AND`s在 `WHERE` 子句。 每个顶层 `AND`ed表达式必须匹配以上任意一个。 比第一层更深的东西 `AND`s，或者，如果 `WHERE` 子句用法 `OR`在顶层，作为临时过滤器处理。

### 排序依据

默认情况下，查询按第一个选择的量度以降序对结果进行排序。 您可以通过指定覆盖默认排序顺序 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`. 如果您使用 `ORDER BY`，您必须指定 `ORDER BY` 在第一个选择的量度上。

也可以使用反向订单 `-` （减）在指标前面。 以下两种语句的结果是相同的顺序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支持

| 功能 | 示例 | 详细信息 |
|---|---|---|
| [强制转换（列类型）](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 当前不支持类型强制转换，但不会引发任何错误。 忽略该 `CAST` 函数。 |
| [时间戳(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 将时间字符串解析为时间戳，以在 `WHERE` 子句。 |
| [TO_TIMESTAMP(timeString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 将时间字符串解析为时间戳，以在 `WHERE` 子句，可以选择为该时间字符串提供格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 将日期字符串解析为时间戳，以在 `WHERE` 子句。 |
| [TO_DATE(dateString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 将日期字符串解析为时间戳，以在 `WHERE` 子句，（可选）为该日期字符串提供格式。 |

{style="table-layout:auto"}

### Dimension功能支持

这些函数可用于中的维度 `SELECT`， `WHERE` 子句中或条件量度中的。

**字符串函数**

| 功能 | 示例 | 详细信息 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在传递的字段上生成动态维度标识。 |

{style="table-layout:auto"}

**日期时间函数**

| 功能 | 示例 | 详细信息 |
|---|---|---|
| [YEAR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [MONTH（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAY（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [DAYOFWEEK（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是值，因为您需要编号而不是友好名称。 |
| [DAYOFYEAR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [WEEK（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [QUARTER（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [HOUR（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是值，因为您需要编号而不是友好名称。 |
| [MINUTE（日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在传递的字段上生成动态维度标识。 |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是此函数某些部分的值，因为您需要编号而不是友好名称。<br/>支持的部件包括：<br> — 关键字： `YEAR`， `MONTH`， `DAYOFMONTH`， `DAYOFWEEK`， `DAYOFYEAR`， `WEEK`， `QUARTER`， `HOUR`， `MINUTE`.<br/> — 字符串：  `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_PART（part、date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在传递的字段上生成动态维度标识。 使用项目ID而不是此函数某些部分的值，因为您需要编号而不是友好名称。<br/>支持的字符串部分包括： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_TRUNC（粒度、日期或日期时间）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在传递的字段上生成动态维度标识。<br/>支持的字符串粒度包括： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |

{style="table-layout:auto"}
