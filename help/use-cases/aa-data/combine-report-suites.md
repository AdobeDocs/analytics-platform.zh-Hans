---
title: 将报告包与不同的架构相结合
description: 了解如何使用数据准备将报告包与不同的架构结合起来
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 64%

---

# 将报告包与不同的架构相结合

此 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans) 将报表包数据从Adobe Analytics引入Adobe Experience Platform，以供Adobe Experience Platform应用程序(如Real-time Customer Data Platform和Customer Journey Analytics(Customer Journey Analytics))使用。 引入Adobe Experience Platform的每个报表包都会配置为单独的源连接数据流，而每个数据流都会作为Adobe Experience Platform数据湖中的数据集。  Analytics Source Connector 会为每个报告包创建一个数据集。

客户使用的Customer Journey Analytics [连接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans) 将Adobe Experience Platform数据湖中的数据集集成到Customer Journey AnalyticsAnalysis Workspace中。 但是，在连接内组合报告包时，需要使用Adobe Experience Platform解决报告包之间的架构差异 [数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) 功能。 其目的是确保Adobe Analytics变量（如prop和eVar）在Customer Journey Analytics中具有一致的含义。

## 报告包之间的架构差异存在问题

假设您的公司希望将来自两个不同报表包的数据引入Adobe Experience Platform以供Customer Journey Analytics使用，并假设两个报表包的架构有所不同：

| 报告包 A | 报告包 B |
| --- | --- |
| eVar1 = 搜索项 | eVar1 = 商业单位 |
| eVar2 = 客户类别 | eVar2 = 搜索项 |

为了简单起见，假设这是两个报告包中定义的唯一 eVar。

此外，假设您执行以下操作：

- 创建用于引入的Analytics源连接（不使用数据准备） **报告包A** 到Adobe Experience Platform数据湖中作为 **数据集a**.
- 创建用于引入的Analytics源连接（不使用数据准备） **报告包B** 到Adobe Experience Platform数据湖中作为 **数据集B**.
- 创建 [Customer Journey Analytics连接](/help/connections/create-connection.md) 已调用 **所有报表包** 那个合并了数据集A和数据集B。
- 创建 [Customer Journey Analytics数据视图](/help/data-views/create-dataview.md) 已调用 **全局视图** 该连接基于所有报表包连接。

如果不使用数据准备来解决数据集 A 和数据集 B 之间的架构差异，全局视图数据视图中的 eVar 将包含以下混合值：

| Customer Journey Analytics中的全局视图数据视图 |
| --- |
| eVar1=> 搜索项和业务单元的组合 |
| eVar2=> 客户类别和搜索项的组合 |

这种情况导致 eVar1 和 eVar2 的报告毫无意义：

- eVar 字段包含具有不同语义的混合值。
- 搜索项分布在 eVar1 和 eVar2 之间。
- 不可能对每个搜索项、业务单位和客户类别使用不同的属性模型。

## 使用Adobe Experience Platform数据准备解决报表包之间的架构差异

Experience Platform 数据准备功能与 Analytics Source Connector 集成，可用于解决上述场景中描述的架构差异。这会导致eVar在Customer Journey Analytics数据视图中具有一致的含义。 （以下使用的命名惯例可以通过自定义来满足您的需要。）

1. 在为报告包A和报告包B创建源连接数据流之前， [创建新架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans) 在Adobe Experience Platform中(我们将其称为 **统一架构** 在我们的示例中。) 将以下内容添加到该架构中：

   | “统一架构” |
   | --- |
   | **XDM ExperienceEvent**&#x200B;类别 |
   | **Adobe Analytics ExperienceEvent 模板**&#x200B;字段组 |

1. 将另一个字段组添加到该架构或[创建自定义字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=zh-Hans#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail)，并将其添加该架构。我们会创建一个新的字段组，并将其称为&#x200B;**统一字段**。然后，我们将向新字段组中添加以下字段：：

   | “统一字段”自定义字段组 |
   | --- |
   | 搜索项 |
   | 商业单位 |
   | 客户类别 |

1. 为&#x200B;**报告包 A**&#x200B;创建源连接数据流，选择&#x200B;**统一架构**，以在数据流中使用。将自定义映射添加到数据流，如下所示：

   | 报告包 A 源字段 | 统一字段字段组中的目标字段 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.搜索项 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.客户类别 |

   >[!NOTE]
   >
   >目标字段的 XDM 路径将取决于自定义字段组的结构。

1. 为&#x200B;**报告包 B**&#x200B;创建源连接数据流，同样选择&#x200B;**统一架构**，以在数据流中使用。工作流将显示两个字段存在描述符名称冲突。这是因为 eVar1 和 eVar2 的描述符在报告包 B 中与在报告包 A 中不同。但我们已经知道这一点，因此可以安全地忽略该冲突，并按如下方式使用自定义映射：

   | 报告包 B 源字段 | 统一字段字段组中的目标字段 |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.商业单位 |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.搜索项 |

1. 现在创建 **所有报表包** Customer Journey Analytics的连接，组合数据集A和数据集B。

1. 创建 **全局视图** Customer Journey Analytics中的数据视图。 忽略原始 eVar 字段，仅包括统一字段字段组中的字段。

   **全局视图** Customer Journey Analytics中的数据视图：

   | 源字段 | 是否包含在数据视图中？ |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;path>_.搜索项 | 是 |
   | _\&lt;path>_.客户类别 | 是 |
   | _\&lt;path>_.商业单位 | 是 |

现在，您已经将源报告包中的 eVar1 和 eVar2 映射到三个新字段。请注意，使用数据准备映射的另一个优点是，目标字段现在基于语义上有意义的名称（如搜索项、商业单元、客户类别），而不是意义较低的 eVar 名称（如 eVar1、eVar2）

>[!NOTE]
>
>统一字段自定义字段组和相关的字段映射可以随时添加到现有的 Analytics Source Connector 数据流和数据集。但是，这仅会影响未来数据。

## 不仅仅是报告包

数据准备工具将数据集与不同架构相结合的能力超越了 Analytics 报告包所具备的能力。假设您有两个包含以下数据的数据集：

| 数据集 A = 使用 Analytics Source Connector 的 Analytics 报告包。 |
| --- |
| `eVar1` => 客户类别 |

| 数据集 B = 呼叫中心数据 |
| --- |
| Some_field => 客户类别 |

通过使用数据准备工具，您可以将分析数据中 eVar 1 内的客户类别与呼叫中心数据中 Some_field 内的客户类别相结合。这里是实现这一点的一种方法。同样，可以更改命名惯例来满足您的需要。

1. 在Adobe Experience Platform中创建架构。 将以下内容添加到该架构中：

   | “扩展架构” |
   | --- | 
   | **XDM 体验活动**&#x200B;类别 |
   | **Adobe Analytics 体验活动模板**&#x200B;字段组 |

1. 创建新字段组并将其添加到该架构中。 将字段添加到字段组：

   | “客户信息”自定义字段组 |
   | --- |
   | 客户类别 |

1. 为&#x200B;**数据集 A**&#x200B;创建数据流，选择&#x200B;**扩展架构**&#x200B;作为架构。将自定义映射添加到数据流，如下所示：

   | 数据集 A 源字段 | 客户信息字段组中的目标字段 |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.客户类别 |

1. 为&#x200B;**数据集 B**&#x200B;创建数据流，再次选择&#x200B;**扩展架构**&#x200B;作为架构。将自定义映射添加到数据流，如下所示：

   | 数据集 B 源字段 | 客户信息字段组中的目标字段 |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.客户类别 |

1. 创建一个Customer Journey Analytics连接，该连接结合了数据集A和数据集B。

1. 使用刚刚创建的Customer Journey Analytics连接，在Customer Journey Analytics中创建数据视图。 忽略原始 eVar 字段，仅包括客户信息字段组中的字段。

   Customer Journey Analytics中的数据视图：

   | 源字段 | 是否包含在数据视图中？ |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | 否 |
   | \_experience.analytics.customDimensions.eVars.eVar2 | 否 |
   | _\&lt;path>_.客户类别 | 是 |

## 数据准备与组件 ID

如上所述，数据准备工具允许您跨多个 Adobe Analytics 报告包将不同字段映射到一起。当您要将多个数据集的数据合并到单个Customer Journey Analytics连接中时，这在Customer Journey Analytics中很有用。 但是，如果您打算将报表包保留在单独的Customer Journey Analytics连接中，但希望在这些连接和数据视图中使用一组报表，则更改Customer Journey Analytics中的基础组件ID可以在即使架构不同的情况下使报表兼容。 有关更多信息，请参阅 [组件设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=zh-Hans)。

更改组件ID是一项仅限Customer Journey Analytics的功能，不会影响从Analytics Source Connector发送到Real-time Customer Profile和RTCDP的数据。
