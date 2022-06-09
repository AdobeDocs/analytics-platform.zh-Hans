---
description: 通过维度间流量可以跨不同维度查看用户路径。
title: 维度间流量
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
source-git-commit: a8b59feccfb5bf1656dc3716fa3d022f8f74ee5a
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 100%

---

# 维度间流量

通过维度间流量可以跨不同维度查看用户路径。

现在每个“流量”列的顶部有一个维度标签，让您在流量可视化图表中使用多个维度时变得更加直观：

![](assets/flow.png)

我们将讨论 2 个用例：应用程序用例和 Web 用例。

## 用例一：应用程序

[!UICONTROL 操作名称]维度已被添加到流量，顶部的返回项目为 [!UICONTROL ItemAdded]：

![](assets/multi-dimensional-flow.png)

要探索此应用程序中屏幕/页面和操作之间的交互，您可以将页面维度拖到多个位置，具体取决于您要探索的内容：

* 将它拖到拖放区域的任一末端（在显示的黑框矩形区域内部）以&#x200B;**替换**&#x200B;末端的顶部结果：

   ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* 将它拖到末端的空白处（注意黑色存储段）以&#x200B;**添加到**&#x200B;可视化：

   ![](assets/multi-dimensional-flow4.png)

如果您决定将右列中的 ItemScaled 项目替换为页面维度，即会得到此结果。顶部结果现在更改为页面维度的顶部结果：

![](assets/multi-dimensional-flow5.png)

现在您可以查看客户是如何在操作和页面间移动的。通过单击不同的节点，可进一步探索流量：

![](assets/multi-dimensional-flow6.png)

如果您将其他“操作名称”维度添加到可视化的末端，即会发生此情况：

![](assets/multi-dimensional-flow7.png)

这将允许进行一些深入的分析，并对您分析的应用程序进行可能的更改。

## 用例二：Web

此用例显示如何分析哪些促销活动为网站带来最多登入。

将“促销活动名称”维度拖到新流量中：

![](assets/multi-dimensional-flow8.png)

现在我希望查看这些促销活动将流量推入哪些页面，这样我就能将页面维度拖到流量结果的右侧以添加到可视化：

![](assets/multi-dimensional-flow9.png)
