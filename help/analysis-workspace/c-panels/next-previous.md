---
description: 显示特定维度的下一个或上一个维度项的面板。
title: 下一个或上一个项目面板
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 下一个或上一个项目面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="下一个或上一个项目"
>abstract="创建一个面板，以了解人员来自的先前维度或人员转到的下一个维度。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="嵌套或上一个项目"
>abstract="分析访客之前来自或前往下一个最常见的位置。<br/><br/>**Dimension**：选择一个维度。 例如&#x200B;**页面**。<br/>**Dimension项**：选择特定的维度项。 例如&#x200B;**主页**。<br/>**方向**：选择&#x200B;**下一步**&#x200B;可查看紧接选定维度项之后的维度项。 选择&#x200B;**上一步**&#x200B;查看选定维度项之前的维度项。<br/>**容器**：选择&#x200B;**会话**&#x200B;可查看同一会话中的下一个/上一个维度项，或选择&#x200B;**人员**&#x200B;可查看同一人员的下一个/上一个维度项。"

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 下一个或上一个项目]**&#x200B;面板包含许多表和可视化图表，用于标识特定维度的下一个或上一个维度项目。 例如，您可能希望探索客户在访问主页后最常访问哪些页面。

## 使用

要使用&#x200B;**[!UICONTROL 下一个或上一个项目]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 下一个或上一个项目]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 为面板指定[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入

您可以使用以下输入设置配置[!UICONTROL 下一个或上一个项]面板：

![下一个或上一个项目面板](assets/next-or-previous-item.png)

| 输入 | 描述 |
| --- | --- |
| **[!UICONTROL 维度]** | 选择要为其浏览下一个或上一个项目的维度。 |
| **[!UICONTROL 维度项]** | 在下次/上一次查询的中心选择特定维度项目。 |
| **[!UICONTROL 方向]** | 指定您要查找[!UICONTROL Next]还是[!UICONTROL Previous]维度项。 |
| **[!UICONTROL 容器]** | 选择容器[!UICONTROL 会话]或[!UICONTROL 人员]（默认值），以确定查询的范围。 |

{style="table-layout:auto"}

选择&#x200B;**[!UICONTROL 生成]**&#x200B;以生成面板。

### 面板输出

[!UICONTROL 下一个或上一个项目]面板返回一组丰富的数据和可视化图表，以帮助您更好地了解特定维度项目之后或之前的具体情况。


![下一个/上一个面板输出](assets/next-or-previous-item-output.png)


| 可视化图表 | 描述 |
| --- | --- |
| **[!UICONTROL 水平条]** | 根据您选择的维度项目列出下一个（或上一个）项目。 将鼠标悬停在单个栏上会突出显示自由格式表中的相应项目。 |
| **[!UICONTROL 摘要数字]** | 当月（到目前为止）所有下一个或上一个维度项目发生次数的高级摘要编号。 |
| **[!UICONTROL 自由格式表]** | 以表格式根据所选的维度项列出下一个（或上一个）项目。 例如，在主页或Workspace页面之后（或之前），哪些（按发生次数）是用户访问的最受欢迎页面。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[创建面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>