---
title: 创建数据馈送
description: 了解如何创建数据馈送以及提供给 Adobe 的文件信息。
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: e7c2598015d3ee271bb7e0f64937fd1c457b5433
workflow-type: tm+mt
source-wordcount: 4033
ht-degree: 20%

---

# 创建数据馈送

{{release-limited-testing}}

创建数据馈送时，您向 Adobe 提供：

* 您想将原始数据文件发送到那里的目标的信息

* 您想在每一个文件中包含的数据

* 发送数据的频率（包括用于捕获延迟到达事件的处理延迟）

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
>title="通知问题、完成时间和到期时间"
>abstract="指定一个或多个电子邮件地址，在数据馈送完成、即将到期或遇到问题时应该将通知发送到这些地址。 用逗号分隔多个电子邮件地址。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="处理延迟"
>abstract="在处理数据馈送文件之前等待迟到的事件的时间。 在处理延迟时段传入的任何迟到的点击都包含在数据馈送中。 <p>处理延迟可用于多种原因，例如为移动设备实施提供使离线设备联机并发送数据的机会，或者在管理以前处理的文件时容纳组织的服务器端进程。</p><p>会话必须在处理延迟截止之后开始才能被包含；在截止之前开始并在处理延迟内结束的会话不包含在内。</p><p>Customer Journey Analytics可根据信息源延迟送达事件通常所需的时间动态确定最佳延迟，但您可以手动将其设置为延迟2、3、4或8小时。</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="用户代理数据和设备查找数据不能存在于同一个数据馈送配置中。"

<!-- markdownlint-enable MD034 -->

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 从界面右上角的应用切换器&#x200B;[!UICONTROL **应用程序**]&#x200B;中选择 ![Customer Journey Analytics](/help/assets/icons/Apps.svg)。

1. 在顶部导航栏中，转到&#x200B;[!UICONTROL **组件**] > [!UICONTROL **导出**]。

1. 选择&#x200B;[!UICONTROL **数据馈送**]&#x200B;选项卡。

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

   应用多个区段时，它们与一个AND运算符连接在一起。 要使用OR运算符连接区段，必须首先在区段生成器中创建新区段，然后将新区段应用于数据馈送。

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

   +++ 不能包含在数据馈送中的量度

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

1. （可选）更改数据馈送输出中显示的组件ID。

   1. 将鼠标悬停在画布上的组件上，然后选择信息图标。

   1. 在组件ID字段中，指定新的组件ID。

      <!--add screenshot-->

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
   | [!UICONTROL **频率**] | 选择应发送数据馈送的频率。 时间戳位于频率范围内的事件将包含在数据馈送交付中。 [!UICONTROL **回顾日期范围**]&#x200B;和&#x200B;[!UICONTROL **处理延迟**]&#x200B;字段也会影响所选投放频率的数据中包含哪些事件。<p>对于实时馈送，选择以包含一小时的数据或一天的数据。 对于回填馈送，此字段已锁定为&#x200B;**每日**，无法更改。</p><ul><li>**每日**：馈送包含一整天的数据，从数据视图时区的午夜到午夜。 <p>回填馈送需要此选项，而实时馈送可以选择此选项。</p></li><li>**小时**：馈送包含一小时的数据。 <p>此选项仅对实时馈送可用。</p></li></ul> |
   | [!UICONTROL **回顾日期范围**] | 控制 Customer Journey Analytics 在处理数据馈送传递时向前回溯的时间范围。 默认值为30天。 <p>回顾日期范围影响区段鉴别、会话计算、派生字段转换和维度持久性。 <p>在配置此选项之前，请参阅以下部分中描述的详细信息和示例，[了解回溯日期范围](#understand-the-lookback-date-range)。</p> |
   | [!UICONTROL **处理延迟**] | 选择在处理数据馈送文件之前等待的时间。 默认值为2小时。 在处理延迟期间传入的任何迟到事件都包含在数据馈送中。 <p>处理延迟可用于多种原因，例如为移动设备实施提供使离线设备联机并发送数据的机会，或者在管理以前处理的文件时容纳组织的服务器端进程。 </p><p>会话必须在处理延迟截止之后开始才能被包含；在截止之前开始并在处理延迟内结束的会话不包含在内。</p><p>Customer Journey Analytics可根据信息源延迟送达事件通常所需的时间动态确定最佳延迟，但您可以手动将其设置为延迟2、3、4或8小时。</p> |
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
   | [!UICONTROL **完成时通过电子邮件通知**] | 指定一个或多个电子邮件地址，在成功发送数据馈送或无法发送数据馈送后，应将通知发送到这些地址。 多个电子邮件地址必须使用逗号分隔。 |
   | [!UICONTROL **启用清单**] | 选择是否在每次数据馈送传递时附带一个清单文件。 清单文件包含数据馈送中包含的每个文件的信息。 |

1. 选择&#x200B;**[!UICONTROL 保存]**。

## 了解回顾日期范围 {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="回顾日期范围"
>abstract="控制Customer Journey Analytics在处理每次投放时回溯多远。<p>频率窗口（小时或天）确定哪些事件包含在数据馈送中，而&#x200B;**回顾日期范围**&#x200B;提供正确分类这些事件所需的历史上下文。</p><p>区段鉴别、维度持久性、会话计算和派生字段转换都可能影响包含的事件。</p><p>较长的回顾可提高准确性；较短的回顾可提高性能。</p>"

<!-- markdownlint-enable MD034 -->

回顾日期范围可控制Customer Journey Analytics在处理每个数据馈送交付时回顾的时间范围。

事件仍必须具有要包含在投放中的频率范围（小时或天）内的时间戳，但属于&#x200B;**回顾日期范围**&#x200B;内的数据提供正确分类这些事件所需的历史上下文。

配置此选项时，请考虑以下重要概念：

* 较长的回顾日期范围通常会导致数据更准确；较短的回顾日期范围会导致更好的交付性能。
* 回顾日期范围以及频度窗口的功能与Analysis Workspace报表日期范围类似。 但是，存在[主要差异](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences)。 这些差异可能会导致Workspace报表和数据馈送交付之间存在数据差异。

处理回顾日期范围内的数据时，将分别考虑区段鉴别、会话计算、维度持久性和派生字段转换：

### 细分资格筛选

将区段应用于数据馈送定义后，回顾日期范围内的数据将确定哪些事件、会话或人员符合该区段的条件。 区段的容器设置确定范围。 (可能的容器包括：“人员”、“会话”或“事件”。 B2B包括以下附加容器：全球客户、客户、商机、购买团体。)

>[!BEGINSHADEBOX]

**示例：**

假设您要创建一个数据馈送，以了解参与特定营销活动（营销活动B）的用户的行为。

要完成此操作，请将区段应用于促销活动B _中名为_&#x200B;用户的数据馈送，以指示只有与此区段中的用户关联的事件应包含在数据馈送中。

在这种情况下，仅当用户同时满足以下两个条件中的&#x200B;**和**&#x200B;时，才会将其包含在数据馈送中：

* 用户有一个时间戳位于数据馈送频率窗口（数据馈送的给定小时或日期）内的事件。
* 该用户在回顾日期范围&#x200B;**内的某个时间符合&#x200B;_促销活动B_区段**&#x200B;的资格。

  对于9天前发生的符合条件的事件，这意味着，如果回顾日期范围设置为30天，则数据馈送中将包括用户&#x200B;****；如果回顾日期范围设置为7天，则数据馈送中将不包括用户&#x200B;****。

>[!ENDSHADEBOX]

### 会话计算

会话边界使用回顾日期范围内的数据计算。<!--Maybe this matters more regarding what the session ID is? Could it impact the Session ID? This could impact several factors, such as session-based persistence.-->

### Dimension持久性

在单个维度上设置持久性时，您还可以设置过期时间，以确定维度项在从中设置它的事件之外保持多久。

当数据视图中的过期时间设置为以下任一选项时，回顾日期范围会影响维度持久性：

* [!UICONTROL **人员报告窗口**]：对于使用&#x200B;[!UICONTROL **人员报告窗口**]&#x200B;作为其过期日期的数据馈送定义中的每个维度，回顾日期范围将成为新的报告窗口。
* [!UICONTROL **自定义时间**]：如果选择的自定义时间超出回顾日期范围，将忽略自定义时间，并且回顾日期范围将用于数据馈送定义中每个维度的维度过期，这些数据馈送定义使用&#x200B;[!UICONTROL **自定义时间**]&#x200B;作为其过期。 不考虑回溯日期范围之前发生的值。

  有关在数据视图中设置维度的持久性的详细信息，请参阅[持久性组件设置](/help/data-views/component-settings/persistence.md)。

要获得最准确的数据，请考虑将回顾日期范围设置为等于或大于数据中维度设置的持久性的值。 但是，请记住，较短的回顾日期范围可提高数据馈送交付的性能。

>[!BEGINSHADEBOX]

**示例：**

假设您希望在访问您的网站之前，在数据馈送中了解最初看到哪些营销活动。

要完成此操作，请在促销活动维度上设置持久性，并将“原有”作为分配模型。

在这种情况下，仅当用户同时满足&#x200B;**和**&#x200B;以下条件时，原始营销活动才会显示在数据馈送输出中：

* 用户有一个时间戳位于数据馈送频率窗口（数据馈送的给定小时或日期）内的事件。

* 该用户在回顾日期范围&#x200B;**内的某个时间符合原始营销活动**&#x200B;的资格。

  如果用户在9天前符合原始促销活动的资格，则回顾日期范围设置为30天时，数据馈送中将包含原始促销活动&#x200B;****；但是如果回顾日期范围设置为7天，则数据馈送中将不包含原始促销活动&#x200B;****。

>[!ENDSHADEBOX]

### 派生字段转换

引用容器的任何派生字段函数在数据馈送导出中使用回顾日期范围。 派生字段中提供了哪些日期功能？<!--Not sure how this applies.-->



