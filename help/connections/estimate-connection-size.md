---
title: 估计连接大小
description: 报告您当前使用Customer Journey Analytics的情况（用于计费）
translation-type: tm+mt
source-git-commit: 27b3b1d9e6042f4c61cd1d5bb9d574cc268c3460
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# 估计连接大小

您可能需要知道[!UICONTROL Customer Journey Analytics]中当前有多少行数据。 本主题旨在向您展示如何报告[!UICONTROL Customer Journey Analytics]的当前使用情况。

1. 在[!UICONTROL Customer Journey Analytics]中，单击&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。
1. 在[!UICONTROL 编辑连接]屏幕上，选择要确定其使用／连接大小的连接。

   ![编辑连接](assets/edit-connection.png)

1. 从左边栏中选择作为连接一部分的数据集。 在这种情况下，它是“B2B印象”数据集。

   ![数据集](assets/dataset.png)

1. 单击其名称旁边的蓝色(i)图标（信息）。 您会注意到数据集有3.8k行/事件。 此外，要获得确切的行数，请单击Experience Platform表下方的&#x200B;**[!UICONTROL 编辑预览]**。 这会将您重定向到[!UICONTROL Adobe Experience Platform]中的数据集。

   ![AEP数据集信息](assets/data-size.png)

1. 注意此数据集的&#x200B;**[!UICONTROL Total records]**&#x200B;总记录数为3.83k记录，数据大小为388.59 KB。

1. 对连接中的其他数据集重复步骤1-5，并添加记录／行数。 最终的聚合数将是连接的使用量度，这是您要从[!UICONTROL Adobe Experience Platform]中摄取的连接数据集的行数。

## 确定摄取的行数

CJA中实际摄取的事件数取决于您的连接配置设置。 此外，如果您选择了错误的人员ID，或者此ID对于数据集中的某些行不可用，则[!UICONTROL Customer Journey Analytics]将忽略这些行。 要确定所摄取的事件的实际行，请执行以下步骤：

1. 保存连接后，创建同一连接的数据视图，不使用任何过滤器。
1. 创建Workspace项目并选择正确的数据视图。 创建自由形式表，并拖放具有&#x200B;**[!UICONTROL Year]**&#x200B;维度的&#x200B;**[!UICONTROL 事件]**&#x200B;度量。 从日期选择日历中选择一个足够大的日期范围，将所有数据封装到连接中。 这将允许您查看被引入[!UICONTROL 事件]的Customer Journey Analytics数。

   ![工作区项目](assets/event-number.png)

   >[!NOTE]
   >
   >这样，您就可以看到从事件数据集摄取的事件数。 它不包含用户档案和查找类型数据集。 按照步骤1-3用户档案和查找数据集，并添加数字以获取此连接的总行数。

## 诊断差异

在某些情况下，您可能会注意到Connection摄取的事件总数与AEP中数据集中的行数不同。 在这种情况下，数据集“B2B印象”有7650行，而数据集包含AEP中的3830行。 出现差异的原因有多种，可以采取以下步骤进行诊断：

1. 按&#x200B;**[!UICONTROL 平台数据集ID]**&#x200B;划分此维度，您会注意到两个大小相同但不同的&#x200B;**[!UICONTROL 平台数据集ID]**&#x200B;的数据集。 每个数据集有3825条记录。 这意味着[!UICONTROL Customer Journey Analytics]由于缺少人员ID或缺少时间戳而忽略了5个记录：

   ![细分](assets/data-size2.png)

1. 此外，如果我们签入[!UICONTROL Adobe Experience Platform]，则没有ID为“5f21c12b732044194bffc1d0”的数据集，因此，在创建初始连接时，有人从[!UICONTROL Adobe Experience Platform]中删除了此特定数据集。 之后，它又被添加到[!UICONTROL Customer Journey Analytics]中，但由[!UICONTROL Adobe Experience Platform]生成不同的[!UICONTROL 平台数据集ID]。

   阅读有关[!UICONTROL Customer Journey Analytics]和[!UICONTROL Adobe Experience Platform]中数据集和连接删除[含义的更多信息。](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)
