---
title: 配置受众分析
description: 了解如何配置受众分析
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 7926f043c9e2808a083f8947fa0882c0faa4051d
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 12%

---

# 配置受众分析 {#configure-audience-analysis}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-merge-policy"
>title="合并策略"
>abstract="合并策略将来自多个数据集的配置文件数据合并到统一的客户配置文件中，用于创建受众。 如果您看到多个合并策略并且不确定选择哪个，请选择“默认基于时间”。 或者，咨询您的数据团队，了解哪些受众与每个合并策略相关联。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-analysis-sandbox"
>title="沙盒"
>abstract="选择包含正确Experience Platform配置文件数据集的沙盒。 这些数据集需要包含您要在Analysis Workspace中报告的受众数据。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-person-id"
>title="人员 ID"
>abstract="从架构中选择一个表示人员ID的字段。 选择仅限于架构中标记为身份并具有身份命名空间的字段列表。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-audience-namespace"
>title="使用主要身份标识命名空间"
>abstract="如果您希望Customer Journey Analytics在标记为“primary=true”属性的身份映射中找到身份，然后将该身份用作该行的人员ID，请启用此选项。 该身份标识是 Experience Platform 中用于分区时使用的主密钥。<br/>如果保持禁用此选项，请从下面的“身份命名空间”字段中选择一个命名空间。 Customer Journey Analytics会在每行的“身份映射”中搜索此命名空间密钥，并将该命名空间下的身份用作该行的人员ID。"

<!-- markdownlint-enable MD034 -->

利用Audience Analysis，可将受众成员资格数据从Experience Platform配置文件数据集摄取到Customer Journey Analytics连接。 受众将可用作新维度，以便在Analysis Workspace中使用。 有关受众分析的更多详细概述信息，请参阅[受众分析概述](/help/connections/audience-analysis/audience-analysis-overview.md)。

>[!IMPORTANT]
>
>每晚重新处理和生成受众数据，使受众数据仅可用于前一天（“昨天”）的分析。
>
>受众在创建受众分析配置的当天即出现在Customer Journey Analytics数据视图中。

## 创建受众分析配置

创建受众分析配置时，您可以选择与要分析的Experience Platform受众关联的沙盒和合并策略。 Customer Journey Analytics会创建新的查找数据集，然后自动将查找数据集和配置文件数据集添加到您选择的连接。

只有系统管理员可以创建受众分析配置。

要创建受众分析配置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 受众分析配置]**。

   ![受众分析主页](assets/audience-analysis-empty.png)

1. 选择&#x200B;**[!UICONTROL 创建配置]**。

   ![创建受众分析配置](assets/audience-analysis-create.png)

1. 在&#x200B;**[!UICONTROL 详细信息]**&#x200B;部分中，指定以下信息：

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 名称]** | 指定配置的名称。 |
   | **[!UICONTROL 沙盒]** | 选择包含要添加到连接的配置文件数据集的Experience Platform沙盒。 单个沙盒最多可支持100个受众分析配置。 <p>Adobe Experience Platform 提供了可将单个 Platform 实例划分为多个单独的虚拟环境的[沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)，以帮助开发和改进数字体验应用程序。您可以将沙盒视为包含数据集的“数据孤岛”。沙盒可用于控制对数据集的访问。</p> |

1. 在&#x200B;**[!UICONTROL 用户档案数据集]**&#x200B;部分中，指定以下信息：

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 合并策略]** | 选择与您想用于受众分析的轮廓数据集所对应的合并策略。 <p>合并策略可确定Adobe Experience Platform如何将来自多个数据集的配置文件数据合并到用于创建受众的统一客户配置文件中。 您选择的合并策略会影响受众中包含哪些配置文件属性。 每天都会在Experience Platform中生成此数据的快照。 此快照提供特定时间点数据的静态视图，不包含任何事件数据。</p><p>如果您看到多个合并策略并且不确定选择哪一个，请选择&#x200B;**[!UICONTROL 默认基于时间]**&#x200B;的合并策略。 您还可以咨询数据团队，以更好地了解哪些受众与每个合并策略关联。</p> |
   | **[!UICONTROL 配置文件数据集]** | 与所选合并策略关联的配置文件数据集。 此配置文件数据集包含要分析的Experience Platform受众数据。 此用户档案数据集将添加到您选择的连接。<p>选择合并策略后，将显示配置文件快照导出。 例如：`Profile-Snapshot-Export-abbc7093-80f4-4b49-b96e-e743397d763f`。</p><p>有关详细信息，请参阅《Experience Platform功能板指南》中的[配置文件属性数据集](https://experienceleague.adobe.com/en/docs/experience-platform/dashboards/query#profile-attribute-datasets)。</p> |

1. 在&#x200B;**[!UICONTROL 连接]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 选择连接]**。

1. 在“连接”对话框中，选中要添加配置文件数据集的连接旁边的复选框，然后选择&#x200B;**[!UICONTROL 使用连接]**。

   一个连接只能与一个受众分析配置相关联。

1. 指定以下信息以配置连接：

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 人员 ID]** | 从架构中选择一个表示人员ID的字段。<p>选择仅限于架构中标记为身份并具有身份命名空间的字段列表。 默认情况下已选中&#x200B;**[!UICONTROL IdentityMap]**，适用于大多数配置。 </p><p>如果没有可供选择的人员ID，则意味着未在架构中定义一个或多个人员ID。 请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。</p> |
   | **[!UICONTROL 使用主标识命名空间]** | 此选项显示您是否为人员ID选择&#x200B;**[!UICONTROL 身份映射]**。 <p>如果您希望Customer Journey Analytics在标记为“primary=true”属性的身份映射中找到身份，然后将该身份用作该行的人员ID，请启用此选项。 该身份标识是 Experience Platform 中用于分区时使用的主密钥。此外，此身份也是用作Customer Journey Analytics人员ID的主要候选项(取决于Customer Journey Analytics连接中数据集的配置方式)。</p> |
   | **[!UICONTROL 身份命名空间]** | 此选项显示您是否为人员ID选择&#x200B;**[!UICONTROL 身份映射]**。 如果您使用主ID命名空间，则会禁用此选项。 <p>身份标识命名空间是 [Experience Platform 身份标识服务的](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces)一个组件。命名空间充当与身份标识相关的上下文的指示器。如果指定命名空间，Customer Journey Analytics会搜索此命名空间键的每行的“身份映射”，并将该命名空间下的身份用作该行的人员ID。 由于Customer Journey Analytics无法对所有行执行完整数据集扫描以确定哪些命名空间存在，因此下拉菜单中会显示所有可能的命名空间。 您必须知道数据中指定了哪些命名空间；系统不会自动检测这些命名空间。</p> |
   | **[!UICONTROL 帐户ID]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | （仅针对基于帐户的连接显示）用于支持数据集的基于帐户的报表的帐户ID。 |

1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 选择数据视图]**。

1. 在数据视图对话框中，选中一个或多个数据视图旁边的复选框，您要在Analysis Workspace中分析Experience Platform受众数据时使用这些数据视图。 这些数据视图自动配置了Experience Platform受众数据以用于报表。

1. 选择&#x200B;**[!UICONTROL 使用数据视图]**。

1. 选择&#x200B;**[!UICONTROL 创建]**&#x200B;以创建配置。

   >[!IMPORTANT]
   >
   >由于配置文件数据集每天更新一次，因此可在创建受众分析配置后一天的Customer Journey Analytics数据视图中访问受众。


1. 24小时后，[在数据视图](#view-audience-dimensions-in-the-data-view)中查看受众维度，以验证受众维度在您选择的数据视图中是否可用。

## 在数据视图中查看受众维度

在您[创建受众分析配置](#create-an-audience-analysis-configuration)后，您可以验证是否已将受众维度添加到您在配置期间选择的数据视图中。

要在数据视图中查看受众维度，您必须是数据视图所分配到的产品配置文件的产品配置文件管理员。 有关详细信息，请参阅[访问控制](/help/technotes/access-control.md)。

在数据视图中查看受众分析维度：

1. 在 Customer Journey Analytics 中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。

1. 在&#x200B;**[!UICONTROL 维度]**&#x200B;部分中，以下维度现在应可用：

   * **[!UICONTROL 受众名称]**

   * **[!UICONTROL 受众来源]**

   * **[!UICONTROL 已退出受众来源]**

   * **[!UICONTROL 已退出受众名称]**

   请注意，其中每个维度都添加到与您在受众分析配置期间选择的合并策略关联的用户档案数据集，并且每个维度都添加到创建的新查找数据集。

   ![数据视图中可用的受众维度](assets/audience-analysis-dataview-dataset.png)

1. 在Analysis Workspace中使用受众分析维度。

   有权使用Analysis Workspace中的数据视图的用户现在可以查看新维度，并在其分析中使用它们。 有关如何在Analysis Workspace中使用受众分析维度的信息，请参阅[在Customer Journey Analytics中分析Experience Platform受众](/help/connections/audience-analysis/analyze-audiences.md)。


