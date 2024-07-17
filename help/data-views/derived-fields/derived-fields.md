---
title: 派生字段
description: 派生字段通过一组可用函数和函数模板指定对架构字段和/或标准组件的报告时间操作。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
source-git-commit: 0a046a89e1742d3470a78ebad4f93cb3b4ea7f4c
workflow-type: tm+mt
source-wordcount: '8366'
ht-degree: 12%

---

# 派生字段

派生字段是Adobe Customer Journey Analytics中实时报表功能的一个重要方面。 通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。然后，您可以在[Workspace](../../analysis-workspace/home.md)中将该派生字段用作组件（量度或维度），甚至在[数据视图](../data-views.md)中将该派生字段进一步定义为组件。

与在Customer Journey Analytics之外的其他位置转换或处理数据相比，派生字段可以节省大量时间和精力。 例如[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)、[数据Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)或您自己的提取转换加载(ETL)/提取加载转换(ELT)进程。

派生字段在[数据视图](../data-views.md)中定义，基于一组定义为规则的函数，并应用于可用的标准和/或架构字段。

示例用例包括：

- 定义派生的“页面名称”字段，该字段可更正不正确收集的页面名称值以更正页面名称值。

- 定义派生的营销渠道字段，以根据一个或多个条件（例如URL参数、页面URL、页面名称）确定正确的营销渠道。

## 派生字段界面

创建或编辑派生字段时，使用派生字段界面。

![派生字段对话框屏幕截图](assets/derived-field-dialog.png)


|  | 名称 | 描述 |
|---------|----------|--------|
| 1 | **选择器** | 使用选择器区域选择您的函数、函数模板、架构字段或标准字段并将它们拖放到规则生成器中。 <br/>使用下拉菜单选择： <br/>![函数](assets/Smock_Function_18_N.svg) [!UICONTROL 函数] — 列出可用的[函数](#function-reference)，</br>![函数模板图标](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL 函数模板] — 列出可用的[函数模板](#function-templates)，<br/>![架构字段图标](assets/Smock_Folder_18_N.svg) [!UICONTROL 架构字段] — 列出数据集类别（事件、配置文件、查询）和以前定义的派生字段中的可用字段，以及<br/>![标准字段图标](assets/Smock_DragHandle_18_N.svg) [!UICONTROL 标准字段] — 可用字段例如Platform数据集ID)。 选择器中只显示字符串和数字标准字段。 如果函数支持其他数据类型，则可以为规则界面中的值或字段选择具有这些其他数据类型的标准字段。<br/>您可以使用![搜索图标](assets/Smock_Search_18_N.svg)搜索框搜索功能、功能模板、架构和标准字段。 <br/>您可以通过选择![筛选图标](assets/Smock_Filter_18_N.svg)筛选来筛选选定的对象列表，并在[!UICONTROL 按]筛选字段中指定筛选器。 您可以使用每个筛选器的![关闭图标](assets/CrossSize75.svg)轻松删除筛选器。 |
| 2 | **规则生成器** | 您可以使用一个或多个规则按顺序构建派生字段。 规则是函数的特定实现，因此始终只与一个函数关联。 通过将函数拖放到规则生成器中来创建规则。 函数类型确定规则的接口。<br/>有关详细信息，请参阅[规则接口](#rule-interface)。 <br/>您可以在规则生成器中已可用的规则开始、结束或之间插入函数。 规则生成器中的最后一个规则可确定派生字段的最终输出。 |
| 3 | **[!UICONTROL **&#x200B;字段设置&#x200B;**]** | 您可以命名和描述派生字段并检查其字段类型。 |
| 4 | **[!UICONTROL **&#x200B;最终输出&#x200B;**]** | 此区域根据过去30天的数据以及您在规则生成器中对派生字段所做的更改，显示输出值的动态更新预览。 |

{style="table-layout:auto"}

## 字段模板向导

首次访问派生字段界面时，将显示[!UICONTROL Start with a field template]向导。

1. 选择最能描述您尝试创建的字段类型的模板。
2. 选择&#x200B;**[!UICONTROL **&#x200B;选择&#x200B;**]**&#x200B;按钮以继续。

派生的字段对话框中填充了所选字段类型所需的或有用的规则（和函数）。 有关可用模板的详细信息，请参阅[函数模板](#function-templates)。

## 规则界面

在规则生成器中定义规则时，将使用规则界面。

![派生字段规则接口的屏幕截图](assets/rule-interface.png)

|  | 名称 | 描述 |
|---------|----------|--------|
| A | **规则名称** | 默认情况下，规则名称为&#x200B;**规则X** （X表示序列号）。 要编辑规则的名称，请选择其名称，然后键入新名称，例如`Query Parameter`。 |
| B | **函数名称** | 规则的选定函数名称，例如[!UICONTROL URL PARSE]。 当函数是函数序列中的最后一个并确定最终输出值时，函数名称后跟[!UICONTROL - FINAL OUTPUT]，例如[!UICONTROL URL PARSE - FINAL OUTPUT]。 <br/>要显示包含函数详细信息的弹出窗口，请选择![帮助图标](assets/Smock_HelpOutline_18_N.svg)。 |
| C | **规则描述** | 您可以选择向规则添加说明。<br/>选择![更多图标](assets/More.svg)，然后选择&#x200B;**[!UICONTROL **&#x200B;添加描述&#x200B;**]**&#x200B;添加描述或&#x200B;**[!UICONTROL **&#x200B;编辑描述&#x200B;**]**&#x200B;编辑现有描述。<br/>使用编辑器输入说明。 您可以使用工具栏设置文本格式（使用样式选择器、粗体、斜体、下划线、右、左、居中、颜色、数字列表、项目符号列表）并向外部信息添加链接。 <br/>要完成说明的编辑，请在编辑器外单击。 |
| D | **功能区域** | 定义函数的逻辑。 接口取决于函数的类型。 [!UICONTROL 字段]或[!UICONTROL 值]的下拉列表根据函数所需的输入类型显示所有类别的可用字段（规则、标准字段、字段）。 或者，您可以将架构和标准字段选择器中的字段拖放到字段或值中。 如果该拖动字段源自查找数据集，则将自动在定义的函数之前插入查找函数。 <br/>有关每个支持的函数的详细信息，请参阅[函数引用](#function-reference)。 |

{style="table-layout:auto"}

## 创建派生字段

1. 选择现有数据视图或创建数据视图。 有关详细信息，请参阅[数据视图](../data-views.md)。

2. 选择数据视图的&#x200B;**[!UICONTROL **&#x200B;组件&#x200B;**]**&#x200B;选项卡。

3. 从左边栏中选择&#x200B;**[!UICONTROL **&#x200B;创建派生字段&#x200B;**]**。

4. 要定义派生字段，请使用[!UICONTROL 创建派生字段]接口。 请参阅[派生字段接口](#derived-field-interface)。

   要保存您的新派生字段，请选择&#x200B;**[!UICONTROL **&#x200B;保存&#x200B;**]**。

5. 作为数据视图左边栏中&#x200B;**[!UICONTROL **&#x200B;架构字段&#x200B;**]**&#x200B;的一部分，您的新派生字段已添加到[!UICONTROL 派生字段>]容器中。


## 编辑派生字段

1. 选择现有数据视图。 有关详细信息，请参阅[数据视图](../data-views.md)。

2. 选择数据视图的&#x200B;**[!UICONTROL **&#x200B;组件&#x200B;**]**&#x200B;选项卡。

3. 在左侧的[!UICONTROL 连接]窗格中选择&#x200B;**[!UICONTROL **&#x200B;架构字段&#x200B;**]**&#x200B;选项卡。

4. 选择&#x200B;**[!UICONTROL **&#x200B;派生字段>**]**&#x200B;容器。

5. 将鼠标悬停在要编辑的派生字段上，然后选择![编辑图标](assets/Smock_Edit_18_N.svg)。

6. 要编辑派生字段，请使用[!UICONTROL 编辑派生字段]接口。 请参阅[派生字段接口](#derived-field-interface)。

   - 选择&#x200B;**[!UICONTROL **&#x200B;保存&#x200B;**]**&#x200B;以保存更新后的派生字段。

   - 选择&#x200B;**[!UICONTROL **&#x200B;取消&#x200B;**]**&#x200B;以取消对派生字段所做的任何更改。

   - 选择“**[!UICONTROL **&#x200B;另存为&#x200B;**]**”，将派生字段另存为新的派生字段。 新派生字段的名称与添加了`(copy)`的原始已编辑派生字段的名称相同。

或者，如果您已将派生字段用作数据视图中维度或量度的组件：

1. 选择组件。 请注意，组件的名称可能与派生字段不同。

1. 在“组件”面板中，选择派生字段旁边的![编辑图标](assets/Smock_Edit_18_N.svg)，该图标位于“架构”字段名称下。

1. 要编辑派生字段，请使用[!UICONTROL 编辑派生字段]接口。 请参阅[派生字段接口](#derived-field-interface)。

   - 选择&#x200B;**[!UICONTROL **&#x200B;保存&#x200B;**]**&#x200B;以保存更新的派生字段。

   - 选择&#x200B;**[!UICONTROL **&#x200B;取消&#x200B;**]**&#x200B;可取消您对派生字段所做的任何更改。

   - 选择&#x200B;**[!UICONTROL **&#x200B;另存为&#x200B;**]**&#x200B;将派生字段另存为新派生字段。 新派生字段的名称与添加了`(copy)`的原始已编辑派生字段的名称相同。



## 删除派生字段

1. 选择现有数据视图。 有关详细信息，请参阅[数据视图](../data-views.md)。

2. 选择数据视图的&#x200B;**[!UICONTROL **&#x200B;组件&#x200B;**]**&#x200B;选项卡。

3. 在[!UICONTROL 连接]窗格中选择&#x200B;**[!UICONTROL **&#x200B;架构字段&#x200B;**]**&#x200B;选项卡。

4. 选择&#x200B;**[!UICONTROL **&#x200B;派生字段>**]**&#x200B;容器。

5. 将鼠标悬停在要删除的派生字段上，然后选择![编辑图标](assets/Smock_Edit_18_N.svg)。

6. 在[!UICONTROL 编辑派生字段]界面中，选择&#x200B;**[!UICONTROL 删除]**。

   [!UICONTROL 删除组件]对话框要求您确认删除。 考虑对数据视图外部的派生字段可能存在的任何外部引用。

   - 选择&#x200B;**[!UICONTROL **&#x200B;继续&#x200B;**]**&#x200B;以删除派生字段。

或者，如果您已将派生字段用作数据视图中维度或量度的组件：

1. 选择组件。 请注意，组件的名称可能与派生字段不同。

1. 在“组件”面板中，选择派生字段旁边的![编辑图标](assets/Smock_Edit_18_N.svg)，该图标位于“架构”字段名称下。

1. 在[!UICONTROL 编辑派生字段]界面中，选择&#x200B;**[!UICONTROL 删除]**。

   [!UICONTROL 删除组件]对话框要求您确认删除。 考虑对数据视图外部的派生字段可能存在的任何外部引用。

   - 选择&#x200B;**[!UICONTROL **&#x200B;继续&#x200B;**]**&#x200B;以删除派生字段。

>[!NOTE]
>
>派生字段在Customer Journey Analytics中的连接级别进行管理。 对与该连接关联的任何数据视图中派生字段所做的任何更改将应用于所有这些关联的数据视图。



## 函数模板

要快速为特定用例创建派生字段，可以使用函数模板。 这些函数模板可以从派生字段界面的选择器区域访问，或者在首次在[!UICONTROL 以字段模板开始]向导中使用时显示。


### 营销渠道

此函数模板使用规则集合来构建营销渠道。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![营销渠道模板规则生成器的屏幕截图](assets/function-template-marketing-channel-template.png)

+++

### 退信数

此函数模板使用规则集合来标识网站退回。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![退回规则生成器的屏幕截图](assets/function-template-bounces.png)

+++

### 多维度合并

此函数模板将两个值合并为一个。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![多Dimension组合规则生成器的屏幕截图](assets/function-template-multi-dimension-combine.png)

+++

### 简单易记的数据集名称

此函数模板提供了一个可读的数据集名称。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![友好数据集名称规则生成器的屏幕截图](assets/function-template-friendly-dataset-name.png)

+++

### URL 中的页面名称

此函数模板创建一个简单的页面名称。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![URL规则生成器中的页面名称屏幕截图](assets/function-template-page-name-from-url.png)

+++

### 节假日

此函数模板对每年的关键时间进行分类。

+++ 详细信息

要使用模板，必须为作为模板中规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![假日季节规则生成器的屏幕截图](assets/function-template-holiday-season.png)

+++

### 每月目标

此函数模板可设置自定义的每月目标。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![每月目标规则生成器的屏幕截图](assets/function-template-monthly-goals.png)

+++

### 获取带分隔符的列表中的所有值

此函数模板将受限列表转换为数组。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![在分隔列表规则生成器中获取所有值的屏幕截图](assets/function-template-get-all-values-in-delimited-list.png)

+++

### 获取带分隔符的列表中的第一个值

此函数模板获取分隔列表中的第一个值。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![分隔列表规则生成器中“获取第一个值”的屏幕截图](assets/function-template-get-first-value-in-delimited-list.png)

+++

### 获取带分隔符的列表中的最后一个值

此函数模板获取分隔列表中的最后一个值。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![在分隔列表规则生成器中获取最后一个值的屏幕截图](assets/function-template-get-last-value-in-delimited-list.png)

+++

### 域名

此函数模板使用正则表达式提取域名。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![域名规则生成器的屏幕截图](assets/function-template-domain-name.png)

+++

### 获取查询字符串参数

此函数模板可提取查询字符串值。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![获取查询字符串参数规则生成器的屏幕截图](assets/function-template-get-query-string-parameter.png)

+++

### 转换字段

此函数模板可将报告从一个字段转移到另一个字段。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![过渡字段规则生成器的屏幕截图](assets/function-template-transition-field.png)

+++

### 简单易用的机器人检测

此函数模板实现了轻量级机器人识别。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![简单机器人检测规则生成器的屏幕截图](assets/function-template-simple-bot-detection.png)

+++

### 退出链接

此函数模板可识别会话中最后点击的链接。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![退出链接规则生成器的屏幕截图](assets/function-template-exit-link.png)

+++

### 下载链接

此函数模板可标记常见的下载链接。

+++ 详细信息

要使用模板，必须为作为模板规则的一部分列出的每个函数指定正确的参数。 有关详细信息，请参阅[函数引用](#function-reference)。

![下载链接规则生成器的屏幕截图](assets/function-template-download-link.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 函数引用

{{select-package}}

对于每个支持的功能，请在下面查找有关以下内容的详细信息：

- 规范：
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


<!-- CASE WHEN -->

### Case When

根据一个或多个字段中的定义条件应用条件。 然后，使用这些标准根据条件的顺序定义新派生字段中的值。

+++ 详细信息

## 规范 {#casewhen-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL If]，[!UICONTROL Else If]容器：</p><ul><li>[!UICONTROL 值]</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 条件]（请参阅包含的运算符，基于选定的值类型）</li></ul></li><li>[!UICONTROL 则将值设置为]，[!UICONTROL 否则将值设置为]：</p><ul><li>[!UICONTROL 值]</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul></li></ul> | <p>字符串</p><ul><li>等于</li><li>等于任何词语</li><li>包含该短语</li><li>包含任何词语</li><li>包含所有词语</li><li>开始于</li><li>以任意术语开头</li><li>结束于</li><li>以任意术语结束</li><li>不等于</li><li>不等于任何词语</li><li>不包含该短语</li><li>不包含任何词语</li><li>不包含所有词语</li><li>未始于</li><li>不以任何术语开头</li><li>未止于</li><li>未以任何术语结尾</li><li>已设置</li><li>未设置</li></ul><p>数值</p><ul><li>等于</li><li>不等于</li><li>高于</li><li>高于或等于</li><li>低于</li><li>低于或等于</li><li>已设置</li><li>未设置</li></ul><p>日期</p><ul><li>等于</li><li>不等于</li><li>晚于</li><li>晚于或等于</li><li>早于</li><li>早于或等于</li><li>已设置</li><li>未设置</li></ul> | <ul><li>每个派生字段5个函数</li><li>每个派生字段有200个[运算符](#operators)。 例如，单个运算符为“反向链接域包含google”。 </li></ul> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例1 {#casewhen-uc1}

您需要定义规则以标识各种营销渠道，方法是应用层叠逻辑将营销渠道字段设置为适当的值：

- 如果反向链接来自搜索引擎并且页面具有查询字符串值，其中`cid`包含`ps_`，则应将营销渠道标识为&#x200B;[!DNL *付费搜索*]。
- 如果反向链接来自搜索引擎并且页面没有查询字符串`cid`，则应将营销渠道标识为&#x200B;[!DNL *免费搜索*]。
- 如果页面具有查询字符串值，其中`cid`包含`em_`，则应将营销渠道标识为&#x200B;[!DNL *电子邮件*]。
- 如果页面具有查询字符串值，其中`cid`包含`ds_`，则应将营销渠道标识为&#x200B;[!DNL *显示广告*]。
- 如果页面具有查询字符串值，其中`cid`包含`so_`，则应将营销渠道标识为&#x200B;[!DNL *付费社交*]。
- 如果反向链接来自[!DNL twitter.com]、[!DNL facebook.com]、[!DNL linkedin.com]或[!DNL tiktok.com]的反向链接域，则应将营销渠道标识为&#x200B;[!DNL *自然社交*]。
- 如果上述规则都不匹配，则应将营销渠道标识为&#x200B;[!DNL *其他反向链接*]。

如果您的站点收到以下示例事件，其中包含[!UICONTROL 反向链接]和[!UICONTROL 页面URL]，则这些事件应按以下方式标识：

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 数据早于 {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | |

{style="table-layout:auto"}

### 派生字段 {#casewhen-uc1-derivedfield}

您定义一个`Marketing Channel`派生字段。 您使用[!UICONTROL CASE WHEN]函数定义规则，这些规则根据`Page URL`和`Referring URL`字段的现有值为创建值。

请注意，在应用[!UICONTROL CASE WHEN]规则之前，使用函数[!UICONTROL URL PARSE]定义规则以获取`Page Url`和`Referring Url`的值。

![规则1](assets/case-when-1.png)时案例的屏幕截图

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

您已在[!DNL Product Finding Methods]维度中收集了多个不同的搜索变体。 要了解搜索与浏览的整体性能，您必须花费大量时间手动组合结果。

您的网站将为[!DNL Product Finding Methods]维度收集以下值。 最后，所有这些值都表示搜索。

| 收集的值 | 实际值 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 数据早于 {#casewhen-uc2-databefore}

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

您定义一个`Product Finding Methods (new)`派生字段。 在规则生成器中创建以下[!UICONTROL CASE WHEN]规则。 这些规则使用[!UICONTROL 包含短语]条件将逻辑应用于`search`和`browse`的旧[!UICONTROL 产品查找方法]字段值的所有可能变体。

![规则2](assets/case-when-2.png)时案例的屏幕截图

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

作为一家旅游公司，您想要为预订的旅行设置分段旅行持续时间，以便报告分段旅行时长。

假设：

- 组织正在将行程持续时间收集到数值字段中。
- 他们希望将1-3天的持续时间存储到名为“[!DNL short trip]”的存储桶中
- 他们希望将4 - 7天的持续时间存储到名为“[!DNL medium trip]”的存储桶中
- 他们希望将8天以上的持续时间存储到名为“[!DNL long trip]”的存储桶中
- 预订了132次旅行，为期1天
- 预订了110次旅行，为期2天
- 预订了105次旅行，为期3天
- 预订了99次4天旅行
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

### 数据早于 {#casewhen-uc3-databefore}

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

您定义一个`Trip Duration (bucketed)`派生字段。 在规则生成器中创建以下[!UICONTROL CASE WHEN]规则。 此规则将逻辑应用于将旧的[!UICONTROL 行程持续时间]字段值存储为三个值： `short trip`、`medium  trip`和`long trip`。

![规则3](assets/case-when-3.png)时案例的屏幕截图


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


## 更多信息 {#casewhen-more-info}

Customer Journey Analytics使用嵌套容器结构，该结构以Adobe Experience Platform的[XDM](https://experienceleague.adobe.com/cn/docs/experience-platform/xdm/home.html?lang=zh-Hans) (Experience Data Model)为模型建模。 有关更多背景信息，请参阅[容器](../create-dataview.md#containers)和[筛选器容器](../../components/filters/filters-overview.md#filter-containers)。 此容器模型虽然本质上较为灵活，但在使用规则生成器时施加了一些限制。

Customer Journey Analytics使用以下默认容器模型：

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

在&#x200B;*选择*&#x200B;和&#x200B;*设置*&#x200B;值时应用并强制实施以下约束。

|  | 限制 |
|:---:|----|
| **A** | 您在规则中同一[!UICONTROL If]、[!UICONTROL Else If]构造（使用[!UICONTROL And]或[!UICONTROL Or]）中的&#x200B;*select*&#x200B;值必须源自同一容器，并且可以是任何类型（字符串![String](assets/Smock_ABC_18_N.svg)、数字![Numeric](assets/Smock_123_18_N.svg)等）。 <br/>![依赖项A](assets/dependency-a.png)的屏幕截图 |
| **B** | 您&#x200B;*在规则中设置*&#x200B;的所有值都必须来自同一容器，并且具有相同的类型或同一类型的派生值。<br/> ![依赖项B](assets/dependency-b.png)的屏幕快照 |
| **C** | 您&#x200B;*在[!UICONTROL If]、[!UICONTROL Else If]规则中的构造中选择*&#x200B;的值&#x200B;*不*&#x200B;必须来自同一容器，并且&#x200B;*不*&#x200B;必须属于同一类型。<br/> ![依赖关系C](assets/dependency-c.png)的屏幕截图 |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### 分类

定义由新派生字段中的相应值替换的一组值。

+++ 详细信息

## 规范 {#classify-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 要分类的字段]：<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>[!UICONTROL 当值等于]且[!UICONTROL 将值替换为]时：</p><ul><li>字符串</li></ul><li>显示原始值<ul><li>布尔值</li></ul></li></ul> | <p>不适用</p> | <ul><li>每个派生字段5个函数</li><li>每个派生字段有200个[运算符](#operators)。 [!UICONTROL 当值等于原始值]时[!UICONTROL 将值替换为新值]的每个条目都被视为操作。</li></ul> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#classify-uc1}

您的CSV文件确实包括`hotelID`的键列以及与`hotelID`关联的一个或多个其他列： `city`、`rooms`、`hotel name`。
您正在某个维度中收集[!DNL Hotel ID]，但想要创建从CSV文件中的`hotelID`派生的[!DNL Hotel Name]维度。

**CSV文件结构和内容**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**当前报告**

| [!DNL Hotel ID] | 产品查看次数 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**所需报告**

| [!DNL Hotel Name] | 产品查看次数 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 数据早于 {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### 派生字段 {#classify-uc1-derivedfield}

您定义一个`Hotel Name`派生字段。 您使用[!UICONTROL CLASSIFY]函数定义了一个规则，您可以在其中对[!UICONTROL Hotel ID]字段的值进行分类，并用新值替换。

如果要包含尚未定义为要分类的值的一部分的原始值（例如酒店ID AMS789），请确保选择&#x200B;**[!UICONTROL 显示原始值]**。 这可确保AMS789是派生字段输出的一部分，即使该值未进行分类。

![分类规则1](assets/classify-1.png)的屏幕截图

### 之后的数据 {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 用例2 {#classify-uc2}

您已收集了多个页面的URL，而不是友好页面名称。 此混合值集合将破坏报表。

### 数据早于 {#classify-uc2-databefore}

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

### 派生字段 {#classify-uc2-derivedfield}

您定义一个`Page Name (updated)`派生字段。 您使用[!UICONTROL CLASSIFIC]函数定义了一个规则，您可以在其中对现有[!UICONTROL 页面名称]字段的值进行分类，并使用更新的正确值替换。

![分类规则2](assets/classify-2.png)的屏幕截图

### 之后的数据 {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## 更多信息 {#classify-moreinfo}

分类规则界面中提供了以下附加功能：

- 若要快速清除所有表值，请选择![清除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL 清除所有表值]**。
- 要上载包含原始值（当值等于时）和新值（替换为）的CSV文件，请选择![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL 上载CSV]**。
- 要下载用于创建具有要上载的原始值和新值的CSV文件的模板，请选择![下载](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL 下载CSV模板]**。
- 要下载在规则界面中填充了所有原始值和新值的CSV文件，请选择![下载](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL 下载CSV值]**。


+++

<!-- CONCATENATE -->

### 拼接

使用定义的分隔符将字段值组合到一个新的派生字段中。

+++ 详细信息

## 规范 {#concatenate-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 值]：<ul><li>规则</li><li>标准字段</li><li>字段</li><li>字符串</li></ul></li><li>[!UICONTROL 分隔符]：<ul><li>字符串</li></ul></li> </ul> | <p>不适用</p> | <p>每个派生字段有2个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例 {#concatenate-uc}

您当前收集起源机场代码和目的地机场代码作为单独的字段。 您希望将这两个字段合并为一个维度，并以连字符(-)分隔。 因此，您可以分析来源和目的地的组合，以确定预订的排名最前的路由。

假设：

- 原始值和目标值收集在同一表中的单独字段中。
- 用户决定在值之间使用分隔符“ — ”。

想象一下会发生以下预订：

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


### 数据早于 {#concatenate-uc-databefore}

| Origin | 目标 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 派生字段 {#concatenate-derivedfield}

您定义了`Origin - Destination`派生字段。 您使用[!UICONTROL CONCATENATE]函数定义规则，以使用`-` [!UICONTROL 分隔符]连接[!UICONTROL 原始]和[!UICONTROL 目标]字段。

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


### 删除重复数据

避免对值计数多次。

+++ 详细信息


## 规范 {#deduplicate-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li></ul> | <ul><li>[!UICONTROL 值]：<ul><li>规则</li><li>标准字段</li><li>字段</li><li>字符串</li></ul></li><li>[!UICONTROL 作用域]：<ul><li>人员</li><li>会话</li></ul></li><li>[!UICONTROL 重复数据删除ID]：<ul><li>规则</li><li>标准字段</li><li>字段</li><li>字符串</li></ul><li>[!UICONTROL 要保留的值]：<ul><li>保留第一个实例</li><li>保留最后一个实例</li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#deduplicate-uc1}

您希望防止在用户重新加载预订确认页面时计数重复收入。 在标识符处使用预订确认ID，以便在同一事件中收到收入时不再次对其进行计数。

### 数据早于 {#deduplicate-uc1-databefore}

| 预订确认ID | 收入 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 359 |
| ABC123456789 | 359 |

{style="table-layout:auto"}

### 派生字段 {#deduplicate-uc1-derivedfield}

您定义一个`Booking Confirmation`派生字段。 您使用[!UICONTROL DEDUPLICATE]函数定义一个规则，以使用[!UICONTROL 重复数据删除ID] [!UICONTROL 预订确认ID]为[!UICONTROL 作用域] [!DNL Person]删除[!UICONTROL 值] [!DNL Booking]的重复项。 您选择[!UICONTROL 保留第一个实例]作为[!UICONTROL 要保留的值]。

![连接规则的屏幕截图](assets/deduplicate-1.png)

### 之后的数据 {#deduplicate-uc1-dataafter}

| 预订确认ID | 收入 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 0 |
| ABC123456789 | 0 |

{style="table-layout:auto"}

## 用例2 {#deduplicate-uc2}

您可以使用事件作为外部营销活动的促销活动点进代理。 重新加载和重定向导致事件量度虚增。 您希望删除重复的跟踪代码维度，以便仅收集第一个维度并将事件过度计数降至最低。

### 数据早于 {#deduplicate-uc2-databefore}

| 访客 ID | 营销渠道 | 活动 |
|----|---|---:|
| ABC123 | 付费搜索 | 1 |
| ABC123 | 付费搜索 | 1 |
| ABC123 | 付费搜索 | 1 |
| DEF123 | 电子邮件 | 1 |
| DEF123 | 电子邮件 | 1 |
| JKL123 | 免费搜索 | 1 |
| JKL123 | 免费搜索 | 1 |

{style="table-layout:auto"}

### 派生字段 {#deduplicate-uc2-derivedfield}

您定义了一个新的`Tracking Code (deduplicated)`派生字段。 您使用[!UICONTROL DEDUPLICATE]函数定义一个规则来删除重复项[!UICONTROL 跟踪代码]，该规则具有[!UICONTROL 会话]的[!UICONTROL 删除重复项范围]和[!UICONTROL 保留第一个实例]作为[!UICONTROL 要保留的值]。

![连接规则的屏幕截图](assets/deduplicate-2.png)

### 之后的数据 {#deduplicate-uc2-dataafter}

| 访客 ID | 营销渠道 | 活动 |
|----|---|---:|
| ABC123 | 付费搜索 | 1 |
| DEF123 | 电子邮件 | 1 |
| JKL123 | 免费搜索 | 1 |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### 查找和替换

查找选定字段中的所有值，并在新的派生字段中用不同的值替换这些值。

+++ 详细信息

## 规范 {#findreplace-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 值]<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>[!UICONTROL 查找所有]、[!UICONTROL 并全部替换为]：<ul><li>字符串</li></ul></li></ul></ul> | <p>字符串</p><ul><li>[!UICONTROL 查找所有]、[!UICONTROL 并全部替换为]</li></ul> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例 {#findreplace-uc}

您收到的外部营销渠道报表的某些值格式不正确，例如`email%20 marketing`而不是`email marketing`。 这些格式错误的值会断开您的报表，并使得查看电子邮件执行情况的难度增加。 要将`email%20marketing`替换为`email marketing`。

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


### 数据早于 {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 派生字段 {#findreplace-uc-derivedfield}

您定义了`Email Marketing (updated)`派生字段。 您使用[!UICONTROL FIND AND REPLACE]函数定义规则以查找所有出现的`email%20marketing`并将其替换为`email marketing`。

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

使用查找数据集中的字段查找值，并在新的派生字段中返回值或用于进一步规则处理。

+++ 详细信息

## 规范 {#lookup-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 要应用查找的字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 查找数据集]</li><ul><li>数据集</li></ul><li>[!UICONTROL 匹配键]<ul><li>规则</li><li>字段</li></ul></li><li>要返回的值<ul><li>规则</li><li>字段</li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段3个函数</p> | <p>用于下一步规则中进一步处理的新派生字段或值</p> |

{style="table-layout:auto"}

## 用例 {#lookup-uc}

您希望使用在您的客户单击通过Adobe Target显示的个性化横幅时收集的活动ID查找活动名称。 要将查找数据集用于Analytics for Target (A4T)活动，其中包含活动ID和活动名称。

### A4T查找数据集 {#lookup-uc-lookup}

| 活动ID | 活动名称 |
|---|---|
| 415851 | MVT测试类别页面 |
| 415852 | Luma - Campaign Max 2022 |
| 402922 | 主页横幅 |

{style="table-layout:auto"}

### 派生字段 {#lookup-uc-derivedfield}

您定义了`Activity Name`派生字段。 您使用[!UICONTROL LOOKUP]函数定义一个规则，以从您收集的数据中查找值，该规则在[!UICONTROL 要应用查找]字段中指定的值（例如&#x200B;**[!DNL ActivityIdentifier]**）。 从[!UICONTROL 查找数据集]列表中选择查找数据集（例如&#x200B;**[!DNL New CJA4T Activities]**）。 然后，从[!UICONTROL 匹配键]列表中选择标识符字段（例如&#x200B;**[!DNL ActivityIdentifier]**），并从[!UICONTROL 要返回的值]列表中选择要返回的字段（例如&#x200B;**[!DNL ActivityName]**）。

![小写规则的屏幕快照](assets/lookup.png)

## 更多信息 {#lookup-more-info}

查找函数在报告时将应用于由Customer Journey Analytics从您配置为连接一部分的查找数据集检索的数据。

您可以在规则生成器中快速插入[!UICONTROL 查找]函数，该函数已包含一个或多个其他函数。

1. 从选择器中选择&#x200B;**[!UICONTROL 架构字段]**。
1. 选择![架构字段图标](assets/Smock_Folder_18_N.svg) **[!UICONTROL 查找数据集]**。
1. 选择您的查找数据集并查找要用于查找的字段。
1. 将查找字段拖放到函数的任何可用输入字段上（例如Case When）。 如果有效，则标有&#x200B;**[!UICONTROL + Add]**的蓝色框允许您删除该字段，并在您删除该查找字段的函数之前自动插入查找函数。 插入的Lookup函数将自动填充所有字段的相关值。
   ![查找拖动](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### 小写

将字段中的值转换为小写，并将其存储到新的派生字段中。

+++ 详细信息

## 规范 {#lowercase-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul> | <p>不适用</p> | <p>每个派生字段有2个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#lowercase-uc}

您希望将所有收集的产品名称转换为小写以便正确报告。

### 数据早于 {#lowercase-uc-databefore}

| 收集的产品名称 | 产品查看次数 |
|---|---:|
| 网球拍 | 35 |
| 网球拍 | 33 |
| 网球拍 | 21 |
| 棒球棒 | 15 |
| 棒球棒 | 12 |
| 棒球棒 | 10 |

{style="table-layout:auto"}

### 派生字段 {#lowercase-uc-derivedfield}

您定义一个`Product Names`派生字段。 您使用[!UICONTROL LOWERCASE]函数定义一个规则，以将[!UICONTROL 收集的产品名称]字段的值转换为小写并将其存储在新的派生字段中。

![小写规则的屏幕快照](assets/lowercase.png)


### 之后的数据 {#lowercase-uc-dataafter}

| 产品名称 | 产品查看次数 |
|---|---|
| 网球拍 | 89 |
| 棒球棒 | 37 |

{style="table-layout:auto"}

+++

<!-- MATH -->

### 数学

对数值字段使用基本的数学运算符（加、减、乘、除和加幂）。

+++ 详细信息

## 规范 {#math-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>数值</li></ul> | <ul><li>一个或多个数字字段</li><li>一个或多个运算符（加、减、乘、除、升幂）</li><li>用户输入值</li></ul> | <ul><li>`+` （添加）</li><li>`-` （减）</li><li>`*` （乘）</li><li>`/` （除）</li><li>`^` （加电）</li></ul> | <ul><li>每个派生字段25个操作</li><li>每个派生字段5个数学函数</li></ul> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#math-uc}

由于通货膨胀，您需要使用5%的通货膨胀率来更正摄取的CRM数据的收入数。

### 数据早于 {#math-uc-databefore}

| CRM ID | 年收入 |
|---|---:|
| 1234 | 35,070,000 |
| 4133 | 7,500,000 |
| 8110 | 10,980 |
| 2201 | 42,620 |

{style="table-layout:auto"}

### 派生字段 {#math-uc-derivedfield}

您定义一个`Corrected Annual Revenue`派生字段。 您使用[!UICONTROL MATH]函数定义一个将原始年收入数字乘以1.05的规则。

![数学规则的屏幕快照](assets/math.png)


### 之后的数据 {#math-uc-dataafter}

| CRM ID | 更正后的年收入 |
|---|---:|
| 1234 | 36,823,500 |
| 4133 | 7,875,000 |
| 8110 | 11,529,00 |
| 2201 | 44,751 |

{style="table-layout:auto"}

## 更多信息 {#math-more-info}

要创建公式，请执行以下操作：

1. 只需在公式字段中开始输入，与所键入内容匹配的数字字段即会显示在弹出菜单中。 或者，您可以从左窗格的可用字段中拖放数值字段。
   ![数学详细信息1](assets/math-more-info-1.png)

1. 添加操作数（例如`*`要相乘），然后添加其他字段或静态值。 可以使用括号定义更复杂的公式。

1. 若要插入静态值（例如`1.05`），请键入该值并从弹出菜单中选择&#x200B;**[!UICONTROL 添加&#x200B;*x*作为静态值]**&#x200B;或添加&#x200B;**[!UICONTROL 添加 — *x*作为负静态值]**。
   ![数学详细信息2](assets/math-more-info-2.png)

1. 绿色复选标记![复选标记](./assets/checkmark.svg)</span>指示数学公式是否有效，否则您将看到警告![警报](./assets/alert.svg)和消息[!UICONTROL 公式表达式无效]。
   ![数学详细信息3](assets/math-more-info-3.png)

在[!UICONTROL MATH]函数中使用静态数字时，有一些重要的注意事项：

- 静态值需要与字段关联。 例如，不支持仅对静态字段使用[!UICONTROL MATH]函数。
- 不能对静态值使用raise to power运算符(`ˆ`)。
- 如果在一个公式中使用多个静态值，则应该使用括号对这些静态值进行分组，以使公式有效。 例如：

   - 此公式返回错误。
     ![数学详细信息4](assets/math-more-info-4.png)

   - 此公式有效。
     ![数学详细信息5](assets/math-more-info-5.png)

使用Math函数进行基于点击级别的计算。 将[Summarize](#summarize)函数用于基于事件、会话或人员范围的计算。

+++


<!-- MERGE FIELDS -->

### 合并字段

将来自两个不同字段的值合并到一个新的派生字段中。

+++ 详细信息

## 规范 {#merge-fields-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#merge-fields-uc}

您要创建一个由页面名称字段和致电原因字段组成的维度，以便跨渠道分析历程。

### 数据早于 {#merge-fields-uc-databefore}

| 页面名称 | 会话 | 访客 |
|---|--:|--:|
| 帮助页面 | 250 | 200 |
| 主页 | 500 | 250 |
| 产品详细信息页面 | 300 | 200 |

{style="table-layout:auto"}

| 来电原因 | 会话 | 访客 |
|---|--:|--:|
| 有关我的订单的问题 | 275 | 250 |
| 更改我的订单 | 150 | 145 |
| 排序问题 | 100 | 95 |

{style="table-layout:auto"}

### 派生字段 {#merge-fields-uc-derivedfield}

您定义一个`Cross Channel Interactions`派生字段。 您使用[!UICONTROL MERGE FIELDS]函数定义规则以合并[!UICONTROL 页面名称]字段和[!UICONTROL 呼叫原因]字段中的值，并将其存储在新的派生字段中。

![合并字段规则的屏幕截图](assets/merge-fields.png)

### 之后的数据 {#merge-fields-uc-dataafter}

| 跨渠道交互 | 会话 | 访客 |
|---|--:|--:|
| 主页 | 500 | 250 |
| 产品详细信息页面 | 300 | 200 |
| 有关我的订单的问题 | 275 | 250 |
| 帮助页面 | 250 | 200 |
| 更改我的订单 | 150 | 145 |
| 排序问题 | 100 | 95 |

{style="table-layout:auto"}

## 更多信息 {#merge-fields-moreinfo}

您必须在“合并字段”规则中选择相同类型的字段。 例如，如果您选择日期字段，则要合并的所有其他字段都必须为日期字段。

![合并字段约束屏幕截图](assets/merge-fields-constraint.png)

+++


<!-- NEXT OR PREVIOUS -->

### 下一个或上一个

将某个字段作为输入，并解析该字段在会话或使用的范围内的下一个或上一个值。 这仅适用于“访问”和“事件”表格字段。

+++ 详细信息

## 规范 {#prevornext-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 方法]：<ul><li>上一个值</li><li>下一个值</li></ul></li><li>[!UICONTROL 作用域]：<ul><li>人员</li><li>会话</li></ul></li><li>[!UICONTROL 索引]：<ul><li>数值</li></ul><li>[!UICONTROL 包含重复项]：<ul><li>布尔值</li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段3个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#prevornext-uc1}

您想要了解&#x200B;**next**&#x200B;或&#x200B;**previous**&#x200B;值是您收到的数据的内容，其中已考虑重复值。

### 数据 {#prevornext-uc1-databefore}

**示例1 — 处理包含重复**

| 已接收数据 | 下一个值<br/>会话<br/>索引= 1<br/>包含重复项 | 下一个值<br/>会话<br/>索引= 1<br/>不包含重复项 | 上一个值<br/>会话<br/>索引= 1<br/>包含重复项 | 上一个值<br/>会话<br/>索引= 1<br/>不包含重复项 |
|---|---|---|---|---|
| 主页 | 主页 | 搜索 | *没有值* | *没有值* |
| 主页 | 搜索 | 搜索 | 主页 | *没有值* |
| 搜索 | 搜索 | 产品详细信息 | 主页 | 主页 |
| 搜索 | 产品详细信息 | 产品详细信息 | 搜索 | 主页 |
| 产品详细信息 | 搜索 | 搜索 | 搜索 | 搜索 |
| 搜索 | 产品详细信息 | 产品详细信息 | 产品详细信息 | 产品详细信息 |
| 产品详细信息 | 搜索 | 搜索 | 搜索 | 搜索 |
| 搜索 | 搜索 | *没有值* | 产品详细信息 | 产品详细信息 |
| 搜索 | *没有值* | *没有值* | 搜索 | 产品详细信息 |

{style="table-layout:auto"}

**示例2 — 处理接收的数据中包含空值的重复项**

| 已接收数据 | 下一个值<br/>会话<br/>索引= 1<br/>包含重复项 | 下一个值<br/>会话<br/>索引= 1<br/>不包含重复项 | 上一个值<br/>会话<br/>索引= 1<br/>包含重复项 | 上一个值<br/>会话<br/>索引= 1<br/>不包含重复项 |
|---|---|---|---|---|
| 主页 | 主页 | 搜索 | *没有值* | *没有值* |
| 主页 | 主页 | 搜索 | 主页 | *没有值* |
| 主页 | 搜索 | 搜索 | 主页 | *没有值* |
| 搜索 | 搜索 | 产品详细信息 | 主页 | 主页 |
|   |   |   |   |   |
| 搜索 | 搜索 | 产品详细信息 | 搜索 | 主页 |
| 搜索 | 产品详细信息 | 产品详细信息 | 搜索 | 主页 |
| 产品详细信息 | *没有值* | *没有值* | 搜索 | 搜索 |
|   |   |   |   |   |

{style="table-layout:auto"}

### 派生字段 {#prevnext-uc1-derivedfield}

您定义了`Next Value`或`Previous value`派生字段。 您使用[!UICONTROL NEXT或PREVIOUS]函数定义一个选择[!UICONTROL 接收的数据]字段的规则，选择[!UICONTROL Next值]或[!UICONTROL Previous值]作为[!UICONTROL 方法]，[!UICONTROL 会话]作为范围，并将[!UICONTROL 索引]的值设置为`1`。

![合并字段规则的屏幕截图](assets/prevnext-next.png)

## 更多信息 {#prevnext-moreinfo}

您只能选择属于“访问”或“事件”表的字段。

[!UICONTROL 包含重复项]确定如何处理[!UICONTROL NEXT或PREVIOUS]函数的重复值。

- 包括重复外观，以及下一个或上一个值。 如果选择[!UICONTROL 包含重复项]，它将忽略当前点击中下一个或上一个值的所有顺序重复项。

- 选定字段没有（空白）值的行将不会在[!UICONTROL NEXT或PREVIOUS]函数输出中返回下一个或上一个值。

+++

<!-- REGEX REPLACE -->

### 正则表达式替换

使用正则表达式将字段中的值替换为新派生字段。

+++ 详细信息

## 规范 {#regex-replace-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul><ul><li>[!UICONTROL 正则表达式]：</li><ul><li>字符串</li></ul></li><li>[!UICONTROL 输出格式]：<ul><li>字符串</li></ul></ul><ul><li>区分大小写</li><ul><li>布尔值</li></ul></li></ul></li> | <p>不适用</p> | <p>每个派生字段有1个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例 {#regex-replace-uc}

您希望获取URL的一个部分，并将其用作分析流量的唯一页面标识符。 您对正则表达式使用`[^/]+(?=/$|$)`来捕获URL的结尾，并将`$1`作为输出模式。

### 数据早于 {#regex-replace-uc-databefore}

| 页面 URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### 派生字段 {#regex-replace-uc-derivedfield}

您创建了一个`Page Identifier`派生字段。 使用[!UICONTROL REGEX REPLACE]函数定义规则，以使用`[^/]+(?=/$|$)`的[!UICONTROL Regex]和`$1`的[!UICONTROL 输出格式]替换[!UICONTROL 引用URL]字段的值。

![Regex替换规则的屏幕截图](assets/regex-replace.png)


### 之后的数据 {#regex-replace-uc-dataafter}

| 页面标识符 |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## 更多信息 {#regex-replace-more-info}

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
| `$n` | 输出与第n个子表达式匹配的内容。 例如，`$1`输出第一个子表达式。 |
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
| <ul><li>字符串</li><li>数值</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul></ul><ul><li>[!UICONTROL 方法]：</li><ul><li>从左侧</li><li>从右侧</li><li>转换为数组</li></ul></li><li>对于分隔符：<ul><li>字符串</li></ul><li>对于索引：<ul><li>数值</li></ul></li> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}

## 用例1 {#split-uc1}

您可以将语音应用程序响应收集到单个维度的分隔列表中。 您希望列表中的每个值在响应报表中都是唯一值。

### 数据早于 {#split-uc1-databefore}

| 语音应用程序响应 | 活动 |
|---|--:|
| 它非常棒，非常有意义，会推荐给其他人 | 1 |
| 它很棒，有点混乱，会推荐给别人 | 1 |
| 那不太好，很混乱，不会向别人推荐 | 1 |

{style="table-layout:auto"}

### 派生字段 {#split-u1-derivedfield}

您创建了一个`Responses`派生字段。 您使用[!UICONTROL SPLIT]函数定义一个规则，以使用[!UICONTROL Convert to array]方法将[!UICONTROL 语音应用程序响应]字段中的值转换为使用`,`作为[!UICONTROL 分隔符]的值。

![拆分规则1](assets/split-1.png)的屏幕截图

### 之后的数据 {#split-uc1-dataafter}

| 响应 | 活动 |
|---|--:|
| 非常棒 | 2 |
| 将推荐给其他人 | 2 |
| 不太好 | 1 |
| 完全合理 | 1 |
| 有点令人困惑 | 1 |
| 非常令人困惑 | 1 |
| 不会向他人推荐 | 1 |

{style="table-layout:auto"}

## 用例2 {#split-uc2}

您可以将语音应用程序响应收集到单个维度的分隔列表中。 您希望将列表中第一个值的响应转换为其自身的维度。 您要将列表中的最后一个值放入其自身的维度中。

### 数据早于 {#split-uc2-databefore}

| 响应 | 活动 |
|---|--:|
| 非常棒，非常合理，会推荐给别人 | 1 |
| 它很棒，有点混乱，会推荐给别人 | 1 |
| 那不太好，很混乱，不会向别人推荐 | 1 |

{style="table-layout:auto"}

### 派生字段 {#split-u2-derivedfield}

您创建了一个`First Response`派生字段。 使用[!UICONTROL SPLIT]函数定义一个规则，以从响应`,`左侧的[!UICONTROL 响应]字段中获取第一个值作为分隔符。

![拆分规则的屏幕截图 — 第一个值](assets/split-2.png)

通过选择“从右侧”、“1作为分隔符”和“1作为索引”，您可以创建一个`Second Response`派生字段，以从[!UICONTROL 响应]字段中获取最后一个值。

![拆分规则的屏幕截图 — 最后一个值](assets/split-3.png)

### 之后的数据 {#split-uc2-dataafter}

| 第一次响应 | 活动 |
|---|--:|
| 非常棒 | 2 |
| 不太好 | 1 |

{style="table-layout:auto"}

| 第二次响应 | 活动 |
|---|--:|
| 将推荐给其他人 | 2 |
| 不会向他人推荐 | 1 |

{style="table-layout:auto"}

+++

<!-- SUMMARIZE -->

### 总结

在事件、会话和用户级别将聚合类型函数应用于量度或维度。

+++ 详细信息

## 规范 {#summarize-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li><li>数值</li><li>日期</li></ul> | <ul><li>值<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>总结方法</li><li>范围<ul><li>事件</li><li>会话</li><li>人员</li></ul></li></ul> | <ul><li>数值<ul><li>MAX — 从一组值中返回最大值</li><li>MIN — 返回一组值中的最小值</li><li>MEDIAN — 返回一组值的中位数</li><li>MEAN — 返回一组值的平均值</li><li>SUM — 返回一组值的和</li><li>COUNT — 返回收到的值的数量</li><li>DISTINCT — 返回一组不同的值</li></ul></li><li>字符串<ul><li>DISTINCT — 返回一组不同的值</li><li>COUNT DISTINCT — 返回非重复值的数量</li><li>最常见 — 返回最常收到的字符串值</li><li>LEAST COMMON — 返回最不常收到的字符串值</li><li>FIRST — 收到的第一个值；仅适用于会话和事件表</li><li>LAST — 收到的最后一个值；仅适用于会话和事件表</li></ul></li><li>日期<ul><li>DISTINCT — 返回一组不同的值</li><li>COUNT DISTINCT — 返回非重复值的数量</li><li>最常见 — 返回最常收到的字符串值</li><li>LEAST COMMON — 返回最不常收到的字符串值</li><li>FIRST — 收到的第一个值；仅适用于会话和事件表</li><li>LAST — 收到的最后一个值；仅适用于会话和事件表</li><li>EARLIEST — 收到的最早值（由时间确定）；仅适用于会话和事件表</li><li>LATEST — 收到的最新值（由时间确定）；仅适用于会话和事件表</li></ul></li></ul> | 每个派生字段有3个函数 | 新建派生字段 |

{style="table-layout:auto"}

## 用例 {#summarize-uc}

您要将添加到购物车收入分为三个不同的类别：小、Medium和大。 这使您能够分析和识别高价值客户的特征。

### 数据早于 {#summarize-uc-databefore}

假设：

- 添加到购物车收入作为数值字段收集。

方案：

- CustomerABC123将ProductABC的35美元添加到购物车，然后将ProductDEF以75美元单独添加到购物车。
- CustomerDEF456为其购物车中添加50美元的ProductGHI ，然后单独将ProductJKL添加到购物车中，价格为275美元。
- CustomerGHI789为他们的购物车增加了500美元的ProductMNO。

逻辑：

- 如果访客的添加到购物车的总收入少于$150，则设置为小。
- 如果访客的添加到购物车的总收入大于$150但小于$500，则设置为Medium。
- 如果访客的添加到购物车的总收入大于或等于$500，则设置为大。

结果：

- CustomerABC123的添加到购物车收入的总价$110。
- CustomerDEF456的添加到购物车总收入为$325。
- CustomerGHI789的合计添加到购物车收入为500美元。

### 派生字段 {#summarize-uc-derivedfield}

您创建了一个`Add To Cart Revenue Size`派生字段。 您使用[!UICONTROL SUMMARIZE]函数和[!UICONTROL Sum] [!UICONTROL Summarize方法]，并将[!UICONTROL 作用域]设置为[!UICONTROL 人员]，以对[!UICONTROL cart_add]字段的值求和。 然后，使用第二个[!UICONTROL CASE WHEN]规则将结果拆分为树类别大小。

![摘要规则1](assets/summarize.png)的屏幕截图



### 之后的数据 {#summarize-uc-dataafter}

| 添加到购物车收入大小 | 访客 |
|---|--:|
| 小 | 1 |
| 媒介 | 1 |
| 大 | 1 |

{style="table-layout:auto"}

## 更多信息 {#summarize-more-info}

使用汇总函数进行基于事件、会话或人员范围的计算。 将[Math](#math)函数用于基于点击级别的计算。

+++

<!-- TRIM -->

### 修剪

将来自字段值开头或结尾的空白、特殊字符或字符数修剪到新的派生字段中。

+++ 详细信息

## 规范 {#trim-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 字段]<ul><li>规则</li><li>标准字段</li><li>字段</li></ul></li><li>修剪空格</li><li>修剪特殊字符<ul><li>输入特殊字符</li></ul></li><li>从左侧修剪<ul><li>从 <ul><li>字符串开始</li><li>位置<ul><li>位置#</li></ul></li><li>字符串<ul><li>字符串值</li><li>索引</li><li>标记以包含字符串</li></ul></li></ul></li><li>至<ul><li>字符串结束</li><li>位置<ul><li>位置#</li></ul></li><li>字符串<ul><li>字符串值</li><li>索引</li><li>标记以包含字符串</li></ul></li><li>长度</li></ul></li></ul></li><li>从右侧修剪<ul><li>从 <ul><li>字符串结束</li><li>位置<ul><li>位置#</li></ul></li><li>字符串<ul><li>字符串值</li><li>索引</li><li>标记以包含字符串</li></ul></li></ul></li><li>至<ul><li>字符串开始</li><li>位置<ul><li>位置#</li></ul></li><li>字符串<ul><li>字符串值</li><li>索引</li><li>标记以包含字符串</li></ul></li><li>长度</li></ul></li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段有1个函数</p> | <p>新建派生字段</p> |


## 用例1 {#trim-uc1}

您可以收集产品数据，但这些数据包含隐藏的空白字符，会对报表产生碎片。 您希望轻松修剪任何多余的空格

### 数据早于 {#trim-uc1-databefore}

| 产品 ID | 活动 |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### 派生字段 {#trim-u1-derivedfield}

您创建了一个`Product Identifier`派生字段。 您使用[!UICONTROL TRIM]函数定义规则以从&#x200B;**[!UICONTROL 产品ID]**&#x200B;字段&#x200B;**[!UICONTROL 修剪空白]**。

![拆分规则1](assets/trim-1.png)的屏幕截图

### 之后的数据 {#trim-uc1-dataafter}

| 产品标识符 | 活动 |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## 用例2 {#trim-uc2}

您在收集到的页面名称上的数据在页面名称的末尾包含一些错误的特殊字符，必须删除这些字符。

### 数据早于 {#trim-uc2-databefore}

| 名称 | 活动 |
|---|--:|
| 主页# | 1 |
| 主页？ | 1 |
| 主页% | 1 |
| 主页&amp; | 1 |
| 主页/ | 1 |

{style="table-layout:auto"}

### 派生字段 {#trim-u2-derivedfield}

您创建了一个`Page Name`派生字段。 使用[!UICONTROL TRIM]函数，使用[!UICONTROL 特殊字符] `#?%&/`从[!UICONTROL 名称]字段中定义一个规则，用于[!UICONTROL 修剪特殊字符]。

![拆分规则的屏幕截图 — 第一个值](assets/trim-2.png)

### 之后的数据 {#trim-uc2-dataafter}

| 页面名称 | 活动 |
|---|--:|
| 主页 | 5 |

{style="table-layout:auto"}


## 用例3 {#trim-uc3}

您收集包括storeID的数据。 storeID包含缩写的美国州代码作为前两个字符。 您只需在报表中使用该状态代码。

### 数据早于 {#trim-uc3-databefore}

| storeID | 活动 |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| 或234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### 派生字段 {#trim-u3-derivedfield}

您创建了一个`Store Identifier`派生字段。 您使用[!UICONTROL TRIM]函数定义一个规则以将[!UICONTROL storeID]字段从字符串结束位置截断[!UICONTROL 从右侧]截断`3`。

![拆分规则的屏幕截图 — 第一个值](assets/trim-3.png)

### 之后的数据 {#trim-uc3-dataafter}

| 存储标识符 | 活动 |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| 或者 | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL 解析

解析URL的不同部分，包括协议、主机、路径或查询参数。

+++ 详细信息

## 规范 {#urlparse-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>字符串</li></ul> | <ul><li>[!UICONTROL 字段]：</li><ul><li>规则</li><li>标准字段</li><li>字段</li></ul><li>[!UICONTROL 选项]：<ul><li>[!UICONTROL 获取协议]</li><li>[!UICONTROL 获取主机]</li><li>[!UICONTROL 获取路径]</li><li>[!UICONTROL 获取查询字符串值]<ul><li>[!UICONTROL 查询参数]：<ul><li>字符串</li></ul></li></ul></li><li>[!UICONTROL 获取哈希值]</li></ul></li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段5个函数</p> | <p>新建派生字段</p> |

{style="table-layout:auto"}


## 用例1 {#urlparse-uc1}

您只需将反向链接URL中的反向链接域用作营销渠道规则集的一部分。

### 数据早于 {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc1-derivedfield}

您定义一个`Referring Domain`派生字段。 您使用[!UICONTROL URL PARSE]函数定义一个规则，以便从[!UICONTROL 反向链接URL]字段中提取主机并将其存储在新的派生字段中。

![URL解析规则1](assets/url-parse-1.png)的屏幕截图

### 之后的数据 {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 用例2 {#urlparse-uc2}

您希望在[!DNL Page URL]中使用查询字符串的`cid`参数的值作为派生跟踪代码报告输出的一部分。

### 数据早于 {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 派生字段 {#urlparse-uc2-derivedfield}

您定义一个`Query String CID`派生字段。 您使用[!UICONTROL URL PARSE]函数定义规则以获取[!UICONTROL 页面URL]字段中查询字符串参数的值，并将`cid`指定为查询参数。 输出值存储在新的派生字段中。

![URL解析规则2](assets/url-parse-2.png)的屏幕截图

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

- 在为派生字段定义规则时，您最多可以使用十个不同的架构字段（不包括标准字段）。
   - 在这个最多十个不同的架构字段中，只允许三个查找架构或配置文件架构字段。
- 每个Customer Journey Analytics连接最多可以有100个派生字段。


### 函数限制摘要

| 功能 | 限制 |
|---|---|
| <p>Case When</p> | <ul><li>5大小写When每个派生字段的函数</li><li>每个派生字段有200个[运算符](#operators)</li></ul> |
| <p>分类</p> | <ul><li>5按派生字段对函数进行分类</li><li>每个派生字段有200个[运算符](#operators)</li></ul> |
| <p>拼接</p> | <ul><li>2每个派生字段的拼接函数</li></ul> |
| <p>删除重复数据</p> | <ul><li>5每个派生字段删除重复函数</li></ul> |
| <p>查找和替换</p> | <ul><li>每个派生字段2个查找和替换函数</li></ul> |
| <p>查询</p> | <ul><li>每个派生字段5个查找函数</li></ul> |
| <p>小写</p> | <ul><li>每个派生字段有2个小写函数</li></ul> |
| <p>数学</p> | <ul><li>每个派生字段25个操作</li><li>每个派生字段5个数学函数</li></ul> |
| <p>合并字段</p> | <ul><li>每个派生字段有2个合并字段函数</li></ul> |
| <p>下一个或上一个</p> | <ul><li>3每个派生字段的下一个或上一个函数</li></ul> |
| <p>正则表达式替换</p> | <ul><li>每个派生字段有1个正则表达式替换函数</li></ul> |
| <p>拆分</p> | <ul><li>每个派生字段有5个拆分函数</li></ul> |
| <p>总结</p> | <ul><li>3汇总每个派生字段的函数</li></ul> |
| <p>修剪</p> | <ul><li>每个派生字段有1个修剪函数</li></ul> |
| <p>URL 解析</p> | <ul><li>每个派生字段有5个URL解析函数</li></ul> |

{style="table-layout:auto"}

### 运算符

If或Else If构造中的运算符（在Case When函数中）是条件与&#x200B;**one**&#x200B;值的组合。 该条件的每个附加值都会增加运算符的数量。

例如，以下条件使用13个运算符。

![示例运算符](assets/operators-sample.png)

Classification函数中的运算符是[!UICONTROL 当值等于原始值]时[!UICONTROL 将值替换为新值]的单个条目。

例如，下面的分类规则使用3个运算符。

![分类规则1](assets/classify-1.png)的屏幕截图


## 更多信息 {#trim-more-info}

[`Trim`](#trim)和[`Lowercase`](#lowercase)是[数据视图](../component-settings/overview.md)中的组件设置中可用的功能。 通过使用派生字段，您可以组合这些函数，以直接在Customer Journey Analytics中进行更复杂的数据转换。 例如，您可以使用`Lowercase`删除事件字段中的区分大小写，然后使用[`Lookup`](#lookup)将新的小写字段与仅具有小写查找键的查找数据集进行匹配。 或者，在新字段中设置`Lookup`之前，您可以使用`Trim`删除字符。

对派生字段中的查找和配置文件字段的支持允许您根据事件查找和配置文件属性转换数据。 在查找或用户档案数据集中具有帐户级别数据的B2B场景中，此项特别有用。 此外，此支持对于处理来自查找数据（如营销活动信息和选件类型）或来自配置文件数据（如成员层和帐户类型）的常用字段中的数据非常有用。

有关派生字段的更多背景信息，请参阅：

- [充分利用您的数据：用于在Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)中使用派生字段的框架

- Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)的[派生字段用例
