---
title: 限制
description: 在Customer Journey Analytics的各种BI工具中限制BI扩展的用例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 0%

---

# 限制


在此使用案例中，您要报告2023年期间产品名称的前5次发生次数。

+++ Customer Journey Analytics

用例的&#x200B;**[!UICONTROL Limit]**&#x200B;面板示例：

![Customer Journey Analytics限制面板](../assets/cja-limit.png)

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
   1. 选择&#x200B;**[!UICONTROL 发生次数总和]**。

1. 在&#x200B;**[!UICONTROL 筛选器]**&#x200B;窗格中：
   1. 从该视觉对象上的&#x200B;**[!UICONTROL 筛选器中选择]**&#x200B;日期范围是（全部）**&#x200B;**。
   1. 选择&#x200B;**[!UICONTROL 相对日期]**&#x200B;作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 将筛选器定义为&#x200B;**[!UICONTROL 当值]** **[!UICONTROL 在最后]** `1` **[!UICONTROL 日历年]**&#x200B;内时显示项。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。
   1. 从该视觉对象上的&#x200B;**[!UICONTROL 筛选器中选择]** product_name is (All)**[!UICONTROL 。]**
   1. 选择&#x200B;**[!UICONTROL 前N]**&#x200B;项作为&#x200B;**[!UICONTROL 筛选器类型]**。
   1. 选择&#x200B;**[!UICONTROL 显示项]** **[!UICONTROL 前]** `5` **[!UICONTROL 按值]**。
   1. 从&#x200B;**[!UICONTROL 数据]**&#x200B;窗格中拖放&#x200B;**[!UICONTROL 总发生次数]**&#x200B;并将其放在&#x200B;**[!UICONTROL 在此处添加数据字段]**&#x200B;上。
   1. 选择&#x200B;**[!UICONTROL 应用筛选器]**。

1. 在“可视化”窗格中：
   * 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以从列中删除日期范围。

   您的Power BI桌面应该如下所示。

   ![Power BI桌面使用日期范围名称进行筛选](../assets/uc12-powerbi-final.png)

Power BI Desktop使用BI扩展执行的查询包含`limit`语句，但不包含预期的语句。 Power BI Desktop会使用明确的产品名称结果来强制实施对前5次发生次数的限制。

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau桌面]

1. 选择底部的&#x200B;**[!UICONTROL 表1]**&#x200B;选项卡以从&#x200B;**[!UICONTROL 数据源]**&#x200B;切换。 在&#x200B;**[!UICONTROL 表1]**&#x200B;视图中：
   1. 从&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 日期范围]**&#x200B;条目。
   1. 在&#x200B;**[!UICONTROL 筛选器字段\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 日期范围]**，然后选择&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 筛选器\[日期范围\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 相对日期]**，选择&#x200B;**[!UICONTROL 年]**，然后选择&#x200B;**[!UICONTROL 以前年份]**。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。
   1. 将&#x200B;**[!UICONTROL 产品名称]**&#x200B;从&#x200B;**[!UICONTROL 表]**&#x200B;列表拖至&#x200B;**[!UICONTROL 行]**。
   1. 从&#x200B;**[!UICONTROL 表]**&#x200B;列表中拖动&#x200B;**[!UICONTROL 发生次数]**&#x200B;条目，并将该条目放入&#x200B;**[!UICONTROL 列]**&#x200B;旁边的字段中。 值更改为&#x200B;**[!UICONTROL SUM（发生次数）]**。
   1. 从&#x200B;**[!UICONTROL 显示我]**&#x200B;中选择&#x200B;**[!UICONTROL 文本表]**。
   1. 从&#x200B;**[!UICONTROL 适合]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 适合宽度]**。
   1. 在&#x200B;**[!UICONTROL 行]**&#x200B;中选择&#x200B;**[!UICONTROL 产品名称]**。 从下拉菜单中选择&#x200B;**[!UICONTROL 筛选器]**。
      1. 在&#x200B;**[!UICONTROL 筛选器\[产品名称\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 顶部]**&#x200B;选项卡。
      1. 选择&#x200B;**[!UICONTROL By字段：]** **[!UICONTROL Top]** `5` **[!UICONTROL By发生次数]** **[!UICONTROL 总和]**。
      1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。

         ![AlertRed](/help/assets/icons/AlertRed.svg)您注意到该表消失。 使用此过滤器时，按发生次数选择前5个产品名称&#x200B;**无法**&#x200B;正常工作。
      1. 选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;托架中的&#x200B;**[!UICONTROL 产品名称]**，然后从下拉菜单中选择&#x200B;**[!UICONTROL 删除]**。 此时将重新显示该表。
   1. 在&#x200B;**[!UICONTROL 标记]**&#x200B;托架中选择&#x200B;**[!UICONTROL SUM（发生次数）]**。 从下拉菜单中选择&#x200B;**[!UICONTROL 筛选器]**。
      1. 在&#x200B;**[!UICONTROL 筛选器\[发生次数\]]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 至少]**。
      1. 输入`47.799`作为值。 此值可确保表中只显示排名前5的项目。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;和&#x200B;**[!UICONTROL 确定]**。

         您的Tableau桌面应该如下所示。

         ![Tableau桌面限制](../assets/uc12-tableau-final.png)

如上所示，在定义针对产品名称的“前5次发生次数”过滤器时，由Tableau Desktop执行的此查询会失败。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

定义发生次数排名前5的过滤器时，Tableau Desktop执行的查询如下所示。 该限制在查询和应用的客户端中不可见。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!TAB Looker]

1. 在Looker的&#x200B;**[!UICONTROL 浏览]**&#x200B;界面中，刷新您的连接。 选择![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 清除缓存并刷新]**。
1. 在Looker的&#x200B;**[!UICONTROL 浏览]**&#x200B;界面中，确保您拥有干净的设置。 如果不是，请选择![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 删除字段和筛选器]**。
1. 选择&#x200B;**[!UICONTROL 筛选器]**&#x200B;下的&#x200B;**[!UICONTROL +筛选器]**。
1. 在&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;对话框中：
   1. 选择&#x200B;**[!UICONTROL ‣抄送数据视图]**
   1. 从字段列表中，选择&#x200B;**[!UICONTROL 日‣间范围日期]**，然后选择&#x200B;**[!UICONTROL 日期范围日期]**。
      ![Looker筛选器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc数据视图日期范围日期]**&#x200B;筛选器，因为&#x200B;**[!UICONTROL 在]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 之前]** **[!UICONTROL 2024/01/01]**&#x200B;的范围内。
1. 从左边栏中的&#x200B;**[!UICONTROL ‣ Cc数据视图]**&#x200B;部分：
   1. 选择&#x200B;**[!UICONTROL 产品名称]**。
   1. 在左边栏（底部）中选择&#x200B;**[!UICONTROL MEASURES]**&#x200B;下的&#x200B;**[!UICONTROL 计数]**。
1. 请确保在&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;列上选择&#x200B;**[!UICONTROL ↓]** （**[!UICONTROL 降序，排序顺序： 1]**）。
1. 请确保在&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;列上选择&#x200B;**[!UICONTROL ↓]** （**[!UICONTROL 降序，排序顺序： 1]**）。
1. 选择&#x200B;**[!UICONTROL 运行]**。
1. 选择&#x200B;**[!UICONTROL ‣可视化图表]**。

您应该会看到如下所示的可视化图表和表格。

![非重复查找器计数](../assets/uc12-looker-result.png)

Looker使用BI扩展生成的查询包括`FETCH NEXT 5 ROWS ONLY`，这意味着限制通过Looker和BI扩展执行。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```


>[!TAB Jupyter笔记本]

1. 在新单元格中输入以下语句。

   ```python
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. 执行单元格。 您应该会看到类似于以下屏幕快照的输出。

   ![Jupyter笔记本结果](../assets/uc12-jupyter-results.png)

查询由Jupyter Notebook中定义的BI扩展执行。

>[!TAB RStudio]

1. 在新块中输入以下介于` ` ``{r} `和` `` ` `之间的语句。

   ```R
   ## Dimension 1 Limited
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE) %>%
      head(5)
   print(df)
   ```

1. 运行块。 您应该会看到类似于以下屏幕快照的输出。

   ![RStudio结果](../assets/uc12-rstudio-results.png)

RStudio使用BI扩展生成的查询包括`LIMIT 5`，这意味着限制通过RStudio和BI扩展应用。

```sql
SELECT "product_name", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2024-01-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "n" DESC
LIMIT 5
```

>[!ENDTABS]

+++
