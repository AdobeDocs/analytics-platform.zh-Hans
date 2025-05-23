---
title: 如何在Customer Journey Analytics的Report Builder中选择日期范围
description: 介绍如何在Report Builder for Customer Journey Analytics中使用日历、滚动日期和自定义表达式
role: User
feature: Report Builder
type: Documentation
exl-id: 7252214f-a7d6-451b-99c9-d39e8e47120b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 49%

---

# 选择日期范围

要更改现有数据块的日期范围，请执行以下操作：

- 选择&#x200B;**[!UICONTROL 编辑数据块]**，或者
- 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;中选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;链接。

使用以下选项更改数据块的日期范围。

## 日程表

**[!UICONTROL 日历]**&#x200B;选项允许您使用以下选项创建静态或滚动日期：

### 日期范围

日期范围字段显示数据块请求的当前日期范围。 您可以直接输入日期或使用![日历](/help/assets/icons/Calendar.svg)指定日期范围。

![日期范围日历](assets/date-range-calendar.png){zoomable="yes"}

### 预设

使用预设下拉菜单选择预设。 您还可以输入文本来搜索预设。

![日期范围预设](assets/date-range-presets.png){zoomable="yes"}

预设下拉菜单包括一组标准的预设日期范围和日期范围组件，可用于您保存的数据视图或者与您共享的数据视图。

### 滚动日期

要定义滚动日期，请执行以下操作：

![USe滚动日期](assets/date-range-rolling-date.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 使用滚动日期]**&#x200B;来定义滚动日期定义的逻辑。 您可以选择括号中的文本（例如&#x200B;**[!UICONTROL 固定开始 — 每日滚动]**）以扩展面板并指定&#x200B;**[!UICONTROL 开始]**&#x200B;和&#x200B;**[!UICONTROL 结束]**&#x200B;的详细信息。

1. 选择&#x200B;**[!UICONTROL 开始]**、 **[!UICONTROL 结束]**&#x200B;或&#x200B;**[!UICONTROL 固定日期]**。

   - 当选择了&#x200B;**[!UICONTROL 开始]**&#x200B;或&#x200B;**[!UICONTROL 结束]**&#x200B;时，您可以生成一个完整的表达式。例如：**&#x200B;** **[!UICONTROL 当前年份的结束]**&#x200B;**[!UICONTROL 加上]**`1`**[!UICONTROL 天]**。为表达式的每个部分选择适当的值。

      - 选择当前时间的值。例如，**[!UICONTROL 当前年份]**。
      - 为可选的附加计算选择值。 例如，**[!UICONTROL 加上]**。
      - 当您指定了额外的计算时，请指定一个值。例如，`1`。
      - 当您指定了额外的计算时，请选择用于该计算的时段。例如，**[!UICONTROL 天]**。

   - 选择&#x200B;**[!UICONTROL 固定日期]**&#x200B;后，请指定固定日期或使用选取器选择日期。

1. 选择&#x200B;**[!UICONTROL 隐藏]**&#x200B;以隐藏滚动日期计算的详细信息。


### 自定义表达式

通过自定义选项表达式，您可以通过构建自定义表达式更改日期范围，或者输入数学公式。

![日期范围自定义表达式](assets/date-range-custom-expression.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 使用滚动日期]**。

1. 选择&#x200B;**[!UICONTROL 使用自定义表达式]**。

   选择&#x200B;**[!UICONTROL 使用自定义表达式]**&#x200B;时，标准滚动日期范围控件将禁用。

1. 输入[自定义表达式](#create-a-custom-expression)。

1. 使用&#x200B;**[!UICONTROL 日期预览]**&#x200B;验证生成的日期范围。

#### 创建自定义表达式

1. 输入[日期引用](#date-references)。

1. 添加可选的[日期运算符](#date-operators)以将日期移动到过去或未来。

您可以输入包含多个运算符的自定义表达式，如`tm-11m-1d`。

#### 日期引用

下表列出了日期引用示例。

| 日期引用 | 类型 | 描述 |
|----------------|--------------|----------------------------|
| `1/1/10` | 静态日期 | 以 ISO 日期格式输入 |
| `td` | 滚动日期 | 当天的开始 |
| `tw` | 滚动日期 | 本周的开始 |
| `tm` | 滚动日期 | 本月的开始 |
| `tq` | 滚动日期 | 本季度的开始 |
| `ty` | 滚动日期 | 本年度的开始 |

#### 日期运算符

下表列出了日期运算符示例。

| 日期运算符 | 单位 | 描述 |
|----------------|---------|--------------------|
| `+6d` | 日 | 添加 6 天到日期引用 |
| `+1w` | 周 | 添加一整周到日期引用 |
| `-2m` | 月 | 从日期引用减去 2 整周 |
| `-4q` | 季度 | 从日期引用减去 4 个季度 |
| -`1y` | 年 | 从日期引用减去 1 年 |

#### 日期表达式

下表列出了日期表达式示例。

| 日期表达式 | 含义 |
|-----------------|--------------------------------------|
| `td` | 今天 |
| `td-1w` | 上周的第一天 |
| `tm-1d` | 上个月的第一天 |
| `td-52w` | 52 周以前的同一天 |
| `tm-11m-1d` | 去年同一个月的上一天 |
| `"2020-09-06"` | 具体日期：2020年9月9日 |



## 来自单元格中的日期范围

日期范围可以在工作表单元格中指定。使用&#x200B;**[!UICONTROL 单元格中的日期范围]**&#x200B;选项从所选单元格中选择数据块的开始日期和结束日期。 选择&#x200B;**[!UICONTROL 从单元格]**&#x200B;选项时，面板会显示&#x200B;**[!UICONTROL 从]**&#x200B;到&#x200B;**[!UICONTROL 到]**&#x200B;字段，您可以在其中输入单元格位置或使用![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)选取当前选定的单元格。

![从单元格工作表1！H4选择到工作表1！I4](./assets/date-range-from-cell.png){zoomable="yes"}


## 排除当天

选择&#x200B;**[!UICONTROL 排除当天]**&#x200B;从选定的日期范围中排除当天。 当天从用于定义日期范围的所有模式中排除：日历、滚动日期或自定义表达式。


## 有效日期范围

下表描述了有效的日期范围格式。

- 开始日期和结束日期必须采用以下格式：YYYY-MM-DD

- 开始日期必须早于或等于结束日期。两个日期均可以设置在未来。

- 使用滚动日期时，开始日期必须是当天或过去。如果选择&#x200B;**[!UICONTROL 排除当天]**，则开始日期必须为过去。

- 您可以为未来创建静态日期范围设置。例如，您可能需要为下周的市场营销活动启动设置未来的日期。此选项提前为营销活动创建工作簿监控。

## 更改日期范围

您可以编辑现有数据块的日期范围。

1. 在数据块中选择单元格。

- 在&#x200B;**[!UICONTROL 命令]**&#x200B;面板中选择&#x200B;**[!UICONTROL 编辑数据块]**，或者
- 在&#x200B;**[!UICONTROL 快速编辑]**&#x200B;面板中选择&#x200B;**[!UICONTROL 日期范围]**&#x200B;链接。

1. 使用任何可用的日期选择选项修改日期范围。

1. 选择&#x200B;**[!UICONTROL 应用]**。

Report Builder 将新日期范围应用到选区中的所有数据块。
