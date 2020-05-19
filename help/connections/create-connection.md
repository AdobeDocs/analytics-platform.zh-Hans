---
title: 创建连接
description: 描述如何在 Customer Journey Analytics 中创建与 Platform 数据集的连接。
translation-type: tm+mt
source-git-commit: 204eb143d513b9b73fad020efabe6891a1253608
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 68%

---


# 创建连接

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

单击[此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html)，查看视频概述。

>[!IMPORTANT] 您可以将多个 [!DNL Experience Platform] 数据集合并到单个连接中。

1. 访问 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 单击 **[!UICONTROL 右上方的]** “新建连接”。

   ![创建连接](assets/create-connection.png)

1. 在Experience Platform中选择一个沙箱，其中包含要创建连接的数据集。

   Adobe Experience Platform提供将 [单个](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) Platform实例分区为单独的虚拟环境的沙箱，以帮助开发和改进数字体验应用程序。 您可以将沙箱视为包含数据集的“数据孤岛”。 沙箱用于控制对数据集的访问。 您无法跨沙箱访问数据。 选择沙箱后，左边栏会显示该沙箱中可从中提取的所有数据集。

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   （如果您有许多数据集可供选择，可以使用数据集列表上方的搜索栏搜索正确的数据集。）

1. Next, for each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | 数据集类型 | 描述 | 时间戳 | 架构 | 人员 ID |
   |---|---|---|---|---|
   | [!UICONTROL 事件] | 表示及时事件的数据（例如 Web 访问、互动、交易、POS 数据、调查数据、广告展示数据等）。例如，这可能是典型的点击流数据，包含客户 ID 或 Cookie ID 以及时间戳。使用“事件”数据，您可以灵活地选择将哪个 ID 用作人员 ID。 | 自动设置为 [UICONTROL Experience Platform] 中基于事件的架构的默认时间戳字段。 | 任何基于 XDM 类且具有“时间序列”行为的内置或自定义架构。示例包括“XDM 体验事件”或“XDM 决策事件”。 | 您可以选择想要包含的人员 ID。Experience Platform 中定义的每个数据集架构，可以拥有自己定义的一个或多个标识集，并与命名空间关联。其中任何标识都可用作人员 ID。示例包括 Cookie ID、拼接 ID、用户 ID、跟踪代码等。 |
   | [!UICONTROL 查找] | 类似于分类文件。此数据用于查找在“事件”或“个人资料”数据中找到的值或键。例如，您可以上传将事件数据中的数字 ID 映射到产品名称的查找数据。 | 不适用 | 任何基于 XDM 类且具有“记录”行为的内置或自定义架构，“XDM 个人资料”类除外。 | 不适用 |
   | [!UICONTROL 配置文件] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. 例如，允许您上传关于客户的 CRM 数据。 | 不适用 | 任何基于“XDM 个人资料”类的内置或自定义架构。 | 您可以选择想要包含的人员 ID。[!DNL Experience Platform] 中定义的每个数据集，都拥有自己定义的一个或多个人员 ID 集，例如 Cookie ID、拼合 ID、用户 ID、跟踪代码等。<br>![人员 ID](assets/person-id.png)**注意&#x200B;**：如果您创建的连接包含具有不同 ID 的数据集，报告将反映这一点。要真正合并数据集，您需要使用相同的人员 ID。 |

1. 单击 **[!UICONTROL 下一]** 步，转到“创建 [!UICONTROL 连接”对话框] 。

   ![创建连接](assets/create-connection2.png)

1. In the [!UICONTROL Create Connection] dialog, define these settings:

   | 字段 | 描述 |
   |---|---|
   | [!UICONTROL 名称连接] | 为连接指定一个描述性名称。如果没有名称，将无法保存连接。 |
   | [!UICONTROL 描述] | 添加更多详细信息以将此连接与其他连接区分开来。 |
   | [!UICONTROL 数据集] | 此连接中包含的数据集。 |
   | [!UICONTROL 从今天开始自动导入此连接中的所有新数据集。] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL 导入所有现有数据] | 当选择此选项并保存连接时，将会从 [!DNL Experience Platform] 中导入此连接中所有数据集的所有现有（历史）数据。未来，还将自动导入添加到这个已保存连接的任何新数据集的所有现有历史数据。<br>**请注意，保存此连接后，无法更改此设置。** |

   **请记住以下事项：**

   * 如果连接中所有数据集的历史数据的累计大小超过 15 亿行，则会出现一条错误消息，指示您无法导入此数量的历史数据。但是，如果您要添加一个包含 10 亿行历史数据的数据集并导入该数据，一周后，再添加另一个同等大小的数据集并导入其历史数据，则导入可正常进行。
   * 我们会优先处理新添加到此连接中数据集的新数据，因此这些新数据的滞后时间最短。
   * 任何回填（历史）数据的导入速度都会比较慢。

1. 单击&#x200B;**[!UICONTROL 保存]**。

工作流程的下一步是[创建数据视图](/help/data-views/create-dataview.md)。
