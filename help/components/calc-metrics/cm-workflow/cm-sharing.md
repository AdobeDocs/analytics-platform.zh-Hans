---
description: 了解如何与整个组织、组或个人用户共享量度。
title: 共享计算量度
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---

# 共享计算量度

在[计算量度管理器](cm-manager.md)中，您可以共享计算量度。 根据您的权限，可以与整个组织、组或个人用户共享计算指标：

* **管理员**：管理员可以将计算量度与整个组织、组织内的组以及单个用户共享。 有关详细信息，请参阅 [Admin Console 文档](https://helpx.adobe.com/cn/enterprise/using/manage-products.html)。
* **非管理员**：非管理员只能共享他们已创建的计算量度，并且只能共享给个人用户。

要共享一个或多个计算指标，请执行以下操作：

1. 在[计算量度管理器](cm-manager.md)中，选择要共享的一个或多个计算量度。
1. 从操作栏中选择![共享](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共享]**。
1. 在&#x200B;**[!UICONTROL 共享计算量度]**&#x200B;对话框中：

   ![共享计算量度对话框](assets/share-calculated-metrics-dialog.png)

   1. （可选）使用![搜索](/help/assets/icons/Search.svg)到&#x200B;*搜索个人或组*，并限制要与其共享计算指标的组或个人的列表。

   1. 从&#x200B;**[!UICONTROL 组织]**&#x200B;或&#x200B;**[!UICONTROL 组]**&#x200B;部分中选择一个或多个选项，或者搜索并选择一个或多个个人。 可用的选项取决于您的角色。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以共享计算量度。 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。

## 最佳实践

以下是您应该共享计算指标并与谁共享计算指标的一些最佳实践。

* 作为管理员，只有在您确信组织中的任何人能够熟练使用计算量度时，才能与所有人共享计算量度。 您还可以考虑优先使用这些计算指标。 有关详细信息，请参阅[将计算量度标记为收藏](cm-favorite.md)。

* 作为管理员，如果计算量度为特定组的用户部分提供了业务价值，那么就应当将该计算量度与该组共享。

* 作为管理员或个人用户，请将计算指标与一个或多个个人共享以验证计算指标。 如果事实证明，区段没有用处，则可以删除计算指标。


<!--

Depending on your permissions, you can share metrics with your whole organization, groups, or individual users.

|  Role | Permissions |
|---|---|
|  Administrator  | Can share metrics with All, with Groups, and with Users. Groups are set up as permission groups in the Admin console.  |
|  Non-Administrator  | Can share metrics only with individual users.  |

To share a calculated metric:

1. In the Calculated metrics manager, mark the checkbox next to the metric you want to share.

   ![Calculated metrics manager showing the available icons across the top of the window including Hide Filters, Tag, Share, Delete, and Copy.](assets/cm_task_bar.png)

1. Select the **[!UICONTROL Share]** icon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   The Share Calculated metric dialog box displays.

   ![Share Calculated metric window with All selected for the Organization.](assets/cm_share.png)

1. Select **[!UICONTROL Share]**.

1. Choose who you want to share with:

   * **[!UICONTROL All]** (Administrators only): Shares with all users in the organization.

     Consider sharing with all only if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an [approved metric](/help/components/calc-metrics/cm-workflow/cm-approving.md).
   
   * **[!UICONTROL Groups]** (Administrators only): Select any groups you want to share with.

     Consider sharing with a group if the metric provides good business value for that team.
   
   * **[!UICONTROL Individual users]**: Search for and select the individual users you want to share with.

      This is the only share option available to all users. Administrators might want to use this option to vet and validate a metric prior to making it available to a group or to everyone. If the metric isn't useful, it can be discarded. Administrators should not officially approve this type of metric.

1. Select **[!UICONTROL Share]**.

   The Shared icon appears next to the metric: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. You can filter on metrics shared with you by going to **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Optional) To filter the list of calculated metrics in the Calculated metrics manager to show only metrics that are shared with you, select the **Filter** icon, expand **[!UICONTROL Other filters]**, then select **[!UICONTROL Shared with me]**.

-->