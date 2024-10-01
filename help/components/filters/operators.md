---
title: 运算符
description: 确定组件如何与筛选器中的值交互。
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# 运算符

通过筛选器生成器，您可以使用选定的运算符比较和约束组件的值。 运算符分为两个类别：[[!UICONTROL 标准]](#standard-operators)和[[!UICONTROL 非重复计数]](#distinct-count-operators)。

## 标准运算符

| 运算符 | 描述 |
| --- | --- |
| **[!UICONTROL 等于]** | 返回与某一数字或字符串值完全匹配的项目。如果使用通配符，请使用匹配运算符。 |
| **[!UICONTROL 不等于]** | 返回不包含输入值的完全匹配项的所有项目。如果使用通配符，则使用“不匹配”运算符。 |
| **[!UICONTROL 等于任何]** | 返回包含与所输入的子字符串值匹配的值的任意项并以逗号分隔。 |
| **[!UICONTROL 包含]** | 返回与输入值的子字符串匹配的项目。例如，如果页面名称维度的值包含`Search`，则此运算符与名称中包含子字符串`Search`的所有页面匹配，包括`Search Results`、`Search`和`Searching`。 此运算符区分大小写。 |
| **[!UICONTROL 不包含]** | 从结果中排除与输入值匹配的所有项。 例如，如果页面名称维度的值不包含`Search`，则此运算符将排除其名称中包含子字符串`Search`的所有页面，包括`Search Results`、`Search`和`Searching`。 |
| **[!UICONTROL 包含全部]** | 返回包含所有子字符串（以空格分隔）的项，顺序不限。例如，指定`Search Results`作为此运算符的值将匹配`Search Results`和`Results of Search`，但不匹配单独的`Search`或`Results`。 此运算符支持最多 100 个以空格分隔的单词。 |
| **[!UICONTROL 不包含所有]** | 从结果中排除与每个输入值匹配的所有项。 例如，将`Search Results`指定为此运算符的值将排除`Search Results`和`Results of Search`，但不排除`Search`或`Results`。 此运算符支持最多 100 个以空格分隔的单词。 |
| **[!UICONTROL 包含任何]** | 返回包含与任意指定子字符串的项。例如，指定`Search Results`作为此运算符的值将匹配`Search Results`、`Results of Search`、`Search`和`Results`。 此运算符支持最多 100 个以空格分隔的单词。 |
| **[!UICONTROL 不包含任何]** | 从结果中排除与任意子字符串匹配的所有项。 例如，将`Search Results`指定为此运算符的值将排除`Search Results`、`Results of Search`、`Search`和`Results`。 此运算符支持最多 100 个以空格分隔的单词。 |
| **[!UICONTROL 开头]** | 返回以指定值的字符或字符串开头的项目。 |
| **[!UICONTROL 开头不为]** | 返回不是以指定值的字符或字符串开头的项目。 |
| **[!UICONTROL 结束]** | 返回以指定值的字符或字符串结束的项目。 |
| **[!UICONTROL 结束不为]** | 返回不以指定值的字符或字符串结尾的所有项目。 |
| **[!UICONTROL 匹配]** | 返回与基于给定数字或字符串值的项目完全匹配的项目。 支持使用星号 (`*`) 作为通配符。此运算符区分大小写。例如：<ul><li>`a*e` 匹配 `ae`、`abcde`、`adobe` 和 `a whole sentence`。</li><li>`adob*` 匹配 `adobe`、`adobe analytics` 和 `adobo recipe`</li><li>`*dobe` 匹配 `dobe`、`adobe` 和 `cute little dobe`。</li></ul> |
| **[!UICONTROL 不匹配]** | 排除与字符串匹配的所有项。支持使用星号 (`*`) 作为通配符。 |
| **[!UICONTROL 存在]** | 如果值不是 null 则返回项。 |
| **[!UICONTROL 不存在]** | 如果值是 null 则返回项。 |

## 不同的计数运算符

您可以按维度中项目的非重复计数进行筛选。 例如，您可以为查看了5个以上不重复产品或查看了5个以上不重复页面的访问的人创建过滤器。

| 运算符 | 描述 |
| --- | --- |
| **[!UICONTROL 等于]** | 返回独特计数等于输入值的维度项目。 |
| **[!UICONTROL 不等于]** | 返回独特计数不等于输入值的维度项目。 |
| **[!UICONTROL 大于]** | 返回独特计数大于输入值的维度项目。 |
| **[!UICONTROL 小于]** | 返回独特计数小于输入值的维度项目。 |
| **[!UICONTROL 大于或等于]** | 返回独特计数大于或等于输入值的维度项目。 |
| **[!UICONTROL 小于或等于]** | 返回独特计数小于或等于输入值的维度项目。 |
