---
title: 创建数据馈送
description: 了解如何创建数据馈送以及提供给 Adobe 的文件信息。
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '3924'
ht-degree: 12%
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
>title="在出现问题、完成或即将过期时发送通知"
>abstract="指定一个或多个电子邮件地址，以便在数据馈送完成、即将过期或遇到问题时接收通知。 请使用逗号分隔多个电子邮件地址。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_frequency_granularity"
>title="频率和粒度"
>abstract="**提交频率**（实时馈送）：提交数据馈送的频率。 每小时投放包含一小时的数据；每日投放包含一天的数据。 回顾日期范围和处理延迟也会影响包含哪些事件。<p>**粒度**（回填馈送）：用于划分历史数据的时间间隔。 每个区块都包含一天的数据，并且会尽快发送，而不是每天发送一次。 此字段始终设置为“每日”，不能修改。</p>"

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

   您在此处应用的区段是对可能已应用于数据视图的任何区段之外的区段。

1. （可选）在左边栏中，使用&#x200B;**搜索**&#x200B;字段来查找特定组件。 或者，选择&#x200B;**排序**&#x200B;图标![排序组件图标](/help/assets/icons/SortOrderDown.svg)以应用以下任何排序选项：

   | 选项 | 功能 |
   | --------- | ---------- |
   | [!UICONTROL **建议**] | 为组件排序，将推荐的组件置于列表的顶部。 您或您组织中的其他人最频繁且最近使用的组件显示在列表的较高位置。 |
   | [!UICONTROL **按字母顺序**] | 按字母顺序为组件排序。 |
   | [!UICONTROL **分类**] | 与&#x200B;[!UICONTROL **推荐**]&#x200B;类似的组件排序，不同之处在于计算量度和标准量度是分开分组的，而不是混合在一起。 |

1. 将组件添加到数据馈送配置。 左边栏仅显示对数据馈送有效的组件。

   * **拖放**：将组件从左边栏拖到画布上。 按住&#x200B;**[!UICONTROL Shift]**，或按住&#x200B;**[!UICONTROL Command]** (macOS)或&#x200B;**[!UICONTROL Ctrl]** (Windows)以同时选择和拖动多个组件。
   * **加号按钮**：选择左边栏中任何组件旁边的加号![添加](/help/assets/icons/Add.svg)图标以将其添加到画布中。
   * **[!UICONTROL 全部显示]**：选择组件列表底部的&#x200B;**[!UICONTROL 全部显示]**&#x200B;以打开显示所有可用组件的对话框。 选中要添加的每个组件旁边的复选框，然后选择&#x200B;**[!UICONTROL 添加选定项]**。 当搜索词或筛选器标记在左边栏中处于活动状态时，还会显示&#x200B;**[!UICONTROL 全部添加]**&#x200B;按钮，允许您一次添加所有筛选结果。

   添加字段时，请考虑以下事项：

   * 某些组件是必需的、不受支持的，或者在数据馈送中具有限制。 有关详细信息，请参阅数据馈送中的[组件可用性](/help/components/exports/cja-data-feeds/df-components.md)。

   * 添加属于XDM数组字段（例如，Adobe Journey Optimizer建议字段）或映射字段的组件时，对话框会提示您从同一子容器添加任何其他组件。 在数据馈送输出中，所有这些组件都显示在一列中。 有关详细信息，请参阅数据馈送中的[子容器组件](/help/components/exports/cja-data-feeds/df-sub-event.md)

1. （可选）通过拖动组件对画布上的组件重新排序。 您定义的顺序将保留为导出数据馈送文件中的列顺序。

1. （可选）通过拖动列边框调整画布上的列大小。

   列宽将保存在Cookie中，并在您下次在同一浏览器上返回此数据馈送时保留。

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
   | [!UICONTROL **频率**]<br/>&#x200B;仅适用于实时馈送 | 选择应发送数据馈送的频率。 时间戳位于频率范围内的事件将包含在数据馈送交付中。 [!UICONTROL **回顾日期范围**]&#x200B;和&#x200B;[!UICONTROL **处理延迟**]&#x200B;字段也会影响所选投放频率的数据中包含哪些事件。<p>选择以包含一小时的数据或一天的数据。</p><ul><li>**每日**：馈送包含一整天的数据，从数据视图时区的午夜到午夜。</li><li>**小时**：馈送包含一小时的数据。</li></ul> |
   | [!UICONTROL **粒度**]<br/>&#x200B;仅适用于回填馈送 | 用于将历史数据划分为块的时间间隔。 每个区块包含一整天的数据，时间范围从数据视图时区的午夜到午夜。 <p>粒度决定着数据的分组方式，而不是数据的提交频率。 回填数据会尽快提供，而不是每天提供一次。</p><p>此字段始终设置为&#x200B;[!UICONTROL **每日**]，无法修改。</p> |
   | [!UICONTROL **回顾日期范围**] | 控制 Customer Journey Analytics 在处理数据馈送传递时向前回溯的时间范围。 默认值为30天。<p>频率窗口（小时或天）决定数据馈送中包含哪些事件，而&#x200B;**回顾日期范围**&#x200B;则提供正确分类这些事件所需的历史上下文。</p><p>细分资格筛选、维度持久性、会话计算和派生字段转换都会影响所包含的事件。</p> <p>在配置此选项之前，请参阅以下部分中描述的详细信息和示例，[了解回溯日期范围](#data-feed-lookback-date-range)。</p> |
   | [!UICONTROL **处理延迟**] | 选择Customer Journey Analytics在处理数据馈送文件之前等待的时间。 在处理延迟期间传入的任何迟到事件都包含在数据馈送中。 <p>最小处理延迟为2小时，但某些类型的数据需要更长的延迟。 您选择的延迟取决于连接中的数据类型，例如流式传输、批处理、拼接、查找或配置文件数据。</p><p>选择足够长的延迟，以便连接中最慢的数据完成处理。 如果延迟太短，则仍在处理的数据不会包含在数据馈送文件中。</p><p>在配置此选项之前，请参阅以下部分中描述的详细信息和示例，[了解处理延迟](#data-feed-processing-delay)。</p> |
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
>abstract="控制 Customer Journey Analytics 在处理每次投放时回顾的数据时间范围。<p>频率窗口（小时或天）决定数据馈送中包含哪些事件，而&#x200B;**回顾日期范围**&#x200B;则提供正确分类这些事件所需的历史上下文。</p><p>细分资格筛选、维度持久性、会话计算和派生字段转换都会影响所包含的事件。</p><p>较长的回溯范围可提高准确性；较短的回溯范围可提升性能。</p>"

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

会话边界使用回顾日期范围内的所有事件进行计算，而不只是投放窗口中的事件。 在投放窗口之前启动的会话仍被识别为同一会话。

会话ID基于您的数据视图中的人员、会话开始时间和会话设置。 会话在投放之间保留相同的会话ID，以便您可以加入跨多个小时或每日投放的会话中的事件。

使用数据馈送中的会话时，请考虑以下事项：

* 如果会话在回顾日期范围之前启动，则其早期事件将不可用，因此会话值可能与Analysis Workspace不同。 有关详细信息，请参阅[了解数据馈送与Analysis Workspace之间的数据差异](/help/components/exports/cja-data-feeds/df-comparison-workspace.md)。
* 更改数据视图中的会话设置会更改会话ID。 后续投放中的会话ID与早期投放中的会话ID不匹配。

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

## 了解处理延迟 {#data-feed-processing-delay}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="延迟处理"
>abstract="Customer Journey Analytics在处理数据馈送文件之前等待的时间。 在处理延迟期间传入的任何迟到事件都包含在数据馈送中。<p>最小处理延迟为2小时，但某些类型的数据需要更长的延迟。 选择足够长的延迟，以便连接中最慢的数据到达Experience Platform数据湖并摄取到Customer Journey Analytics中。 如果延迟太短，则仍在处理的数据不会包含在数据馈送文件中。</p><p>拼合最多可添加4小时。 要解决此问题，请在延迟时间的基础上再增加4小时，以延迟任何拼合的数据。</p>"

<!-- markdownlint-enable MD034 -->

### 处理延迟的工作方式

处理延迟是Customer Journey Analytics在处理数据馈送文件之前等待的时间。 在处理延迟期间传入的任何迟到事件都包含在数据馈送中。

由于各种原因，需要处理延迟，例如为了说明管道延迟，为了让移动设备实施有机会使离线设备联机并发送数据，或者在管理以前处理的文件时适应组织的服务器端流程。

最小处理延迟为2小时，但某些类型的数据需要更长的延迟。

>[!BEGINSHADEBOX]

**示例：**

假设每小时数据馈送包括从中午1:00到下午2:00的数据，并且处理延迟为2小时。 对该数据馈送文件的处理于下午4:00开始，包括处理开始前到达的任何数据。

>[!ENDSHADEBOX]

### 根据您的数据选择处理延迟

不同类型的数据需要经过不同的时间才能在Customer Journey Analytics中使用。 数据经过两个处理阶段，每个阶段的时间将相加为总时间。

选择足够长的处理延迟，以便连接中最慢的数据完成两个阶段。 如果延迟太短，则仍在处理的数据不会包含在数据馈送文件中。

#### 阶段1：数据到达Experience Platform数据湖

到达时间因您收集的数据类型而异。 选择适合您正在收集的数据类型的延迟。

* **来自Edge Network或流式摄取的事件数据集**：数据通常在60分钟内到达数据湖（请参阅[延迟](/help/technotes/guardrails.md#latencies)）。

* **Analytics源连接器数据集**：数据通常在2.25小时内到达数据湖（请参阅[延迟](/help/technotes/guardrails.md#latencies)）。

  <!--When using the Analytics Source Connector, the minimum processing delay increases from 2 hours to 6 hours (?) to account for the source connector data. (checking to see if this is feasible) -->

* **来自其他源连接器的数据集**：延迟因源连接器和发送批次的时间而异。 Experience Platform中的上游处理（例如数据准备）可以添加更多时间。

* **查找数据集**：数据到达数据湖的时间取决于数据的上传频率。 查找数据通常作为数据库的完整副本上传，其中只有一小部分记录发生了更改。 以较小的批次上载查找数据以缩短处理时间。

  小型上传通常在最小延迟内处理。

  大型上传（例如，每周上传数百万条记录）的处理优先级较低，并且可能需要3到4小时的时间。 如果上载量很大，则不会延迟事件数据，但查找值可能不会反映最新的更新。

* **配置文件数据集**：数据到达数据湖的时间取决于数据上传的频率。 配置文件数据通常批量摄取，例如完整配置文件表的每日快照。 以较小的批次上载配置文件数据以缩短处理时间。

  小型上传通常在最小延迟内处理。

  大型上传（例如，每周上传数百万条记录）的处理优先级较低，并且可能需要3到4小时的时间。 在大量上传的情况下，事件数据不会延迟，但配置文件值可能不会反映最新的更新。

#### 阶段2：数据从数据湖摄取到Customer Journey Analytics

根据数据集是否已启用拼合，数据摄取时间会有所不同。

* **非拼接数据集**：这最多可能需要90分钟（请参阅[延迟](/help/technotes/guardrails.md#latencies)）。

* **拼接的数据集**：在非拼接数据集所需的90分钟基础上，拼接最多可添加4小时（请参阅[延迟](/help/technotes/guardrails.md#latencies)）。 如果为连接启用了拼合，请将延迟设置为至少6小时，可能为8小时。 通过拼合重放更新的数据通常不包含在已处理的数据馈送文件中。

  启用拼合后，最小处理延迟从2小时增加到6小时，以处理拼合的数据。

>[!BEGINSHADEBOX]

**示例：**

如果您的连接包含多种类型的数据，请选择包含最慢数据的延迟。 在下面的示例中，大约为8小时。

拼合过程最多需要4小时才能将信息摄取到Customer Journey Analytics中。 要解决此问题，请在延迟时间的基础上再增加4小时，以延迟任何拼合的数据。

| 数据源 | 阶段1：到达数据湖 | 阶段2：摄取到Customer Journey Analytics | 合计 |
| --- | --- | --- | --- |
| Edge Network或流式摄取 | 60分钟 | 90分钟 <p>不拼合</p> | 2.5小时 |
| Analytics 源连接器 | 2.25小时 | 90分钟+ 4小时用于拼合 <p>通过拼合</p> | 7.75小时 |

>[!ENDSHADEBOX]


