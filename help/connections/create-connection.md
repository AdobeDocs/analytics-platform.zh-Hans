---
title: 创建连接
description: 介绍如何在客户旅程分析中创建与平台数据集的连接。
translation-type: tm+mt
source-git-commit: 7fdda3a4171400ba018fe31b492737553c575998

---


# 创建连接

通过连接，您可以将数据集集成 [!DNL Adobe Experience Platform] 到 [!UICONTROL Workspace]中。 为了报告数据集， [!DNL Experience Platform] 您首先必须在和中的数据集之间建立连接 [!DNL Experience Platform] 关系 [!UICONTROL Workspace]。

单击 [此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) ，查看视频概述。

>[!IMPORTANT] 您可以将多个数 [!DNL Experience Platform] 据集合并到一个连接中。

1. 请访问 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 单击 **[!UICONTROL Create new connection]** 右上角的。

![创建连接](assets/create-connection.png)

1. 左边栏显示了您可以从中 [!DNL Experience Platform] 提取的所有数据集。 选择一个或多个要拉入的数据集，然后 [!UICONTROL Customer Journey Analytics] 单击 **[!UICONTROL Add]**。 (如果您有大量数据集可供选择，则可以使用数据集列表上方的搜索栏搜索正确的数据集。)

1. 接下来，对于您添加到此连接的每个数据集， [!UICONTROL Customer Journey Analytics] 会根据传入的数据自动设置数据集类型。 有3种不同的数据集类型：数 [!UICONTROL Event] 据、 [!UICONTROL Profile] 数据和数 [!UICONTROL Lookup] 据。

   | 数据集类型 | 描述 | 时间戳 | 架构 | 人员 ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | 表示及时事件的数据(例如，Web访问、交互、交易、POS数据、调查数据、广告印象数据等)。 这是典型的点击流数据，带有客户ID或cookie ID，以及时间戳。 利用事件数据，我们允许您使用您需要的ID。 | 将设置为时间戳。 | 此数 [!DNL Experience Platform] 据集类型所基于的模式。 | 不适用 |
   | [!UICONTROL Lookup] | 与分类文件类似。 此数据用于查找在事件或用户档案数据中找到的值或键。 例如，您可以上传将事件数据中的数字ID映射到产品名称的查找数据。 | 不适用 | 此数 [!DNL Experience Platform] 据集类型所基于的模式。 | 不适用 |
   | [!UICONTROL Profile] | 与- [!UICONTROL Customer Attributes] 类似，适用于非更改属性和非临时属性。 应用于数据中的访客、用户或客户的数 [!UICONTROL Event] 据。 例如，允许您上传有关客户的CRM数据。 | 不适用 | 此数 [!DNL Experience Platform] 据集类型所基于的模式。 | 您可以选择要包含的人物ID。 在中定义的每个数 [!DNL Experience Platform] 据集都有其自己的一组定义的一个或多个人员ID，如Cookie ID、拼合ID、用户ID、跟踪代码等。<br>![人](assets/person-id.png)**员&#x200B;**:如果您创建的连接包含具有不同ID的数据集，报告将反映这一点。 要真正合并数据集，您需要使用相同的Person ID。 |

1. 单击 **[!UICONTROL Next]** 将转到对话 [!UICONTROL Create Connection] 框。

   ![创建连接](assets/create-connection2.png)

1. 在对话 [!UICONTROL Create Connection] 框中，定义以下设置：

   | 字段 | 描述 |
   |---|---|
   | [!UICONTROL Name Connection] | 为连接指定一个描述性名称。 无法保存连接，但没有名称。 |
   | [!UICONTROL Description] | 添加更多详细信息以区分此连接与其他连接。 |
   | [!UICONTROL Datasets] | 此连接中包含的数据集。 |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | 如果要建立持续连接，请选择此选项，以便添加到此连接中的数据集的任何新数据批自动流入 [!UICONTROL Workspace]。 |
   | [!UICONTROL Import all existing data] | 当您选择此选项并保存连接时，将导入此连接中所有数据集的 [!DNL Experience Platform] 所有现有（历史）数据。 将来，添加到此保存的连接的任何新数据集的所有现有历史数据也将自动导入。 <br>**请注意，保存此连接后，便无法更改此设置。** |

   **请记住以下事项：**

   * 如果连接中所有数据集的历史数据的累积大小超过15亿行，则会显示一条错误消息，指示您无法导入此数量的历史数据。 但是，如果您添加一个包含10亿行历史数据的数据集，并导入该数据，一周后，再添加一个大小相同的数据集并导入其历史数据，这将会有效。
   * 我们将添加到连接中的数据集的新数据列为优先级，因此此数据具有最低的延迟。
   * 任何回填（历史）数据都以较慢的速度导入。

1. 单击 **[!UICONTROL Save]**.

工作流的下一步是创 [建数据视图](/help/data-views/create-dataview.md)。
