---
title: 派生字段
description: 派生字段通过一组可用函数和函数模板指定对架构字段和/或标准组件的报告时间操作。
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 29%

---


# 派生字段（有限测试）{#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>这是尚未普遍提供的新派生字段函数的初步文档。 使用此信息可了解新的派生字段函数。 本文档仍可能会发生更改，并且当前的本文版本不承担任何法律义务。
>><br/>请参阅[派生字段](derived-fields.md)，了解有关派生字段的一般功能以及当前可用的已发布函数和函数模板的信息。
>

## 函数参考

{{select-package}}

对于每个支持的函数，请参阅以下详细信息：

- 规范：
   - 输入数据类型：支持的数据类型，
   - 输入：输入的可能值，
   - 包含的运算符：此函数支持的运算符（如果有），
   - 限制：适用于此特定函数的限制，
   - 输出。

- 用例，包括：
   - （可选）定义派生字段之前的数据，
   - 如何定义派生字段，
   - （可选）定义派生字段后的数据。

- 约束条件（如果适用）。



<!-- DATE MATH -->

### 日期数学 {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="日期数学"
>abstract="此函数提供返回两个日期或日期时间字段之间差异的功能。"

返回两个日期或两个日期时间字段之间的差值。

+++ 详细信息

## 规范 {#datemath-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>日期</li><li>日期时间</li></ul> | <ul><li>[!UICONTROL 范围]<ul><li>事件</li><li>会话</li><li>人员</li></ul></li><li>[!UICONTROL 值]：<ul><li>日期</li><li>日期时间</li><li>静态日期（用户输入）</li><li>静态日期时间（用户输入）</li><li>动态日期<ul><li>今天</li></ul></li><li>动态日期时间<ul><li>现在</li></ul></li></ul></li><li>[!UICONTROL 粒度]：<ul><li>Seconds</li><li>Minutes</li><li>小时</li><li>Days</li><li>Weeks</li><li>Months</li><li>季度</li><li>年</li></ul></li><li>对于每个日期或日期时间返回：<ul><li>第一次（会话或人员内）</li><li>上次（会话或人员内）</li></ul></li></ul> | <p>不适用</p> | <p>每个派生字段有 2 个函数</p> | <p>新的派生字段</p> |

{style="table-layout:auto"}


## 用例 1 {#datemath-uc1}

作为一家酒店公司的营销分析师，您想要了解上周客户签到日期和预订日期之间的天数差异。


### 派生字段 {#datemath-uc1-derivedfield}

您定义一个 `Days between booking and check-in` 派生字段。您使用[!UICONTROL DATE MATH]函数定义规则以计算[!UICONTROL 范围] [!DNL Person]在[!UICONTROL 预订日期]和[!UICONTROL 登记日期]之间的天数。 您选择[!UICONTROL 天]作为[!UICONTROL 输出粒度]。 并且您选择[!UICONTROL 返回]预订日期[!UICONTROL 和]登记日期[!UICONTROL 的最后一个]以确保在计算中使用最后一个人员范围值。

![日期数学规则的屏幕截图](assets/datemath-1.png)


## 用例 2 {#datemath-uc2}

作为一家实体店的营销分析师，您想要了解客户距商店上次访问是多少天前。 您可以使用移动设备应用程序中的地理位置功能以及商店中的信标来捕获客户的实际访问。

### 派生字段 {#datemath-uc2-derivedfield}

您可以定义一个新的 `Days Since Visit To Shop` 派生字段。您使用[!UICONTROL DATE MATH]函数定义规则以计算自定义日期时间（您在[!UICONTROL Date]中指定）和[!UICONTROL 本地时间]（来自事件数据集的[!UICONTROL placeContext]字段组）之间的天数，该自定义日期时间具有[!UICONTROL 重复数据删除范围]/[!UICONTROL 人员]。 选择[!UICONTROL 返回最后]以确保在计算中使用[!UICONTROL 本地时间]的最后一个人员范围值。 选择“日”作为[!UICONTROL 输出粒度]。

![日期数学规则2](assets/datemath-2.png)的屏幕截图


## 用例 3 {#datemath-uc3}

您希望了解会话中客户下订单之前的搜索时间（以分钟为单位）。

您定义了一个新的`Time Between Search And Order In Minutes`派生字段，该字段是两个[[!UICONTROL CASE WHEN]函数](#case-when)的结果，用于定义[!UICONTROL 搜索时间]和[!UICONTROL 订单时间]值。
然后使用这两个值计算差值，其中[!UICONTROL DATE MATH]函数的[!UICONTROL 作用域]设置为[!UICONTROL 会话]，值设置为[!UICONTROL 搜索时间]和[!UICONTROL 订单时间]，而[!UICONTROL 输出粒度]设置为[!UICONTROL 分钟]。 对于这两个值，请选择[!UICONTROL 返回第一个]以确保返回第一个[!UICONTROL 搜索时间]和[!UICONTROL 订单时间]。

![日期数学规则3](assets/datemath-3.png)的屏幕截图



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### 深度 {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="深度"
>abstract="此函数可用于返回任意字段的深度，其功能类似于事件深度标准组件。"

返回字段的深度，类似于现成可用的标准事件深度维度[](/help/components/dimensions/overview.md#standard-dimensions)。

+++ 详细信息

## 规范 {#depth-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| 任何 | 任意字段 | 不适用 | 每个派生字段有 3 个函数 | 新的派生字段 |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## 用例 {#depth-uc1}

您希望了解搜索深度（您也可以将其解释为搜索次数）。 因此，您可以稍后使用该搜索深度查找与特定搜索深度关联的搜索词。


### 派生字段 {#depth-uc1-derivedfield}

您可以定义一个新的 `Search Depth` 派生字段。您使用[!UICONTROL DEPTH]函数定义规则以检索[!UICONTROL Search]的深度并将其存储在新的派生字段中。

深度规则![屏幕截图](assets/depth-1.png)

+++


<!-- TYPECASE -->

### 类型转换 {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="类型转换"
>abstract="此函数可实现字段类型的即时转换，使该字段能够在 Customer Journey Analytics 中进行进一步转换。"

更改字段的字段类型，使其可用于Customer Journey Analytics中的其他转换。

+++ 详细信息

## 规范 {#typecast-io}

| 输入数据类型 | 输入 | 包含的运算符 | 限制 | 输出 |
|---|---|---|---|---|
| <ul><li>数值</li><li>日期</li><li>日期时间</li><li>字符串</li></ul> | <ul><li>[!UICONTROL 字段] | <p><ul><li>整数<ul><li>到字符串<strong>（必须）</strong></li></ul></li><li>双线<ul><li>到字符串<strong>（必须）</strong><ul><li>包含要继承的小数位数（最多5位？）</li></ul></li><li>到整数<strong>（应该）</strong></li></ul></li><li>字节<ul><li>到字符串<strong>（必须）</strong></li></ul></li><li>长型<ul><li>到字符串<strong>（必须）</strong></li></ul></li><li>日期<ul><li>到字符串<strong>（必须）</strong><ul><li>提供定义输出格式的功能</li></ul></li><li>示例<ul><li>日期（例如2025年1月7日）<ul><li data-stringify-indent="1" data-stringify-border="0">月/日/年<ul><li data-stringify-indent="2" data-stringify-border="0">例如 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">月-日-年<ul><li data-stringify-indent="2" data-stringify-border="0">例如 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">日-月-年<ul><li data-stringify-indent="2" data-stringify-border="0">例如 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">日-月-年<ul><li data-stringify-indent="2" data-stringify-border="0">例如 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">年-月-日<ul><li data-stringify-indent="2" data-stringify-border="0">例如 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如 2025-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">月/日/年<ul><li data-stringify-indent="2" data-stringify-border="0">例如 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如 01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">年/月/日<ul><li data-stringify-indent="2" data-stringify-border="0">例如 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">年/月/日<ul><li data-stringify-indent="2" data-stringify-border="0">例如 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY 年 MM 月 DD 日<ul><li data-stringify-indent="2" data-stringify-border="0">例如 2025年1月7日</li></ul></li></ul></li></ul></li></ul></li><li>日期时间<ul><li>到字符串<strong>（必须）</strong><ul><li>提供定义输出格式的功能</li></ul></li><li>示例<ul><li data-stringify-indent="0" data-stringify-border="0">日期时间（例如2025年1月7日，1:30pm，52秒）<ul><li data-stringify-indent="2" data-stringify-border="0">月/日/年时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY年MM月DD日hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">日-月-年时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">年/月/日时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">年-月-日时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 2025-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">月/日/年时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">月-日-年时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">年-月-日时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">例如 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY 年 MM 月 DD 日时分秒<ul><li data-stringify-indent="3" data-stringify-border="0">例如 2025年1月7日13:30:52</li></ul></li></ul></li></ul></li><li>字符串<ul><li>到数字<strong>（应该）</strong><ul><li>如果我们具有的值本质上不是数字，则它们将返回空值。</li><li>我们需要用户输入精度和要使用的区域设置。 </li></ul></li></ul></li></ul></li></ul></p> | <p>每个派生字段有 3 个函数</p> | <p>新的派生字段</p> |

{style="table-layout:auto"}


## 用例 1 {#typecast-uc1}

您有一个整数字段，即屏幕高度（例如，事件数据集中的device.screenHeight），您要将其用作基于字符串的维度。


### 派生字段 {#typecast-uc1-derivedfield}

您定义一个 `Screen Height` 派生字段。您使用[!UICONTROL TYPECAST]函数将规则定义为[!UICONTROL Typecast to] [!UICONTROL String] [!UICONTROL 屏幕高度]字段，并将其存储在新的派生字段中。

![Typecast规则1](assets/typecast-1.png)的屏幕截图



## 用例 2 {#typecast-uc2}

您想在同类群组表（仅支持整数）中使用收入，但收入字段具有双精度类型。

![Typecast规则2](assets/typecast-2.png)的屏幕快照


### 派生字段 {#typecast-uc2-derivedfield}

您定义一个 `Revenue (integer)` 派生字段。您使用[!UICONTROL TYPECAST]函数将规则定义为[!UICONTROL Typecast to] [!UICONTROL Integer] [!UICONTROL Revenue]字段，并将其存储在新的派生字段中。


+++
