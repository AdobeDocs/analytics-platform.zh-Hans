---
title: 创建连接
description: 介绍如何在客户旅程分析中创建与平台数据集的连接。
translation-type: tm+mt
source-git-commit: 4b672b0decfecc5a3c607ad966ebb2ecbf178a96
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 4%

---


# 创建连接

通过连接，您可以将数据集从 [!DNL Adobe Experience Platform] Workspace [!UICONTROL 集成]。 要报告数据集 [!DNL Experience Platform] ，您首先必须在Workspace中的数据集之间建立 [!DNL Experience Platform] 连 [!UICONTROL 接]。

单击 [此处](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) ，查看视频概述。

>[!IMPORTANT] 您可以将多个数 [!DNL Experience Platform] 据集合并到一个连接中。

1. 请访问 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 单击 **[!UICONTROL 右上方的]** “新建连接”。

   ![创建连接](assets/create-connection.png)

1. 首先，在 **[!UICONTROL 选择数据集]**&#x200B;下，选择 [!UICONTROL Experience] Platform中的沙箱，该沙箱包含要创建连接的数据集。
Adobe Experience Platform提供将 [单个](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) Platform实例分区为单独虚拟环境的沙箱。 您可以将沙 [!UICONTROL 箱视为] “数据孤岛”，其中包含数据集并用于控制对数据集的访问。 请注意，您无法跨沙箱访 [!UICONTROL 问数据]。

1. 选择沙箱后，左边栏会显示该沙箱中可从中提取的所有数据集。 选择一个或多个要纳入Customer Journey Analytics的数 [!UICONTROL 据集] ，然后单击 **[!UICONTROL 添加]**。 (如果您有许多数据集可供选择，则可以使用数据集列表上方的搜索栏搜索正确的数据集。)

1. 接下来，对于您添加到此连接的每个数据集， [!UICONTROL Customer Journey Analytics] （客户旅程分析）会根据传入的数据自动设置数据集类型。 有3种不同的数据集类型： [!UICONTROL 事件] 数据 [!UICONTROL 、用户档案] 数据和 [!UICONTROL 查找数据] 。

   | 数据集类型 | 描述 | 时间戳 | 架构 | 人员 ID |
   |---|---|---|---|---|
   | [!UICONTROL 事件] | 表示及时事件的数据(例如Web访问、交互、交易、POS数据、调查数据、广告印象数据等)。 例如，这可能是典型的点击流数据，其中有客户ID或cookie ID以及时间戳。 对于事件数据，您可以灵活地使用哪个ID作为人员ID。 | 在UICONTROL Experience Platform中，自动从基于事件的模式设置为默认 [时间戳字段]。 | 任何基于具有“时间序列”行为的XDM类的内置或自定义模式。 示例包括“XDM体验事件”或“XDM决策事件”。 | 您可以选择要包括的人物ID。 在Experience Platform中定义的每个数据集模式可以有其自己的一组定义的一个或多个标识，并与一个标识命名空间关联。 任何这些ID都可用作人员ID。 示例包括Cookie ID、拼接ID、用户ID、跟踪代码等。 |
   | [!UICONTROL 查找] | 与分类文件类似。 此数据用于查找在事件或用户档案数据中找到的值或键。 例如，您可以上传将事件数据中的数字ID映射到产品名称的查找数据。 | 不适用 | 除“XDM个人模式”类外，任何基于具有“记录”行为的XDM类的内置用户档案或自定义数据。 | 不适用 |
   | [!UICONTROL 配置文件] | 与“客 [!UICONTROL 户属性] ”类似——适用于非更改属性和非临时属性。 应用于访客、用户或事件数据中的  。 例如，允许您上传有关客户的CRM数据。 | 不适用 | 任何基于“XDM个人模式”类的内置或自定义用户档案。 | 您可以选择要包括的人物ID。 在中定义的每个数 [!DNL Experience Platform] 据集都有其自己的一组一个或多个人员ID，如Cookie ID、拼合ID、用户ID、跟踪代码等。<br>![人](assets/person-id.png)**员&#x200B;**: 如果您创建的连接包含具有不同ID的数据集，报告将反映这一点。 要真正合并数据集，您需要使用相同的Person ID。 |

1. 单击 **[!UICONTROL 下一]** 步将转到创建 [!UICONTROL 连接对话框] 。

   ![创建连接](assets/create-connection2.png)

1. 在“创 [!UICONTROL 建连接] ”对话框中，定义以下设置：

   | 字段 | 描述 |
   |---|---|
   | [!UICONTROL 名称连接] | 为连接指定一个描述性名称。 无法保存不带名称的连接。 |
   | [!UICONTROL 描述] | 添加更多详细信息以区分此连接与其他连接。 |
   | [!UICONTROL 数据集] | 此连接中包含的数据集。 |
   | [!UICONTROL 从今天开始自动导入此连接中的所有新数据集。] | 如果要建立持续连接，请选择此选项，以便添加到此连接中数据集的任何新数据批自动流入Workspace [!UICONTROL 中]。 |
   | [!UICONTROL 导入所有现有数据] | 当您选择此选项并保存连接时，将导入此连接中所有数据集 [!DNL Experience Platform] 的所有现有（历史）数据。 将来，添加到此已保存连接的任何新数据集的所有现有历史数据也将自动导入。 <br>**请注意，保存此连接后，便无法更改此设置。** |

   **请记住以下事项：**

   * 如果连接中所有数据集的历史数据的累计大小超过15亿行，则会出现一条错误消息，指示您无法导入此数量的历史数据。 但是，如果您添加一个包含10亿行历史数据的数据集并导入该数据，一周后，再添加一个大小相同的数据集并导入其历史数据，这会奏效。
   * 我们将新数据添加到连接中的数据集中，因此此数据具有最低的延迟。
   * 任何回填（历史）数据都以较慢的速度导入。

1. 单击&#x200B;**[!UICONTROL 保存]**。

工作流的下一步是创 [建数据视图](/help/data-views/create-dataview.md)。
