---
description: 在 Analysis Workspace 中使用临时筛选器。
title: 临时项目筛选器
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: c053a1517030b68875fe7f4518dbbd473dbe1b47
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 61%

---

# 临时项目筛选器

临时项目过滤器允许您将任何组件直接拖放到面板拖放区域中，以创建过滤器。 过滤器将变为 [项目级别筛选器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html?lang=zh-Hans) 当前项目的本地位置。

以下是一段关于创建临时项目筛选器的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. 将任何组件类型（维度、维度项目、事件、量度、区段、区段模板、日期范围）拖放到面板顶部的过滤器拖放区域。 组件类型会自动转换为临时过滤器或 [快速过滤器](/help/components/filters/quick-filters.md) 兼容。

   以下是如何为 Twitter 反向链接域创建筛选器的示例：

   ![](assets/ad-hoc1.png)

   您的面板自动应用此筛选器，而您可立即看到结果。

1. 您可以向面板添加无限数量的过滤器。
1. 如果决定要保存此筛选器，请参阅以下部分。

请记住：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入过滤器区域：不能从中生成过滤器的计算量度和维度/量度。
* 对于所有维度和事件，Analysis Workspace 将创建“存在”点击过滤器。示例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如果将“未指定”或“无”拖入筛选器放置区域，则它自动转换为“不存在”筛选器，以使其在筛选时受到正确对待。

## 保存临时项目筛选器 {#ad-hoc-save}

可选择按以下这些步骤保存这些筛选器：

1. 将光标悬停在放置区域中的筛选器上，然后单击“i”图标。
1. 单击编辑铅笔以转到过滤器生成器。
1. 单击&#x200B;**[!UICONTROL “使其对所有项目可用，并添加到组件列表”]**。
1. 单击&#x200B;**[!UICONTROL 保存]**。

保存后，该过滤器即会显示在您的左边栏组件列表中，并且可以从过滤器管理器中与其他用户共享。

