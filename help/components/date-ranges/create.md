---
title: 创建日期范围
description: 创建日期范围以用于报告。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 4%

---


# 创建日期范围

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

您可以使用以下两种方法之一创建自定义日期范围：

* 单击左侧日期范围组件列表旁`+`的“”按钮，直接在工作区项目中显示
* 在日期范围管理器中

要在日期范围管理器中创建日期范围，请执行以下操作：

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. 导航到 [!UICONTROL 组件] >日 [!UICONTROL 期范围]。
1. 单击“ [!UICONTROL 添加] ”按钮以打开创建日期范围的模态窗口。

## 创建日期范围模态窗口

模态窗口有四个可编辑的字段：

* **日期范围**: 您希望此组件的日期范围。
* **标题**: 您希望此组件的名称。 标题用于工作区项目。
* **描述**: 此组件的描述。 单击“i”图标时会看 ![到](../assets/i.png) 描述。
* **标记**: 使用标记来组织日期范围。 日期范围可以属于多个标记。

## 选择日期范围

在模态窗口中单击日期范围时，您有以下几个选项：

* **日历**: 选择开始和结束日期。
* **使用滚动日期**: 如果希望日期范围随时间变化，请选中此框。 如果希望日期范围保持静态，请不要选中此框。
* **选择预设**: 如果您希望根据Adobe默认优惠的范围创建自定义日期范围，请使用此下拉菜单。 当您选择预设时，您可以进一步自定义日期范围以满足您的需求。 它不会影响Adobe优惠的预设。

## 滚动日期范围

如果要滚动日期范围，可以在滚动日期范围时进行自定义。 您可以控制开始和结束日期彼此独立滚动的时间。

* **日期开始时**: 选择日期开始是在某个时间段的开始、在某个时间段的结束，还是使用固定日期。
* **使用的时间段**: 选择日期范围滚动的频率。 您可以让它每天、每周、每月、每个季度或每年滚动。
* **偏移**: 选择日期范围的偏移。 您可以添加或减少天数、周数、月数、季度数或年数。

## 滚动日期示例

某些日期范围在某些报表中非常有用。

年初至今：

```text
Start: Start of current year
End: End of current day
```

上星期四至本星期四：

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

会计年度(例如，如果会计年度开始为12月)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
