---
title: 转移资产
description: 了解如何将组件从一个用户转移到另一个用户
role: Admin
solution: Customer Journey Analytics
source-git-commit: 9663a24c2430d3822cb83876ea048b6423405215
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 0%

---


# 转移资产

通过资产转移工具，您可以将资产的所有权转移给其他用户。 Assets可以包括项目、过滤器、日期范围、计算量度、注释、警报和计划项目等组件。

Assets通常与单个所有者绑定，并且在某些情况下，甚至管理员也无法编辑或共享筛选器、计算量度等。 当用户离开组织或更改其角色时，可能有必要将这些资产的所有权转移给其他用户，以确保连续性和适当的访问权限。

## 权限

资源传输需要“产品管理员”权限才能进行Customer Journey Analytics。

## 转移资产

1. 在CJA中，导航到&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 资产转移]**。

   ![资产转移菜单项](/help/tools/asset-transfer/assets/asset-transfer.png)

1. 在&#x200B;**[!UICONTROL 用户]**&#x200B;对话框中，搜索并选择要从中转移资产的用户。

   >[!IMPORTANT]
   >
   >您只能进行1:1传输，即从一个用户传输到另一个用户。 不支持一对多或多对一传输。


1. 选择用户后，传输资产选项将显示在屏幕底部。

   ![菜单选项](/help/tools/asset-transfer/assets/after-selection.png)

1. 单击&#x200B;**[!UICONTROL 转移资产]**。

1. 在&#x200B;**[!UICONTROL 转移资产]**&#x200B;屏幕上，首先选择要向其转移资产的收件人。

1. 现在，在左侧导航中浏览每个组件文件夹，以选择要传输的单个组件或文件夹中的所有资产。

   >[!NOTE]
   >
   >将资产从管理员转移到非管理员不会将收件人升级到管理员。


   >[!NOTE]
   >
   >    在传输引用其他组件的资产（例如，引用其他筛选器和计算量度的项目）时，不属于项目当前所有者的组件将仅与收件人共享。 所有其他组件的所有权将移交给收件人。

1. 要选择文件夹中的&#x200B;_所有_&#x200B;资源，请选中表顶部的&#x200B;**[!UICONTROL Name]**&#x200B;旁边的复选框。

   ![选择要转移的资产](/help/tools/asset-transfer/assets/select-assets.png)

1. 完成所有选择后，单击右上方的&#x200B;**[!UICONTROL 传输]**。

1. 出现确认消息时，单击&#x200B;**[!UICONTROL 确认]**。

   >[!IMPORTANT]
   >
   >在转移过程中请勿关闭屏幕，以免流产过程。 这可确保流畅的传输体验。

## 传输结果

转移有三种可能的结果：

- **传输成功**：“Assets传输成功。”

- **部分成功**：“已成功传输某些资产。”

- **传输失败**：“无法传输资产。 请重试。”

## 在从Adobe Analytics升级到Customer Journey Analytics期间转移资源

资产转移的主要用例之一是在从Adobe Analytics升级到Customer Journey Analytics期间。

Adobe Analytics中的[组件迁移](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration)功能允许您将管理员拥有的项目迁移到其他管理员。 随后将在Customer Journey Analytics中重新创建构成这些项目的所有组件，并且收件人管理员将拥有所有这些组件，而不管这些组件的创建者是谁。

随后，此资产传输工具可让管理员将组件重新分配给其合法所有者，无论他们是否为管理员。

>[!IMPORTANT]
>
>虽然您可以使用此工具传输组件，但作为管理员，您仍然需要确保收件人有权访问查看/使用这些组件所需的数据视图。 您可以在[Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)中查看和分配权限。

## 导出到 CSV

**[!UICONTROL 导出到CSV]**&#x200B;选项仅允许管理员将显示的用户列表下载到.csv文件。 它不允许他们将已转移资产的列表导出到.csv文件。

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->