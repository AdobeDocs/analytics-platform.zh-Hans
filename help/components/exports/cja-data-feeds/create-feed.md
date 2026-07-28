---
title: 创建数据馈送
description: 了解如何创建数据馈送以及提供给 Adobe 的文件信息。
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: bb3fcdcd879c503c311a58cf2fd982dd38305c6a
workflow-type: tm+mt
source-wordcount: 3225
ht-degree: 27%

---

# 创建数据馈送

{{release-limited-testing}}

创建数据馈送时，您为 Adobe 提供：

* 您想将原始数据文件发送到那里的目标的信息

* 您想在每一个文件中包含的数据

* 发送数据的频率（包括捕获延迟送达点击的处理延迟）

在创建数据馈送之前，重要的是要对数据馈送有基本的了解，并确保满足所有前提条件。 更多信息请参阅[数据馈送概述](data-feed-overview.md)。

## 创建和配置数据馈送 {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="清单"
>abstract="选择是否在每次数据馈送传递时附带一个清单文件。 清单文件包含数据馈送中每个文件的相关信息。 如果用一个包发送数据馈送数据，您还可以选择包含一个完成文件，但建议包含清单文件。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="完成时通知"
>abstract="指定一个或多个电子邮件地址，用于在数据馈送发送完成后接收通知。 多个电子邮件地址必须使用逗号分隔。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="回顾日期范围"
>abstract="控制在处理数据馈送传递时 Customer Journey Analytics 回顾的时间范围。<br/>此设置不会改变频率窗口（小时或天）。 但是，回顾日期范围可能会影响传递的数据。 细分资格筛选、会话计算、某些派生字段转换以及维度持久性都会受到回溯日期范围的影响。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="用户代理数据和设备查找数据不能存在于同一个数据馈送配置中。"

<!-- markdownlint-enable MD034 -->

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 从界面右上角的应用切换器&#x200B;[!UICONTROL **应用程序**]&#x200B;中选择 ![Customer Journey Analytics](/help/assets/icons/Apps.svg)。

1. 在顶部导航栏中，转到&#x200B;[!UICONTROL **组件**] > [!UICONTROL **数据馈送**]。

1. 选择屏幕右上角的&#x200B;[!UICONTROL **创建**]。

   或者，如果之前未创建任何数据馈送，则在空表中选择&#x200B;[!UICONTROL **创建数据馈送**]。

   显示的页面具有以下选项卡： [!UICONTROL **详细信息**]、[!UICONTROL **数据结构**]&#x200B;和&#x200B;[!UICONTROL **投放**]。

   ![新数据馈送页面](assets/data-feed-new.png)

1. 在&#x200B;[!UICONTROL **详细信息**]&#x200B;选项卡上，完成以下字段：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **名称**] | 数据馈送的名称。 名称在所选数据视图中必须是唯一的，长度最多为255个字符。<!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **标记**] | 将任何标记应用到数据馈送以方便分类。<!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **描述**] | 指定数据馈送的说明（最多500个字符）。 编辑数据馈送时，您添加的描述可见。 |
   | [!UICONTROL **数据视图**] | 选择包含要导出的数据的数据视图。<p>选择数据视图时，请考虑以下事项：</p> <ul><li>如果为同一数据视图创建了多个数据馈送，则每个数据馈送必须具有不同的列定义。</li><li>可用列的列表取决于所选数据视图所属的登录公司。 如果更改数据视图，则可用列的列表可以更改。 </li></ul> |

1. 选择&#x200B;[!UICONTROL **下一步**]。

1. 在&#x200B;[!UICONTROL **数据结构**]&#x200B;选项卡上，确保在&#x200B;**[!UICONTROL 数据视图]**&#x200B;字段中选择了正确的数据视图。

   <!--add screenshot-->

1. 在&#x200B;[!UICONTROL **区段**]&#x200B;下拉菜单中，搜索并选择任何区段以过滤馈送中包含的数据。

   应用多个区段时，它们与一个AND运算符连接在一起。 （要使用OR运算符连接区段，必须首先在区段生成器中创建新区段，然后将新区段应用于数据馈送。）

1. 将组件添加到数据馈送配置。 左边栏仅显示对数据馈送有效的组件。

   * **拖放**：将组件从左边栏拖到画布上。 按住&#x200B;**[!UICONTROL Shift]**，或按住&#x200B;**[!UICONTROL Command]** (macOS)或&#x200B;**[!UICONTROL Ctrl]** (Windows)以同时选择和拖动多个组件。
   * **加号按钮**：选择左边栏中任何组件旁边的加号![添加](/help/assets/icons/Add.svg)图标以将其添加到画布中。
   * **[!UICONTROL 全部显示]**：选择组件列表底部的&#x200B;**[!UICONTROL 全部显示]**&#x200B;以打开显示所有可用组件的对话框。 选中要添加的每个组件旁边的复选框，然后选择&#x200B;**[!UICONTROL 添加选定项]**。 当搜索词或筛选器标记在左边栏中处于活动状态时，还会显示&#x200B;**[!UICONTROL 全部添加]**&#x200B;按钮，允许您一次添加所有筛选结果。

   添加属于XDM数组字段的组件（例如，Adobe Journey Optimizer建议字段）时，它以可折叠嵌套组的形式出现在画布上，而不是平面项。 该组反映底层数据结构，并在导出的文件中输出为嵌套数组。

   <!--add screenshot-->

   +++ 始终包含在数据馈送中的维度

   默认情况下，每个数据馈送中都包含以下维度，且无法删除这些维度：

   | 维度名称 | 注释 | 数据馈送 | 其他报表 |
   |---|---|---|---|
   | 时间戳 UTC | 事件发生日期和时间，以UTC时区表示。 支持亚秒（微秒）粒度。 | 必需 | 不可用 |
   | 行 ID | 数据馈送中包含的每一行的唯一标识符。 | 必需 | 不可用 |
   | 会话 ID | 数据馈送中包含的每个会话的唯一标识符。 | 必需 | 不可用 |
   | 人员 ID | 数据视图和连接的人员标识符 | 必需 | 可选标准 |
   | 帐户ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 使用帐户容器时的帐户ID | 必需 | 可选标准 |

   +++

   +++ 不能包含在数据馈送中的维度

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

   +++

   +++ 无法在数据馈送中一起使用的维度

   >[!IMPORTANT]
   >
   >某些维度不能在Experience Platform数据集中一起使用，因此无法包含在同一个数据馈送中。
   >
   >如果您选择在您的数据馈送中包含&#x200B;**用户代理**&#x200B;或&#x200B;**移动设备ID**&#x200B;维度，则下面列出的维度无法添加到数据馈送中。
   >
   >如果您使用Web SDK，此限制在数据到达Experience Platform数据集之前在数据流中实施。 有关详细信息，请参阅数据收集指南中的[创建和配置数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure)中的[配置设备查找](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/datastreams/configure#geolocation-device-lookup)。

   以下维度不能与&#x200B;**用户代理**&#x200B;或&#x200B;**移动设备ID**&#x200B;维度一起使用：

   * 浏览器类型
   * 浏览器
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

   +++

   +++ 必须在数据馈送中替换的量度

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

   +++

   +++ 可选标准组件

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

   +++

1. （可选）通过拖动组件对画布上的组件重新排序。 您定义的顺序将保留为导出数据馈送文件中的列顺序。

1. （可选）在继续之前，请使用页面右侧的&#x200B;**[!UICONTROL 信息源摘要]**&#x200B;和&#x200B;**[!UICONTROL 架构预览]**&#x200B;面板来查看您的数据结构：

   * **[!UICONTROL 信息源摘要]**&#x200B;显示您添加的组件、列、维度和量度总数的实时计数。
   * **[!UICONTROL 架构预览]**&#x200B;显示了数据馈送架构的JSON表示形式，该表示形式会在您添加或重新排序组件时更新。
   * 使用&#x200B;**[!UICONTROL 示例行]**&#x200B;按钮可打开一个显示示例输出行的对话框，以便您可以验证结构是否正确显示。 此对话框仅显示示例数据，而不反映您的实际数据。

   <!--add screenshot-->

1. 在&#x200B;[!UICONTROL **投放**]&#x200B;选项卡的&#x200B;[!UICONTROL **计划**]&#x200B;部分中，选择要创建的馈送类型（实时或回填），然后指定报表时段、频率和其他配置选项：

   <!--add screenshot-->

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **馈送类型**] | 选择要创建的信息源类型：<ul><li>[!UICONTROL **实时馈送**]：导出当前和未来的数据。</li><li>[!UICONTROL **回填馈送**]：导出历史数据。 </li></ul> |
   | [!UICONTROL **开始日期**] | 数据馈送开始的日期。 对于实时馈送，这必须是今天或未来的日期。 对于回填馈送，此日期必须是数据视图的数据保留窗口中的过去日期。 开始日期基于数据视图的时区。 |
   | [!UICONTROL **到期日期**] <br/>仅适用于实时馈送 | 数据馈送过期且不再运行的日期。 日期基于数据视图的时区。 |
   | [!UICONTROL **结束日期**]<br/>&#x200B;仅适用于回填馈送 | 数据馈送结束的日期。 结束日期不能是将来的日期。 日期基于数据视图的时区。 |
   | [!UICONTROL **频率**] | 选择应发送数据馈送的频率。 时间戳位于频率范围内的事件将包含在数据馈送交付中。 [!UICONTROL **回顾日期范围**]&#x200B;和&#x200B;[!UICONTROL **处理延迟**]&#x200B;字段也会影响所选投放频率的数据中包含哪些事件。<p>对于实时馈送，选择以包含一小时的数据或一天的数据。 对于回填馈送，此字段已锁定为&#x200B;**每日**，无法更改。</p><ul><li>**每日**：馈送包含一整天的数据，从数据视图时区的午夜到午夜。 <p>回填馈送需要此选项，而实时馈送则可选此选项。</p></li><li>**小时**：馈送包含一小时的数据。 <p>此选项仅对实时馈送可用。</p></li></ul> |
   | [!UICONTROL **回顾日期范围**] | 控制在处理数据馈送传递时 Customer Journey Analytics 回顾的时间范围。 默认值为30天。 <p>此设置不会更改频率窗口（小时或天），该窗口定义要包含在数据馈送输出中的事件的时间范围。 但是，回顾日期范围可能会以下列方式影响投放的数据： </p><ul><li>**区段鉴别**：将区段应用于您的数据馈送定义时，回顾日期范围内的任何事件都会确定人员是否符合条件。 区段的容器设置确定范围。 (可能的容器包括：“人员”、“会话”或“事件”。 B2B具有以下附加容器：全球客户、客户、商机、购买团体。)  <p>例如，如果使用了人员容器并且该人员在回顾日期范围内符合条件，则该人员在频率窗口期间的所有事件也符合条件。</p></li><li>**会话计算**：会话边界是使用回顾日期范围内的数据计算的。</li><li>**派生字段转换**：引用容器的任何派生字段函数在数据馈送导出中使用回顾日期范围。</li><li>**Dimension持久性**：如果选择在单个维度上设置持久性，则还需要选择到期时间，以确定维度项在从中设置它的事件之外保持多久。 <p>当数据视图中的过期时间设置为以下任一选项时，回顾日期范围会影响维度持久性：</p><ul><li>对于数据馈送定义中使用&#x200B;[!UICONTROL **报告窗口**]&#x200B;作为其到期时间的每个维度，回顾日期范围将成为新的报告窗口。</li><li>对于数据馈送定义中使用&#x200B;[!UICONTROL **自定义时间**]&#x200B;作为其到期时间的每个维度，如果选择的自定义时间超出回顾日期范围，则忽略自定义时间，并将回顾日期范围用于维度到期。<p>有关在数据视图中设置维度的持久性的详细信息，请参阅[持久性组件设置](/help/data-views/component-settings/persistence.md)。</p></li></ul> |
   | [!UICONTROL **处理延迟**] | 选择在处理数据馈送文件之前等待的时间。 默认值为2小时。 在处理延迟期间传入的任何迟到的点击都包含在数据馈送中。 <p>处理延迟可用于多种原因，例如为移动设备实施提供使离线设备联机并发送数据的机会，或者在管理以前处理的文件时容纳组织的服务器端进程。 </p><p>馈送可能会延迟2、3、4或8小时。</p><p>会话必须在处理延迟截止之后开始才能被包含；在截止之前开始并在处理延迟内结束的会话不包含在内。</p> |
   | [!UICONTROL **压缩格式**] | 为传送到云目标的Parquet输出文件选择压缩格式。 从以下格式中选择：<ul><li>[!UICONTROL **Snappy**]：文件大小适中的快速压缩和解压缩。 现代数据平台（如BigQuery、Snowflake和Apache Spark）广泛支持。</li><li>[!UICONTROL **GZip**]：广泛兼容，包括与本身不支持Snappy的工具兼容。 如果您的下游管道需要广泛识别的压缩标准，则建议使用。</li><li>[!UICONTROL **Z标准(Zstd)**]：压缩效率高，解压缩速度快。 如果优先考虑最小化文件大小，并且您的工具支持Zstd，则适合。</li></ul> |

1. 在&#x200B;[!UICONTROL **投放**]&#x200B;选项卡的&#x200B;[!UICONTROL **目标**]&#x200B;部分中，配置要将数据发送到的目标。

   >[!NOTE]
   >
   >在配置报表目标时，请考虑以下事项：
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* 您之前配置的任何云帐户均可用于数据馈送。 您可以从位置管理器的[组件>导出>位置帐户](/help/components/exports/cloud-export-accounts.md)中配置云帐户。
   >
   >* Cloud帐户与您的Customer Journey Analytics用户帐户相关联。 其他用户无法使用或查看您配置的云帐户，除非您将其提供给组织中的所有用户。
   >
   >* 您可以在[组件>导出>位置](/help/components/exports/cloud-export-locations.md)中编辑从“位置”管理器创建的任何位置。

   请完成以下字段：

   | 字段 | 功能 |
   |---------|----------|
   | [!UICONTROL **查看所有用户的目标**] | 如果您是系统管理员，则可以启用此选项以查看由组织中的所有用户创建的目标。 禁用此选项后，仅显示您创建的目标。 |
   | [!UICONTROL **帐户**] | 执行以下其中一项操作：<ul><li>**使用现有帐户：**&#x200B;选择&#x200B;**[!UICONTROL 帐户]**&#x200B;字段旁边的下拉菜单。 或者，开始键入帐户名称，然后从下拉菜单中选择该名称。 <p>只有在配置帐户或与您所属的某个组织共享帐户后，您才可以使用帐户。</p></li><li>**创建新帐户：**&#x200B;在&#x200B;**[!UICONTROL 帐户]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 添加帐户]**。 有关如何配置帐户的信息，请参阅[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)。</li></ul> |
   | [!UICONTROL **位置**] | 执行以下其中一项操作：<ul><li>**使用现有位置：**&#x200B;选择&#x200B;**[!UICONTROL 位置]**&#x200B;字段旁边的下拉菜单。 或者，开始键入位置名称，然后从下拉菜单中选择该位置。</li><li>**创建新位置：**&#x200B;在&#x200B;**[!UICONTROL 位置]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 添加位置]**。 有关如何配置位置的信息，请参阅[配置云导出位置](/help/components/exports/cloud-export-locations.md)。</li></ul> |
   | [!UICONTROL **完成时通知**] | 指定一个或多个电子邮件地址，在成功发送数据馈送或无法发送数据馈送后，应将通知发送到这些地址。 多个电子邮件地址必须使用逗号分隔。 |
   | [!UICONTROL **启用清单**] | 选择是否在每次数据馈送传递时附带一个清单文件。 清单文件包含数据馈送中包含的每个文件的信息。 |

1. 选择&#x200B;**[!UICONTROL 保存]**。


