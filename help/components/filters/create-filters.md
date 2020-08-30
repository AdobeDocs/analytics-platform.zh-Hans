---
title: 创建过滤器
description: 了解过滤器创建用户界面。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# 创建过滤器

过滤器生成器提供了一个将量度、维度、过滤器和事件拖放到其中的画布，从而根据容器层次结构逻辑、规则和运算符过滤访客。通过使用该集成开发工具，您可以生成和保存简单或复杂的过滤器，以确定跨访问和页面点击的访客属性和操作。

您可以通过将任何组件类型(维、维项、事件、度量、段、段模板、日期范围)拖放到面板顶部的筛选器拖放区中来创建即时过滤器。

组件类型将自动转换为过滤器。 或者，您也可以单击 **[!UICONTROL 添加过滤器]** 的双曲余切值。

请记住以下事项：

* 您 **不能** 将以下组件类型拖放到筛选器区域中：无法从中构建过滤器的计算量度和维度／量度。
* 对于完整尺寸和事件,Analysis Workspace创建“存在”点击过滤器。 示例：“在 eVar1 存在的地方点击”或“在 event1 存在的地方点击”。
* 如果筛选器拖放区域中删除了“未指定”或“无”，则会自动将其转换为“不存在”筛选器，以正确处理它。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>以这种方式创建的过滤器是项目内部的。

您可以按照以下步骤选择将这些过滤器公开（全局）:

1. 将指针悬停在拖放区域中的筛选器上并单击“i”图标。
1. 在显示的信息面板中，单击&#x200B;**[!UICONTROL 设为公用]**。

   ![](assets/segment-info.png)

## 其他应用过滤器的方法

还存在将过滤器应用到项目的其他几种方法：

| 操作 | 描述 |
|--- |--- |
| 从选区创建筛选器 | 创建内联筛选器。 选择行，右键单击选择，然后创建内联筛选器。 此过滤器仅应用于打开的项目，不会另存为CJA过滤器。 1. 选择行。2. 右键单击选定的内容。3.单击 *从选区创建筛选器*. |
| “组件”>“新建过滤器” | 显示Filter Builder。 请参阅 [Filter Builder](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html) 的双曲余切值。 |
| “共享”>“共享项目”或“共享”>“策划项目数据” | 输入 [特选和共享](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)，了解您应用到项目的过滤器如何在共享分析中为收件人提供。 |
| 将过滤器用作维 | 视频：[在 Analysis Workspace 中使用区段作为维度](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
