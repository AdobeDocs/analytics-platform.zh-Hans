---
title: 创建过滤器
description: 了解过滤器创建用户界面。
translation-type: ht
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# 创建过滤器

过滤器生成器提供了一个将量度、维度、过滤器和事件拖放到其中的画布，从而根据容器层次结构逻辑、规则和运算符过滤访客。通过使用该集成开发工具，您可以生成和保存简单或复杂的过滤器，以确定跨访问和页面点击的访客属性和操作。

将任意组件类型（维度、维度项目、事件、量度、区段、区段模板、日期范围）放入面板顶部的过滤器拖放区域中，即可创建即时过滤器。

组件类型将被自动转换为过滤器。或者，您还可以单击&#x200B;**[!UICONTROL 添加过滤器]**&#x200B;下拉框中的“+”号。

请记住以下事项：

* 您&#x200B;**不能**&#x200B;将以下组件类型放入过滤器区域：不能从中生成过滤器的计算量度和维度/量度。
* 对于所有维度和事件，Analysis Workspace 将创建“存在”点击过滤器。示例：“在 eVar1 存在的地方点击”或“在 event1 存在的地方点击”。
* 如果将“未指定”或“无”放入过滤器下拉区域中，它们将自动转换为“不存在”过滤器，以便在过滤时正确进行处理。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>通过这种方式创建的过滤器是项目的内部过滤器。

您可以选择按照以下步骤操作，将这些过滤器设为公用（全局）过滤器：

1. 在拖放区域中将光标悬停在过滤器上，然后单击“i”图标。
1. 在显示的信息面板中，单击&#x200B;**[!UICONTROL 设为公用]**。

   ![](assets/segment-info.png)

## 应用过滤器的其他方法

还有其他一些方法也可以将过滤器应用到项目中：

| 操作 | 描述 |
|--- |--- |
| 根据选定的内容创建过滤器 | 创建内联过滤器。选择行，接着右键单击选定的内容，然后创建内联过滤器。该过滤器只适用于打开的项目并且不能另存为 CJA 过滤器。1. 选择行。2. 右键单击选定的内容。3. 单击&#x200B;*从所选内容创建过滤器*。 |
| “组件”>“新建过滤器” | 屏幕上会显示“过滤器生成器”。有关过滤器的更多信息，请参阅[过滤器生成器](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html)。 |
| “共享”>“共享项目”或“共享”>“策划项目数据” | 在[策划并共享](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，了解应用到项目中的过滤器如何用于给收件人共享的分析当中。 |
| 使用过滤器作为维度 | 视频：在 Analysis Workspace 中使用过滤器作为维度 |

>[!VIDEO](https://video.tv.adobe.com/v/23974?captions=chi_hans)
