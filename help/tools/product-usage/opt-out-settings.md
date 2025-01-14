---
title: 产品使用情况选择退出设置
description: 管理组织中各个用户的选择退出设置。
exl-id: 0ea24582-bab8-4a76-ac00-7c265423e8bb
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 11%

---

# 产品使用情况选择退出设置 {#product-usage-opt-out-settings}

{{release-limited-testing}}

_选择退出设置_&#x200B;页面允许您从产品使用情况跟踪中排除或重新包含组织内的用户。 它仅对产品管理员可见。

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 产品使用情况]** > **[!UICONTROL 选择退出设置]**

此页面上提供以下设置：

* **[!UICONTROL 选择退出用户]**：包含您组织中所有Customer Journey Analytics用户的下拉列表。 从该下拉列表中选择一个用户，然后选择&#x200B;**[!UICONTROL 选择退出]**&#x200B;以将该用户从产品使用情况跟踪中排除。 该用户已添加到下面的[!UICONTROL 选择退出用户列表]表中。
* **[!UICONTROL 选择退出用户列表]**：显示当前选择退出产品使用情况跟踪的所有用户的表。 要选择用户重新加入产品使用情况跟踪，请选中给定用户旁边的复选框，然后选择&#x200B;**[!UICONTROL 选择加入]**&#x200B;按钮。

Adobe使用客户端和服务器端跟踪的组合来收集贵组织的产品使用情况数据。 最初选择禁用某个用户时，该用户仍可能会在其Debugger中看到客户端跟踪数据，直到他们注销并重新登录Customer Journey Analytics为止。 Adobe的服务器端验证可确保为已选择退出的用户丢弃客户端跟踪数据。

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="选择退出的用户"
>abstract="将用户排除在产品使用情况跟踪之外。"

>[!CONTEXTUALHELP]
>id="product_usage_opt_out_settings"
>title="选择退出的用户"
>abstract="将用户排除在产品使用情况跟踪之外。"
