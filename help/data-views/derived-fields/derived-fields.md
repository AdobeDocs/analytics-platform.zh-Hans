---
title: 派生字段
description: 派生字段通过一组可用函数和函数模板来指定模式字段和/或标准组件的报告时间操作。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
badgeDerivedFields: label="New Feature" type="Positive"
source-git-commit: cb63cd52a1618f2e1048f2779c4e6c0317e94f64
workflow-type: tm+mt
source-wordcount: '3003'
ht-degree: 8%

---


# 派生字段

{{release-limited-testing}}

>[!NOTE]
>
>待定的最终更新，您可能会看到 [!UICONTROL 自定义字段] 而不是 [!UICONTROL 派生字段] 跨用户界面。


派生字段是Customer Journey Analytics(CJA)中实时报表功能的一个重要方面。 利用派生字段，可通过可自定义的规则生成器，即时定义（通常复杂）数据操作。 然后，您可以将该派生字段用作 [工作区](../../analysis-workspace/home.md) 或进一步将派生字段定义为 [数据视图](../data-views.md).

与转换或处理CJA外其他位置的数据相比，派生字段可节省大量时间和精力。 例如 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans), [数据Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)，或在您自己的提取转换加载(ETL)/提取加载转换(ELT)流程中。

派生字段在 [数据视图](../data-views.md)，基于一组定义为规则的函数，并应用于可用的标准和/或架构字段。

示例用例包括：

- 定义派生的“页面名称”字段，以更正不正确收集的页面名称值，从而更正页面名称值。

- 定义派生的“营销渠道”字段，以根据一个或多个条件（例如URL参数、页面URL、页面名称）确定适当的营销渠道。

## 派生字段接口

创建或编辑派生字段时，使用派生字段界面。

![派生字段对话框](assets/derived-field-dialog.png)


|  | 名称 | 描述 |
|---------|----------|--------|
| 1 | **选择器** | 您可以使用选择器区域选择并拖放您的 ![函数](assets/Smock_Function_18_N.svg) 函数，![函数模板图标](assets/Smock_FileTemplate_18_N.svg) 函数模板，![架构字段图标](assets/Smock_Folder_18_N.svg) 架构字段，或![“标准字段”图标](assets/Smock_DragHandle_18_N.svg)标准字段。 <br/>使用下拉菜单选择 [!UICONTROL 函数], [!UICONTROL 函数模板], [!UICONTROL 架构字段]和 [!UICONTROL 标准字段].<br/>您可以使用 ![“搜索”图标](assets/Smock_Search_18_N.svg) 搜索框。 <br/>您可以通过选择 ![“过滤器”图标](assets/Smock_Filter_18_N.svg) 在 [!UICONTROL 过滤字段依据] 对话框。 您可以使用 ![关闭图标](assets/CrossSize75.svg) 的值。 |
| 2 | **规则生成器** | 您可以使用一个或多个规则按顺序构建派生字段。 规则是函数的特定实现，因此始终只与一个函数关联。 通过将函数拖放到规则生成器中来创建规则。 函数类型确定规则的界面。<br/>请参阅 [规则界面](#rule-interface) 以了解更多信息。 <br/>您可以在规则生成器中已有的可用规则之间，在开始、结束或插入函数。 规则生成器中的最后一个规则确定派生字段的最终输出。 |
| 3 | **[!UICONTROL **&#x200B;字段设置&#x200B;**]** | 您可以命名并描述派生字段，并检查其字段类型。 |
| 4 | **[!UICONTROL **&#x200B;最终输出&#x200B;**]** | 此区域会根据过去30天的数据以及您对规则生成器中的派生字段所做的更改，即时显示输出值的更新预览。 |

{style="table-layout:auto"}

## 字段模板向导

首次访问派生字段界面时， [!UICONTROL 从字段模板开始] 向导。

1. 选择最能描述您尝试创建的字段类型的模板。
2. 选择 **[!UICONTROL **&#x200B;选择&#x200B;**]** 按钮继续。

派生字段对话框中填充了对所选字段类型必需或有用的规则（和函数）。 请参阅 [函数模板](#function-templates) 以了解有关可用模板的更多信息。

## 规则界面

在规则生成器中定义规则时，您将使用规则界面。

![规则界面](assets/rule-interface.png)

|  | 名称 | 描述 |
|---------|----------|--------|
| A | **规则名称** | 默认情况下，规则名称为 **规则X** （X引用序列号）。 要编辑规则的名称，请选择其名称并键入新名称，例如 `Query Parameter`. |
| B | **函数名称** | 例如，规则的选定函数名称 [!DNL URL PARSE]. 当函数是函数序列中的最后一个函数并确定最终输出值时，函数名称后跟 [!DNL - FINAL OUTPUT]，例如 [!DNL URL PARSE - FINAL OUTPUT]. <br/>要显示包含函数更多信息的弹出窗口，请选择 ![“帮助”图标](assets/Smock_HelpOutline_18_N.svg). |
| C | **规则描述** | 您可以选择向规则添加描述。<br/>选择 ![“更多”图标](assets/More.svg)，然后选择 **[!UICONTROL **&#x200B;添加描述&#x200B;**]** 添加描述或 **[!UICONTROL **&#x200B;编辑描述&#x200B;**]** 以编辑现有描述。<br/>使用编辑器输入描述。 您可以使用工具栏设置文本格式（使用样式选择器、粗体、斜体、下划线、右、左、居中、颜色、数字列表、项目符号列表），并添加指向外部信息的链接。 <br/>要完成编辑描述，请在编辑器外部单击。 |
| D | **功能区** | 定义函数的逻辑。 接口取决于函数的类型。 请参阅 [函数引用](#function-reference) 详细了解支持的每个功能。 |

{style="table-layout:auto"}

## 创建派生字段

1. 选择现有的数据视图或创建数据视图。 请参阅 [数据视图](../data-views.md) 以了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;创建派生字段&#x200B;**]** 从左边栏。

4. 要定义派生字段，请使用 [!UICONTROL 创建派生字段] 界面。 请参阅 [派生字段接口](#derived-field-interface).

   要保存新的派生字段，请选择 **[!UICONTROL **&#x200B;保存&#x200B;**]**.

5. 您的新派生字段将添加到 [!UICONTROL 派生字段>] 容器，作为 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 的双曲余切值。


## 编辑派生字段

1. 选择现有数据视图。 请参阅 [数据视图](../data-views.md) 以了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 选项卡 [!UICONTROL 连接] 窗格。

4. 选择 **[!UICONTROL **&#x200B;派生字段>**]** 容器。

5. 将鼠标悬停在要编辑的派生字段上，然后选择 ![“编辑”图标](assets/Smock_Edit_18_N.svg).

6. 要编辑派生字段，请使用 [!UICONTROL 编辑派生字段] 界面。 请参阅 [派生字段接口](#derived-field-interface).

   - 选择 **[!UICONTROL **&#x200B;保存&#x200B;**]** 以保存更新的派生字段。

   - 选择 **[!UICONTROL **&#x200B;取消&#x200B;**]** 取消您对派生字段所做的任何更改。

   - 选择 **[!UICONTROL **&#x200B;另存为&#x200B;**]** 将派生字段另存为新派生字段。 新派生字段与原始编辑的派生字段具有相同的名称，其中 `(copy)` 中。

## 删除派生字段

1. 选择现有数据视图。 请参阅 [数据视图](../data-views.md) 以了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 选项卡 [!UICONTROL 连接] 中。

4. 选择 **[!UICONTROL **&#x200B;派生字段>**]** 容器。

5. 将鼠标悬停在要删除的派生字段上，然后选择 ![“编辑”图标](assets/Smock_Edit_18_N.svg).

6. 使用中 **[!UICONTROL **&#x200B;编辑派生字段&#x200B;**]** 界面中，选择删除。

   A [!UICONTROL 删除组件] 对话框要求您确认删除。 考虑数据视图外的派生字段可能存在的任何外部引用。

   - 选择 **[!UICONTROL **&#x200B;继续&#x200B;**]** 删除派生字段。


## 函数模板

为了快速为特定用例创建派生字段，可使用函数模板。 这些函数模板可以从派生字段界面的选择器区域访问，或在 [!UICONTROL 从字段模板开始] 向导。


### 营销渠道

此模板配置为使用 [Url解析](#dnl-url-parse) 和 [用例](#dnl-case-when) 函数多次，以从URL获取适当的值。 然后，对这些值应用逻辑，以将URL与特定营销渠道关联。

+++ 详细信息

要使用模板，必须为作为模板规则一部分列出的每个函数指定正确的参数。 请参阅 [函数引用](#function-reference) 以了解更多信息。

![营销渠道模板规则生成器](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 函数引用

对于每个受支持的函数，请在下面找到详细信息：

- 规范：
   - 输入数据类型：支持的数据类型，
   - 输入：输入的可能值，
   - 包含的运算符：此函数支持的运算符（如果有），
   - 限制：可在派生字段中使用的最大规则数（使用此函数），
   - 输出。

- 用例包括：
   - 定义派生字段前的数据，
   - 如何定义派生字段，
   - 定义派生字段后的数据。

- 约束（如果适用）。


<!-- Concatenate -->

### [!DNL Concatenate]

将两个或多个字段、派生字段或用户输入的值合并到具有定义分隔符的单个字段中。

+++ 详细信息

## 规范 {#concatenate-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|:--:|---|
| <p>字符串</p> | <ul><li>要组合的两个或多个值<ul><li>字段</li><li>从前一个规则派生的值</li><li>用户输入的值</li></ul></li><li>分隔符<ul><li>输入或选择每个值的分隔符</li></ul></li> </ul> | <p>不适用</p> | <p>2</p> | <p>新派生字段</p> |

{style="table-layout:auto"}


## 用例 {#concatenate-uc}

您当前将原点和目的地机场代码作为单独的字段进行收集。 您希望获取这两个字段，并将它们合并到一个以连字符(-)分隔的维度中。 因此，您可以分析原点和目的地的组合，以确定已预订的最热门的路线。

假设：

- 源值和目标值在同一表中的单独字段中收集。
- 用户确定在值之间使用分隔符“ — ”。

想象一下，将发生以下预订：

- 客户ABC123预订在盐湖城(SLC)和奥兰多(MCO)之间的航班
- 客户ABC456预订在盐湖城(SLC)和洛杉矶(LAX)之间的航班
- 客户ABC789预订在盐湖城(SLC)和西雅图(SEA)之间的航班
- 客户ABC987预订在盐湖城(SLC)和圣何塞(SJO)之间的航班
- 客户ABC654预订在盐湖城(SLC)和奥兰多(MCO)之间的航班

所需的报表应当类似于：

| 源/目标 | 预订 |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 数据之前 {#concatenate-uc-databefore}

| Origin | 目标 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生字段 {#concatenate-derivedfield}

您定义新 [!UICONTROL 源 — 目标] 派生字段。 您使用 [!UICONTROL 连接] 函数来定义要连接的规则 [!UICONTROL 原始] 和 [!UICONTROL 目标] 字段 `-` [!UICONTROL 分隔符].

![[!DNL Concatenate] 规则](assets/concatenate.png)

### 之后的数据 {#concatenate-dataafter}

| 源 — 目标<br/>（派生字段） |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

根据一个或多个字段中的定义条件应用条件。 然后，这些条件用于根据条件的顺序定义新派生字段中的值。

+++ 详细信息

## 规范 {#casewhen-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|:---:|---|
| <ul><li>字符串</li><li>数值</li><li>Date/Date-Time</li></ul> | <ul><li>输入字段</li><li>条件</li></ul> | <p><u>字符串</u></p><ul><li>等于</li><li>等于任何词语</li><li>包含该短语</li><li>包含任何词语</li><li>包含所有词语</li><li>开始于</li><li>以任意词开头</li><li>结束于</li><li>以任何术语结尾</li><li>不等于</li><li>不等于任何词语</li><li>不包含该短语</li><li>不包含任何词语</li><li>不包含所有词语</li><li>未始于</li><li>不以任何术语开头</li><li>未止于</li><li>不以任何术语结尾</li><li>已设置</li><li>未设置</li></ul><p><u>数值</u></p><ul><li>等于</li><li>不等于</li><li>高于</li><li>高于或等于</li><li>低于</li><li>低于或等于</li><li>已设置</li><li>未设置</li></ul><p><u>日期</u></p><ul><li>等于</li><li>不等于</li><li>晚于</li><li>晚于或等于</li><li>在之前</li><li>早于或等于</li><li>已设置</li><li>未设置</li></ul> | <p>5</p> | <p>新派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#casewhen-uc1}

您需要定义规则以通过应用级联逻辑将营销渠道字段设置为正确的值，来识别各种营销渠道：

- 如果反向链接来自搜索引擎，并且页面具有查询字符串值，其中 `cid` 包含 `ps_`，营销渠道应被识别为 [!DNL *付费搜索*].
- 如果反向链接来自搜索引擎，并且页面没有查询字符串 `cid`，营销渠道应被识别为 [!DNL *免费搜索*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `em_`，营销渠道应被识别为 [!DNL *电子邮件*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `ds_`，营销渠道应被识别为 [!DNL *展示广告*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `so_`，营销渠道应被识别为 [!DNL *付费社交*].
- 如果反向链接来自的反向链接域 [!DNL twitter.com], [!DNL facebook.com], [!DNL linkedin.com]或 [!DNL tiktok.com]，营销渠道应被识别为 [!DNL *自然社交*].
- 如果上述规则均不匹配，则应将营销渠道标识为 [!DNL *其他反向链接*].

如果您的网站收到以下示例事件，包含 [!UICONTROL 反向链接] 和 [!UICONTROL 页面URL]，则这些事件应如下所示：

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 |  | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 数据之前 {#casewhen-uc1-databefore}

| [!UICONTROL 反向链接] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### 派生字段 {#casewhen-uc1-derivedfield}

您定义新 `Marketing Channel` 派生字段。 您使用 [!UICONTROL 大小写] 函数来定义规则，以便根据这两个规则的现有值为其创建值 `Page URL` 和 `Referring URL` 字段。

请注意函数的用法 [!UICONTROL URL解析] 定义规则以获取 `Page Url` 和 `Referring Url` 在 [!UICONTROL 大小写] 规则。

![[!DNL Case when] 规则1](assets/case-when-1.png)

### 之后的数据 {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## 用例2 {#casewhen-uc2}

您在 [!DNL Product Finding Methods] 维度。 要了解搜索与浏览的整体性能，您必须花费大量时间手动组合结果。

您的网站会为您的 [!DNL Product Finding Methods] 维度。 最后，所有这些值都表示搜索。

| 收集的值 | 实际值 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes ] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 数据之前 {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### 派生字段 {#casewhen-uc2-derivedfield}

您定义 `Product Finding Methods (new)` 派生字段。 您可以创建以下内容 [!UICONTROL 大小写] 规则生成器中的规则。 这些规则会将逻辑应用于旧的所有可能变体 [!UICONTROL 产品查找方法] 字段值 `search` 和 `browse` 使用 [!UICONTROL 包含短语] 标准。

![[!DNL Case When] 规则2](assets/case-when-2.png)

### 之后的数据 {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## 用例3 {#casewhen-uc3}

作为一家旅游公司，您希望将已预订行程的行程时长存储起来，以便报告已存储的行程时长。

假设：

- 组织正在将行程持续时间收集到数字字段中。
- 他们希望将1-3天的持续时间存储到名为“[!DNL short trip]&#39;
- 他们希望将4-7天的持续时间存储到名为“[!DNL medium trip]&#39;
- 他们希望将8天以上的持续时间存储到名为“[!DNL long trip]&#39;
- 132次旅行被预订，为期1天
- 共预订了110次旅行，为期2天
- 共预订了105次旅行，为期3天
- 99次旅行在4天内预订
- 92次旅行在5天内预订
- 85次旅行在6天内预订
- 82次旅行在7天内预订
- 为期8天的78次旅行预订
- 50次旅行已预订9天
- 44次旅行在10天内预订
- 38次旅行在11天内预订
- 31次旅行在12天内预订

所需的报表应类似于：

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### 数据之前 {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### 派生字段 {#casewhen-uc3-derivedfield}

您定义 `Trip Duration (bucketed)` 派生字段。 您可以创建以下内容 [!UICONTROL 大小写] 规则生成器中的规则。 此规则将逻辑应用于存储旧 [!UICONTROL 行程持续时间] 字段值分为三个值： `short trip`, `medium  trip`和 `long trip`.

![[!DNL Case When] 规则3](assets/case-when-3.png)


### 之后的数据 {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## 约束

CJA使用嵌套的容器结构，该结构建模于Adobe Experience Platform [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) （体验数据模型）。 请参阅 [容器](../create-dataview.md#containers) 和 [过滤器容器](../../components/filters/filters-overview.md#filter-containers) 以了解更多背景信息。 此容器模型虽然在性质上是灵活的，但在使用规则生成器时仍会施加一些限制。

CJA使用以下默认容器模型：

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>



以下约束在 *选择* 和 *设置* 值。

|  | 约束 |
|:---:|----|
| **<span style='color: red'>A</span>** | 您的值 *选择* 在同一 [!UICONTROL 如果], [!UICONTROL Else If] 构造(使用 [!UICONTROL 和] 或 [!UICONTROL 或])必须源于同一容器，并且可以是任何类型（字符串） ![字符串](assets/Smock_ABC_18_N.svg)，数字 ![数值](assets/Smock_123_18_N.svg)，等等)。 <br/>![依赖项A](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | 所有值 *set* 跨规则必须来自同一容器，并且具有相同类型或派生值的相同类型。 <br/> ![依赖项B](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | 您的值 *选择* 跨 [!UICONTROL 如果], [!UICONTROL Else If] 规则中的构造 *not* 必须源自同一容器，并且 *not* 必须是同一类型。 <br/> ![依赖项C](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

查找选定字段中的所有值，并在新派生字段中将这些值替换为不同的值。

+++ 详细信息

## 规范 {#findreplace-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|:---:|---|
| <p>字符串</p> | <ul><li><span>“替换时间”字段标准</span></li><li><span>“替换为”字段值</span><ul><li><span>用户输入</span></li><li><span>单独字段</span></li></ul></li></ul> | <p><u>字符串</u></p><ul><li>全部查找并全部替换</li></ul> | <p>1</p> | <p>新派生字段</p> |

{style="table-layout:auto"}


## 用例 {#findreplace-uc}

例如，您收到了外部营销渠道报表的一些格式错误的值 `email%20 marketing` 而不是 `email marketing`. 这些格式错误的值会断开您的报表，使您更难以查看电子邮件的执行情况。 要替换 `email%20marketing` with `email marketing`.

**原始报表**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**首选报表**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### 数据之前 {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生字段 {#findreplace-uc-derivedfield}

您定义 `Email Marketing (updated)` 派生字段。 您使用 [!UICONTROL 查找和替换] 函数来定义规则以查找和替换所有出现的 `email%20marketing` with `email marketing`.

![[!DNL Find and Replace] 规则](assets/find-and-replace.png)

### 之后的数据 {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

定义一组由相应值替换的查找值。

+++ 详细信息


## 规范 {#lookup-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|:---:|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>单个字段</li><li>查找文件<ul><li>Key Column（键列）</li><li>新建字段列</li></ul></li></ul> | <p>不适用</p> | <p>5</p> | <p>新派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#lookup-uc1}

您的CSV文件中包含的键列适用于 `hotelID` 和与 `hotelID`: `city`, `rooms`, `hotel name`.
您正在收集 [!DNL Hotel ID] ，但是希望创建 [!DNL Hotel Name] 从派生的维度 `hotelID` 中。

**CSV文件结构和内容**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |

{style="table-layout:auto"}

**当前报表**

| [!DNL Hotel ID] | 产品查看次数 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |

{style="table-layout:auto"}


**所需报表**

| [!DNL Hotel Name] | 产品查看次数 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 数据之前 {#lookup-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |

{style="table-layout:auto"}


### 派生字段 {#lookup-uc1-derivedfield}

您定义 `Hotel Name` 派生字段。 您使用 [!UICONTROL 查找] 函数来定义一个规则，您可以在该规则中查找 [!UICONTROL 酒店ID] 字段，并替换为新值。

![[!DNL Lookup] 规则1](assets/lookup-1.png)

### 之后的数据 {#lookup-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 用例2 {#lookup-uc2}

您收集了多个页面的URL，而不是易记页面名称。 此混合值集合会中断报表。

### 数据之前 {#lookup-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### 派生字段 {#lookup-uc2-derivedfield}

您定义 `Page Name (updated)` 派生字段。 您使用 [!UICONTROL 查找] 函数来定义规则，从中查找现有值 [!UICONTROL 页面名称] 字段，并替换为更新的正确值。

![[!DNL Lookup] 规则2](assets/lookup-2.png)

### 之后的数据 {#lookup-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

解析URL的不同部分，包括协议、主机、路径或查询参数。

+++ 详细信息

## 规范 {#urlparse-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|:---:|---|
| <ul><li>字符串</li></ul> | <ul><li>单个字段</li><li>解析选项<ul><li>获取协议</li><li>获取主机</li><li>获取路径</li><li>获取查询值<ul><li>查询参数</li></ul></li><li>获取哈希值</li></ul></li></ul></li></ul> | <p>不适用</p> | <p>5</p> | <p>新派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#urlparse-uc1}

您只希望将反向链接URL中的反向链接域用作营销渠道规则集的一部分。

### 数据之前 {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc1-derivedfield}

您定义  `Referring Domain` 派生字段。 您使用 [!UICONTROL URL解析] 函数来定义从 [!UICONTROL 引荐URL] 字段，并将其存储在新的派生字段中。

![[!DNL Url Parse] 规则1](assets/url-parse-1.png)

### 之后的数据 {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 用例2 {#urlparse-uc2}

要使用 `cid` 查询字符串的参数 [!DNL Page URL] 作为派生跟踪代码报表输出的一部分。

### 数据之前 {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc2-derivedfield}

您定义 `Query String CID` 派生字段。 您使用 [!UICONTROL URL解析] 函数，以定义规则以在 [!UICONTROL 页面URL] 字段，指定 `cid` 作为查询参数。 输出值将存储在新派生字段中。

![[!DNL Url Parse] 规则2](assets/url-parse-2.png)

### 之后的数据 {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++