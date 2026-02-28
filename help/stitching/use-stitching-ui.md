---
title: 启用拼合
description: 了解如何在连接UI中启用拼合。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c6ccbdf89c51deef33b562a053b9c3b4bc626497
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 8%

---

# 启用拼接

您可以对作为连接的一部分配置的一个或多个事件数据集启用拼合。 您许可的Customer Journey Analytics包将决定您能够为拼合启用的事件数据集数量。

当您[创建连接](/help/connections/create-connection.md#dataset-settings)或[编辑连接](/help/connections/create-connection.md)时，您可以将拼合作为事件数据集的[数据集设置](/help/connections/manage-connections.md#edit-a-connection)的一部分来启用。

## 先决条件

您需要检查并满足您指定的拼接方法的先决条件：[基于字段的拼接](fbs.md#prerequisites)或[基于图形的拼接](gbs.md#prerequisites)。


## 印前检查检查

如果您满足前提条件，则可能需要在启用身份拼接之前对事件数据集中的数据执行一些预检检查：

* 如果您要为持久ID或人员ID使用XDM架构字段，请确保在事件数据集的架构中正确标记身份。 [请参阅身份命名空间概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces)。
* 验证持久ID和人员ID的标识覆盖范围：

   * **永久ID**

     查询7天的数据，其中您的永久ID字段不为null，并除以针对数据集中所有事件的7天数据查询。 该百分比应高于95%。

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

      * `{PERSISTENT_ID_FIELD}`是永久ID的字段。 例如：`identityMap.ecid[0]`。
      * `{DATASET_TABLE_NAME}`是事件数据集的表名称。
      * `{FORMAT_STRING}`是时间戳字段的格式字符串。 例如：`MM/DD/YY HH12:MI AM`。
      * `{START_DATE} `是开始日期。 例如：`2024-01-01 00:00:00`。
      * `{END_DATE}`是标准格式的结束日期。 例如：`2024-01-08 00:00:00`。


   * **人员 ID**
      * 对于基于图形的拼接，请确保身份图形包含一些片段，这些片段关联来自您选择的永久ID命名空间和人员ID命名空间的ID值。 您可以通过转到[Experience Platform身份图形查看器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"}运行测试，并通过一些测试持久ID值查询该图形。 验证这些永久ID值是否与图表中的人员ID值相关联。
      * 对于基于字段的拼合，请查询7天的数据，其中人员ID字段不为null，然后除以针对数据集中所有事件的7天数据查询。 理想情况下，该百分比应高于5%。

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



## 启用身份标识拼接 {#enable-identity-stitching}

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="身份标识图的更改"
>abstract="在使用身份标识图进行拼接前，请先确保您已完成身份标识图的设置。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/stitching/gbs" text="基于图形的拼接"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="人员 ID"
>abstract="从可用身份标识中选择一个人员 ID（个人的唯一标识符）。如果您希望使用基于图形的拼接，请选择&#x200B;**[!UICONTROL 身份标识图]**。"

要启用拼接，请在&#x200B;**[!UICONTROL 添加数据集]**&#x200B;或&#x200B;**[!UICONTROL 编辑数据集]**&#x200B;对话框的事件数据集部分中：

启用身份拼接时![身份拼接选项](assets/identity-stitching-ui.png)

1. 选择&#x200B;**[!UICONTROL 启用身份拼接]**。

   如果启用或禁用拼合连接中已保存的事件数据集，**[!UICONTROL 更改人员ID]**&#x200B;对话框将显示人员ID更改的影响。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   **[!UICONTROL 启用身份拼接]**&#x200B;对话框汇总了拼接身份的结果。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

1. 从&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉菜单中选择一个永久ID。

   如果您为永久ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 选择&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。

1. 从&#x200B;**[!UICONTROL 人员ID]**&#x200B;下拉菜单中选择人员ID。

   如果您为人员ID选择&#x200B;**[!UICONTROL 身份映射]**，则必须选择命名空间。 您有两个选项：

   * 选择&#x200B;**[!UICONTROL 使用主身份命名空间]**&#x200B;以使用主身份命名空间。
   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。


   如果您为人员ID选择&#x200B;**[!UICONTROL 身份图形]**（要使用[基于图形的拼接](/help/stitching/gbs.md)），则必须选择命名空间。

   >[!NOTE]
   >
   >确保您有权使用身份图。
   >

   在此之前，将显示&#x200B;**[!UICONTROL 更改为身份图]**&#x200B;对话框，以确保您在使用身份图进行拼合之前，已完成为数据集设置身份图以作为基于[图形的先决条件](/help/stitching/gbs.md#prerequisites)的一部分。 选择&#x200B;**[!UICONTROL 继续]**&#x200B;以继续。

   * 从&#x200B;**[!UICONTROL 命名空间]**&#x200B;下拉菜单中选择一个命名空间。


1. 从&#x200B;**[!UICONTROL 重播窗口]**&#x200B;下拉菜单中选择一个重播窗口。 可用选项取决于您有权访问的Customer Journey Analytics包。

保存连接后，当开始为这些数据集摄取数据时，会触发启用拼合功能的数据集拼合过程。

>[!CAUTION]
>
>对于在Connections界面中启用拼合的数据集，回填状态会立即错误地报告为![状态绿色](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _回填已完成]**（对于已完成的回填数）。 使用其他方法验证是否回填了来自拼接数据集的数据。
>


## 限制

除了[基于字段的拼接限制](/help/stitching/fbs.md#limitations)和[基于图形的拼接限制](/help/stitching/gbs.md#limitations)之外，在Connections界面中启用拼接时，还将应用以下限制：

* 作为单个连接的一部分，您只能拼合一次事件数据集。 您不能多次定义同一事件数据集，也不能对每个实例使用单独的拼接配置。 如果要对同一数据集应用不同的拼接配置，请为每个配置使用单独的连接。


## 迁移

在Connections界面中启用的拼合可以并行存在，而不会在基于请求的拼合方面出现任何问题。

例如，由于较早或当前的拼接请求，您在数据湖中有基于Web的拼接数据集。 您可以使用Connections界面从呼叫中心数据集添加拼合数据，以将该数据与基于Web的数据相结合。

最终，Adobe会将您的基于请求的拼接数据集迁移到连接中的新拼接体验。
