---
title: SQL聯結器
description: 瞭解如何使用Query Service、Power BI和/或Tableau，以使用SQL聯結器存取資料檢視。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 829f7556c731ce55ccf1e03e2dea69b12e4501e4
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 2%

---

# SQL聯結器

{{release-limited-testing}}

此 [!DNL Customer Journey Analytics (CJA) SQL Connector] 啟用SQL存取 [資料檢視](./data-views.md) 您已在CJA中定義的專案。 您的資料工程師和分析人員可能更熟悉Power BI、Tableau或其他商業智慧和視覺化工具（進一步稱為BI工具）。 他們現在可以根據CJA使用者在建立其Analysis Workspace專案時使用的相同資料檢視來建立報告和儀表板。

Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans?lang=cn) 是Experience Platform資料湖中可用資料的SQL介面。 使用 [!DNL CJA SQL Connector] 已啟用， [!DNL Query Service] 延伸以將CJA資料檢視視為中的表格或檢視 [!DNL Query Service] 工作階段。 因此，商業智慧工具若使用 [!DNL Query Service] 因為其PostgresSQL介面可順暢地受益於這項擴充功能。

主要優點包括：

- 不需要在BI工具本身中重新建立CJA資料檢視的同等表示法。 <br/>另請參閱 [資料檢視](data-views.md) 有關資料檢視功能的詳細資訊，以瞭解必須重新建立的內容。<br/>

- 提高BI工具與CJA之間報告和分析的一致性。

- 將CJA資料與BI工具中可用的其他資料來源結合。

## 先决条件

若要使用此功能，您必須

- 啟用 [!UICONTROL CJA SQL聯結器] 在您的Experience Platform組織中。

- 設定相關產品設定檔、使用者群組及/或個別使用者的功能。<br/>
使用者必須擁有下列專案的存取權：
   - Experience Platform查詢服務，
   - CJA工作區專案，以及
   - 他們想要使用的CJA資料檢視。

- 使用不會到期的認證到期來將BI工具連線到CJA SQL Connector。 Thr [認證指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 提供有關設定即將到期的認證或不即將到期的認證的詳細資訊。

另請參閱 [存取控制](../admin/cja-access-control.md) 如需詳細資訊，請參閱CJA管理區段。


## 使用情况

若要使用 [!DNL CJA SQL Connector] 功能，您可以直接使用SQL或使用特定BI工具中可用的拖放體驗。

### SQL

您可以使用「查詢編輯器」或標準PostgresSQL命令列介面(CLI)使用者端，直接在SQL敘述句中使用功能。

+++ 查詢編輯器

在Experience PlatformUI中：

1. 選取 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從 **[!UICONTROL **&#x200B;資料管理&#x200B;**]** 在左側邊欄中。

2. 選取 ![建立查詢](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;建立查詢&#x200B;**]**.

3. 若要執行查詢，請輸入您的SQL陳述式，然後選取 ![播放](assets/Smock_Play_18_N.svg) 按鈕（或按SHIFT + ENTER）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查詢並複製您的PostgresSQL認證：

   1. 選取 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄（在下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選取 **[!UICONTROL **&#x200B;認證&#x200B;**]** 從頂端列。

   3. 若要複製連線字串，請使用 ![複製](assets/Smock_Copy_18_N.svg) 在 **[!UICONTROL ** PSQL命令&#x200B;**]** 區段。

2. 開啟您的PostgresSQL CLI。

3. 若要登入並開始執行查詢，請在PostgresSQL CLI中貼上連線字串。

+++

另請參閱 [查詢編輯器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 以取得詳細資訊。


### BI Tools

目前CJA SQL Connector支援Power BI和Tableau。

+++ Power BI

1. 在Adobe Experience Platform UI中，查詢您的PostgresSQL憑證詳細資訊。

   1. 選取 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄（在下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選取 **[!UICONTROL **&#x200B;認證&#x200B;**]** 從頂端列。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 若要複製每個Postgres認證引數([!UICONTROL 主機]， [!UICONTROL 連線埠]， [!UICONTROL 資料庫]， [!UICONTROL 使用者名稱]Power BI和其他)。

2. 在Power BI：

   1. 在主視窗中選取 **[!UICONTROL **&#x200B;取得資料&#x200B;**]** 從頂端工具列。

   2. 選取 **[!UICONTROL **&#x200B;更多……**]** 在左側邊欄中。

   3. 在 **取得資料** 畫面，搜尋 `PostgresSQL` 並選取 **[!UICONTROL ** PostgresSQL資料庫&#x200B;**]** 從清單中。

   4. 在 **[!UICONTROL ** PostgressSQL資料庫&#x200B;**]** 對話方塊：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 文字欄位。

      2. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 在 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 文字欄位。

         新增 `?FLATTEN` 至 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 引數，因此其顯示如下 `prod:all?FLATTEN` 例如。 另請參閱 [平面化巢狀資料結構以搭配協力廠商BI工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得詳細資訊。

      3. 當系統提示輸入 **[!UICONTROL **&#x200B;資料連線能力&#x200B;**]** 模式，選取 **[!UICONTROL ** DirectQuery **]** 以確保資料結構正確平面化。

      4. 系統會提示您輸入 **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** 和 **[!UICONTROL **&#x200B;密碼&#x200B;**]**. 使用Experience Platform查詢中的對等引數 [!UICONTROL 認證].
   5. 成功登入後，CJA資料檢視表格會出現在Power BI的 **[!UICONTROL **&#x200B;導覽器&#x200B;**]**. 識別資料檢視表的方法為使用 `dv_` 以他們的名稱。


   6. 選取您要使用的資料檢視表格，然後選取 **[!UICONTROL **&#x200B;載入&#x200B;**]**.

   與一個或多個選定表格相關的所有維度和量度都會顯示在右窗格中，並準備好用於您的視覺效果中。

   另請參閱 [將Power BI連線至查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 以取得詳細資訊。

+++

+++Tableau

1. 在Experience PlatformUI中，查詢您的PostgresSQL認證的詳細資訊。

   1. 選取 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄（在下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選取 **[!UICONTROL **&#x200B;認證&#x200B;**]** 從頂端列。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 若要複製每個Postgres認證引數([!UICONTROL 主機]， [!UICONTROL 連線埠]， [!UICONTROL 資料庫]， [!UICONTROL 使用者名稱]和其他)。

2. 在Tableau：

   1. 選取 **[!UICONTROL **&#x200B;更多&#x200B;**]** 從 **[!UICONTROL **&#x200B;至伺服器&#x200B;**]** 在左側邊欄中。

   2. 選取 **[!UICONTROL ** PostgresSQL **]** 從清單中。

   3. 在 [!UICONTROL PostgresSQL] 對話方塊：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 文字欄位。

      2. 貼上 **[!UICONTROL **&#x200B;連線埠&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;連線埠&#x200B;**]** 文字欄位。

      3. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 文字欄位。

         新增 `%3FFLATTEN` 至 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 引數，因此其顯示如下 `prod:all%3FFLATTEN` 例如。 另請參閱 [平面化巢狀資料結構以搭配協力廠商BI工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得詳細資訊。

      4. 選取 **[!UICONTROL **&#x200B;使用者名稱和密碼&#x200B;**]** 從 **[!UICONTROL **&#x200B;驗證&#x200B;**]** 清單。

      5. 貼上 **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** 文字欄位。

      6. 貼上 **[!UICONTROL **&#x200B;密碼&#x200B;**]** Experience Platform查詢中的引數 [!UICONTROL 認證] 到 **[!UICONTROL **&#x200B;密碼&#x200B;**]** 文字欄位。

      7. 選取 **[!UICONTROL **&#x200B;登入&#x200B;**]**.
   4. CJA資料檢視在中顯示為表格 **[!UICONTROL **&#x200B;表格&#x200B;**]** 清單。 資料檢視表的前置詞為 `dv_`.

   5. 拖曳您要在畫布上使用的表格。

   您現在可以使用資料檢視表格中的資料，以建置您的報告和視覺效果。

   另請參閱 [將Tableau連線至查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 以取得詳細資訊。

+++

另請參閱 [將使用者端連線至查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 有關各種可用工具的概覽和更多資訊。

## 功能

依預設，您的資料檢視具有從易記名稱產生的表格安全名稱。 例如，資料檢視命名為 [!UICONTROL 我的網頁資料] 具有檢視名稱 `dv_my_web_data`.

如果您想要使用資料檢視ID作為表格名稱，可以新增選用的 `CJA_USE_IDS` 設定為您的資料庫名稱。 例如， `prod:all?CJA_USE_IDS` 顯示您的資料檢視，名稱如下 `dv_ABC123`.

### 数据管理

Customer Journey Analytics中的資料控管相關設定繼承自Adobe Experience Platform。 CJA 和 Adobe Experience Platform 数据管理之间的集成允许标记敏感 CJA 数据和实施隐私政策。

在 Experience Platform 使用的数据集上创建的隐私标签和策略可以在 CJA 数据视图工作流中显示。 因此，使用CJA SQL Connector查詢的資料在未遵守定義的隱私權標籤和原則時會顯示適當的警告或錯誤。

### 列出資料檢視

在標準PostgreSQL CLI中，您可以使用以下專案列出檢視： `\dv`

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

### 巢狀與平面化

依預設，資料檢視的結構描述會使用巢狀結構，就像原始的XDM結構描述一樣。 此整合也支援 `FLATTEN` 選項。 您可以使用此選項來強制資料檢視（和工作階段中的任何其他表格）的架構平面化。 平面化可讓您在不支援結構化結構描述的BI工具中更輕鬆地使用。 另請參閱 [在查詢服務中使用巢狀資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得詳細資訊。

### 支援的SQL

另請參閱 [查詢服務SQL參考](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以取得支援哪種SQL型別的完整參考。

請參閱下方的圖樣表格，以取得圖樣和範例的概觀。

+++模式

| 模式 | 示例 |
|---|---|
| 結構描述探索 | <pre>選取*從dv1，其中1=0</pre> |
| 排名/劃分 | <pre>選取dim1，SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按dim1分組</pre><pre>選取dim1，SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，並且<br/>  filterId = &#39;12345&#39;<br/>按dim1分組</pre><pre>選取dim1，SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，並且<br/>  AND (dim2 = &#39;A&#39;或dim3 IN (&#39;X&#39;， &#39;Y&#39;， &#39;Z&#39;))<br/>按dim1分組</pre> |
| HAVING子句 | <pre>選取dim1，SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按dim1分組<br/>擁有m1 > 100</pre> |
| 相異，頂端 <br/>維度值 | <pre>從dv1選取不同的DIM1</pre><pre>選取dim1 AS dv1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按dim1分組</pre><pre>選取dim1 AS dv1<br/>從dv1<br/>其中\&#39;timestamp\&#39; >= &#39;2022-01-01&#39;和\&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>按dim1分組<br/>ORDER BY SUM(metric1)<br/>上限15</pre> |
| 量度總計 | <pre>選取SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</pre> |
| 多維度<br/>劃分<br/>和頂級特性 | <pre>選取dim1、dim2、SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>群組依據dim1， dim2</pre><pre>選取dim1、dim2、SUM(metric1) AS m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按1、2分組<br/>ORDER BY 1， 2</pre><pre>選取DISTINCT dim1， dim2<br/>從dv1</pre> |
| 子選取：<br/>其他結果<br/>篩選 | <pre>選取dim1， m1<br/>從(<br/>  選取dim1，SUM(metric1) AS m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</br>  按dim1分組<br/>)<br/>WHERE dim1在(&#39;A&#39;， &#39;B&#39;)</pre> |
| 子選取：<br/>加入<br/>資料集不在<br/>CJA | <pre>選取b.key， a.dim1， a.m1<br/>從(<br/>  選取dim1，SUM(metric1) AS m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按dim1分組<br/>) a<br/>LEFT JOIN查閱b ON a.dim1 = b.key</pre> |
| 子選取：<br/>查詢跨越<br/>資料檢視 | <pre>SELECT索引鍵，SUM(m1) AS total<br/>從(<br/>  選取dim1作為索引鍵，選取SUM(metric1) AS m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按dim1分組<br/><br/>  聯集<br/><br/>  選取dim2作為索引鍵，選取SUM(m1) AS m1<br/>  從dv2<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按dim2分組<br/>依索引鍵分組<br/>ORDER BY總計</pre> |
| 子選取： <br/>分層來源， <br/>篩選， <br/>和彙總 | 使用子選取項進行分層：<br><pre>選取rows.dim1， SUM(rows.m1) AS total<br/>從(<br/>  選取\_.dim1，\_.m1<br/>  從(<br/>    從dv1選取\*<br/>    其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  ) \_<br/>  其中\_.dim1於(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>)列<br/>按1分組<br/>ORDER BY總計</pre><br/>搭配使用CTE的圖層：<br/><pre>列為(<br/>  以\_ AS (<br/>    選取*從data_ares<br/>    其中\&#39;timestamp\&#39;介於&#39;2021-01-01&#39;和&#39;2021-02-01&#39;之間<br/>  )<br/>  選取_.item，_.units FROM _<br/>  其中_.item不是NULL<br/>)<br/>SELECT rows.item， SUM(rows.units) AS units<br/>FROM列WHERE rows.item在(&#39;A&#39;， &#39;B&#39;， &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 選取<br/>量度排在前<br/> 或混合<br/>維度 | <pre>選取SUM(metric1) AS m1， dim1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按2分組</pre> |

{style="table-layout:auto"}

+++

### 维度

您可以選取任何預設可用的維度或在資料檢視中定義的維度。 您可以依維度的ID來選取維度。

### 度量

可供選取的量度包括：

- 任何預設可用的量度，

- 在資料檢視中定義，

- 與使用者有權存取的資料檢視相容的計算量度。

您可以透過包在中的量度ID來選取量度 `SUM(metric)` 運算式，就像處理其他SQL來源一樣。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 以取得發生次數量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 以計算維度的近似相異值。 請參閱以下連結中的詳細資料： [計算差異](#counting-distincts).

- [內嵌計算](#inline-calculations) 快速組合量度和/或對其執行數學。

#### 計算差異

由於CJA運作方式的基礎性質，您唯一可獲得確切相異計數的維度是 `adobe_personid` 維度。 下列SQL敘述句 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 傳回預設訪客量度的值，該量度為不同人員的計數。 對於其他維度，會傳回近似的相異計數。

#### 條件量度

您可以內嵌 `IF` 或 `CASE` 子句於 `SUM` 或 `COUNT` 函式來新增所選量度特定的其他篩選。 新增這些子句類似於將篩選器套用至Workspace報表表格中的量度欄。

示例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 內嵌計算

您可以將其他套用至量度運算式，在 `SELECT` 而不需在計算量度中定義數學。 下表列出支援的運算式型別。

| 運運算元或函式 | 详细信息 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、減、乘、除和模數/餘數 |
| `-X` 或 `+X` | 變更符號或量度，其中X是量度運算式 |
| `PI()` | π常數 |
| `POSITIVE`， `NEGATIVE`， `ABS`， `FLOOR`， `CEIL`， `CEILING`， `EXP`， `LN`， `LOG10`， `LOG1P`， `SQRT`， `CBRT`， `DEGREES`， `RADIANS`， `SIN`， `COS`， `TAN`， `ACOS`， `ASIN`， `ATAN`， `COSH`， `SINH`、和 `TANH` | 一元數學函式 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二進位數學函式 |

{style="table-layout:auto"}

### 特殊欄

**时间戳**

此 `timestamp` 特殊欄用於提供查詢的日期範圍。 日期範圍可透過以下方式定義： `BETWEEN` 運算式或一對 `timestamp` `>`， `>=`， `<`， `<=` 檢查 `AND`ed在一起。
此 `timestamp` 為選用，若未提供完整範圍，則會使用預設值：

- 如果只提供最低值(`timestamp > X` 或 ` timestamp >= X`)，範圍是從X到現在。

- 如果只提供最大值(`timestamp < X` 或 `timestamp <= X`)，範圍為X-30天到X。

- 如果未提供任何專案，則範圍為從現在–30天到現在。

時間戳記範圍會轉換為RankingRequest中的日期範圍全域篩選器。
時間戳記欄位也可用於日期 — 時間函式，以剖析、截斷事件時間戳記。

**日期范围**

此 `daterange` 特殊欄的工作方式類似於  `timestamp`，但篩選時間限製為完整天。 此 `daterange` 也是選用專案，其預設範圍與相同 `timestamp`.
此 `daterange` 欄位也可用於日期時間函式，以剖析、截斷事件日期。

**filterId**

此 `filterId` 特殊欄是選用欄位，用於將外部定義的篩選器套用至查詢。 將外部定義的篩選器套用至查詢，類似於在工作區中的面板上拖曳篩選器。 下列專案可提供多個篩選器ID： `AND` — 他們。

### WHERE子句

WHERE子句有三個步驟處理：

1. 從以下位置尋找日期範圍： `timestamp` 特殊欄位。

2. 尋找任何外部定義的 `filterId`要包含在篩選中的。

3. 將剩餘運算式轉換為臨時篩選。

處理是透過剖析第一層級來完成 `AND`位於 `WHERE` 子句。 每個頂層 `AND`ed運算式必須符合上述其中一項。 任何比第一層級更深入的內容 `AND`s，或，如果 `WHERE` 子句使用 `OR`在頂層，會以臨時篩選來處理。

### 排序方式

依預設，查詢會依第一個選取的量度以遞減順序來排序結果。 您可以透過指定覆寫預設的排序順序 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`. 如果您使用 `ORDER BY`，您必須指定 `ORDER BY` 於第一個選取的量度。

您也可以使用反向順序 `-` （減號）在量度之前。 以下兩個陳述式會產生相同的順序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支援

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [CAST(COLUMN AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 目前不支援型別轉換，但不會擲回錯誤。 此 `CAST` 已忽略函式。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 將時間字串剖析為時間戳記，以便用於 `WHERE` 子句。 |
| [TO_TIMESTAMP(timeString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 將時間字串剖析為時間戳記，以便用於 `WHERE` 子句，選擇性地提供該時間字串的格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 將日期字串剖析為時間戳記，以便用於 `WHERE` 子句。 |
| [TO_DATE(dateString， formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 將日期字串剖析為時間戳記，以便用於 `WHERE` 子句，選擇性地提供該日期字串的格式。 |

{style="table-layout:auto"}

### Dimension功能支援

這些函式可用於中的維度 `SELECT`， `WHERE` 子句中或在條件量度中。

**字符串函数**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在傳入的欄位上產生動態維度身分識別。 |

{style="table-layout:auto"}

**日期時間函式**

| 函数 | 示例 | 详细信息 |
|---|---|---|
| [YEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [MONTH（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [DAY（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [DAYOFWEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 使用專案ID而非值，因為您需要編號而不是好記名稱。 |
| [DAYOFYEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [WEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [QUARTER（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [HOUR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 使用專案ID而非值，因為您需要編號而不是好記名稱。 |
| [MINUTE（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 使用專案ID而非此函式某些部分的值，因為您需要編號而不是好記名稱。<br/>支援的零件包括：<br> — 關鍵字： `YEAR`， `MONTH`， `DAYOFMONTH`， `DAYOFWEEK`， `DAYOFYEAR`， `WEEK`， `QUARTER`， `HOUR`， `MINUTE`.<br/> — 字串：  `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_PART（part， date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。 使用專案ID而非此函式某些部分的值，因為您需要編號而不是好記名稱。<br/>支援的字串部分包括： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |
| [DATE_TRUNC（粒度、日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在傳入的欄位上產生動態維度身分識別。<br/>支援的字串粒度為： `'YEAR'`， `'Y'`， `'MONTH'`， `'M'`， `'DAYOFMONTH'`， `'DAY'`， `'D'`， `'DAYOFWEEK'`， `'DOW'`， `'DAYOFYEAR'`， `'DOY'`， `'WEEK'`， `'WOY`&#39;， `'W'`， `'QUARTER'`， `'QOY'`， `'Q'`， `'HOUR'`，或 `'MINUTE'`. |

{style="table-layout:auto"}

