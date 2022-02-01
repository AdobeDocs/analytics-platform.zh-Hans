---
description: 显示如何生成简单的“每次访问页面查看次数”量度。
title: 构建简单的“每次访问的页面查看次数”量度
feature: Calculated Metrics
exl-id: 46c83a1f-cb2d-4d5d-af4f-e1d2e4566743
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---

# 构建简单的“每次访问的页面查看次数”量度

显示如何生成简单的“每次访问页面查看次数”量度。

有关 UI 组件的详细描述，请参阅 [生成指标](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

下面说明了如何生成简单的“每次访问页面查看次数”量度。

1. 导航至计算量度生成器。
1. 为量度指定“每次访问页面查看次数”或类似的名称。
1. 为量度提供用户友好的&#x200B;**[!UICONTROL 描述]**，以显示其用途。
1. 选择正确的&#x200B;**[!UICONTROL 格式]**，在此例中，选择“小数”。
1. 确定您希望报表显示多少个小数位。
1. 设置量度极性。对于此量度，上升趋势是有利的（绿色）。
1. 添加&#x200B;**[!UICONTROL 标记]**&#x200B;以组织您的量度。
1. 对于此量度，首先将“页面查看次数”拖到画布中，然后再将“访问次数”拖到下方（等到出现蓝线时再放下它）。
1. 选择“除以”运算符。（“除以”是默认的运算符。）
1. 现在，当您生成量度时，即可在右上角看到该量度的&#x200B;**[!UICONTROL 预览]**。
1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 请注意，无论您何时对量度定义进行更改，**[!UICONTROL 概要]**&#x200B;公式都会随之发生更新。
1. 现在，您会自动转到[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)，这与筛选器管理器相似。通过此项，您可以共享、批准、（重新）标记、重命名或删除量度。
