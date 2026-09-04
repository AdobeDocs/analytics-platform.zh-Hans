---
title: Content Analytics组件
description: 了解特定Content Analytics组件的详细信息，例如维度、（计算）指标和派生字段
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: e3936b74ba4b4cf23e1b7235e545091a8cb546ed
workflow-type: tm+mt
source-wordcount: 1869
ht-degree: 56%

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
* [付费媒体](#paid-media)

在下表中，![AI 生成](/help/assets/icons/AI.svg)表示一个 AI/ML 生成的属性/值对。

## 体验元数据

| 标题 | 描述 | 类型 |
|---|---|---|
| ID SOURCE | 对于Content Analytics，值为`ContentAnalytics`。 | 维度 |
| 渠道 | 体验的渠道。 值为`Web`、`Mobile`或`Paid Media`。 | 维度 |
| 内容体验Id | 体验的唯一 ID。 <br>对于&#x200B;**Web**：网页的URL。 <br/>对于&#x200B;**粒度Web**：哈希计算客户端，基于前缀为`web-`的内容有效负载（文本、图像、CTA）。 <br/>对于&#x200B;**移动设备**：哈希计算客户端，基于前缀为`mobile-`的内容有效负载（文本、图像、CTA）。 | 维度 |
| 内容体验Source | 对于&#x200B;**Web**：网页的URL。<br/>对于&#x200B;**移动设备**：屏幕名称，通过Experience Platform Mobile SDK传入。 | 维度 |
| 体验渠道（已弃用） | 体验的渠道。 值为`Web`或`Mobile`。 | 维度 |
| Experience Extras | 任何其他要跟踪的数据。 如外部ID或投放位置。 | 维度 |
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
| 体验说服策略 | ![AI 生成](/help/assets/icons/AI.svg) 某个给定体验中存在的说服策略。 可能的值包括：社会身份、社会认同、权威、具体性、入门机会、克服抵触、互惠、锚定和比较、社会影响、稀缺性和拟人化。 | 维度<br/>派生字段 |
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
| 体验视图 | 体验浏览次数的可量化衡量。 | 量度 |
| 体验点击次数 | 体验点击次数的可量化衡量。 | 量度 |

{style="table-layout:fixed"}


## 资产元数据

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产 ID | 资产的唯一标识符。 资产二进制决定了唯一性。 如果资产二进制发生变化，ID 也会发生变化。 唯一 ID 可以是 URL，也可以是创建的哈希值。 | 维度 |
| 资产来源 | | 维度 |
| 资产 HTML 路径 | 资产的串联 HTML 路径。 | 维度 |
| 资产链接 URL | 距离资产最近的页面锚点。 | 维度 |
| 资产显示宽度 | 内容资产显示宽度。 | 维度 |
| 资产显示高度 | 内容资产显示高度。 | 维度 |
| 资产绝对左侧 | 内容资产绝对左侧。 | 维度 |
| 资产绝对顶部 | 内容资产绝对顶部。 | 维度 |
| 资产额外内容 | 任何其他要跟踪的数据。 如外部ID或投放位置。 | 维度 |

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
| 资产图像类型 | ![AI 生成](/help/assets/icons/AI.svg) 资产的图像类型。 可能的值包括：photograph、sketch、painting、digital_cartoon、infographics、graphic_design、collage 和 software_screenshot。 | 维度<br/>派生字段 |
| 资产相机位置 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机位置。 | 维度<br/>派生字段 |
| 资产相机接近度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机接近度。 | 维度<br/>派生字段 |
| 资产人员类别 | ![AI 生成](/help/assets/icons/AI.svg) 资产的人员类别。 可能的值包括：人、男人、女人、社会群体、人群、人们、男孩、女孩和孩子。 | 维度<br/>派生字段 |
| 资产视觉内容密度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的视觉内容密度。 可能的值包括：低、中或高。 低内容密度意味着图像单位面积上存在的信息量很少。 | 维度 |
| 资产视觉注意力分散度 | ![AI 生成](/help/assets/icons/AI.svg) 资产的视觉注意力分散度。 可能的值包括：低、中或高。 注意力分散是指观看者在画面不同部分之间注意力分散的程度。 | 维度<br/>派生字段 |
| 资产照明条件 | ![AI 生成](/help/assets/icons/AI.svg) 资产的照明条件。 可能的值包括：黄金时段、蓝色时段、中午、阴天、夜晚、高调、低调、日光、白炽灯、荧光灯、彩色和工作室。 | 维度<br/>派生字段 |
| 资产相机设置 | ![AI 生成](/help/assets/icons/AI.svg) 资产的相机设置。 可能的值包括：fast shutter speed、long exposure。 散景模糊、运动模糊、移轴模糊、闪光灯、广角、黑白、超现实、双重曝光、微距和正常模式。 | 维度<br/>派生字段 |

{style="table-layout:fixed"}


## 资产事件

| 标题 | 描述 | 类型 |
|---|---|---|
| 资产视图 | 对资产浏览次数进行可量化衡量。 | 量度 |
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



## 付费媒体

当通过[Adobe Experience Platform付费媒体源连接器](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/home)启用&#x200B;**付费媒体**&#x200B;渠道时（例如，Meta Ads或Google Ads），这些组件将添加到数据视图中。 它们可让您报告付费媒体实体、创意内容，并与您的Web和移动内容一起支出。

上述AI生成的[资产属性](#asset-attributes)和[体验属性](#experience-attributes)也可用于付费媒体创意。 相同的功能也适用于Web、移动和付费媒体渠道。

### 付费媒体维度

| 标题 | 描述 | 类型 |
|---|---|---|
| 广告网络 | 从中摄取付费媒体数据的广告平台。 | 维度 |
| 帐户名称 | 广告帐户的名称。 | 维度 |
| 营销活动名称 | 付费媒体营销活动的名称。 | 维度 |
| 广告组名称 | 广告组（Meta广告集/Google广告组）的名称。 | 维度 |
| 广告名称 | 单个广告的名称。 | 维度 |
| 体验名称 | 广告体验（创意合成）的名称。 | 维度 |
| 资产名称 | 创意资源的名称。 | 维度 |
| 促销活动状态 | 营销活动的状态。 | 维度 |
| 广告组状态 | 广告组的状态。 | 维度 |
| 广告状态 | 广告的状态。 | 维度 |
| 服务状态 | 指示实体当前是否正在交付的详细服务状态。 | 维度 |
| 帐户货币 | 广告帐户的货币。 | 维度 |
| 帐户时区 | 广告帐户的时区。 | 维度 |
| 帐户类型 | 广告帐户的类型。 | 维度 |
| 帐户业务名称 | 与广告帐户关联的业务名称。 | 维度 |
| 营销活动类型 | 营销活动的主要渠道类型。 | 维度 |
| 营销活动目标 | 营销活动的目标或目的。 | 维度 |
| 营销活动竞价策略 | 活动的竞价策略。 | 维度 |
| 营销活动预算类型 | 营销活动的预算分配类型。 | 维度 |
| 营销活动每日预算 | 每日预算金额（以广告帐户币种表示）。 | 维度 |
| 营销活动生命周期预算 | 生命周期预算金额（以广告帐户币种表示）。 | 维度 |
| 营销活动开始时间 | 营销活动开始的时间。 | 维度 |
| 营销活动结束时间 | 营销活动结束的时间。 | 维度 |
| 广告组类型 | 广告组的类型。 | 维度 |
| 广告组竞价策略 | 广告组的竞价策略。 | 维度 |
| 广告组优化目标 | 广告组的优化目标。 | 维度 |
| 广告组开始时间 | 广告组的开始时间。 | 维度 |
| 广告组结束时间 | 广告组结束的时间。 | 维度 |
| 广告类型 | 广告的类型/格式。 | 维度 |
| 广告审核状态 | 广告的审核/批准状态。 | 维度 |
| 广告Creative类型 | 广告使用的创意类型。 | 维度 |
| 广告标题 | 广告创意的标题/标题。 | 维度 |
| 广告Call to action | 广告创意的Call-to-action。 | 维度 |
| 广告目标URL | 广告的登陆/目标URL。 | 维度 |
| 广告显示URL | 在广告上显示URL。 | 维度 |
| 体验类型 | 广告体验的类型/格式。 | 维度 |
| 体验登陆页面URL | 体验的登陆页面URL。 | 维度 |
| 体验Call to action | call-to-action的体验。 | 维度 |
| 资产类型 | 创意资源的类型（例如，图像或视频）。 | 维度 |
| 资源宽度 | 资源的宽度（像素）。 | 维度 |
| 资源高度 | 资源的高度（像素）。 | 维度 |
| 资源宽高比 | 资源的宽高比。 | 维度 |
| 资产导向 | 资源的方向。 | 维度 |
| 设备类型 | 报告的量度的设备类型细分。 | 维度 |
| 放置环境 | 报告的量度的投放位置细分。 | 维度 |
| 平台 | 报告的量度的平台细分。 | 维度 |
| 国家/地区 | 所报告量度的国家/地区细分。 | 维度 |
| 区域 | 已报告量度的区域细分。 | 维度 |

{style="table-layout:fixed"}

### 付费媒体量度

| 标题 | 描述 | 类型 |
|---|---|---|
| 展示次数 | 广告显示的次数。 | 量度 |
| 点击量 | 广告的点击次数。 | 量度 |
| 支出 | 支出金额（以广告帐户币种表示）。 | 量度 |
| 转化 | 转换总数。 | 量度 |
| 转化值 | 转换的总值。 | 量度 |
| 范围 | 查看该广告的唯一人数。 | 量度 |
| 参与 | 与广告的互动次数。 | 量度 |
| 视频查看 | 视频查看次数。 | 量度 |
| 视频完成 | 观看至结束的视频数量。 | 量度 |
| 视频播放 | 视频播放的次数。 | 量度 |
| 购买 | 购买转换的次数。 | 量度 |
| 添加到购物车 | 添加到购物车转换的次数。 | 量度 |
| 潜在客户 | 商机转换次数。 | 量度 |
| 注册 | 注册转换的次数。 | 量度 |
| 下载 | 下载转换次数。 | 量度 |
| 订阅 | 订阅转换次数。 | 量度 |
| 登陆页面查看次数 | 登陆页面查看次数。 | 量度 |
| 点击后转化 | 归因于点击的转化。 | 量度 |
| 后视图转化 | 归因到视图的转化。 | 量度 |
| 总订单值 | 订单的总值。 | 量度 |
| 链接点击次数 | 链接点击次数。 | 量度 |
| 出站点击次数 | 出站点击次数。 | 量度 |
| 应用程序安装次数 | 应用程序安装次数。 | 量度 |
| 商机提交 | 潜在客户表单提交次数。 | 量度 |

{style="table-layout:fixed"}

### 付费媒体计算量度

| 标题 | 描述 | 类型 |
|---|---|---|
| 点进率 | 点击次数除以展示次数。 | 计算量度 |
| 每次点击成本 | 支出除以点击量。 | 计算量度 |
| 每毫升成本 | 每千次展示的成本。 | 计算量度 |
| 每次转换成本 | 支出除以转化。 | 计算量度 |
| 广告支出回报率 | 转化值除以支出。 | 计算量度 |
| 频率 | 印象除以范围。 | 计算量度 |
| 参与率 | 参与次数除以展示次数。 | 计算量度 |
| 视频完成率 | 视频完成次数除以视频播放次数。 | 计算量度 |
| 转化率 | 转化次数除以点击量。 | 计算量度 |
| 平均订单价值 | 订单总值除以购买量。 | 计算量度 |

{style="table-layout:fixed"}
