---
title: 派生字段
description: 派生字段通过一组可用函数和函数模板指定对架构字段和/或标准组件的报告时间操作。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
source-git-commit: b8d6b8b0f2740e118bd744bcb7b7ee46aefc75ed
workflow-type: tm+mt
source-wordcount: '4348'
ht-degree: 15%

---


# 派生字段

派生字段是Adobe Customer Journey Analytics中实时报表功能的一个重要方面。 通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。然后，您可以将该派生字段用作中的组件（量度或维度） [工作区](../../analysis-workspace/home.md) 或者甚至进一步将派生字段定义为中的组件 [数据视图](../data-views.md).

与在Customer Journey Analytics之外的其他位置转换或处理数据相比，派生字段可以节省大量时间和精力。 例如 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)， [数据Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)，或在您自己的提取转换加载(ETL)/提取加载转换(ELT)进程中。

派生字段定义于 [数据视图](../data-views.md)基于一组定义为规则的函数，并应用于可用的标准和/或架构字段。

示例用例包括：

- 定义派生的“页面名称”字段，该字段可以更正不正确的收集页面名称值以更正页面名称值。

- 定义派生的营销渠道字段，以根据一个或多个条件（例如URL参数、页面URL、页面名称）确定正确的营销渠道。

## 派生字段界面

创建或编辑派生字段时，使用派生字段界面。

![派生字段对话框屏幕快照](assets/derived-field-dialog.png)


|  | 名称 | 描述 |
|---------|----------|--------|
| 1 | **选择器** | 您可以使用选择器区域选择您的函数、函数模板、架构字段或标准字段并将其拖放到规则生成器中。 <br/>使用下拉菜单在以下内容之间进行选择： <br/>![函数](assets/Smock_Function_18_N.svg) [!UICONTROL 函数]  — 列表可用 [函数](#function-reference)， </br>![“功能模板”图标](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL 函数模板]  — 列表可用 [函数模板](#function-templates)， <br/>![架构字段图标](assets/Smock_Folder_18_N.svg)  [!UICONTROL 架构字段]  — 列出数据集类别（事件、个人资料、查找）中可用的字段和以前定义的派生字段，以及 <br/>![“标准字段”图标](assets/Smock_DragHandle_18_N.svg) [!UICONTROL 标准字段]  — 标准可用字段（如Platform数据集ID）。 选择器中只显示字符串和数字标准字段。 如果函数支持其他数据类型，则可以为规则界面中的值或字段选择具有这些其他数据类型的标准字段。<br/>您可以使用以下内容搜索功能、功能模板、架构和标准字段 ![“搜索”图标](assets/Smock_Search_18_N.svg) 搜索框。 <br/>您可以通过选择来过滤所选对象列表 ![过滤器图标](assets/Smock_Filter_18_N.svg) 在中筛选和指定筛选器 [!UICONTROL 字段过滤条件] 对话框。 您可以使用轻松删除过滤器 ![“关闭”图标](assets/CrossSize75.svg) 每个过滤器的。 |
| 2 | **规则生成器** | 可使用一个或多个规则按顺序构建派生字段。 规则是函数的特定实现，因此始终只与一个函数关联。 通过将函数拖放到规则生成器中来创建规则。 函数类型确定规则的接口。<br/>请参阅 [规则界面](#rule-interface) 了解更多信息。 <br/>您可以在规则生成器中已可用的规则的开头、结尾或之间插入函数。 规则生成器中的最后一个规则确定派生字段的最终输出。 |
| 3 | **[!UICONTROL **&#x200B;字段设置&#x200B;**]** | 您可以命名和描述派生字段，并检查其字段类型。 |
| 4 | **[!UICONTROL **&#x200B;最终输出&#x200B;**]** | 此区域根据过去30天的数据以及您在规则生成器中对派生字段所做的更改，显示输出值的动态更新预览。 |

{style="table-layout:auto"}

## 字段模板向导

首次访问派生字段界面时， [!UICONTROL 从字段模板开始] 将显示向导。

1. 选择最能描述您尝试创建的字段类型的模板。
2. 选择 **[!UICONTROL **&#x200B;选择&#x200B;**]** 按钮以继续。

派生的字段对话框中填充了所选字段类型所需的或有用的规则（和函数）。 参见 [函数模板](#function-templates) 以了解有关可用模板的详细信息。

## 规则界面

在规则生成器中定义规则时，将使用规则界面。

![派生字段规则界面的屏幕截图](assets/rule-interface.png)

|  | 名称 | 描述 |
|---------|----------|--------|
| A | **规则名称** | 默认情况下，规则名称为 **规则X** （X表示序列号）。 要编辑规则的名称，请选择其名称，然后键入新名称，例如 `Query Parameter`. |
| B | **函数名称** | 规则的选定函数名称，例如 [!UICONTROL URL分析]. 当函数是函数序列中的最后一个并确定最终输出值时，函数名称后面跟有 [!UICONTROL  — 最终输出]例如 [!UICONTROL URL分析 — 最终输出]. <br/>要显示包含函数详细信息的弹出窗口，请选择 ![“帮助”图标](assets/Smock_HelpOutline_18_N.svg). |
| C | **规则描述** | 您可以选择向规则添加描述。<br/>选择 ![“更多”图标](assets/More.svg)，然后选择 **[!UICONTROL **&#x200B;添加描述&#x200B;**]** 添加描述或 **[!UICONTROL **&#x200B;编辑描述&#x200B;**]** 以编辑现有描述。<br/>使用编辑器输入说明。 您可以使用工具栏设置文本格式（使用样式选择器、粗体、斜体、下划线、右、左、居中、颜色、数字列表、项目符号列表）并向外部信息添加链接。 <br/>要完成编辑说明，请单击编辑器外部的。 |
| D | **功能区域** | 定义函数的逻辑。 接口取决于函数的类型。 的下拉列表 [!UICONTROL 字段] 或 [!UICONTROL 值] 根据函数期望的输入类型，显示所有类别的可用字段（规则、标准字段、字段）。 参见 [函数引用](#function-reference) 每个受支持功能的详细信息。 |

{style="table-layout:auto"}

## 创建派生字段

1. 选择现有数据视图或创建数据视图。 参见 [数据视图](../data-views.md) 了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;创建派生字段&#x200B;**]** 从左边栏开始。

4. 要定义派生字段，请使用 [!UICONTROL 创建派生字段] 界面。 参见 [派生字段界面](#derived-field-interface).

   要保存新的派生字段，请选择 **[!UICONTROL **&#x200B;保存&#x200B;**]**.

5. 您的新派生字段将添加到 [!UICONTROL 派生字段>] 容器，作为的一部分 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 数据视图的左边栏中。


## 编辑派生字段

1. 选择现有数据视图。 参见 [数据视图](../data-views.md) 了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 在中选项卡 [!UICONTROL 连接] 左侧的窗格。

4. 选择 **[!UICONTROL **&#x200B;派生字段>**]** 容器。

5. 将鼠标悬停在要编辑的派生字段上，然后选择 ![“编辑”图标](assets/Smock_Edit_18_N.svg).

6. 要编辑派生字段，请使用 [!UICONTROL 编辑派生字段] 界面。 参见 [派生字段界面](#derived-field-interface).

   - 选择 **[!UICONTROL **&#x200B;保存&#x200B;**]** 以保存更新的派生字段。

   - 选择 **[!UICONTROL **&#x200B;取消&#x200B;**]** 以取消对派生字段所做的任何更改。

   - 选择 **[!UICONTROL **&#x200B;另存为&#x200B;**]** 将派生字段另存为新派生字段。 新派生字段的名称与原始编辑的派生字段的名称相同， `(copy)` 已添加到其中。

## 删除派生字段

1. 选择现有数据视图。 参见 [数据视图](../data-views.md) 了解更多信息。

2. 选择 **[!UICONTROL **&#x200B;组件&#x200B;**]** 选项卡。

3. 选择 **[!UICONTROL **&#x200B;架构字段&#x200B;**]** 按Tab键进入 [!UICONTROL 连接] 窗格。

4. 选择 **[!UICONTROL **&#x200B;派生字段>**]** 容器。

5. 将鼠标悬停在要删除的派生字段上，然后选择 ![“编辑”图标](assets/Smock_Edit_18_N.svg).

6. 使用中 **[!UICONTROL **&#x200B;编辑派生字段&#x200B;**]** 界面中，选择删除。

   A [!UICONTROL 删除组件] 对话框要求您确认删除。 考虑对数据视图外部的派生字段可能存在的任何外部引用。

   - 选择 **[!UICONTROL **&#x200B;继续&#x200B;**]** 以删除派生字段。

>[!NOTE]
>
>派生字段在Customer Journey Analytics中的连接级别进行管理。 对与该连接关联的任何数据视图中的派生字段所做的任何更改将应用于所有这些关联的数据视图。



## 函数模板

要快速为特定用例创建派生字段，可使用函数模板。 这些函数模板可以从派生字段界面中的选择器区域访问，或者在首次使用时显示在中 [!UICONTROL 从字段模板开始] 向导。


### 营销渠道

此模板配置为使用 [Url分析](#dnl-url-parse) 和 [案例时间](#dnl-case-when) 函数多次以从URL获取适当的值。 然后，对这些值应用逻辑以将URL与特定营销渠道关联。

+++ 详细信息

要使用模板，必须为作为模板中规则的一部分列出的每个函数指定正确的参数。 参见 [函数引用](#function-reference) 了解更多信息。

![营销渠道模板规则生成器的屏幕截图](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 函数引用

对于每个支持的功能，请查找以下详细信息：

- 规格：
   - 输入数据类型：支持的数据类型，
   - 输入：输入的可能值，
   - 包含的运算符：此函数支持的运算符（如果有）、
   - 限制：适用于此特定函数的限制，
   - 输出。

- 用例，包括：
   - 定义派生字段之前的数据，
   - 如何定义派生字段，
   - 定义派生字段后的数据。

- 约束（如果适用）。


<!-- Concatenate -->

### 拼接

将字段值合并到一个具有定义的分隔符的新派生字段中。

+++ 详细信息

## 规范 {#concatenate-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 值]:<ul><li>规则</li><li>标准字段</li><li>字段</li><li>字符串</li></ul></li><li>[!UICONTROL 分隔符]:<ul><li>字符串</li></ul></li> </ul> | <p>不适用</p> | <p>每个派生字段有2个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例 {#concatenate-uc}

您当前收集起源机场代码和目的地机场代码作为单独的字段。 您希望取用这两个字段并将它们组合为一个维度，该维度由连字符(-)分隔。 因此，您可以分析起点和目的地的组合，以确定预订的排名最前的路由。

假设：

- 原始值和目标值收集在同一表中的单独字段中。
- 用户确定在值之间使用分隔符“ — ”。

想象一下发生以下预订的情况：

- 客户ABC123预订盐湖城(SLC)和奥兰多(MCO)之间的航班
- 客户ABC456预订盐湖城(SLC)和洛杉矶(LAX)之间的航班
- 客户ABC789预订盐湖城(SLC)和西雅图(SEA)之间的航班
- 客户ABC987预订盐湖城(SLC)和圣何塞(SJO)之间的航班
- 客户ABC654预订盐湖城(SLC)和奥兰多(MCO)之间的航班

所需报表应如下所示：

| 来源/目标 | 预订 |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 在此之前的数据 {#concatenate-uc-databefore}

| Origin | 目标 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生字段 {#concatenate-derivedfield}

您定义新的 [!UICONTROL 来源 — 目标] 派生字段。 您使用 [!UICONTROL 连接] 函数来定义用于连接 [!UICONTROL 原始] 和 [!UICONTROL 目标] 字段使用 `-` [!UICONTROL 分隔符].

![连接规则的屏幕截图](assets/concatenate.png)

### 之后的数据 {#concatenate-dataafter}

| 来源 — 目标<br/>（派生字段） |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### Case When

根据一个或多个字段中的定义条件应用条件。 然后，这些标准用于根据条件的顺序定义新派生字段中的值。

+++ 详细信息

## 规范 {#casewhen-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 如果]， [!UICONTROL Else If] 容器：</p><ul><li>[!UICONTROL 值]</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 标准] （根据选定的值类型，请参阅包含的运算符）</li></ul></li><li>[!UICONTROL 然后将值设置为]， [!UICONTROL 否则，将值设置为]：</p><ul><li>[!UICONTROL 值]</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul></li></ul> | <p>字符串</p><ul><li>等于</li><li>等于任何词语</li><li>包含该短语</li><li>包含任何词语</li><li>包含所有词语</li><li>开始于</li><li>以任意术语开头</li><li>结束于</li><li>以任意术语结尾</li><li>不等于</li><li>不等于任何词语</li><li>不包含该短语</li><li>不包含任何词语</li><li>不包含所有词语</li><li>未始于</li><li>不以任何术语开头</li><li>未止于</li><li>未以任何术语结尾</li><li>已设置</li><li>未设置</li></ul><p>数值</p><ul><li>等于</li><li>不等于</li><li>高于</li><li>高于或等于</li><li>低于</li><li>低于或等于</li><li>已设置</li><li>未设置</li></ul><p>日期</p><ul><li>等于</li><li>不等于</li><li>晚于</li><li>晚于或等于</li><li>早于</li><li>早于或等于</li><li>已设置</li><li>未设置</li></ul> | <ul><li>每个派生字段5个函数</li><li>每个派生字段200个运算符。 例如，“反向链接域包含google”就是一个运算符。 </li></ul> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例1 {#casewhen-uc1}

您需要定义规则以标识各种营销渠道，方法是应用层叠逻辑将营销渠道字段设置为适当的值：

- 如果反向链接来自搜索引擎，并且页面具有一个查询字符串值，其中 `cid` 包含 `ps_`，则营销渠道应标识为 [!DNL *付费搜索*].
- 如果反向链接来自搜索引擎，而页面没有查询字符串 `cid`，则营销渠道应标识为 [!DNL *免费搜索*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `em_`，则营销渠道应标识为 [!DNL *电子邮件*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `ds_`，则营销渠道应标识为 [!DNL *显示广告*].
- 如果页面具有查询字符串值，其中 `cid` 包含 `so_`，则营销渠道应标识为 [!DNL *付费社交*].
- 如果反向链接来自的反向链接域 [!DNL twitter.com]， [!DNL facebook.com]， [!DNL linkedin.com]，或 [!DNL tiktok.com]，则营销渠道应标识为 [!DNL *自然社交*].
- 如果上述规则都不匹配，则应将营销渠道标识为 [!DNL *其他反向链接*].

如果您的站点收到以下示例事件，包含 [!UICONTROL 反向链接] 和 [!UICONTROL 页面URL]，这些事件的标识如下：

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 在此之前的数据 {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### 派生字段 {#casewhen-uc1-derivedfield}

您定义新的 `Marketing Channel` 派生字段。 您使用 [!UICONTROL 大小写条件] 函数定义规则，这些规则根据两者的现有值为创建值 `Page URL` 和 `Referring URL` 字段。

注意函数的用法 [!UICONTROL URL分析] 定义规则以获取值 `Page Url` 和 `Referring Url` 早于 [!UICONTROL 大小写条件] 应用规则。

![规则1时案例的屏幕截图](assets/case-when-1.png)

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

您已收集了以下网站中搜索的多个不同变体： [!DNL Product Finding Methods] 维度。 要了解搜索与浏览的整体性能，您必须花费大量时间手动组合结果。

您的网站为收集以下值 [!DNL Product Finding Methods] 维度。 最后，所有这些值都表示搜索。

| 收集的值 | 实际值 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 在此之前的数据 {#casewhen-uc2-databefore}

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

您定义 `Product Finding Methods (new)` 派生字段。 您可以创建以下内容 [!UICONTROL 大小写条件] 规则生成器的规则。 这些规则将逻辑应用于旧版本的所有可能变体 [!UICONTROL 产品查找方法] 字段值 `search` 和 `browse` 使用 [!UICONTROL 包含短语] 标准。

![规则2时案例的屏幕截图](assets/case-when-2.png)

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

作为一家旅游公司，您想要为预订的旅行报告分段旅行时长。

假设：

- 组织正在将行程持续时间收集到一个数值字段中。
- 他们希望将1-3天的持续时间存储到一个名为&#39;的存储段中。[!DNL short trip]‘
- 他们希望将4-7天的持续时间存储到一个名为&#39;的存储桶中。[!DNL medium trip]‘
- 他们希望将8天以上的持续时间存储到一个名为“[!DNL long trip]‘
- 预订了132次旅行，为期1天
- 预订了110次旅行，为期2天
- 预订了105次旅行，为期3天
- 预订了99次旅行，为期4天
- 预订了92次旅行，为期5天
- 预订了85次旅行，为期6天
- 预订了82次旅行，为期7天
- 预订了78次旅行，为期8天
- 预订了50次旅行，为期9天
- 预订了44次旅行，为期10天
- 预订了38次旅行，为期11天
- 预订了31次旅行，为期12天

您所需的报表应如下所示：

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### 在此之前的数据 {#casewhen-uc3-databefore}

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

您定义 `Trip Duration (bucketed)` 派生字段。 您可以创建以下内容 [!UICONTROL 大小写条件] 规则生成器的规则。 此规则将逻辑应用于存储旧的 [!UICONTROL 行程持续时间] 字段值分为三个值： `short trip`， `medium  trip`、和 `long trip`.

![规则3时案例的屏幕截图](assets/case-when-3.png)


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


## 更多信息

Customer Journey Analytics使用嵌套容器结构，该结构以Adobe Experience Platform的模式建模。 [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) （体验数据模型）。 参见 [容器](../create-dataview.md#containers) 和 [筛选容器](../../components/filters/filters-overview.md#filter-containers) 了解更多背景信息。 虽然此容器模型本质上很灵活，但在使用规则生成器时施加了一些限制。

Customer Journey Analytics使用以下默认容器模型：

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

以下限制条件适用，并在以下情况下强制执行 *选择* 和 *设置* 值。

|  | 约束 |
|:---:|----|
| **<span style='color: red'>A</span>** | 您的价值 *选择* 在同一个 [!UICONTROL 如果]， [!UICONTROL Else If] 构造(使用 [!UICONTROL 和] 或 [!UICONTROL 或])，并且可以是任何类型（字符串） ![字符串](assets/Smock_ABC_18_N.svg)，数值 ![数值](assets/Smock_123_18_N.svg)，等等)。 <br/>![依赖项A屏幕截图](assets/dependency-a.png) |
| **<span style='color: red'>B</span>** | 您的所有值 *设置* 跨规则必须来自同一容器并具有同一类型或同一类型的派生值。 <br/> ![依赖项B的屏幕截图](assets/dependency-b.png) |
| **<span style='color: blue'>C</span>** | 您的值 *选择* 跨越 [!UICONTROL 如果]， [!UICONTROL Else If] 规则中的构造是 *非* 必须源自相同的容器，并且 *非* 必须是同一类型。 <br/> ![依赖项C屏幕截图](assets/dependency-c.png) |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### 查找和替换

查找选定字段中的所有值，并在新的派生字段中将这些值替换为不同的值。

+++ 详细信息

## 规范 {#findreplace-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 值]<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>[!UICONTROL 查找全部]， [!UICONTROL 并将其全部替换为]：<ul><li>字符串</li></ul></li></ul></ul> | <p>字符串</p><ul><li>[!UICONTROL 查找全部]， [!UICONTROL 并将其全部替换为]</li></ul> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例 {#findreplace-uc}

例如，您收到的外部营销渠道报表的某些值格式不正确 `email%20 marketing` 而不是 `email marketing`. 这些格式错误的值会割裂您的报表，并使查看电子邮件的性能变得更加困难。 要替换的 `email%20marketing` 替换为 `email marketing`.

**原始报告**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**首选报告**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### 在此之前的数据 {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生字段 {#findreplace-uc-derivedfield}

您定义 `Email Marketing (updated)` 派生字段。 您使用 [!UICONTROL 查找和替换] 函数来定义查找和替换所有出现的规则 `email%20marketing` 替换为 `email marketing`.

![查找和替换规则的屏幕快照](assets/find-and-replace.png)

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

### 查询

定义一组查找值，这些值将在新的派生字段中被相应值替换。

+++ 详细信息


## 规范 {#lookup-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 应用查找的字段]:<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>[!UICONTROL 当值等于] 和 [!UICONTROL 替换值为]：</p><ul><li>字符串</li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#lookup-uc1}

您的确有一个CSV文件，其中包含键列 `hotelID` 和一个或多个与关联的其他列 `hotelID`： `city`， `rooms`， `hotel name`.
您正在收集 [!DNL Hotel ID] 但想要创建 [!DNL Hotel Name] 维度派生自 `hotelID` CSV文件。

**CSV文件结构和内容**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |

{style="table-layout:auto"}

**当前报告**

| [!DNL Hotel ID] | 产品查看次数 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |

{style="table-layout:auto"}


**所需报告**

| [!DNL Hotel Name] | 产品查看次数 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 在此之前的数据 {#lookup-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |

{style="table-layout:auto"}


### 派生字段 {#lookup-uc1-derivedfield}

您定义 `Hotel Name` 派生字段。 您使用 [!UICONTROL 查找] 函数来定义一个规则，您可以在其中查找 [!UICONTROL 酒店ID] 字段，并替换为新的值。

![查找规则1的屏幕截图](assets/lookup-1.png)

### 之后的数据 {#lookup-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 用例2 {#lookup-uc2}

您已收集了多个页面的URL而不是友好页面名称。 此混合值集合将破坏报表。

### 在此之前的数据 {#lookup-uc2-databefore}

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

您定义 `Page Name (updated)` 派生字段。 您使用 [!UICONTROL 查找] 函数，定义可在其中查找现有值的规则 [!UICONTROL 页面名称] 字段和替换为更新的正确值。

![查找规则2的屏幕截图](assets/lookup-2.png)

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

<!-- MERGE FIELDS -->

### 合并字段

将来自两个不同字段的值合并到一个新的派生字段中。

+++ 详细信息

## 规范 {#merge-fields-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 字段]:</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#merge-fields-uc}

您希望创建一个由页面名称字段和致电原因字段组成的新维度，以便跨渠道分析历程。

### 在此之前的数据 {#merge-fields-uc-databefore}

| 页面名称 | 会话 | 访客 |
|---|--:|--:|
| 帮助页面 | 250 | 200 |
| home page | 500 | 250 |
| 产品详细信息页面 | 300 | 200 |

{style="table-layout:auto"}

| 来电原因 | 会话 | 访客 |
|---|--:|--:|
| 关于我订单的问题 | 275 | 250 |
| 更改我的订单 | 150 | 145 |
| 订购问题 | 100 | 95 |

{style="table-layout:auto"}

### 派生字段 {#merge-fields-uc-derivedfield}

您定义 `Cross Channel Interactions` 派生字段。 您使用 [!UICONTROL 合并字段] 函数来定义规则，以合并来自以下项的值： [!UICONTROL 页面名称] 字段和 [!UICONTROL 来电原因] 字段并将其存储在新的派生字段中。

![“合并字段”规则的屏幕快照](assets/merge-fields.png)

### 之后的数据 {#merge-fields-uc-dataafter}

| 跨渠道交互 | 会话 | 访客 |
|---|--:|--:|
| home page | 500 | 250 |
| 产品详细信息页面 | 300 | 200 |
| 关于我订单的问题 | 275 | 250 |
| 帮助页面 | 250 | 200 |
| 更改我的订单 | 150 | 145 |
| 订购问题 | 100 | 95 |

{style="table-layout:auto"}

## 更多信息 {#merge-fields-moreinfo}

您必须在“合并字段”规则中选择相同类型的字段。 例如，如果您选择日期字段，则要合并的所有其他字段都必须是日期字段。

![合并字段约束屏幕截图](assets/merge-fields-constraint.png)

+++


<!-- REGEX REPLACE -->

### 正则表达式替换

使用正则表达式将字段中的值替换为新派生字段。

+++ 详细信息

## 规范 {#regex-replace-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li></ul> | <ul><li>[!UICONTROL 字段]:</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul><ul><li>[!UICONTROL 正则表达式]:</li><ul><li>字符串</li></ul></li><li>[!UICONTROL Output Format（输出格式）]:<ul><li>字符串</li></ul></ul><ul><li>区分大小写</li><ul><li>布尔值</li></ul></li></ul></li> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#regex-replace-uc}

您希望获取URL的一个部分，并将其用作唯一页面标识符来分析流量。 您将使用 `[^/]+(?=/$|$)` 用于捕获URL结尾的正则表达式，并且 `$1` 作为输出模式。

### 在此之前的数据 {#regex-replace-uc-databefore}

| 页面 URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### 派生字段 {#regex-replace-uc-derivedfield}

您创建 `Page Identifier` 派生字段。 您使用 [!UICONTROL 正则表达式替换] 函数来定义规则以替换 [!UICONTROL 反向链接URL] 字段使用 [!UICONTROL 正则表达式] 之 `[^/]+(?=/$|$)` 和 [!UICONTROL 输出格式] 之 `$1`.

![Regex Replac规则的屏幕截图](assets/regex-replace.png)


### 之后的数据 {#regex-replace-uc-dataafter}

| 页面标识符 |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## 更多信息

Customer Journey Analytics使用Perl正则表达式语法的子集。 支持以下表达式：

| 表达式 | 描述 |
| --- | --- |
| `a` | 单个字符 `a`。 |
| `a\|b` | 单个字符 `a` 或者 `b`。 |
| `[abc]` | 单个字符 `a`、`b` 或者 `c`。 |
| `[^abc]` | 除 `a`、`b` 或者 `c` 之外的任意单个字符。 |
| `[a-z]` | 在 `a`–`z` 之间的任意单个字符。 |
| `[a-zA-Z0-9]` | 在 `a`–`z`、`A`–`Z` 或者数字 `0`–`9` 之间的任意单个字符。 |
| `^` | 匹配行的开头。 |
| `$` | 匹配行的结尾。 |
| `\A` | 字符串的开始。 |
| `\z` | 字符串的结束。 |
| `.` | 匹配任意字符。 |
| `\s` | 任意空白字符。 |
| `\S` | 任意非空白字符。 |
| `\d` | 任意数字。 |
| `\D` | 数字类型 |
| `\w` | 任意字母、数字或下划线。 |
| `\W` | 任意非单词字符。 |
| `\b` | 任意单词边界。 |
| `\B` | 任何不是单词边界的字符。 |
| `\<` | 单词的开头. |
| `\>` | 单词的结尾. |
| `(...)` | 捕获包含的任何内容。 |
| `(?:...)` | 无标记捕获。 防止在输出字符串中引用匹配项。 |
| `a?` | 零个或一个 `a`。 |
| `a*` | 零个或多个 `a`。 |
| `a+` | 一个或多个 `a`。 |
| `a{3}` | 恰好 3 个 `a`。 |
| `a{3,}` | 3 个或更多 `a`。 |
| `a{3,6}` | 3 到 6 个 `a`。 |

您可以在 [!UICONTROL 输出格式] 中使用这些序列，以任何次数和顺序来实现所需的字符串输出。

| 输出占位符序列 | 描述 |
| --- | --- |
| `$&` | 输出与整个表达式匹配的内容。 |
| `$n` | 输出与第 n 个子表达式匹配的内容。 例如，`$1` 输出第一个子表达式。 |
| ``$` `` | 输出上一个匹配的结束（如果没有找到上一个匹配，则输出文本的开始）和当前匹配的开始之间的文本。 |
| `$+` | 输出与正则表达式中最后标记的子表达式匹配的内容。 |
| `$$` | 输出字符串 `"$"`。 |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### 拆分

将字段中的值拆分为新的派生字段。

+++ 详细信息

## 规范 {#split-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li></ul> | <ul><li>[!UICONTROL 字段]:</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul><ul><li>[!UICONTROL 方法]:</li><ul><li>从左侧</li><li>从右侧</li><li>转换为数组</li></ul></li><li>对于分隔符：<ul><li>字符串</li></ul><li>对于索引：<ul><li>数值</li></ul></li> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例1 {#split-uc1}

您可以将语音应用程序响应收集到单个维度的分隔列表中。 您希望列表中的每个值在响应报表中都是唯一值。

### 在此之前的数据 {#split-uc1-databefore}

| 语音应用程序响应 | 活动 |
|---|--:|
| 非常好，完全合理，会推荐给别人 | 1 |
| 它很棒，有点令人困惑，会推荐给别人 | 1 |
| 那不是很好，非常令人困惑，不会向别人推荐 | 1 |

{style="table-layout:auto"}

### 派生字段 {#split-u1-derivedfield}

您创建 `Responses` 派生字段。 您使用 [!UICONTROL SPLIT] 函数来定义规则以使用  [!UICONTROL 转换为数组] 方法转换以下位置的值： [!UICONTROL 语音应用程序响应] 字段使用 `,` 作为 [!UICONTROL 分隔符].

![拆分规则1的屏幕截图](assets/split-1.png)

### 之后的数据 {#split-uc1-dataafter}

| 响应 | 活动 |
|---|--:|
| 太棒了 | 2 |
| 将推荐给其他人 | 2 |
| 那可不怎么样 | 1 |
| 完全合理 | 1 |
| 有点令人困惑 | 1 |
| 非常令人困惑 | 1 |
| 不会推荐给其他人 | 1 |

{style="table-layout:auto"}

## 用例2 {#split-uc2}

您可以将语音应用程序响应收集到单个维度的分隔列表中。 您希望将列表中第一个值的响应放入其自身的维度中。 您希望将列表中的最后一个值放入其自身的维度中。

### 在此之前的数据 {#split-uc2-databefore}

| 响应 | 活动 |
|---|--:|
| 非常好，完全合理，会推荐给别人 | 1 |
| 它很棒，有点令人困惑，会推荐给别人 | 1 |
| 那不是很好，非常令人困惑，不会向别人推荐 | 1 |

{style="table-layout:auto"}

### 派生字段 {#split-u2-derivedfield}

您创建  `First Response` 派生字段。 您使用 [!UICONTROL SPLIT] 函数来定义一个规则，以从中获取第一个值。 [!UICONTROL 响应] 响应左侧的字段 `,` 作为分隔符。

![拆分规则 — 第一个值的屏幕截图](assets/split-2.png)

您创建 `Second Response` 用于获取最后一个值的派生字段 [!UICONTROL 响应] 字段，方法是选择右侧的，选择1作为分隔符，选择1作为索引。

![拆分规则 — 最后一个值的屏幕截图](assets/split-3.png)

### 之后的数据 {#split-uc2-dataafter}

| 第一次响应 | 活动 |
|---|--:|
| 太棒了 | 2 |
| 那可不怎么样 | 1 |

{style="table-layout:auto"}

| 第二个响应 | 活动 |
|---|--:|
| 将推荐给其他人 | 2 |
| 不会推荐给其他人 | 1 |

{style="table-layout:auto"}

+++


<!-- URL PARSE -->

### URL 解析

解析URL的不同部分，包括协议、主机、路径或查询参数。

+++ 详细信息

## 规范 {#urlparse-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 字段]:</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 选项]:<ul><li>[!UICONTROL 获取协议]</li><li>[!UICONTROL 获取主机]</li><li>[!UICONTROL 获取路径]</li><li>[!UICONTROL 获取查询字符串值]<ul><li>[!UICONTROL 查询参数]:<ul><li>字符串</li></ul></li></ul></li><li>[!UICONTROL 获取哈希值]</li></ul></li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#urlparse-uc1}

您只需将反向链接URL中的反向链接域用作营销渠道规则集的一部分。

### 在此之前的数据 {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc1-derivedfield}

您定义  `Referring Domain` 派生字段。 您使用 [!UICONTROL URL分析] 函数来定义从提取主机的规则。 [!UICONTROL 反向链接URL] 字段并将其存储在新的派生字段中。

![Url解析规则1的屏幕截图](assets/url-parse-1.png)

### 之后的数据 {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 用例2 {#urlparse-uc2}

您希望使用 `cid` 中查询字符串的参数 [!DNL Page URL] 作为派生跟踪代码报表输出的一部分。

### 在此之前的数据 {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc2-derivedfield}

您定义 `Query String CID` 派生字段。 您使用 [!UICONTROL URL分析] 函数来定义规则以获取 [!UICONTROL 页面URL] 字段，指定 `cid` 作为查询参数。 输出值存储在新的派生字段中。

![Url解析规则2的屏幕截图](assets/url-parse-2.png)

### 之后的数据 {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## 限制

以下限制通常适用于派生字段功能：

- 为派生字段定义规则时，最多可以使用十个不同的架构字段（不包括标准字段）。
   - 在这个最多十个不同的架构字段中，最多只允许三个查找架构或配置文件架构字段。
- 每个Customer Journey Analytics连接最多可以有100个派生字段。

## 更多信息

- [充分利用数据：用于在Customer Journey Analytics中使用派生字段的框架](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)

- [Customer Journey Analytics的派生字段用例](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)

