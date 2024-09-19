---
title: 将帐户数据作为查询数据集进行添加
description: 了解如何将帐户数据作为查询数据集添加到Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# 将帐户数据作为查询数据集进行添加

此B2B用例将向您展示如何将帐户数据添加到人员级别和事件级别分析。 添加帐户数据时，您可以回答类似下面的问题：

* 与该帐户匹配的公司名是什么？
* 该帐户中包含哪些角色？
* 某些特定角色（如 IT 经理）在两个不同帐户中的行为是否存在差异？

要添加帐户数据信息，请添加并使用包含此信息的[查找](/help/technotes/glossary.md)数据集。

涉及的步骤包括：

1. [在Experience Platform中创建查询架构](#create-lookup-schema)。
1. [在Experience Platform中创建查询数据集](#create-lookup-dataset)，以便您摄取基于CSV的帐户数据。
1. 在Customer Journey Analytics中[合并连接](#combine-datasets-in-a-connection)中的数据集，包括您创建的查询数据集。
1. [在Customer Journey Analytics中创建数据视图](#create-a-data-view-from-this-connection)。
1. [在Workspace中Customer Journey Analytics此数据](#analyze-the-data-in-workspace)。

>[!NOTE]
>
>查询表的大小可高达 1 GB。
>

## 创建查找架构

当您为[lookup](/help/technotes/glossary.md)表创建自己的架构时，该架构可确保使用的数据集以正确设置（记录类型）的Customer Journey Analytics可用。 最佳做法是[创建一个自定义架构类](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)，该架构类可重复用于所有查询表。

![创建新类对话框。](../assets/create-new-class.png)

## 创建查询数据集

创建架构后，您需要在Experience Platform中根据该架构创建一个查找数据集。 此查询数据集包含帐户信息。 例如：公司名称、员工总数、域名、公司所属的行业、年收入等。 确保数据包含可与事件数据中使用的人员标识符匹配的人员标识符。

1. 在Experience Platform中，转到&#x200B;**[!UICONTROL 数据管理>数据集]**。
1. 单击 **[!UICONTROL + 创建数据集]**。
1. 单击&#x200B;**[!UICONTROL 使用模式创建数据集]**。
1. 选择您创建的Lookup Schema类。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 命名数据集（例如，`B2B Info`）并提供描述。
1. 单击&#x200B;**[!UICONTROL 完成]**。

## 引入数据

如果您使用的是 CSV 文件，那么关于如何[将 CSV 文件映射到 XDM 模式](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)的说明应该对您会有帮助。

另外，还可以使用[其他方法](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)。

载入数据并建立查询大约需要 2-4 小时，具体取决于查询表的大小。

## 在连接中组合数据集

在本例中，您将3个数据集合并到一个Customer Journey Analytics连接中：

| 数据集名称 | 描述 | Adobe Experience Platform架构类 | 数据集详细信息 |
| --- | --- | --- | --- |
| B2B Impression | 包含帐户级别的点击流（事件级）数据。例如，包含用于运行营销广告的电子邮件 ID 和相应的帐户 ID 以及营销活动名称。此外，还包含每个用户对这些广告的展示次数。 | 基于XDM ExperienceEvent架构类 | `emailID` 用作主标识，并分配到一个 `Customer ID` 命名空间。因此，它在Customer Journey Analytics中显示为默认&#x200B;**[!UICONTROL 人员ID]**。 ![展示次数](../assets/impressions-mixins.png) |
| B2B Profile | 此用户档案数据集可告知有关帐户中用户的更多信息，例如其职务、其所属帐户、其 LinkedIn 个人档案等。 | 基于“XDM 个人用户档案”模式类 | 选择`emailID`作为此架构中的主ID。 |
| B2B Info | 请参阅上面的“创建查询数据集”。 | B2B帐户（自定义查找架构类） | 在将B2B Info数据集与Customer Journey Analytics中的B2B Impression数据集连接时，`accountID`和B2B Impressions数据集之间的关系会自动创建，如以下步骤所述。 ![查询](../assets/lookup-mixins.png) |

要合并数据集，请按以下步骤操作：

1. 在 Customer Journey Analytics 中，选择&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。
1. 选择要合并的数据集。
1. 对于B2B Info数据集，请选择在查询表中使用的键（例如`personKey.sourceKey`）。 然后，选择与其匹配的键（对应的维度），以及事件数据集中的键（例如p`ersonKey.sourceKey`）。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 命名并描述此连接，并根据[这些说明](/help/connections/create-connection.md)配置此连接。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 从此连接创建数据视图

按照[创建数据视图](/help/data-views/create-dataview.md)中的说明操作。

* 从数据集添加您需要的所有组件（维度和量度）。 确保对于需要重复数据删除才能进行过度计数的指标，请相应地配置这些指标（请参阅[指标重复数据删除组件设置](/help/data-views/component-settings/metric-deduplication.md)）。 此类量度的示例包括员工人数或收入。

## 在Workspace中分析数据

您现在可以根据所有这 3 个数据集中的数据来创建工作区项目。

例如，您可以找到介绍部分中列出的问题的答案：

* 按 accountID 对 emailID 进行细分，可确定某个电子邮件 ID 属于哪个公司。
* 可确定有多少员工被映射到某个特定的帐户 ID。
* 还可以确定某个帐户 ID 属于哪个行业。

>[!MORELIKETHIS]
>
>有关详细信息，请参阅[示例B2B项目](example.md)。

