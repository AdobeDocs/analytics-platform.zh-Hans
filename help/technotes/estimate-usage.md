---
title: 管理您的Customer Journey Analytics使用情况
description: 介绍如何管理Customer Journey Analytics使用情况。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 42%

---

# 管理您的Customer Journey Analytics使用情况

>[!TIP]
>
>使用[**[!UICONTROL 用法&#x200B;]**接口](/help/connections/manage-connections.md#usage)到**&#x200B;查看&#x200B;**在Customer Journey Analytics的所有连接中使用已摄取和可报告行的情况。



您可以在[**[!UICONTROL 连接&#x200B;]**接口](/help/connections/create-connection.md)中管理您的Customer Journey Analytics使用情况。 在此界面中，您可以在连接级别将Customer Journey Analytics数据保留定义为以月计的滚动时段（1个月、3个月、6个月等）。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

如果您保留默认值（未选中），则保留期将被 Adobe Experience Platform 数据保留设置所取代。如果您在Experience Platform中有25个月的数据，则Customer Journey Analytics将通过回填获取25个月的数据。 如果您在 Platform 中删除了其中的 10 个月，则 Customer Journey Analytics 将会保留剩余的 15 个月。

数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此轮廓或查找数据集不存在滚动数据窗口设置。如果您的连接包括任何配置文件或查找数据集，则由于它们与事件数据集相连，因此会根据您在事件数据集时间戳上的数据保留设置将数据保留在Customer Journey Analytics中。


>[!MORELIKETHIS]
>
>[查看您的Customer Journey Analytics使用情况](/help/connections/manage-connections.md#usage)

