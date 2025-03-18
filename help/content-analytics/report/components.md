---
title: Content Analytics组件
description: 有关特定Content Analytics组件的详细信息，例如维度、（计算）量度和派生字段
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 62491fcbf37961d33be92d209e5710bf9696c223
workflow-type: tm+mt
source-wordcount: '1390'
ht-degree: 17%

---

# Content Analytics组件

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

Content Analytics可将以下类别的组件(维度、（计算）量度、派生字段)添加到Customer Journey Analytics中已可用的组件中：

* [体验元数据](#experience-metadata)
* [体验属性](#experience-attributes)
* [体验事件](#experience-events)
* [资源元数据](#asset-metadata)
* [资产属性](#asset-attributes)
* [Assets活动](#asset-events)
* [计算量度](#calculated-metrics)

在下表中，![AI生成的](/help/assets/icons/AI.svg)表示AI/ML生成的值。

## 体验元数据

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 体验渠道 | 体验的渠道。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验来源 | 体验的Source URL。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验 ID | 体验的唯一id。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验名称 | 体验的名称。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验描述 | 体验描述。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验缩略图 URL | 体验缩略图的URL。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验水平百分比深度 | 体验的水平百分比深度可量化值。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验垂直百分比深度 | 体验的垂直百分比深度的可量化值。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验水平像素深度 | 体验的水平像素深度的可量化值。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验垂直像素深度 | 体验的垂直像素深度的可量化值。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |

{style="table-layout:fixed"}



## 体验属性

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 体验可读性得分 | ![AI生成了](/help/assets/icons/AI.svg)体验的可读性分数。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 体验关键词 | ![AI为体验生成了](/help/assets/icons/AI.svg)关键字。 | Dimension<br>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验说服策略 | ![AI生成的](/help/assets/icons/AI.svg)在给定体验中存在的说服策略。 可能的价值是：社会认同、社会证明、权威、具体、踏入大门、克服抗拒性、互惠、锚定和比较、社会影响、稀缺性和拟人化。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验叙述 | ![AI生成](/help/assets/icons/AI.svg)从营销人员角度来看，体验基于相关性生成的叙述。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验语气 | ![AI生成了](/help/assets/icons/AI.svg)色调，体验正在根据营销人员视角下的相关性生成这些色调 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验营销情感 | ![AI生成](/help/assets/icons/AI.svg)阅读作为体验一部分的文本时，在读者中激起的情绪：紧迫感、排他性、鼓励、挑战、好奇心、成就、信任、简单和迷恋。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 体验表情符号计数 | ![AI生成了](/help/assets/icons/AI.svg)体验的emoji数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验井号标记计数 | ![AI生成了](/help/assets/icons/AI.svg)体验的井号标签数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验句子计数 | ![AI生成的](/help/assets/icons/AI.svg)体验的句子数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验停用词比例 | ![AI生成的](/help/assets/icons/AI.svg)体验的停用词数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验文本引用计数 | ![AI生成了](/help/assets/icons/AI.svg)体验的文本引号数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验字数 | ![AI生成了](/help/assets/icons/AI.svg)体验字数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验每句字数 | ![AI生成](/help/assets/icons/AI.svg)体验的每句字数。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |

{style="table-layout:fixed"}


## 体验事件

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 体验视图 | 对体验查看次数的可量化度量。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 体验点击次数 | 对体验点击次数的可量化度量。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |

{style="table-layout:fixed"}


## 资源元数据

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 资产来源 | 资源的公共可访问源URL。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产 ID | 资产的唯一标识符。 资产二进制文件确定唯一性。 如果资产二进制文件发生更改，则ID会随之发生更改。 唯一ID可以是URL，也可以是创建的哈希。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产名称 | 资源的名称。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产类型 | 资源的类型。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产缩略图 URL | 资产缩略图的URL。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产 HTML 路径 | 资源的HTML连接路径。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产链接 URL | 资产的最近页面锚点。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产显示宽度 | 内容资产显示宽度。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产显示高度 | 内容资产显示高度。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产绝对左侧 | 内容资产绝对左侧。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产绝对顶部 | 内容资产绝对顶部。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产创建者 | 用于创建资源的标识符。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产创建日期 | 资源创建日期。 | 维度 | 最近\| 会话 |
| 资产上次更新时间 | 用于资产更新的标识符。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产上次更新日期 | 资产更新日期。 | 维度 | 最近\| 会话 |

{style="table-layout:fixed"}


## 资产属性

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 资产导向 | ![AI生成了](/help/assets/icons/AI.svg)资源方向。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产整体基调 | ![AI生成了](/help/assets/icons/AI.svg)资源的整体色调。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产前景颜色 | ![AI生成了](/help/assets/icons/AI.svg)资源的前景颜色。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资源背景颜色 | ![AI生成了](/help/assets/icons/AI.svg)资源的背景颜色。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产标记 | ![AI为资源生成了](/help/assets/icons/AI.svg)标记。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产场景 | ![AI为资源生成了](/help/assets/icons/AI.svg)场景。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产对象 | ![AI生成了](/help/assets/icons/AI.svg)资源的对象。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产摄影风格 | ![AI生成了资产的](/help/assets/icons/AI.svg)摄影样式。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产图像类型 | ![AI生成了](/help/assets/icons/AI.svg)资源的图像类型。 可能的值包括：photographic、sketch、painting、digital_cartoon、infographics、graphic_design、collage和software_screenshot。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产相机位置 | ![AI已生成资产的](/help/assets/icons/AI.svg)个相机位置。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产相机接近度 | ![AI生成了资产的](/help/assets/icons/AI.svg)相机近似值。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产人员类别 | ![AI为该资产生成了](/help/assets/icons/AI.svg)人员类别。 可能的值包括：人、男人、女人、社会团体、人群、人、男孩、女孩和孩子。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产视觉内容密度 | ![AI生成了](/help/assets/icons/AI.svg)资源的视觉内容密度。 可能的值包括：低、中或高。 低内容密度意味着每单位图像区域显示的信息量很小。 | 维度 | 显示\| 没有值<br/>最近\| 会话 |
| 资产视觉注意力分散度 | ![AI已生成](/help/assets/icons/AI.svg)资源的视觉注意分布。 可能的值包括：低、中或高。 注意力扩散是指观看者的注意力在图像的不同部分之间的分散程度。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产照明条件 | ![AI生成了](/help/assets/icons/AI.svg)资源的照明条件。 可能的值包括：黄金时间、蓝色时间、正午、阴天、夜间、高键、低键、白光、白炽灯、荧光、彩色和录音室。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |
| 资产相机设置 | ![AI生成了](/help/assets/icons/AI.svg)资源的相机设置。 可能的值包括：快门速度、长曝光。 Bokeh blur、motion blur、tilt-shift blur、flash、wide-angle、black and white、surreal、double-exposure、macro和normal mode。 | Dimension<br/>派生字段 | 显示\| 没有值<br/>最近\| 会话 |

{style="table-layout:fixed"}


## 资源事件

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 资产视图 | 资产查看次数的可量化衡量指标。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |
| 资产单击次数 | 对资产点击次数的可量化度量。 | 量度 | 对值<br/>进行计数，十进制\| 小数位：0 |

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

| 标题 | 描述 | 类型 | 设置 |
|---|---|---|---|
| 资产点进率 | 资产点击次数/资产查看次数 | 计算量度 | |
| 体验点进率 | 体验点击次数/体验查看次数 | 计算量度 | |

{style="table-layout:fixed"}

