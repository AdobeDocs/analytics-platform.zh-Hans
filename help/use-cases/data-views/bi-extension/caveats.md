---
title: 注意事项
description: 在Customer Journey Analytics中的各种BI工具中使用BI扩展时的注意事项
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: cb0102923f10f39becd40cc4187d2e11fb8c4e2f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# 注意事项


在使用Customer Journey Analytics BI扩展时，每个受支持的BI工具都存在一些注意事项。

+++ BI 工具

>[!BEGINTABS]

>[!TAB Power BI桌面]

* Power BI Desktop Advanced日期范围筛选是排他性的。  对于结束日期，您需要选择要在其中报告的一天之后的日期。 例如，**[!UICONTROL 位于]** `1/1/2023` **[!UICONTROL 或之后，且位于]** `1/2/2023`之前。
* 创建连接时，Power BI桌面默认为&#x200B;**[!UICONTROL 导入]**。 请确保使用&#x200B;**[!UICONTROL 直接查询]**。
* Power BI Desktop通过Power Query公开数据转换。  Power Query主要与Import类型连接配合使用，因此许多您应用日期或字符串函数之类的转换都会引发错误，指出您需要切换到Import类型连接。  如果您需要在查询时转换数据，则应该使用派生维度和量度，这样Power BI就不需要自己进行转换。
* Power BI Desktop不了解如何处理日期时间类型列，因此不支持&#x200B;**[!UICONTROL daterange *X *]**&#x200B;维度，如&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute &#x200B;]**。
* 默认情况下，Power BI Desktop会尝试使用更多查询服务会话建立多个连接。  转到项目的Power BI设置并禁用并行查询。
* Power BI Desktop执行所有排序和限制客户端操作。 Power BI Desktop对于前&#x200B;*X*&#x200B;个包含绑定值的过滤也具有不同的语义。 因此，您不能像在Analysis Workspace中一样创建相同的排序和限制。
* 早期版本的Power BI Desktop 2024年10月发行版中断了PostgreSQL数据源。 确保使用本文中提到的版本。

>[!TAB Tableau桌面]

* Tableau桌面日期范围过滤是独占的。 对于结束日期，您需要选择要在其中报告的一天之后的日期。
* 默认情况下，当您向工作表的行添加日期或日期时间维度（如&#x200B;**[!UICONTROL Daterangemonth]**）时，Tableau Desktop会将该字段包装在&#x200B;**[!UICONTROL YEAR()]**&#x200B;函数中。  要获得所需的内容，您需要选择该维度，然后从下拉菜单中选择要使用的日期函数。  例如，当您尝试使用&#x200B;**[!UICONTROL Daterangemonth]**&#x200B;时，将&#x200B;**[!UICONTROL Year]**&#x200B;更改为&#x200B;**[!UICONTROL Month]**。
* 在Tableau Desktop中，将结果限制为前&#x200B;*X*&#x200B;并不明显。 您可以显式限制结果，也可以使用计算字段和&#x200B;**[!UICONTROL INDEX()]**&#x200B;函数限制结果。  将Top *X*&#x200B;筛选器添加到维度时，会使用不受支持的内部连接生成复杂的SQL。

>[!TAB Looker]

* Looker具有每个节点的最大连接数设置，该设置要求介于5-100之间。  不能将此值设置为1。  此设置意味着Looker连接始终使用至少5个可用的查询服务会话。
* 通过Looker，可使用基于Customer Journey Analytics数据视图的视图创建项目。 然后，Looker使用LookerML基于维度和量度创建模型，这些维度和量度在数据视图中可用。  此项目视图不会自动更新以匹配源。  如果您对CJA数据视图维度、量度、计算量度或区段进行了更改或添加了其他内容，则这些更改不会自动显示在Looker中。  您必须手动更新项目视图或创建新项目。
* 查找器在日期或日期时间字段上的用户体验（如&#x200B;**[!UICONTROL 日期范围日期]**&#x200B;或&#x200B;**[!UICONTROL 日期范围日期]**）令人困惑。
* 查阅者的日期范围为独占而非包含。  **[!UICONTROL until （之前）]**&#x200B;为灰色，因此您可能缺少该方面。  对于您的结束日期，您需要选择要在其中报告的前一天。
* Looker不会自动将您的量度视为量度。  当您选择某个量度时，默认情况下，查找器会尝试将该量度视为查询中的维度。  要将量度视为量度，您需要创建如上所述的自定义字段。 作为快捷方式，您可以选择&#x200B;**[!UICONTROL ⋮]**，选择&#x200B;**[!UICONTROL 聚合]**，然后选择&#x200B;**[!UICONTROL 总和]**。

>[!TAB Jupyter笔记本]

* Jupyter Notebook的主要注意事项是该工具不像其他BI工具那样是拖放用户界面。 您可以创建良好的视觉效果，但您必须编写代码才能完成此操作。

>[!TAB RStudio]

* R dplyr使用平面架构，因此需要&#x200B;**[!UICONTROL FLATTEN]**&#x200B;选项。
* RStudio的主要注意事项是该工具不像其他BI工具那样是拖放用户界面。 您可以创建良好的视觉效果，但您必须编写代码才能完成此操作。

>[!ENDTABS]

+++
