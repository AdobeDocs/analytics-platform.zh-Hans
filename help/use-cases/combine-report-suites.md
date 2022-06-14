---
title: 将具有不同架构的报表包组合在一起
description: 了解如何使用数据准备将具有不同架构的报表包组合在一起
source-git-commit: 02483345326180a72a71e3fc7c60ba64a5f8a9d6
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 3%

---


# 将不同架构的报表包组合在一起

的 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 将来自Adobe Analytics的报表包数据导入Adobe Experience Platform(AEP)，以供AEP应用程序(如Real-time Customer Data Platform和Customer Journey Analytics(CJA))使用。 引入AEP的每个报表包都配置为单个源连接数据流，并且每个数据流都作为数据集登陆AEP数据湖中。 Analytics源连接器为每个报表包创建一个数据集。

CJA客户使用 [连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans) 将来自AEP数据湖的数据集集成到CJA的Analysis Workspace中。 但是，在连接中组合报表包时，需要使用AEP的 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) 功能。 其目的是确保Adobe Analytics变量（如prop和eVar）在CJA中具有一致的含义。

## 报表包之间的架构差异存在问题

假设您的公司要将来自两个不同报表包的数据引入AEP以供CJA使用，并假定两个报表包的架构存在差异：

| 报表包A | 报表包B |
| --- | --- |
| eVar1 =搜索词 | eVar1 =业务单位 |
| eVar2 =客户类别 | eVar2 =搜索词 |

为简单起见，假设这两个报表包都只定义了这些eVar。

此外，假定您执行以下操作：

- 创建用于摄取的Analytics源连接（不使用数据准备） **报表包A** 作为 **数据集A**.
- 创建用于摄取的Analytics源连接（不使用数据准备） **报表包B** 作为 **数据集B**.
- 创建 [CJA连接](/help/connections/create-connection.md) 调用 **所有报表包** 数据集A和数据集B的组合集。
- 创建 [CJA数据视图](/help/data-views/create-dataview.md) 调用 **全局视图** 基于所有报表包连接。

如果不使用数据准备来解决数据集A和数据集B之间的架构差异，则“全局视图”数据视图中的eVar将包含以下混合值：

| CJA中的全局视图数据视图 |
| --- |
| eVar1 =>搜索词和业务单位的组合 |
| eVar2 =>客户类别和搜索词的组合 |

这种情况导致eVar1和eVar2的无意义报告：

- eVar字段包含具有不同语义的值的混合。
- 搜索词在eVar1和eVar2之间分发。
- 无法对每个搜索词、业务单位和客户类别使用不同的归因模型。

## 使用AEP数据准备解决报表包之间的架构差异

Experience Platform数据准备功能与Analytics源连接器集成，可用于解决上述方案中描述的架构差异。 这会导致eVar在CJA数据视图中具有一致的含义。 （可以根据您的需要自定义下面使用的命名约定。）

1. 在为报表包A和报表包B创建源连接数据流之前， [创建自定义字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail.) 在AEP中(我们称之为 **统一字段** 在我们的示例中)，其中包含以下字段：

   | “统一字段”自定义字段组  |
   | --- |
   | 搜索词 |
   | 业务单位 |
   | 客户类别 |

1. [创建新架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) 在AEP中(我们称之为 **统一模式** )。 将以下字段组添加到架构中：

   | “统一架构”的字段组 |
   | --- |
   | XDM体验事件 |
   | Adobe Analytics体验事件模板 |
   | 统一字段 |

   创建的源连接数据流时 **报表包A**，选择 **统一模式** 用于数据流。

1. 按如下方式添加自定义映射：

   | 报表包A源字段 | “统一字段”字段组中的目标字段 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >目标字段的XDM路径将取决于您如何设置自定义字段组。

1. 创建的源连接数据流时 **报表包B**，再次选择 **统一模式** 用于数据流。

   工作流显示两个字段存在描述符名称冲突。 这是因为eVar1和eVar2的描述符在报表包B中与在报表包A中不同。但我们已经知道这一点，因此我们可以安全地忽略冲突并使用如下自定义映射：

   | 报表包B源字段 | “统一字段”字段组中的目标字段 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. 现在，创建 **所有报表包** 连接（数据集A和数据集B的组合）。

1. 创建 **全局视图** 数据视图。

   忽略原始eVar字段，并仅包含统一字段字段字段组中的字段。

   CJA中的全局视图数据视图：

   | 源字段 | 是否包含在数据视图中？ |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;path>_.Search_term | 是 |
   | _\&lt;path>_.Customer_category  | 是 |
   | _\&lt;path>_.Business_unit | 是 |

   您现在已将eVar1和eVar2从源报表包映射到三个新字段。 请注意，使用数据准备映射的另一个优势是，目标字段现在基于语义上有意义的名称（搜索词、业务部门、客户类别），而不是较不有意义的eVar名称(eVar1、eVar2)。

   >[!NOTE]
   >
   >可以随时将统一字段自定义字段组和关联的字段映射添加到现有的Analytics源连接器数据流和数据集。 但是，这仅会影响将来的数据。

## 不仅仅是报表包

数据准备功能可以合并具有不同架构的数据集，这些功能不仅限于Analytics报表包。 假设您有两个包含以下数据的数据集：

| 数据集A =通过Analytics源连接器提供的Analytics报表包 |
| --- |
| `eVar1` =>客户类别 |

| 数据集B =呼叫中心数据 |
| --- |
| Some_field =>客户类别 |

使用数据准备，您可以将AnalyticseVar1中的客户类别与呼叫中心数据中Some_field中的客户类别组合。 你可以这样做。 再次重申，可以根据您的需要更改命名约定。

1. 创建自定义字段组：

   | “客户信息”自定义字段组  |
   | --- |
   | Customer_category |

1. 在AEP中创建架构。 将以下字段组添加到架构中：

   | “扩展架构”的字段组 |
   | --- | 
   | XDM体验事件 |
   | Adobe Analytics体验事件模板 |
   | 客户信息 |

1. 为创建数据流时 **数据集A**，选择 **扩展架构** 作为您的架构。

1. 按如下方式添加自定义映射：

   | 数据集A源字段 | “客户信息”字段组中的目标字段 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. 为创建数据流时 **数据集B**，再次选择 **扩展架构** 作为您的架构。

1. 按如下方式添加自定义映射：

   | 数据集B源字段 | “客户信息”字段组中的目标字段 |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

   创建一个将数据集A和数据集B组合在一起的CJA连接。在CJA中使用您刚刚创建的CJA连接创建一个数据视图。 忽略原始eVar字段，并仅包含“客户信息”字段组中的字段。

   CJA中的数据视图：

   | 源字段 | 是否包含在数据视图中？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;path>_.Customer_category | 是 |

## 数据准备与组件ID

如上所述，数据准备允许您在多个Adobe Analytics报表包中将不同的字段映射到一起。 当您要将多个数据集中的数据合并到单个CJA连接中时，这在CJA中非常有用。 但是，如果您打算将报表包保留在单独的CJA连接中，但希望跨这些连接和数据视图使用一组报表，则更改CJA中的基础组件ID可让报表兼容，即使架构不同也是如此。 请参阅 [组件设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) 以了解更多信息。

更改组件ID是仅限CJA的函数，不会影响Analytics源连接器中发送到实时客户配置文件和RTCDP的数据。

