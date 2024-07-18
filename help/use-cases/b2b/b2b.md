---
title: 将帐户级别的数据作为查询数据集进行添加
description: 了解如何将基于帐户的数据作为查询数据集添加到Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: b4c77c3ef4d57aac6e914a2373b6a9169f4872df
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 73%

---

# 将帐户级别的数据作为查询数据集进行添加

此 B2B 用例将向您展示如何指定帐户级别（而非个人级别）的数据来进行分析。帐户级别的数据分析可以回答以下问题：

* 与该帐户匹配的公司名是什么？
* 与该帐户/公司相关联的员工有多少？
* 该帐户中包含哪些角色？
* 与其他帐户相比，该帐户在特定营销活动中的整体表现如何？
* 某些特定角色（如 IT 经理）在两个不同帐户中的行为是否存在差异？

所有这些都可通过将帐户级别信息作为[查询](/help/technotes/glossary.md)数据集引入来实现。

首先，在Adobe Experience Platform中创建一个查询架构，然后通过引入基于.csv的帐户级别数据来创建查询表数据集。 接下来，继续创建一个Customer Journey Analytics(Customer Journey Analytics)连接，该连接可合并各种数据集，包括您创建的查询数据集。 您随后创建一个数据视图，最后能够在 Workspace 中利用所有这些数据。

>[!NOTE]
>
>查询表的大小可高达 1 GB。

## 1. 创建查询模式 (Experience Platform)

为[lookup](/help/technotes/glossary.md)表创建自己的架构，以确保使用的数据集能够以正确设置（记录类型）的Customer Journey Analytics提供。 最佳实践是[创建一个名为查找的自定义模式类](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans#create-new-class)，该类中没有任何元素，可以重新用于所有查找表。

![创建新类对话框。](../assets/create-new-class.png)

## 2.创建查询数据集(Experience Platform)

创建模式后，需使用该模式在 Experience Platform 中创建一个查询数据集。此查询数据集包含帐户级别的营销信息，例如：公司名称、员工总数、域名、公司所属行业、年收入、是否为Experience Platform的当前客户、所处销售阶段、帐户中的哪个团队在使用Customer Journey Analytics等。

1. 在 Adobe Experience Platform 中，转到&#x200B;**[!UICONTROL 数据管理 > 数据集]**。
1. 单击 **[!UICONTROL + 创建数据集]**。
1. 单击&#x200B;**[!UICONTROL 使用模式创建数据集]**。
1. 选择您已创建的 Lookup 模式类。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 命名数据集（在我们的示例中，命名为“B2B Info”）并提供描述。
1. 单击&#x200B;**[!UICONTROL 完成]**。

## 3. 将数据引入 Experience Platform

如果您使用的是 CSV 文件，那么关于如何[将 CSV 文件映射到 XDM 模式](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=zh-Hans)的说明应该对您会有帮助。

另外，还可以使用[其他方法](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hans)。

载入数据并建立查询大约需要 2-4 小时，具体取决于查询表的大小。

## 4. 将多个数据集合并到一个连接 (Customer Journey Analytics)

在本例中，我们要将3个数据集合并到一个Customer Journey Analytics连接中：

| 数据集名称 | 描述 | Adobe Experience Platform架构类 | 数据集详细信息 |
| --- | --- | --- | --- |
| B2B Impression | 包含帐户级别的点击流（事件级）数据。例如，包含用于运行营销广告的电子邮件 ID 和相应的帐户 ID 以及营销活动名称。此外，还包含这些广告对每个用户的展示次数。 | 基于 XDM ExperienceEvent 模式类 | `emailID` 用作主标识，并分配到一个 `Customer ID` 命名空间。因此，它将在 Customer Journey Analytics 中显示为默认的&#x200B;**[!UICONTROL 人员 ID]**。![展示次数](../assets/impressions-mixins.png) |
| B2B Profile | 此用户档案数据集可告知有关帐户中用户的更多信息，例如其职务、其所属帐户、其 LinkedIn 个人档案等。 | 基于“XDM 个人用户档案”模式类 | 选择`emailID`作为此架构中的主ID。 |
| B2B Info | 请参阅上面的“创建查询数据集”。 | B2BAccount（自定义查询模式类） | 通过将B2B Info数据集与Customer Journey Analytics中的B2B Impression数据集连接，`accountID`和B2B Impressions数据集之间的关系已自动创建，如以下步骤所述。 ![查询](../assets/lookup-mixins.png) |

要合并数据集，请按以下步骤操作：

1. 在 Customer Journey Analytics 中，选择&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。
1. 选择要合并的数据集（在我们的示例中，我们要合并以上三个数据集）。
1. 对于“B2B Info”数据集，请选择将在查询表中使用的 `accountID` 键值。然后，选择与其匹配的键值（对应的维度）,即事件数据集中的 `accountID`。
1. 单击&#x200B;**[!UICONTROL 下一步]**。
1. 命名并描述此连接，并根据[这些说明](/help/connections/create-connection.md)配置此连接。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 5. 从此连接创建一个数据视图

按照有关[创建数据视图](/help/data-views/create-dataview.md)的说明进行操作。

* 从数据集添加您所需要的所有组件（维度和量度）。

## 6. 在工作区中分析数据

您现在可以根据所有这 3 个数据集中的数据来创建工作区项目。

例如，您可以找到介绍部分中列出的问题的答案：

* 按 accountID 对 emailID 进行细分，可确定某个电子邮件 ID 属于哪个公司。
* 可确定有多少员工被映射到某个特定的帐户 ID。
* 还可以确定某个帐户 ID 属于哪个行业。

![project-lookup2](assets/analyze.png)
