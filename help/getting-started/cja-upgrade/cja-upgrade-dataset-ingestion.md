---
title: 升级到 Customer Journey Analytics 时监控数据集摄取
description: 了解在升级到Customer Journey Analytics时如何监测数据集摄取
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 33%

---

# 升级到 Customer Journey Analytics 时监控数据集摄取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="验证数据集中的数据"
>abstract="现在您已经配置了实施，可以使用数据集活动管理器查看已摄取和失败的批次。如果您主要看到的是已摄取的批次，那么这一步就完成了。如果您主要看到的是失败的批次或没有批次，请检查您的实施，以确保它正确地将数据发送到 Adobe。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

在配置Web SDK或API实施后，您需要检查各个批次的状态，以验证数据是否已摄取到数据集中。

1. 在Experience Platform UI的左侧导航中选择&#x200B;**[!UICONTROL 监控]**。

   此时将显示监控仪表板。 利用此仪表板，可查看来自批次或流式摄取的集客数据状态。

   <!-- insert screenshot -->

1. 选择&#x200B;**[!UICONTROL 批次端对端]**&#x200B;以查看批次列表。

   如果未显示任何批次，请检查您的实施，以确保正确地将数据发送到Adobe。

   <!-- insert screenshot -->

1. 为给定数据集选择批次ID，然后验证&#x200B;**[!UICONTROL 状态]**&#x200B;字段中是否显示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL Failed]**&#x200B;显示在&#x200B;**[!UICONTROL Status]**&#x200B;字段中，请检查您的实施以确保其向Adobe正确发送数据。

   重复此步骤以验证每个批次的状态。

{{upgrade-final-step}}

