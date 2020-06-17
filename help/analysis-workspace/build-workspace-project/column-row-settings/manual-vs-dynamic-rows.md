---
description: 如何与表中的静态行交互。
title: 静态行与动态行
uuid: caf033ef-d252-4f8a-802e-7edbbac5c8c0
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 91%

---


# 静态行与动态行

>[!NOTE] 您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

Analysis Workspace 表格会在您将维度拖入到表格中时生成“动态”行，这意味着给定量度中与该维度对应的所有项目都将提取到表格中。

例如，当您将浏览器维度拖动到表格时，其所有维度项目（例如，Android 浏览器、Mobile Safari、Firefox 等）都将动态提取到表格中。

与此相反，无论您何时手动选择特定量度、区段、数据范围或单个维度项目并将其拖动到表格中，结果都会生成硬编码或“静态”行或列表。您现在可以通过以下方式与静态行进行交互：

* 单击静态行中的“预览”图标可预览区段、量度和日期范围。
* 单击“x”图标以从表格中删除该行。
* 限制显示的行数和启用分页显示。
* 添加“混合维度项目”。例如，从浏览器维度添加一个项目，然后从产品维度添加另一个项目。

   说明如下：

   ![](assets/static_rows.png)

此外，现在只有当您处于静态行模式时，才能更改列总数的计算方式。只需单击齿轮图标并在以下 2 个选项之间进行切换：

![](assets/column-totals.png)

| 选项 | 描述 |
|---|---|
| （默认）通过汇总当前每列的值来计算总数。 | 此选项仅计算表格中的当前行。（客户端计算） |
| 根据每个量度的所有行计算总数。 | 此选项包括此维度的所有维度项目，甚至包括未列在表格中的维度项目。（服务器端计算） |

