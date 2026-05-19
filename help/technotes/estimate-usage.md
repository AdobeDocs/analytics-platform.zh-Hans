---
title: 管理您的Customer Journey Analytics使用情况
description: 介绍如何管理Customer Journey Analytics使用情况。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
autotag-review: '2026-05-19T09:30:13.855Z'
TQID: 'https://experienceleague.adobe.com/SWjkycY-YwNFMXRXwBypDtTL2ffFn40-Fp88vSxv-74'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 37%

---

# 管理您的Customer Journey Analytics使用情况

>[!TIP]
>
>使用[**[!UICONTROL 用法&#x200B;]**接口](/help/connections/manage-connections.md#usage)到**&#x200B;查看&#x200B;**在Customer Journey Analytics的所有连接中使用已摄取和可报告行的情况。



您可以在[**[!UICONTROL 连接&#x200B;]**接口](/help/connections/create-connection.md)中管理您的Customer Journey Analytics使用情况。 在此界面中，您可以在连接级别将Customer Journey Analytics数据保留定义为以月计的滚动时段（1个月、3个月、6个月等）。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。 它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

如果您保留默认值（未选中），则保留期将被 Adobe Experience Platform 数据保留设置所取代。 如果您在Experience Platform中有25个月的数据，则Customer Journey Analytics将通过回填获取25个月的数据。 如果您在 Platform 中删除了其中的 10 个月，则 Customer Journey Analytics 将会保留剩余的 15 个月。

数据保留基于时间戳，仅适用于事件数据集和摘要数据集。 由于没有适用的时间戳，因此轮廓或查找数据集不存在滚动数据窗口设置。 如果您的连接包括任何配置文件或查找数据集，则由于它们与事件数据集相连，因此会根据您在事件数据集时间戳上的数据保留设置将数据保留在Customer Journey Analytics中。


>[!MORELIKETHIS]
>
>[查看您的Customer Journey Analytics使用情况](/help/connections/manage-connections.md#usage)

