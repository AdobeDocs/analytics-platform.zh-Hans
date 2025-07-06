---
description: 了解如何使用区段生成器中的运算符来比较和约束值。
title: 运算符
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 46%

---

# 运算符

通过区段生成器，您可以使用选定的运算符比较和约束组件的值。 运算符分为三类：[标准](#standard-operators)、[Data Warehouse](#data-warehouse-operators)和[非重复计数](#distinct-count-operators)。

根据您选择的运算符：

* 您可以输入一个值。
* 您可以输入部分值，然后从下拉菜单（如果可用）中进行选择。
* 立即从下拉菜单中选择一个值（如果可用）。

当您为验证可用值的运算符（如&#x200B;**[!UICONTROL 等于]**）键入值，并且该值与可用于该组件的值不匹配时，您会看到![AlertRed](/help/assets/icons/AlertRed.svg)图标。 您可以从下拉菜单中选择一个值，或按&#x200B;**[!UICONTROL _Enter_]**&#x200B;输入该值。

![区段等于](assets/segment-operator-equals.png)

## 通配符

支持通配符的运算符唯一支持的通配符是星号： `*`。 如果您需要搜索特定的&#42;字符，可以使用反斜杠（如`\*`）对其进行转义。

例如，您有一个名为&#x200B;*我的酷炫产品*&#x200B;的页面名称。

* 区段规则&#x200B;**[!UICONTROL 页面名称]** **[!UICONTROL 匹配]** `* product`将匹配上述页面名称。
* 但是，规则&#x200B;**[!UICONTROL 页面名称]** **[!UICONTROL 匹配]** `My \* product`仅与页面名称&#x200B;*My *产品*&#x200B;匹配。

## 标准运算符

| 运算符 | 所选维度、区段或量度事件... |
|--- |--- |
| **[!UICONTROL 等于]** | 返回与某一数字或字符串值完全匹配的项目。注意：如果使用通配符，则使用&#x200B;**[!UICONTROL 匹配]**&#x200B;运算符。 |
| **[!UICONTROL 不等于]** | 返回不包含输入值的完全匹配项的所有项目。注意：如果使用通配符，则使用&#x200B;**[!UICONTROL 与]**&#x200B;运算符不匹配。 |
| **[!UICONTROL 等于任何]** | 返回与输入字段中的任何值完全匹配的项目（最多 500 个项目）。例如，使用此运算符输入`Search Results, Homepage`页面名称&#x200B;**[!UICONTROL 维度的]**&#x200B;将匹配&#x200B;*搜索结果*&#x200B;和&#x200B;*主页*，并计为2个项目。 此运算符的输入字段以逗号分隔。 |
| **[!UICONTROL 不等于]**&#x200B;中的任何一个 | 识别与输入字段中的任何值完全匹配的项目（最多 500 个项目），然后只返回不包含这些值的项目。例如，为`Search Results, Homepage`Page Name **[!UICONTROL 维度输入带有此运算符的]**&#x200B;将识别&#x200B;*搜索结果*&#x200B;和&#x200B;*主页*，然后从返回的项目中&#x200B;**排除**&#x200B;这些结果。 此示例将计为 2 个项目。此运算符的输入字段以逗号分隔。 |
| **[!UICONTROL 包含]** | 返回与输入值的子字符串匹配的项目。例如，如果规则为&#x200B;**[!UICONTROL Page Name]** **[!UICONTROL 包含]** `Search`，则此规则将匹配包含子字符串`Search`的所有页面，包括&#x200B;*搜索结果*、*搜索*&#x200B;和&#x200B;*搜索*。 “contains”子句在 Adobe Analytics 中不区分大小写，但在 Customer Journey Analytics 中区分大小写。 |
| **[!UICONTROL 不包含]** | 返回&#x200B;**[!UICONTROL contains]**&#x200B;规则的逆数。 具体地说，与输入值匹配的所有项目都将从输入值中排除。例如，如果规则为&#x200B;**[!UICONTROL Page Name]** **[!UICONTROL 不包含]** `Search`，则不会匹配包含子字符串`Search`的任何页面，包括&#x200B;*搜索结果*、*搜索*&#x200B;和&#x200B;*搜索*。 这些值将从结果中排除。 |
| **[!UICONTROL 包含全部]** | 返回与子字符串匹配的项目，包括联接在一起的多个值。例如，如果为`Search Results`Page Name **[!UICONTROL 维度输入带有此运算符的]**，则将分别匹配&#x200B;*搜索结果*&#x200B;和&#x200B;*搜索结果*，但不匹配&#x200B;*搜索*&#x200B;或&#x200B;*结果*。 该规则将匹配&#x200B;*Search*&#x200B;和&#x200B;*Results*（一起找到）。 此运算符的输入字段以空格分隔（100 个词）。 |
| **[!UICONTROL 不包含所有]** | 识别与子字符串匹配的项目，包括联接在一起的多个值，然后只返回不包含这些值的项目。 例如，如果为`Search Results`Page Name **[!UICONTROL 维度输入带有此运算符的]**，则将分别识别&#x200B;*搜索结果*&#x200B;和&#x200B;*搜索结果*（但不包括&#x200B;*搜索*&#x200B;或&#x200B;*结果*），然后排除这些项目。 此运算符的输入字段以空格分隔（100 个词）。 |
| **[!UICONTROL 包含任何]** | 返回与子字符串匹配的项目，包括联接在一起或单独识别的多个值。例如，使用此运算符输入`Search Results`将匹配&#x200B;*搜索结果*、*搜索结果*、*搜索*&#x200B;和&#x200B;*结果*。 它将匹配一起出现或单独出现的&#x200B;*搜索*&#x200B;或&#x200B;*结果*。 此运算符的输入字段以空格分隔（100 个词）。 |
| **[!UICONTROL 不包含任何]** | 根据子字符串识别项目，然后返回不包含这些子字符串的值。其中会包含多个联接在一起或单独识别的值。例如，输入`Search Results`Page Name **[!UICONTROL 维度的]**&#x200B;将匹配&#x200B;*搜索结果*、*搜索结果*、*搜索*&#x200B;和&#x200B;*结果*，其中&#x200B;*搜索*&#x200B;或&#x200B;*结果*&#x200B;是同时存在还是单独存在的。 然后会排除包含这些子字符串的项目。此运算符的输入字段以空格分隔（100 个词）。 |
| **[!UICONTROL 开头]** | 返回以输入的字符串值开头的项目。 |
| **[!UICONTROL 开头不为]** | 返回不是以输入的字符串值开头的所有项目。 这与&#x200B;**[!UICONTROL 开头为]**&#x200B;运算符的相反。 |
| **[!UICONTROL 结束]** | 返回以输入的字符串值结束的项目。 |
| **[!UICONTROL 结束不为]** | 返回未以输入的字符串值结尾的所有项目。 这与&#x200B;**[!UICONTROL 结尾为]**&#x200B;运算符的相反。 |
| **[!UICONTROL 匹配]** | 返回与给定的数字或字符串值完全匹配的项目。**[!UICONTROL matches]**&#x200B;子句在Adobe Analytics和Customer Journey Analytics中区分大小写。 **注意**：在使用[通配符](#wildcards) （通配）功能时使用此运算符。 “通配”示例：<ul><li>`a*e` 将匹配 `ae`、`abcde`、`adobe` 和 `a whole sentence`</li><li>`adob*` 将匹配 `adobe`、`adobe analytics` 和 `adobo recipe`</li><li>`*dobe` 将匹配 `dobe`、`adobe` 和 `cute little dobe`</li></ul> |
| **[!UICONTROL 不匹配]** | 返回不包含输入值的完全匹配项的所有项目。注意：在使用[通配符](#wildcards) （通配）功能时使用此运算符。 |
| **[!UICONTROL 存在]** | 返回存在的项目的数量。例如，如果您使用&#x200B;**[!UICONTROL exist]**&#x200B;运算符评估&#x200B;**[!UICONTROL 页面未找到]**&#x200B;维度，则会返回错误页面的数量。 |
| **[!UICONTROL 不存在]** | 返回所有不存在的项目。例如，如果您使用&#x200B;**[!UICONTROL 不存在]**&#x200B;运算符评估&#x200B;**[!UICONTROL 页面未找到]**&#x200B;维度，则会返回不存在此错误页面的页面数。 |

## Data Warehouse 运算符

| 运算符 | 所选维度、区段或量度事件... |
| --- | --- |
| **[!UICONTROL 小于]** | 返回数字计数小于输入值的项目。 |
| **[!UICONTROL 小于或等于]** | 返回数字计数小于或等于输入值的项目。 |
| **[!UICONTROL 大于]** | 返回数字计数大于输入值的项目。 |
| **[!UICONTROL 大于或等于]** | 返回数字计数大于或等于输入值的项目。 |

## 不同的计数运算符

您可以按维度中项目的非重复计数进行分段。示例： *查看超过5个不同产品的访客*，或&#x200B;*查看超过5个不同页面的访问*。

| 运算符 | 所选维度、区段或量度事件... |
| --- | --- |
| **[!UICONTROL 等于]** | 返回独特计数等于输入值的维度项目。 |
| **[!UICONTROL 不等于]** | 返回独特计数不等于输入值的维度项目。 |
| **[!UICONTROL 大于]** | 返回独特计数大于输入值的维度项目。 |
| **[!UICONTROL 小于]** | 返回独特计数小于输入值的维度项目。 |
| **[!UICONTROL 大于或等于]** | 返回独特计数大于或等于输入值的维度项目。 |
| **[!UICONTROL 小于或等于]** | 返回独特计数小于或等于输入值的维度项目。 |


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [不同的维度计数](https://video.tv.adobe.com/v/27257?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]
