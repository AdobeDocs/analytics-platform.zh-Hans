---
description: 通过同步可视化信息，您可以控制与可视化对应的数据表或数据源。
keywords: Analysis Workspace;将可视化与数据源同步
title: 管理数据源
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 27%

---

# 管理数据源 {#manage-data-sources}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="锁定选择"
>abstract="启用此设置可将可视化图表锁定到数据源中的选定位置或选定项目。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="显示表格"
>abstract="选择&#x200B;**[!UICONTROL 显示表格]**&#x200B;将会为当前可视化图表生成一个新的数据源，并将其与原始数据源分开。"

<!-- markdownlint-enable MD034 -->



通过同步可视化图表，您可以控制与可视化图表对应的数据表或数据源。

>[!TIP]
>
>您可以通过可视化图表标题旁边的![StatusOrange](/help/assets/icons/StatusOrange.svg)颜色来分辨哪些可视化图表相关。 颜色一致表示可视化图表基于同一个数据源。
>

您可以显示或隐藏数据源。 您还可以将选定内容锁定到选定位置或选定项目。 这些设置决定了当有新数据输入时，可视化图表发生更改（或不发生更改）的方式。

![数据Source选项对话框显示下一节中描述的选项。](assets/lock-selection.png)


| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 数据源]** | 从下拉菜单中选择可视化图表所基于的数据源。 |
| **[!UICONTROL 链接的可视化图表]** | 列出所有链接的可视化图表。 应用于数据源（自由格式表）。 |
| **[!UICONTROL 显示数据源]** | 可让您显示或隐藏与可视化图表对应的数据源（自由格式表）。 |
| **[!UICONTROL 锁定选择]** | 选择此选项可将可视化图表![LockClosed](/help/assets/icons/LockClosed.svg)锁定到相应数据表中当前选定的数据。 启用后，选择以下选项：  <ul><li>**选定位置**：可视化图表锁定在相应数据表中选择的&#x200B;**位置**&#x200B;上。 即使这些位置中的特定项目发生更改（例如，由于排序或筛选），这些位置也会继续可视化。 例如，如果您要始终显示此可视化图表的数据源中列出的前五个促销活动名称，请选择此选项。 无论显示哪个促销活动名称，</li> <li>**选定项**：可视化图表在相应数据表中当前选择的特定&#x200B;**项**&#x200B;上被锁定。 这些项目将继续可视化，即使它们在表中的项目之间更改了排名。 例如，如果您希望始终显示此可视化图表的数据源中列出的五个特定促销活动名称，请选择此选项。 无论这些促销活动名称的排名如何。</li></ul>如果可视化图表被锁定到所连接数据表中不再可见的数据，则可以生成一个新表。 选择&#x200B;**[!UICONTROL 显示表]**&#x200B;为当前可视化图表生成新的数据源（独立于原始数据源）。 |
