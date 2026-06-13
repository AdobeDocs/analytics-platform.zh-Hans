---
title: Customer Journey Analytics中的GA4报表
description: 查找每个GA4报表部分的Customer Journey Analytics等效项。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Customer Journey Analytics中的GA4报表

当您知道自己正在查看哪个GA4报告并想要在Analysis Workspace中重新创建其大致等效报告时，可使用此页作为查找参考。 报告按GA4的导航部分组织。 有关在将GA数据迁移到Customer Journey Analytics后可用的高级跨渠道报表方案，请参阅[Google Analytics数据报表](/help/use-cases/third-party/ga/report.md)。

## 实时

+++实时

GA4的实时报表显示过去30分钟内的活动 — 活动用户、触发的事件、用户的位置、推动流量的因素以及用户所在的页面。

Customer Journey Analytics没有单独的实时报表区域。 请改为在Analysis Workspace中构建一个面板并启用&#x200B;**[!UICONTROL 实时刷新]**&#x200B;切换开关（**Ultimate**&#x200B;包的一部分），以便其可视化图表每分钟更新一次：

1. 使用要监视的维度和量度构建[自由格式](/help/analysis-workspace/c-panels/freeform-panel.md)面板（切换还适用于[空白](/help/analysis-workspace/c-panels/blank-panel.md)、[归因](/help/analysis-workspace/c-panels/attribution.md)和[下一个或上一个项目](/help/analysis-workspace/c-panels/next-previous.md)面板）。 要镜像GA4的实时信息卡，请使用&#x200B;**[!UICONTROL Page]**、**[!UICONTROL Event type]**、**[!UICONTROL Referring Domain]**&#x200B;或&#x200B;**[!UICONTROL Countries]**&#x200B;作为维度，并将&#x200B;**[!UICONTROL Sessions]**&#x200B;作为量度。
2. 启用&#x200B;**[!UICONTROL 实时刷新]**&#x200B;切换功能，并选择一个介于&#x200B;**[!UICONTROL 最近15分钟]**&#x200B;到&#x200B;**[!UICONTROL 最近24小时]**&#x200B;之间的时段。 数据仅限于24小时滚动时段，并且面板每分钟刷新一次，刷新时间最长为30分钟。

实时报表支持事件级和会话级数据，且不能使用拼合，因此首选的是&#x200B;**[!UICONTROL 会话]**&#x200B;而非&#x200B;**[!UICONTROL 人员]**。 请参阅[使用实时报表](/help/components/real-time/use-real-time.md)以了解完整过程，并参阅[实时报表概述](/help/components/real-time/real-time.md)以了解授权和延迟详细信息。

+++

## 客户获取

+++用户获取（首次联系）

GA4的用户客户获取报表使用首次联系归因将每个用户归因于首次将他们带到您网站的渠道、来源和媒介。

在Analysis Workspace中，将&#x200B;**[!UICONTROL 首次联系]**&#x200B;归因模型应用于&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度。 必须先配置营销渠道，然后才能使用。 请参阅[创建营销渠道派生的字段](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)。

1. 将&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中。
2. 右键单击度量列标题并选择&#x200B;**[!UICONTROL 使用非默认归因模型]**。
3. 选择回溯时段适合您的分析的&#x200B;**[!UICONTROL 首次联系]**。

或者，使用[[!UICONTROL 归因]面板](/help/analysis-workspace/c-panels/attribution.md)对首次联系和最近联系渠道的性能进行并排比较。

+++

+++流量获取（基于会话）

GA4的“流量获取”报告使用基于会话的归因将每个会话归因于启动它的渠道、来源和媒介。 您可以按默认渠道组、来源/媒介、反向链接或营销活动对其进行划分。

在Analysis Workspace中，具有默认&#x200B;**[!UICONTROL 最近联系]**&#x200B;归因模型的&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度提供了基于会话的渠道报表：

1. 将&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中。
2. 将所需的量度拖动到默认&#x200B;**[!UICONTROL 事件]**&#x200B;量度旁边。

GA4的划分映射到以下Customer Journey Analytics维度：

* **渠道**： **[!UICONTROL 营销渠道]**。 Customer Journey Analytics没有内置渠道分组 — 使用&#x200B;**[!UICONTROL 营销渠道]**&#x200B;功能模板将它们定义为[派生字段](/help/data-views/derived-fields/derived-fields.md)，或者在使用Analytics源连接器时从Adobe Analytics结转规则（请参阅[使用营销渠道维度](/help/use-cases/aa-data/marketing-channels.md)）。
* **Source/媒体和反向链接**： **[!UICONTROL 反向链接域]**&#x200B;和&#x200B;**[!UICONTROL 反向链接类型]**。
* **营销活动**：未自动收集GA4的`utm_*`参数 — 在实施期间必须将每个参数映射到XDM字段，然后才能显示为维度。 如果促销活动值作为跟踪代码到达，请使用&#x200B;**[!UICONTROL 跟踪代码]**&#x200B;维度。

+++

+++归因和转化路径

ga4的归因报表（位于Advertising下）显示了不同渠道对转化的贡献情况，并允许进行模型比较和转化路径分析。

在Analysis Workspace中，使用[[!UICONTROL 归因]面板](/help/analysis-workspace/c-panels/attribution.md)：

1. 选择“面板”图标并将&#x200B;**[!UICONTROL 归因]**&#x200B;面板拖动到画布上。
2. 将&#x200B;**[!UICONTROL 营销渠道]**&#x200B;维度拖到&#x200B;**[!UICONTROL 添加Dimension]**&#x200B;框中。
3. 将您的转化量度（例如，购买事件）拖到&#x200B;**[!UICONTROL 添加量度]**&#x200B;框中。
4. 选择&#x200B;**[!UICONTROL 生成]**。

[!UICONTROL 归因面板]生成了一个模型比较表和[!UICONTROL 渠道流量]可视化图表，其中显示了访客在转换前采用的热门路径。 选择&#x200B;**[!UICONTROL 添加模型]**&#x200B;以同时比较多个归因模型。

+++

## 参与

+++页面和屏幕

GA4的“页面和屏幕”报表显示各个页面和应用程序屏幕的性能指标。

在Analysis Workspace中，将&#x200B;**[!UICONTROL 页面]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中，并添加所需的量度。 通用量度包括&#x200B;**[!UICONTROL 会话]**、**[!UICONTROL 人员]**、**[!UICONTROL 跳出率]**&#x200B;和&#x200B;**[!UICONTROL 每个会话逗留时间]**。

若要按URL路径结构（例如，`/blog/`或`/products/`）对页面进行分组，如果您的实施定义了&#x200B;**[!UICONTROL 网站区域]**&#x200B;维度，或创建一个[派生字段](/help/data-views/derived-fields/derived-fields.md)，该字段使用&#x200B;**[!UICONTROL URL解析]**&#x200B;函数来解析页面URL。 如果您维护明确的页面到区段映射，则[查找数据集](/help/connections/standard-lookups.md)可以改为提供分组。

+++

+++登陆页面

GA4的登陆页面报告显示了用户在开始会话时到达的页面。

在Analysis Workspace中，将&#x200B;**[!UICONTROL 登入页面]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中。 **[!UICONTROL 会话]**&#x200B;是此维度最相关的量度。

+++

+++事件

GA4的事件报表通过事件级别的量度显示每个事件触发的次数。

在GA4中，事件具有名称和可选参数（例如，带有参数`video_title`的事件`video_play`）。 在Customer Journey Analytics中，事件名称的标准维度是&#x200B;**[!UICONTROL 事件类型]**（源自`xdm.eventType`）。 事件参数映射到其他XDM字段，其名称取决于您的实施。

将&#x200B;**[!UICONTROL 事件类型]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中以列出所有事件类型，以及&#x200B;**[!UICONTROL 事件]**&#x200B;量度。

+++

+++关键事件（转化）

GA4的键事件报告（以前称为转化）按名称列出每个键事件及其计数 — 在GA4属性配置中标记为业务关键型的事件。

Customer Journey Analytics没有“关键事件”标记；每次交互都是一个事件，因此没有要打开的预设转化列表。

要按名称重新创建GA4的转化列表，请使用&#x200B;**区段作为行**。 [[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)不能将量度放置在该行位置，但可以将该区段放置在该处：

1. 对于每个转化，请创建一个隔离其事件的区段 — 例如，一个事件范围的区段，其中`xdm.eventType`等于`commerce.purchases`。 在表示转换之后命名每个区段（例如，**购买**）。
2. 将每个转化区段拖入[!UICONTROL 自由格式表]的行区域，每行一个。
3. 将&#x200B;**[!UICONTROL Events]**&#x200B;度量添加为列。 每一行显示转换的计数，镜像GA4的键事件列表。 请改用&#x200B;**[!UICONTROL 人员]**&#x200B;计算独特转化者。

要添加转化率，请创建定义为转化量度除以&#x200B;**[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 人员]**&#x200B;的计算量度（选择量度列表旁边的&#x200B;**+**&#x200B;图标）。

您在此处隔离的每个转化也可以定义为数据视图中的可重用量度。 有关如何设置该步骤，请参阅[常用量度](#common-metrics)下的&#x200B;**关键事件→自定义事件量度**&#x200B;条目。

+++

## 盈利

+++电子商务购买

ga4的“电子商务购买”报表显示产品级别的购买数据，包括项目、收入和数量。

在Customer Journey Analytics中，电子商务报表将&#x200B;**[!UICONTROL Product]**&#x200B;维度与购买量度一起使用。 此报表要求您的实施发送XDM商务数据（如`xdm.commerce.purchases`、`xdm.commerce.order`和`xdm.productListItems`）。

1. 将&#x200B;**[!UICONTROL Product]**&#x200B;维度拖动到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中。
2. 将诸如&#x200B;**[!UICONTROL 订单]**、**[!UICONTROL 收入]**&#x200B;和&#x200B;**[!UICONTROL 单位]**&#x200B;之类的电子商务指标拖动到默认&#x200B;**[!UICONTROL 事件]**&#x200B;指标旁边。

+++

+++购买历程(funnel)

GA4的购买历程报告显示了用户如何在您的购物funnel中移动 — 例如，从添加到购物车到开始结账再到购买 — 以及他们在哪里退出。

在Analysis Workspace中，使用[**[!UICONTROL 流失]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)可视化图表：

1. 选择“可视化图表”图标，然后将&#x200B;**[!UICONTROL 流失]**&#x200B;可视化图表拖动到画布上。
2. 找到&#x200B;**[!UICONTROL 页面]**&#x200B;维度并将其展开以显示单个页面值。
3. 将第一个funnel步骤（例如，产品页面）拖动到第一个&#x200B;**[!UICONTROL 添加接触点]**&#x200B;插槽。
4. 继续为每个步骤添加接触点。

流失可视化图表接受任何维度、量度或区段作为接触点，而不仅仅是页面，因此它匹配GA4基于事件的漏斗并扩展到混合事件、页面和区段的序列。

+++

+++促销活动

ga4的促销活动报表显示了内部促销活动（横幅、特色版面）如何推动产品交互。

在Customer Journey Analytics中，促销数据要求您捕获XDM架构字段中的促销展示次数和点击次数。 收集后，创建一个[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，该表包含包含提升名称维度的“展示次数”和“点击次数”量度。 与您的Customer Journey Analytics管理员合作，确认您的数据视图中提供了哪些促销数据。

+++

+++发布者广告

GA4的“发布者广告”报表显示来自Google Ad Manager或AdMob的广告收入，这些广告面向发布者货币化的资产。

Customer Journey Analytics没有本机发布者ad-revenue集成。 要报告此数据，请使用源连接器或直接数据引入将来自广告盈利平台（如Google Ad Manager或AdMob）的收入数据作为数据集引入Adobe Experience Platform。 摄取数据后，即可在Customer Journey Analytics中生成报表。

+++

## 维系

+++维系概述

GA4的“维系概述”报告结合了多种维系视图（新用户与旧用户）和一个同类群组图表，其中显示了在同一时期内回访的用户数量。

**新用户与返回用户**：使用&#x200B;**[!UICONTROL 第一个会话]**&#x200B;和&#x200B;**[!UICONTROL 返回会话]**&#x200B;区段作为[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中的行：

1. 将&#x200B;**[!UICONTROL 第一个会话]**&#x200B;区段从“组件”面板拖动到表的行区域，然后将&#x200B;**[!UICONTROL 返回会话]**&#x200B;区段拖动到其下方。
2. 将所需的指标与默认&#x200B;**[!UICONTROL 事件]**&#x200B;指标一起添加。
3. 若要显示一段时间内的趋势，请将[**[!UICONTROL 折线图]**](/help/analysis-workspace/visualizations/line.md)可视化图表拖动到表上方，然后按住ctrl并单击(Windows)或按住cmd并单击(Mac)每行以突出显示两个区段。

**一段时间内的保留率**：使用[**[!UICONTROL 同类群组表]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)可视化图表：

1. 选择“可视化”图标，并将&#x200B;**[!UICONTROL 同类群组表]**&#x200B;拖到画布上。
2. 将&#x200B;**[!UICONTROL 人员]**&#x200B;指标拖入“包含”和“返回标准”字段，然后选择&#x200B;**[!UICONTROL 生成]**。

[!UICONTROL 同类群组表]按人员的初始回访间隔对人员分组，并跟踪后续回访间隔内的回访行为；包含、回访和粒度标准均可配置。

+++

## 用户

+++人口统计详细信息

GA4的人口统计详细信息报告涵盖用户特征（年龄、性别和兴趣，由Google信号提供支持，要求用户登录到启用了个性化的Google帐户），以及位置（国家/地区、城市）和语言。

**位置**&#x200B;直接映射到Customer Journey Analytics维度：在[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中使用&#x200B;**[!UICONTROL 国家/地区]**、**[!UICONTROL 地区]**&#x200B;或&#x200B;**[!UICONTROL 城市]**，或者使用[[!UICONTROL 地图]](/help/analysis-workspace/visualizations/map.md)可视化图表查看地理概览（将&#x200B;**[!UICONTROL 人员]**&#x200B;指标拖动到&#x200B;**[!UICONTROL 添加指标]**&#x200B;插槽并选择&#x200B;**[!UICONTROL 生成]**）。

**年龄、性别和兴趣**&#x200B;需要第一方数据。 如果贵组织通过CRM、注册表单或基于同意的调查收集人口统计数据，请将其摄取为[配置文件数据集](/help/connections/create-connection.md#profile-dataset)，并将其加入事件数据。 此方法比GA4推断的Google信号模型产生更可靠的数据，因为它使用同意的第一方属性。

+++

+++技术详细信息

GA4的技术报告显示了浏览器、操作系统、屏幕分辨率和设备类别。

在Analysis Workspace中，以下维度映射到GA4的技术维度，每个维度均源自标准XDM字段：

| GA4技术维度 | Analysis Workspace维度 | XDM字段 |
|---|---|---|
| 浏览器 | **[!UICONTROL 浏览器]** | `xdm.environment.browserDetails.name` |
| 操作系统 | **[!UICONTROL 操作系统]** | `xdm.environment.operatingSystem` |
| 屏幕分辨率 | **[!UICONTROL 监视器分辨率]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| 设备类别（移动设备、台式机、平板电脑） | **[!UICONTROL 移动设备类型]** | `xdm.device.type` |
| 设备型号 | **[!UICONTROL 移动设备]** | `xdm.device.model` |

从“组件”面板将任意这些维度拖入[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。

>[!NOTE]
>
>由于现代浏览器减少了用户代理字符串中的详细信息，因此完整而准确的值取决于在Web SDK配置中收集[用户代理客户端提示](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints)。

+++

## 浏览

+++自由格式探索

GA4的自由格式浏览是一个空白画布表，其中包含可配置的行、列和可选的图表叠加。

Analysis Workspace的[**[!UICONTROL 自由格式表]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)是直接等效的，也是大多数Workspace项目的基础。 将任意维度拖到行中，将任意量度拖到列中，将任意区段拖到表上方的区段拖放区域中。

有关GA4 Explore与Workspace之间的术语映射，请参阅[Analysis Workspace快速入门](home.md#getting-started-in-analysis-workspace)。

+++

+++funnel探索

GA4的Funnel探索定义了一系列步骤，并测量每个步骤的完成情况和流失情况。

在Analysis Workspace中，使用[**[!UICONTROL 流失]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)可视化图表：

1. 选择“可视化图表”图标，然后将&#x200B;**[!UICONTROL 流失]**&#x200B;可视化图表拖动到画布上。
2. 将代表您第一步的维度、量度或区段拖到第一个&#x200B;**[!UICONTROL 添加接触点]**&#x200B;槽中。
3. 继续为序列中的每个后续步骤添加接触点。

由于任何维度、量度或区段都可以作为接触点，因此[!UICONTROL 流失]与GA4基于事件的漏斗相匹配，并扩展到混合了事件、页面和区段的跨渠道序列。

+++

+++路径探索

GA4的路径探索（Universal Analytics称为此用户流）可可视化用户导航的页面或事件序列。

在Analysis Workspace中，使用[**[!UICONTROL 流量]**](/help/analysis-workspace/visualizations/c-flow/flow.md)可视化图表：

1. 选择“可视化图表”图标，并将&#x200B;**[!UICONTROL 流量]**&#x200B;可视化图表拖到画布上。
2. 从要路径化的维度中拖动一个值（例如&#x200B;**[!UICONTROL Page]**&#x200B;或&#x200B;**[!UICONTROL 事件类型]**&#x200B;值）到流的中心。
3. 该可视化图表显示了用户在该时间点之前和之后执行的操作。

[!UICONTROL 流量]可视化图表是交互式的 — 选择任意节点可沿任一方向进一步展开路径。 您可以使用任何维度，这样您就可以在页面、事件、营销渠道或自定义链接上访问路径。

+++

+++区段重叠

GA4的区段重叠探索显示多个用户区段如何相交，以维恩图形式显示。

在Analysis Workspace中，使用[**[!UICONTROL 维恩图]**](/help/analysis-workspace/visualizations/venn.md)可视化图表：

1. 选择“可视化图表”图标，然后将&#x200B;**[!UICONTROL 维恩图]**&#x200B;可视化图表拖到画布上。
2. 最多从“组件”面板将三个区段拖入到可视化中。

维恩图显示交叉点大小，下面的[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)显示基础数据。

+++

+++同类群组探索

GA4的同类群组探索按共享特征（通常是客户获取日期）对用户进行分组，并跟踪他们在一段时间内的行为。

在Analysis Workspace中，使用[**[!UICONTROL 同类群组表]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)可视化图表：

1. 选择“可视化”图标，并将&#x200B;**[!UICONTROL 同类群组表]**&#x200B;拖到画布上。
2. 将&#x200B;**[!UICONTROL 人员]**&#x200B;指标拖动到“包含”和“返回标准”字段中。
3. 选择&#x200B;**[!UICONTROL 生成]**。

[!UICONTROL 同类群组表]按人员的初始时间段对其进行分组并跟踪后续时间段的回访行为。 默认情况下，它会根据客户获取日期进行分组，但包含、返回和粒度标准均可配置。

+++

+++用户资源管理器

GA4的用户资源管理器显示单个用户、其会话历史记录和事件的时间线。

Customer Journey Analytics以两种方式支持人员级别分析：

* **启用拼接**：创建特定人员ID值的区段范围，并将其应用于任何Workspace项目。 **[!UICONTROL 人员]**&#x200B;容器跨会话和渠道分离该人员的拼合活动。
* **原始事件数据**：在Adobe Experience Platform UI中使用&#x200B;**数据集预览**&#x200B;来检查原始XDM事件记录。 此视图对于实施验证和调试单个事件非常有用。

+++

+++用户生命周期

GA4的用户生命周期探索会测量每个用户在与您的业务的整个关系中（而不是在固定日期范围内）的累计价值和参与度。 它将历史生命周期量度与Google对购买概率、流失概率和预测收入的机器学习预测结合使用。

这些映射到Customer Journey Analytics可分为两个部分：

**历史生命周期值**&#x200B;可以本机实现。 由于Customer Journey Analytics会在您的完整数据保留窗口内报告，因此您可以设置一个较长的日期范围，并聚合每个人在该回顾中的累计收入和参与度。 使用拼接或永久人员ID，**[!UICONTROL 人员]**&#x200B;容器将该活动与个人相关联，并且计算量度表示每个人的值。 结果不是无限的生命周期，而是近似于无限的漫长、可配置的回顾。

**预测生命周期值**&#x200B;未内置。 Customer Journey Analytics没有产品内购买概率、流失率或预测收入模型。 要使用预测分数，请在外部（例如，在CRM或数据科学工作流中）计算这些分数，并将它们作为用户档案数据集引入Customer Journey Analytics，然后将其作为维度或量度呈现。 Adobe建议与实施顾问合作来设计此方法。

+++

## 常用量度

+++活动用户→人员

GA4的&#x200B;**活动用户**&#x200B;计算在日期范围内至少有一个参与会话的用户。

在Customer Journey Analytics中，最接近的等效项是&#x200B;**[!UICONTROL 人员]**，这是日期范围内的唯一人员ID计数。 [!UICONTROL 人员]包含所有已识别的人员，而不管参与度级别如何，因此对于具有大量被动流量的站点，该数量通常高于GA4的主动用户。

要更密切地比较行为，请应用[参与会话区段](compare-data.md#engaged-sessions)以将[!UICONTROL 人员]量度范围限定于符合您的参与标准的用户。

+++

+++参与会话数→计算量度

GA4的&#x200B;**参与会话**&#x200B;计算持续10秒或更多秒、具有2次或更多页面查看或至少包含一个关键事件的会话。

Customer Journey Analytics没有内置的参与会话量度 — 您将其定义为捕获参与条件的区段，然后将其与&#x200B;**[!UICONTROL 会话]**&#x200B;量度一起使用。 请参阅[参与会话](compare-data.md#engaged-sessions)以了解推荐的方法以及如何从中获取参与率。

+++

+++参与率→计算量度

GA4的&#x200B;**参与率**&#x200B;是参与会话的百分比：参与会话数除以会话总数。

在Customer Journey Analytics中，根据参与会话定义将其构建为计算量度。 有关分步说明，请参阅[参与会话](compare-data.md#engagement-rate)。

+++

+++平均参与时间→每个会话逗留时间

GA4的&#x200B;**平均参与时间**&#x200B;测量了在参与会话期间，浏览器或应用程序处于前台的平均时间。

在Customer Journey Analytics中，使用&#x200B;**[!UICONTROL 会话持续时间（秒）]**，它测量会话中从第一个事件到最后一个事件的经过时间。 此组件包括用户可能未主动参与的时段，因此值可以不同于GA4的测量值。 它是最接近的内置等效项。

+++

+++事件计数→事件

GA4的&#x200B;**事件计数**&#x200B;是记录任何事件的总次数。

在Customer Journey Analytics中，等效的量度是&#x200B;**[!UICONTROL 事件]** — 数据集中选定日期范围和应用的区段的事件记录总数。

+++

+++会话→会话

GA4的&#x200B;**会话**&#x200B;和Customer Journey Analytics的&#x200B;**[!UICONTROL 会话]**&#x200B;均度量日期范围内的会话数。 计数可能会因会话定义规则不同而异。 有关详细信息，请参阅[为什么GA4和Customer Journey Analytics数据不同](compare-data.md#sessions)。

+++

+++应用于人员→首次会话区段的新用户

GA4的&#x200B;**新用户**&#x200B;计算其首次会话在选定日期范围内的用户。

在Analysis Workspace中：

1. 在“组件”面板中找到&#x200B;**[!UICONTROL 第一个会话]**&#x200B;区段。
2. 将其拖到[[!UICONTROL 自由格式表]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)上方的区段拖放区域。
3. 使用&#x200B;**[!UICONTROL 人员]**&#x200B;指标计算独特的新人员。

+++

+++跳出率→跳出率（包含注意事项）

GA4的&#x200B;**跳出率**&#x200B;是未参与的会话的百分比（少于10秒、无键事件、少于2次页面查看）。 这是参与率的倒数。

Customer Journey Analytics的&#x200B;**[!UICONTROL 跳出率]**&#x200B;量度默认使用其他定义，可根据数据视图进行配置。 这些差异会产生截然不同的数字，用于测量不同的行为。

要估算Customer Journey Analytics中GA4的跳出率，请构建一个“参与率”量度，然后使用定义为`1 - Engagement Rate`的第二个计算量度将其反转。 有关分步生成，请参阅[参与会话](compare-data.md#engagement-rate)。

有关定义差异的详细说明，请参阅[为什么GA4和Customer Journey Analytics数据不同](compare-data.md#bounce-rate)。

+++

+++关键事件→自定义事件量度

GA4的&#x200B;**关键事件**（以前称为Conversions）是在GA4属性配置中指定为重要业务结果的事件。

在Customer Journey Analytics中，转化是在数据视图中配置的自定义事件量度。 任何XDM事件都可以公开为度量，并且可以将度量设置为有条件地递增XDM字段值，例如，当`xdm.eventType`等于`commerce.purchases`时，递增的&#x200B;**[!UICONTROL 购买]**&#x200B;度量。 在Analysis Workspace的“组件”面板中通过相关量度的标签找到相关量度；该名称反映了管理员配置该量度的方式。

要重现GA4的关键事件&#x200B;*报告*（每个转化及其计数的列表），请参阅此页面上[参与度](#engagement)下的&#x200B;**关键事件（转化）**&#x200B;条目。

+++

>[!MORELIKETHIS]
>
>* [报告Google Analytics数据](/help/use-cases/third-party/ga/report.md)
