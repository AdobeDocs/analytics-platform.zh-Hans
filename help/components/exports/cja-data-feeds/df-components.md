---
title: Customer Journey Analytics数据馈送中可用的组件
description: 了解在创建Customer Journey Analytics数据馈送时，哪些维度和量度是必需的、不受支持的、受限制的，或者必须被替换。
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: adc7e85339e89c181375c0d3ea5c228d473239a7
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 43%
---
# 数据馈送中的组件可用性

{{release-limited-testing}}

并非所有Customer Journey Analytics组件都可在数据馈送中使用。 某些维度包含在每个数据馈送中，某些组件无法包含，并且某些量度必须替换为替代量度。

使用以下信息了解在[创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)时可以包含的组件。

## 必需维度 {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="必需维度"
>abstract="每个数据馈送都必须包含特定维度，这些维度的名称旁会显示&#x200B;**必需**&#x200B;标签。 这些维度提供进行事件级别分析所需的最基本结构。"

<!-- markdownlint-enable MD034 -->

默认情况下，每个数据馈送中都包含以下维度，且无法删除这些维度：

| 维度名称 | 注释 | 数据馈送 | 其他报表 |
|---|---|---|---|
| 时间戳 UTC | 事件发生日期和时间，以UTC时区表示。 支持亚秒（微秒）粒度。 | 必需 | 不可用 |
| 行 ID | 数据馈送中包含的每一行的唯一标识符。 | 必需 | 不可用 |
| 会话 ID | 数据馈送中包含的每个会话的唯一标识符。 | 必需 | 不可用 |
| 人员 ID | 数据视图和连接的人员标识符 | 必需 | 可选标准 |
| 帐户ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 使用帐户容器时的帐户ID | 必需 | 可选标准 |

## 不支持的维度 {#unsupported-dimensions}

Customer Journey Analytics标准维度不能包含在数据馈送中。 下表列出了这些维：

| 维度名称 | 注释 | 数据馈送 |
|---|---|---|
| 5 分钟 | 发生事件时的五分钟间隔（向下舍入） | 不可用 |
| 15 分钟 | 发生事件时的15分钟间隔（向下舍入） | 不可用 |
| 30 分钟 | 发生事件时的三十分钟间隔（向下舍入） | 不可用 |
| 日 | 发生事件的日期 | 不可用 |
| 每周时间 | 事件发生在一周中的哪一天 | 不可用 |
| 月中几号 | 发生事件的日期 | 不可用 |
| 小时 | 发生事件的小时（向下舍入） | 不可用 |
| 小时 | 发生事件的一天中的第几个小时（向下舍入） | 不可用 |
| 分钟 | 发生事件的分钟数（向下舍入） | 不可用 |
| 一小时中的第几分钟 | 发生事件时所用的分钟（向下舍入） | 不可用 |
| 月 | 发生事件的月份 | 不可用 |
| 月份 | 发生事件的月份 | 不可用 |
| 季度 | 发生事件的季度 | 不可用 |
| 季度 | 发生事件的季度 | 不可用 |
| Second | 发生事件后（向下舍入） | 不可用 |
| 周 | 发生事件的周 | 不可用 |
| 一年中的第几周 | 事件发生的一年中的第几周 | 不可用 |
| 年 | 发生事件的年份 | 不可用 |

## 不支持的指标 {#unsupported-metrics}

以下Customer Journey Analytics标准量度不能包含在数据馈送中：

| 量度名称 | 注释 | 数据馈送 |
|---|---|---|
| Adobe访客配置文件 | | 不可用 |
| Adobe机会联盟 | | 不可用 |
| Adobe机会配置文件 | | 不可用 |
| Adobe帐户联盟 | | 不可用 |
| Adobe帐户配置文件 | | 不可用 |
| Adobe采购组联盟 | | 不可用 |
| Adobe购买组配置文件 | | 不可用 |
| Adobe全球客户联盟 | | 不可用 |
| Adobe全局帐户配置文件 | | 不可用 |
| Adobe人事联合会 | | 不可用 |
| Adobe人员配置文件 | | 不可用 |

## 不能一起使用的维度 {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

<!-- pretty sure this isn't being used -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="用户代理数据和设备查找数据不能包含在同一数据馈送配置中。"

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>某些维度不能在Experience Platform数据集中一起使用，因此无法包含在同一个数据馈送中。
>
>如果选择在数据馈送中包含&#x200B;**用户代理**&#x200B;或&#x200B;**移动设备ID**&#x200B;维度，则无法将下面列出的维度添加到数据馈送中。
>
>如果您使用Web SDK，此限制在数据到达Experience Platform数据集之前在数据流中实施。 有关详细信息，请参阅数据收集指南中的[创建和配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)中的[配置设备查找](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure#geolocation-device-lookup)。

以下维度不能与&#x200B;**用户代理**&#x200B;或&#x200B;**移动设备ID**&#x200B;维度一起使用：

>[!NOTE]
>
>以下列表使用缺省的维名称。 在数据视图中重命名的维度会以其自定义名称显示在数据馈送中。


* 浏览器类型
* 浏览器
* 浏览器ID
* 移动设备制造商
* 移动设备类型
* 移动设备音频支持
* 移动设备 DRM
* 移动设备 Java VM
* 移动设备信息服务
* 移动设备图像支持
* 移动设备颜色深度
* 移动设备网络协议
* 移动设备号码
* 移动设备电子邮件最大长度
* 移动设备邮件修饰
* 移动设备按键通话
* 移动设备屏幕宽度
* 移动设备浏览器 URL 最大长度
* 移动设备操作系统（已弃用）
* 移动设备屏幕高度
* 移动设备视频支持
* 移动设备 cookie 支持
* 移动设备书签最大长度
* 移动设备屏幕大小
* 移动设备名称
* 操作系统类型
* 操作系统
* 操作系统Id

## 需要替换的量度 {#substitute-metrics}

必须替换以下Customer Journey Analytics指标：

| 量度名称 | 注释 | 数据馈送 |
|---|---|---|
| 帐户 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 基于连接中指定的帐户ID | 不可用。 使用帐户ID的不同计数。 |
| 购买组[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 基于关联中的购买群组ID购买群组 | 不可用。 使用不同于购买组ID的计数。 |
| 事件 | 来自连接中所有事件数据集的行数 | 不可用。 使用行ID的不同计数。 |
| 全球帐户 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 基于连接中的全局帐户ID | 不可用。 使用全局帐户ID的不同计数。 |
| 机会 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 基于连接中的机会ID的销售机会 | 不可用。 使用不同于机会ID的计数。 |
| 人员 | 基于连接中指定的人员ID | 不可用。 使用人员ID的不同计数。 |
| 对话 | 对话数 | 不可用。 使用对话ID的不同计数。 |
| 会话结束 | 会话的最后一个事件的事件数 | 不可用 |
| 会话开始 | 会话的第一个事件的事件数 | 不可用 |
| 会话 | 基于数据视图的会话设置 | 不可用。 使用会话ID的不同计数。 |
| 逗留时间（秒） | 汇总两个不同维度值之间的时间 | 不可用 |

## 可选标准组件 {#optional-standard-components}

| 组件名称 | 类型 | 注释 | 数据馈送 |
|---|---|---|---|
| 上午/下午 | 时间划分维度 | 上午或下午 | 不可用 |
| 批次 ID | 维度 | Experience Platform批次的标识符 | 可用 |
| 数据集 ID | 维度 | Experience Platform数据集的标识符 | 可用 |
| 月中几号 | 时间划分维度 | 1-31 | 不可用 |
| 每周时间 | 时间划分维度 | 星期一到星期日 | 不可用 |
| 每年的某一天 | 时间划分维度 | 1-366 | 不可用 |
| 事件深度 | 维度 | 顺序数值（1、2、3等） 分配给会话中的每个事件交互<p>在每个新会话开始时重置</p> | 可用 |
| 小时 | 时间划分维度 | 0-23 | 不可用 |
| 月份 | 时间划分维度 | 1-12月份 | 不可用 |
| 首次会话 | 量度 | 个人在报告窗口内的首次定义的会话 | 不可用 |
| 返回会话 | 量度 | 非个人首次会话的会话 | 不可用 |
| 人员ID命名空间 | 维度 | 人员ID包含的ID类型（例如，电子邮件或Cookie ID） | 可用 |
| 全局帐户ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 维度 | 使用全局帐户容器时的全局帐户ID | 可用 |
| 机会ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 维度 | 使用Opportunity容器时的机会ID | 可用 |
| 购买群ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 维度 | 使用购买组容器时购买组ID | 可用 |
| 季度 | 时间划分维度 | 第一季度、第二季度、第三季度和第四季度 | 不可用 |
| 重复会话 | 量度 | 不是个人的首次会话 | 不可用 |
| 会话类型 | 维度 | 两个值：首次或返回 | 不可用 |
| 每个事件逗留时间 | 维度 | 将耗时指标装入事件桶 | 不可用 |
| 每个会话逗留时间 | 维度 | 将耗时指标装入会话桶 | 不可用 |
| 每人逗留时间 | 维度 | 将耗时指标装入人员桶 | 不可用 |
| 周末/工作日 | 时间划分维度 | 周末或工作日 | 不可用 |
