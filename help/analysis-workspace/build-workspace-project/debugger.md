---
description: 了解如何使用Debugger对Analysis Workspace中的项目问题进行故障诊断。
keywords: Analysis Workspace
feature: Workspace Basics
title: 项目调试器
role: User
source-git-commit: ae8c1fb127accae53ab9363a8cceedd5221a245b
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# 项目调试器

项目调试器可帮助您和Adobe支持人员对您在Analysis Workspace中的项目问题进行故障诊断。 Adobe支持部门可能会要求您启用Debugger，以便对您在Adobe支持部门提出的票证进行故障排除。 例如，可视化的加载时间或可视化中的组件损坏。

>[!NOTE]
>
>若要使用调试器，您必须拥有对项目&#x200B;**的**&#x200B;编辑&#x200B;**或**&#x200B;复制[&#128279;](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-25744)访问权限。
>


## 启用调试器

>[!IMPORTANT]
>
>在启用调试器之前保存您的项目。
>

要启用调试器，请执行以下操作：

1. 从Analysis Workspace项目菜单中选择&#x200B;**[!UICONTROL 帮助]** > **[!UICONTROL 启用Debugger]**。
1. 在&#x200B;**[!UICONTROL 启用调试器]**&#x200B;对话框中选择&#x200B;**[!UICONTROL 确定]**。
1. 在浏览器提示您重新加载页面或站点时确认。


## 使用调试器

启用调试器后，项目中的所有可视化图表都会有一个额外的![错误](/help/assets/icons/Bug.svg)图标。

要将调试器用于特定可视化图表，请执行以下操作：

1. 选择可视化图表顶部的![错误](/help/assets/icons/Bug.svg)。

   ![调试器上下文菜单](assets/debugger-context-menu.png)

1. 从上下文菜单中选择相应的操作。 可用的操作取决于可视化图表并指示要执行的调试类型。 例如，如果您选择&#x200B;**[!UICONTROL 异常]**，则您想要调试可视化图表中的异常功能。
1. 从子菜单中，选择时间戳。
1. 将打开&#x200B;**[!UICONTROL Oberon XML]**&#x200B;调试窗口，其中包含可视化图表执行的特定功能的详细信息。 有关异常请求的输出示例，请参阅下文。

   ![输出调试请求](assets/debugger-oberon.png)

   详情如下：

   * **[!UICONTROL 请求时间戳]**
   * **[!UICONTROL 响应时间戳]**
   * **[!UICONTROL 请求时间]**
   * **[!UICONTROL 排队时间]**
   * **[!UICONTROL 服务器处理时间]**
   * **[!UICONTROL 查找时间]**
   * **[!UICONTROL 复杂性]**
   * **[!UICONTROL 月份边界]**
   * **[!UICONTROL 列]**
   * **[!UICONTROL 区段]**
   * **[!UICONTROL XML]** **[!UICONTROL 请求]**&#x200B;和&#x200B;**[!UICONTROL 响应]**
   * **[!UICONTROL cURL请求]**
   * **[!UICONTROL JSON]** **[!UICONTROL 请求]**&#x200B;和&#x200B;**[!UICONTROL 响应]**

1. 使用![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 将所有字段复制到剪贴板]**&#x200B;以将所有调试信息复制到剪贴板。 将信息粘贴到首选编辑器或工具中。 该信息包括：

   * XML（请求）
   * XML（响应）
   * JSON（请求）
   * JSON（响应）
   * cURL 请求

1. 在![cURL请求](/help/assets/icons/Copy.svg)下使用&#x200B;**[!UICONTROL 复制]** **[!UICONTROL 复制到剪贴板]**&#x200B;将请求复制到剪贴板。
1. 将鼠标悬停在任何&#x200B;**[!UICONTROL 请求]**&#x200B;或&#x200B;**[!UICONTROL 响应]**&#x200B;文本区域上以显示并选择![复制](/help/assets/icons/Copy.svg) **[!UICONTROL 复制到剪贴板]**&#x200B;以将该文本区域（XML或JSON）的内容复制到剪贴板。

1. 交换您复制的任何信息以及Adobe支持部门请求对您的Analysis Workspace项目中的可视化图表进行故障排除的信息。

1. 选择&#x200B;**[!UICONTROL 取消]**&#x200B;以关闭&#x200B;**[!UICONTROL Oberon XML]**&#x200B;调试窗口并返回项目。

对要排除故障的任何其他可视化图表重复上述步骤。

## 禁用调试器

>[!IMPORTANT]
>
>在禁用调试器之前，请保存对项目所做的任何更改并希望在调试练习中保留这些更改。
>

要禁用调试器，请执行以下操作：

1. 从Analysis Workspace项目菜单中选择&#x200B;**[!UICONTROL 帮助]** > **[!UICONTROL 禁用调试器]**。
1. 在&#x200B;**[!UICONTROL 禁用调试器]**&#x200B;对话框中选择&#x200B;**[!UICONTROL 确定]**。
1. 在浏览器提示您重新加载页面或站点时确认。



