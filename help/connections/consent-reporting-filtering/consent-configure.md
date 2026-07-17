---
title: 配置同意报告和筛选
description: 了解如何使用配置向导为Customer Journey Analytics中的连接启用同意报表和可选的摄取时间过滤。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 728
ht-degree: 2%

---

# 配置同意报告和筛选

系统管理员可以为一个或多个连接启用同意报告和（可选）同意过滤。 有关概述信息，请参阅[同意报告和筛选概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

>[!IMPORTANT]
>
>同意筛选在摄取时不包括非同意访客数据。 通过筛选排除的数据不会存储在Customer Journey Analytics中，并且无法针对过去日期恢复。 在启用筛选之前，请仔细查看营销活动选择。

## 创建配置

在创建同意报告和筛选配置时，请选择包含同意策略成员资格数据的沙盒和配置文件数据集，选择要配置的连接或连接，并选择是否筛选每个营销操作的数据。 然后，Customer Journey Analytics会自动创建同意策略查找数据集和同意策略组件。

要创建同意报告和筛选配置，请执行以下操作：

1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 同意报告和筛选]**。

1. 选择&#x200B;**[!UICONTROL 创建配置]**。

1. 在&#x200B;**[!UICONTROL 详细信息]**&#x200B;部分中，指定以下信息：

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 名称]** | 指定配置的名称。 |
   | **[!UICONTROL 沙盒]** | 选择包含带有同意策略成员资格数据的配置文件数据集的Experience Platform沙盒。 <p>每个沙盒最多存在一个同意策略查找数据集。 同一沙盒中的多个配置共享相同的查找数据集。</p> |

1. 在&#x200B;**[!UICONTROL 配置文件数据集]**&#x200B;部分中，选择包含要报告的同意策略成员资格数据（`consentPoliciesIDMap`字段）的配置文件数据集。 当您启用同意报告时，此用户档案数据集将添加到您选择的连接（如果该连接尚未包含在其中）。

1. 在&#x200B;**[!UICONTROL 连接]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 选择连接]**，选中要配置的一个或多个连接旁边的复选框，然后选择&#x200B;**[!UICONTROL 使用连接]**。

   在连接级别应用同意报告和筛选。 已配置连接下的所有数据视图将继承相同的行为。

1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;部分中，单击&#x200B;**[!UICONTROL 选择数据视图]**。

1. 在数据视图对话框中，选中一个或多个要用于同意报告的数据视图旁边的复选框。 这些数据视图自动配置有Experience Platform同意数据以用于报表。

1. 选择&#x200B;**[!UICONTROL 使用数据视图]**。

1. （可选）在&#x200B;**[!UICONTROL 筛选]**&#x200B;部分中，您可以为以下营销操作启用筛选：

   >[!NOTE]
   >
   >启用营销活动过滤功能后，仅当访客与适用于该营销活动的&#x200B;**所有**&#x200B;同意策略相匹配时，Customer Journey Analytics才会摄取访客的数据。 有关详细信息，请参阅[同意报告和筛选概述](/help/connections/consent-reporting-filtering/consent-overview.md)中的[同意筛选](/help/connections/consent-reporting-filtering/consent-overview.md#consent-filtering)。

   | 营销操作 | 描述 |
   |---------|----------|
   | **[!UICONTROL Analytics]** | 在Analysis Workspace中过滤用于标准Customer Journey Analytics报表的数据。 |
   | **[!UICONTROL 数据科学]** | 过滤用于高级分析、机器学习和数据科学用例的数据。 |

1. 选择&#x200B;**[!UICONTROL 创建]**&#x200B;以创建配置。

   如果启用了报表，则Customer Journey Analytics会自动：

   * 将选定的配置文件数据集添加到连接。
   * 为沙盒创建同意策略查找数据集（如果尚不存在），并从Experience Platform同步策略名称和描述。
   * 将同意策略组件（维度、量度和派生字段）添加到已配置连接内的数据视图。

1. 配置完成后，[在数据视图](#view-consent-policy-components-in-the-data-view)中查看同意策略组件以验证它们是否可用。

## 在数据视图中查看同意策略组件

在您[创建配置](#create-a-configuration)后，您可以验证同意策略组件是否已添加到所配置连接下的数据视图中。

要在数据视图中查看同意策略组件，您必须是数据视图所分配到的产品配置文件的产品配置文件管理员。 有关详细信息，请参阅[访问控制](/help/technotes/access-control.md)。

在数据视图中查看同意策略组件：

1. 在 Customer Journey Analytics 中选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。

1. 打开与所配置连接关联的数据视图。

1. 在&#x200B;**[!UICONTROL 维度]**&#x200B;部分中，以下维度现在应可用：

   * **[!UICONTROL 同意策略ID]**

   * **[!UICONTROL 策略名称]**

   * **[!UICONTROL 策略说明]**

1. 在&#x200B;**[!UICONTROL 量度]**&#x200B;部分中，以下量度现在应可用：

   * **[!UICONTROL 经同意的访客]**

   * **[!UICONTROL 经同意的事件]**

   * **[!UICONTROL 唯一的同意政策]**

   <!-- TODO: Add a screenshot of the consent policy components in the data view (assets/consent-components-dataview.png). -->

1. 在Analysis Workspace中使用同意策略组件。

   有权访问Analysis Workspace中的数据视图的用户现在可以查看新组件，并在其分析中使用它们。 有关如何在Analysis Workspace中使用同意策略组件的信息，请参阅[分析同意策略数据](/help/connections/consent-reporting-filtering/consent-analyze.md)。
