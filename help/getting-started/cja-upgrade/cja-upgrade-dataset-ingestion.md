---
title: 升级到 Customer Journey Analytics 时监控数据集摄取
description: 了解在升级到Customer Journey Analytics时如何监测数据集摄取
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 42%

---

# 升级到 Customer Journey Analytics 时监控数据集摄取 {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="验证数据集中的数据"
>abstract="现在您已经配置了 Web SDK 实施，您可以使用数据集活动管理器查看已摄取和失败的批次。如果您看到主要摄取批次，这一步就已完成。如果您看到主要失败批次或没有批次，请检查您的 Web SDK 实施以确保它正确地将数据发送到 Adobe。<br><br>如果一切都正确无误，这一步可以在不到一天的时间内完成。如果存在多个数据收集问题，修正错误可能需要更长的时间。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

配置Web SDK实施后，您需要检查各个批次的状态，以验证数据是否已摄取到数据集中。

1. 在Experience Platform UI的左侧导航中选择&#x200B;**[!UICONTROL 监控]**。

   此时将显示监控仪表板。 利用此仪表板，可查看来自批次或流式摄取的集客数据状态。

   <!-- insert screenshot -->

1. 选择&#x200B;**[!UICONTROL 批次端对端]**&#x200B;以查看批次列表。

   如果未显示批次，请检查您的Web SDK实施，以确保正确地向Adobe发送数据。

   <!-- insert screenshot -->

1. 为给定数据集选择批次ID，然后验证&#x200B;**[!UICONTROL 状态]**&#x200B;字段中是否显示&#x200B;**[!UICONTROL 成功]**。

   如果&#x200B;**[!UICONTROL 失败]**&#x200B;显示在&#x200B;**[!UICONTROL 状态]**&#x200B;字段中，请检查您的Web SDK实施，以确保其向Adobe正确发送数据。

   重复此步骤以验证每个批次的状态。

{{upgrade-final-step}}

