---
description: 了解如何构建简单的计算量度。
title: 构建简单的计算量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 10%

---

# 构建简单的计算量度

以下信息说明如何创建简单的&#x200B;*每次访问页面查看次数*&#x200B;指标。

1. 开始生成度量，如[生成度量](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。
1. 命名量度`Page Views per Session`或类似名称。
1. 为量度提供用户友好的&#x200B;**[!UICONTROL 描述]**&#x200B;以显示该量度的用途。
1. 选择正确的&#x200B;**[!UICONTROL 格式]**。 对于此示例，请选择&#x200B;**[!UICONTROL 十进制]**。
1. 决定您希望报表显示的小数位数。
1. 在&#x200B;**[!UICONTROL 将上升趋势显示为]**&#x200B;下拉菜单中，选择▲ **[!UICONTROL 良好（绿色）]**。
1. 添加&#x200B;**[!UICONTROL 标记]**&#x200B;以组织您的量度。
1. 对于此计算量度，首先将&#x200B;**[!UICONTROL 页面查看次数]**&#x200B;从&#x200B;**[!UICONTROL Metrics]**&#x200B;组件拖动到画布的&#x200B;**[!UICONTROL Definition]**&#x200B;部分。
1. 然后从&#x200B;**[!UICONTROL Metrics]**&#x200B;组件中拖动&#x200B;**[!UICONTROL Sessions]**，并将该量度放在&#x200B;**[!UICONTROL 页面查看次数]**&#x200B;下（等到显示蓝线之后再放置该量度）。
1. 选择除![除](/help/assets/icons/Divide.svg)运算符。 （除是默认运算符。）
1. 生成量度时，您可以看到该量度的&#x200B;**[!UICONTROL 预览]**。
1. **[!UICONTROL 产品兼容性]**&#x200B;显示计算量度是否在Customer Journey Analytics中的所有地方都兼容（不包括试验）。

   ![简单计算量度](assets/simple-calculated-metric.png)
1. 选择&#x200B;**[!UICONTROL 保存]**。

   请注意，无论您何时对量度定义进行更改，**[!UICONTROL 概要]**&#x200B;公式都会随之发生更新。

1. （可选）要共享、批准、（重新）标记、重命名或删除指标，可转到[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)。

