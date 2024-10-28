---
title: 产品使用情况选择退出设置
description: 管理组织内个人用户的退出设置。
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 7%

---

# 产品使用情况选择退出设置 {#product-usage-opt-out-settings}

{{release-limited-testing}}

通过&#x200B;_退出设置_&#x200B;页面，您可以从产品使用情况跟踪中排除或重新包括组织中的用户。 只有产品管理员才能看到它。

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]** > **[!UICONTROL 退出设置]**

此页面上提供以下设置：

* **[!UICONTROL 选择退出用户]**：包含组织中所有Customer Journey Analytics用户的下拉列表。 从此下拉列表中选择一个用户，然后选择&#x200B;**[!UICONTROL 选择退出]**&#x200B;以将该用户从产品使用情况跟踪中排除。 该用户已添加到下面的[!UICONTROL 退出用户列表]表中。
* **[!UICONTROL 选择退出用户列表]**：一个表，其中显示当前选择退出产品使用情况跟踪的所有用户。 如需选择用户重新加入产品使用情况跟踪，请选中给定用户旁边的复选框，然后选择&#x200B;**[!UICONTROL 选择加入]**&#x200B;按钮。

Adobe使用客户端和服务器端跟踪的组合来收集您的组织的产品使用情况数据。 最初选择用户时，该用户可能仍然会在其调试器中看到客户端跟踪数据，直到他们注销并重新登录到Customer Journey Analytics为止。 Adobe的服务器端验证可确保为选择退出用户丢弃客户端跟踪数据。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="选择退出的用户"
>abstract="将用户排除在产品使用情况跟踪之外。"
