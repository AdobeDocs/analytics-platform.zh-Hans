---
title: Content Analytics 组件
description: 有关维度、（计算）量度和派生字段等特定 Content Analytics 组件的详细信息
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 100%

---

# Content Analytics 组件

Content Analytics 将以下类别的组件（维度、（计算）量度、派生字段）添加到 Customer Journey Analytics 中已有的组件中：

* [体验元数据](#experience-metadata)
* [体验属性](#experience-attributes)
* [体验事件](#experience-events)
* [资产元数据](#asset-metadata)
* [资产属性](#asset-attributes)
* [资产事件](#asset-events)
* [计算量度](#calculated-metrics)

在下表中，![AI 生成](/help/assets/icons/AI.svg)表示一个 AI/ML 生成的属性/值对。

## 体验元数据

| 标题 | 描述 | 类型 |
|---|---|---|
| 体验渠道 | 体验的渠道。 | 维度 |
| 体验 ID | 体验的唯一 ID。 | 维度 |
| 体验缩略图 URL | 体验缩略图的 URL。 | 维度 |
| 体验水平百分比深度 | 体验的水平百分比深度的可量化值。 | 维度<br/>派生字段 |
| 体验垂直百分比深度 | 体验的垂直百分比深度的可量化值。 | 维度<br/>派生字段 |

{style="table-layout:fixed"}



## 体验属性

| 标题 | 描述 | 类型 |
|---|---|---|
| 体验属性 | ![AI 生成](/help/assets/icons/AI.svg) 所有体验属性的名称和值的完整列表 | 维度<br>派生字段 |
| 体验可读性得分 | ![AI 生成](/help/assets/icons/AI.svg) 体验的可读性得分 | 维度 |
| 体验关键词 | ![AI 生成](/help/assets/icons/AI.svg) 体验的关键词。 | 维度<br>派生字段 |
| 体验说服策略 | ![AI 生成](/help/assets/icons/AI.svg) 某个给定体验中存在的说服策略。可能的值包括：社会身份、社会认同、权威、具体性、入门机会、克服抵触、互惠、锚定和比较、社会影响、稀缺性和拟人化。 | 维度<br/>派生字段 |
| 体验叙述 | ![AI 生成](/help/assets/icons/AI.svg) 体验基于营销人员观点的相关性而生成的叙述。 | 维度<br/>派生字段 |
| 体验语气 | ![AI 生成](/help/assets/icons/AI.svg) 体验基于营销人员观点的相关性而生成的语气。 | 维度<br/>派生字段 |
| 体验营销情感 | ![AI 生成](/help/assets/icons/AI.svg) 读者在阅读文本时产生的情感是体验的一部分：紧迫性、排他性、鼓励性、挑战性、好奇心、成就感、信任、简单性和魅力。 | 维度<br/>派生字段 |
| 体验表情符号计数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的表情符号数量。 | 量度 |
| 体验主题标签计数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的主题标签数量。 | 量度 |
| 体验句子计数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的句子数量。 | 量度 |
| 体验停用词比例 | ![AI 生成](/help/assets/icons/AI.svg) 体验的停止词数量。 | 量度 |
| 体验文本引用计数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的文本引用数量。 | 量度 |
| 体验字数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的词语数量。 | 量度 |
| 体验每句字数 | ![AI 生成](/help/assets/icons/AI.svg) 体验的每句话的字数。 | 量度 |

{style="table-layout:fixed"}


## 体验事件

| 标题 | 描述 | 类型 |
|---|---|---|
| 体验视图 | 对体验的观看数量进行可量化衡量。 | 量度 |
| 体验点击次数 | 对体验的点击次数进行可量化衡量。 | 量度 |

{style="table-layout:fixed"}


## 资产元数据

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产 ID | 资产的唯一标识符。资产二进制决定了唯一性。如果资产二进制发生变化，ID 也会发生变化。唯一 ID 可以是 URL，也可以是创建的哈希值。 | 维度 |
| 资产 HTML 路径 | 资产的关联 HTML 路径。 | 维度 |
| 资产链接 URL | 距离资产最近的页面锚点。 | 维度 |
| 资产显示宽度 | 内容资产显示宽度。 | 维度 |
| 资产显示高度 | 内容资产显示高度。 | 维度 |
| 资产绝对左侧 | 内容资产绝对左侧。 | 维度 |
| 资产绝对顶部 | 内容资产绝对顶部。 | 维度 |

{style="table-layout:fixed"}


## 资产属性

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产属性 | ![AI 生成](/help/assets/icons/AI.svg) 所有资产属性的名称和值的完整列表 | 维度<br>派生字段 |
| 资产导向 | ![AI 生成](/help/assets/icons/AI.svg) 资产的导向。 | 维度<br/>派生字段 |
| 资产整体基调 | ![AI 生成](/help/assets/icons/AI.svg) 资产的整体基调。 | 维度<br/>派生字段 |
| 资产前景颜色 | ![AI 生成](/help/assets/icons/AI.svg) 资产的前景颜色。 | 维度<br/>派生字段 |
| 资产背景颜色 | ![AI 生成](/help/assets/icons/AI.svg) 资产的背景颜色。 | 维度<br/>派生字段 |
| 资产标记 | ![AI 生成](/help/assets/icons/AI.svg) 资产的标记。 | 维度<br/>派生字段 |
| 资产场景 | ![AI 生成](/help/assets/icons/AI.svg) 资产的场景。 | 维度<br/>派生字段 |
| 资产对象 | ![AI 生成](/help/assets/icons/AI.svg) 资产的对象。 | 维度<br/>派生字段 |
| 资产摄影风格 | ![AI 生成](/help/assets/icons/AI.svg) 资产的摄影风格。 | 维度<br/>派生字段 |
| 资产图像类型 | ![AI 生成](/help/assets/icons/AI.svg) 资产的图像类型。可能的值包括：照片、素描、绘画、数字卡通、信息图表、图形设计、拼贴画和软件屏幕快照。 | 维度<br/>派生字段 |
| 资产相机位置 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机位置。 | 维度<br/>派生字段 |
| 资产相机接近度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机接近度。 | 维度<br/>派生字段 |
| 资产人员类别 | ![AI 生成](/help/assets/icons/AI.svg) 资产的人员类别。可能的值包括：人、男人、女人、社会群体、人群、人们、男孩、女孩和孩子。 | 维度<br/>派生字段 |
| 资产视觉内容密度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的视觉内容密度。可能的值包括：低、中或高。低内容密度意味着图像单位面积上存在的信息量很少。 | 维度 |
| 资产视觉注意力分散度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的视觉注意力分散度。可能的值包括：低、中或高。注意力分散是指观看者在画面不同部分之间注意力分散的程度。 | 维度<br/>派生字段 |
| 资产照明条件 | ![AI 生成](/help/assets/icons/AI.svg) 资产的照明条件。可能的值包括：黄金时段、蓝色时段、中午、阴天、夜晚、高调、低调、日光、白炽灯、荧光灯、彩色和工作室。 | 维度<br/>派生字段 |
| 资产相机设置 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机设置。可能的值包括：快速快门速度、长时间曝光。散景模糊、运动模糊、移轴模糊、闪光灯、广角、黑白、超现实、双重曝光、微距和正常模式。 | 维度<br/>派生字段 |

{style="table-layout:fixed"}


## 资产事件

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产视图 | 对资产的观看数量进行可量化衡量。 | 量度 |
| 资产点击次数 | 对资产点击次数进行可量化衡量。 | 量度 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## 计算量度

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产点进率 | 资产点击次数/资产浏览次数 | 计算量度 |
| 体验点进率 | 体验点击次数/体验浏览次数 | 计算量度 |

{style="table-layout:fixed"}

