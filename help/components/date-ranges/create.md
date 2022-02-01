---
title: 创建日期范围
description: 创建要用在报告中的日期范围。
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 100%

---

# 创建日期范围

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解详情...](/help/getting-started/cja-aa.md)

您可以使用以下两种方法中的任一种创建自定义日期范围：

* 直接在 Workspace 项目中单击左侧日期范围组件列表旁边的“`+`”按钮
* 在日期范围管理器中

要在日期范围管理器中创建日期范围，请执行以下操作：

1. 使用您的 Adobe ID 凭据登录 [analytics.adobe.com](https://analytics.adobe.com)。
1. 依次转到[!UICONTROL 组件] > [!UICONTROL 日期范围]。
1. 单击[!UICONTROL 添加]按钮以打开用以创建日期范围的模式窗口。

## 创建日期范围模式窗口

模式窗口包含四个可供您修改的字段：

* **日期范围**：您要为此组件使用的日期范围。
* **标题**：您要为此组件使用的名称。该标题用在 Workspace 项目中。
* **描述**：您要为此组件使用的描述。单击 ![i](../assets/i.png) 图标后，系统会显示该描述。
* **标记**：使用标记整理日期范围。一个日期范围可以属于多个标记。

## 选择日期范围

单击模式窗口中的日期范围后，您可以选择多个选项：

* **日历**：选择开始日期和结束日期。
* **使用滚动日期**：如果您希望日期范围随时间变化，请选中此框。如果您希望日期范围保持静态，请不要选中此框。
* **选择预设**：如果您希望根据 Adobe 默认提供的范围设置自定义日期范围，请使用此下拉菜单。选择预设后，您可以根据自己的需求进一步自定义日期范围。这不会影响 Adobe 提供的预设。

## 滚动日期范围

如果您需要滚动日期范围，可以自定义滚动时间。您可以单独控制开始日期和结束日期的滚动时间。

* **日期开始时**：选择相应日期是在某个时间段开始时、结束时开始，还是使用固定日期。
* **使用的时间段**：选择日期范围滚动的频率。您可以将它设为每天、每周、每月、每季度或每年滚动一次。
* **偏移**：选择日期范围的偏移。您可以添加或减去日、周、月、季度或年。

## 滚动日期示例

某些日期范围在特定报告中很有用。

年初至今：

```text
Start: Start of current year
End: End of current day
```

上周四到本周四：

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

财年（例如，某个财年是否在 12 月开始）

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
