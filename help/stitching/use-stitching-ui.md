---
title: 使用拼合
description: 如何使用拼合
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
badgePremium: label="Beta 版" type="Informative"
source-git-commit: 0afe57047e2038f1acd9f88a1e7992da9a2819b1
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 3%

---

# 使用拼合

您可以对作为连接的一部分配置的一个或多个事件数据集启用拼合。 您可以为拼合启用的事件数据集的数量由您许可的Customer Journey Analytics包决定。

{{release-limited-testing}}

当您[创建连接](/help/connections/create-connection.md#dataset-settings)或[编辑连接](/help/connections/create-connection.md)时，可以将拼合作为事件数据集的[数据集设置](/help/connections/manage-connections.md#edit-a-connection)的一部分启用。

## 先决条件

要在连接UI中对事件数据集启用拼合，请执行以下操作：

* 必须已定义数据集所基于的架构：

   * 多个配置为标识的字段，允许您为永久ID和人员ID选择不同的值。
   * 至少一个标记为具有关联命名空间的主身份的字段，以防您将身份映射和主身份命名空间用于永久ID或人员ID。

* 如果要使用身份图形和基于图形的拼接，必须为Identity服务[启用事件数据集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。


## 印前检查检查

如果您满足前提条件，则可能需要在启用身份拼接之前对事件数据集中的数据执行一些预检检查：

* 确保在事件数据集的架构中正确标记身份。 [请参阅身份命名空间概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces)。
* 验证持久ID和人员ID的标识覆盖范围：
   * 持久ID：查询7天的数据，其中持久ID字段不为null，除以针对数据集中所有事件的7天数据查询。 该百分比应高于95%。

     可用于验证的查询示例：

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     其中：

      * `{PERSISTENT_ID_FIELD}`是持久ID的字段。 例如：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`是事件数据集的表名称。
      * `{FORMAT_STRING}`是时间戳字段的格式字符串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} `是开始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是标准格式的结束日期。 例如：`2024-01-08 00:00:00`。


   * 人员ID — 查询7天的数据，其中人员ID字段不为null，并除以针对数据集中所有事件的7天数据查询。 此百分比应高于5%。

     可用于验证的查询示例：

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     其中：

      * `{PERSON_ID_FIELD}`是人员ID的字段。 例如：`identityMap.crmId[0]`。
      * `{DATASET_TABLE_NAME}`是事件数据集的表名称。
      * `{FORMAT_STRING}`是时间戳字段的格式字符串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE}`是开始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是标准格式的结束日期。 例如：`2024-01-08 00:00:00`。



## 启用身份标识拼接

>[!NOTE]
>
>如果&#x200B;**[!UICONTROL 启用标识拼接]**&#x200B;在Connections界面中不可用，请使用[请求过程在数据集上启用拼接](/help/stitching/use-stitching.md)。



要启用拼接，请在&#x200B;**[!UICONTROL 添加数据集]**&#x200B;或&#x200B;**[!UICONTROL 编辑数据集]**&#x200B;对话框的事件数据集部分中：

启用身份拼接时![身份拼接选项](assets/identity-stitching-ui.png)

1. 选择&#x200B;**[!UICONTROL 启用身份拼接]**。

   如果为现有事件数据集启用拼合，**[!UICONTROL 更改人员ID]**&#x200B;对话框会显示由于使用拼合而更改人员ID所隐含的影响。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   **[!UICONTROL 启用身份拼接]**&#x200B;对话框汇总了拼接身份的结果。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

1. 从&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉菜单中选择一个永久ID。

   如果您为永久ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 启用&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。

1. 从&#x200B;**[!UICONTROL 人员ID]**&#x200B;下拉菜单中选择人员ID。

   如果您为人员ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 启用&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。


   如果您为人员ID选择&#x200B;**[!UICONTROL 身份图形]**（要使用[基于图形的拼接](/help/stitching/gbs.md)），则必须选择命名空间。

   >[!NOTE]
   >
   >您必须有权使用身份图。
   >

   之前，将显示&#x200B;**[!UICONTROL 更改为身份图]**&#x200B;对话框，以确保您在使用身份图进行拼合之前[已完成数据集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)的身份图的设置。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。


1. 从&#x200B;**[!UICONTROL 回顾窗口]**&#x200B;下拉菜单中选择一个回顾窗口。 可用选项取决于您有权访问的Customer Journey Analytics包。

保存包含为身份拼接启用的数据集的连接后，每个数据集的拼接过程从该数据集的数据摄取开始时开始。

## 限制

除了[基于字段的拼接限制](/help/stitching/fbs.md#limitations)和[基于图形的拼接限制](/help/stitching/gbs.md#limitations)之外，在“连接”界面中启用拼接时，还将应用以下限制：

* 作为单个连接的一部分，您只能拼合一次事件数据集。 您不能定义多个相同的事件数据集，也不能对每个实例使用单独的拼接配置。 如果要对同一数据集应用不同的拼接配置，请为每个配置使用单独的连接。

