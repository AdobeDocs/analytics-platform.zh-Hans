---
title: 处理Customer Journey Analytics报表中的“无值”
description: 了解Customer Journey Analytics报表中何时应该有**[!UICONTROL 无值]**条目，以及这些条目何时表示存在需要注意的数据收集问题。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: bc1e610ccf13ca831f40b2819a4665fe8ea21b7b
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 0%
---

# 如何处理无值

使用Customer Journey Analytics时，在报表和功能板中遇到&#x200B;**[!UICONTROL 无值]**&#x200B;条目会引发有关数据质量、收集方法和报表准确性的重要问题。 这些实例需要仔细监测，因为它们揭示了数据收集中的隐藏漏洞。 难题在于区分两种情况：当&#x200B;**[!UICONTROL 没有值]**&#x200B;条目需要由数据源提供商调查时，以及&#x200B;**[!UICONTROL 没有值]**&#x200B;条目反映数据流入Customer Journey Analytics的正常情况时。 了解这一区别对于保持高效分析运营至关重要。 本指南可帮助您针对Customer Journey Analytics实施中&#x200B;**[!UICONTROL 没有值]**&#x200B;外观做出明智的决策。

## 不了解任何值

**[!UICONTROL 如果维度没有对应值，而事件又包含量度，则不会显示]**&#x200B;值。 在报告中看到&#x200B;**[!UICONTROL 没有值]**&#x200B;并不总是问题。 在许多情况下，它反映了数据集的预期结构。

Dimension项目分为三类：

* **应为[!UICONTROL 无值]**：用户浏览数据的自然结果，例如尚未登录的访客或不适用于每个事件的维度
* **有问题[!UICONTROL 没有值]**：数据收集失败或实施错误的结果，其中值存在但缺失
* **有效值**：维度已成功捕获值

下图显示了当数据从您的源移动到Adobe Experience Platform时，Customer Journey Analytics如何进入其中每个类别。

此流程图说明了Customer Journey Analytics评估如何通过首先检查值存在，然后确定缺少值是预期的还是有问题的，来重点关注传入数据。 此明确的评估可帮助管理员和分析人员区分需要源调查的&#x200B;**[!UICONTROL 无值]**&#x200B;案例和代表正常操作的案例。

![决策流显示源数据通过Adobe Experience Platform移入Customer Journey Analytics，该流检查是否存在维度值，然后检查缺少值是否是预期方案，从而导致自然的“无”值、有问题的“无”值或有效的值](assets/no-value-flow.svg)

## 当没有预期值时

**[!UICONTROL 没有值]**&#x200B;在报表中显示的常见预期原因如下：

* 维度仅适用于特定场景，例如流量源或设备类型
* 尚未为首次访问访客分配标识符
* 访客处于登录前状态，未提供用户信息
* 功能或产品交互不适用于特定用户历程
* 跨设备方案不跨设备携带维度值

在这些情况下，**[!UICONTROL 没有值]**&#x200B;表示用户在从未识别状态转换为已识别状态期间在其身份验证历程中的位置，如下图所示。

![用户身份验证历程，显示用户访问网站并进入登录前状态，没有可用的用户信息，然后显示填充用户信息的登录事件](assets/no-value-login-flow.svg)


## 当没有值需要注意时

调查&#x200B;**[!UICONTROL 没有值]**&#x200B;条目（当它们来自以下任何项时）：

**数据源中的实施问题：**

* 缺少数据元素或null值
* 不正确的变量映射
* 配置不正确的数据层
* 数据收集失败
* 传入数据与定义的架构不匹配

**数据质量问题：**

* 跟踪代码损坏
* 数据收集不完整
* 集成失败
* 数据转换过程中引入的错误
* 数据管道中断

## 管理数据视图设置中的“无值”

通过数据视图设置，您可以控制&#x200B;**[!UICONTROL 无值]**&#x200B;项在报表中的显示方式，包括重命名标签、默认显示或隐藏这些项，以及将&#x200B;**[!UICONTROL 无值]**&#x200B;视为合法字符串值。 查看[无值选项组件设置](/help/data-views/component-settings/no-value-options.md)，以获取设置的完整列表以及它们如何影响百分比分布、过滤和分段。

配置这些设置时，评估您的报告要求，并评估&#x200B;**[!UICONTROL 无值]**&#x200B;的存在对您的分析有何影响。 既考虑对数据可见性的直接影响，又考虑对趋势分析和报告一致性的长期影响。 经过精心选择的配置可增强数据清晰度，同时保持业务分析可访问性和可操作性，无论&#x200B;**[!UICONTROL 没有值]**&#x200B;条目如何显示在您的报表中。 理想的配置将数据表示与实际分析需求相平衡，从而创建一种报表环境，即使&#x200B;**[!UICONTROL 没有值]**&#x200B;数据存在，该环境也能提供准确且有意义的见解。

下表总结了可用的各种配置。

<table>
<thead>
<tr>
<th>类别</th>
<th>设置</th>
<th>作用</th>
<th>影响</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="2">显示选项</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">可以通过在自由格式表搜索过滤器中选择复选框来包含或排除。</td>
<td rowspan="2">可见性</td>
</tr>
<tr>
<td><img src="assets/dont-show-no-value-default.png"/></td>
</tr>
<tr>
<td rowspan="2">自定义命名</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">影响报表维度值显示以及潜在的值合并和量度聚合。</td>
<td rowspan="2">命名</td>
</tr>
<tr>
<td><img src="assets/show-unknown-as-value.png"/></td>
</tr>
<tr>
<td rowspan="3">处理选项</td>
<td><img src="assets/treat-no-value-as-value.png"/></td>
<td>仅适用于非数字维度。
同时影响归因和自由格式表搜索筛选器中的包含**[！UICONTROL无值]**选项。</td>
<td>值处理和可见性</td>
</tr>
<tr>
<td rowspan="2">数值维度支持：<br><img src="assets/dont-show-no-value-default.png"/><br/><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">可以通过在自由格式表搜索过滤器中选择复选框来包含或排除</td>
<td rowspan="2">可见性</td>
</tr>
<tr>
</tr>
</tbody>
</table>


### 如果显示，则将“无值”称为

此设置允许您自定义报表中&#x200B;**[!UICONTROL 无值]**&#x200B;行的显示方式。 您可以在文本字段中输入&#x200B;**[!UICONTROL 无值]**&#x200B;维度项的自定义名称，通过&#x200B;**[!UICONTROL 提供更有意义的上下文。如果显示，请调用“无值”]**。 使用清晰的业务友好型术语而不是`No value`可帮助您的组织更好地了解报表值。 虽然不能直接将&#x200B;**[!UICONTROL 没有值]**&#x200B;用作区段中的字符串，但可以使用&#x200B;**[!UICONTROL 不存在]**&#x200B;运算符达到相同的效果。

您可以使用描述性术语替换`No value`，例如`Pre-login User`表示身份验证状态，`No Customer Tier`表示无层的客户，或`No Tracked Marketing Channel`表示未识别的营销源。 这样可创建更直观的报表。 `Pre-login User`清楚地显示客户在其历程中的位置，而`No Customer Tier`提供特定上下文。 请记住，您选择的描述适用于该维度的所有&#x200B;**[!UICONTROL 无值]**&#x200B;实例，因此请选择能够准确反映缺少维度值的所有情况的术语。

### 默认不显示“无值”

此设置确定是否在报告中默认隐藏&#x200B;**[!UICONTROL 无值]**&#x200B;行。 启用后，最初会过滤掉这些行，但如果需要，仍可以在自由格式表内显示这些行，方法是选中自由格式表搜索过滤器中的复选框。 请注意，隐藏&#x200B;**[!UICONTROL 没有值]**&#x200B;行会影响剩余值的百分比分布，因为百分比仅根据可见项目重新计算。

### 默认显示“无值”

此设置控制报表中是否默认显示&#x200B;**[!UICONTROL 无值]**。 启用后，**[!UICONTROL 没有值]**&#x200B;条目可见，但用户可以使用自由格式表搜索筛选器中的复选框将其排除。 包括或排除&#x200B;**[!UICONTROL 没有值]**&#x200B;行会影响百分比分布，因为百分比仅根据可见项目计算。

### 将“无值”视为值

此设置将&#x200B;**[!UICONTROL 没有值]**&#x200B;视为字符串值（数字维度除外），允许您将其表示自定义为维度值。 此自定义对归因以及自由格式表搜索筛选器中的&#x200B;**[!UICONTROL 不包含值]**&#x200B;选项都有影响。 请记住，在分配自定义字符串值时，数据集中的所有匹配值将合并到同一维度字符串值下。

**[!UICONTROL 将“没有值”视为值]**&#x200B;设置的用途与默认显示&#x200B;**[!UICONTROL 没有值]**&#x200B;的用途不同。 默认情况下，仅显示控件可见性，但视为值会更改Customer Journey Analytics逻辑处理这些条目的方式。 这种区别之所以重要，原因如下：

* 它使过滤和分段中的控制更加细粒度，使&#x200B;**[!UICONTROL 没有值]**&#x200B;成为一个独特的可操作的维度值。
* 通过将&#x200B;**[!UICONTROL 没有值]**&#x200B;视为归因模型和可视化图表中的合法维度值，它可以在整个分析中保持一致的归因和表示法。

在以下情况下，您将&#x200B;**[!UICONTROL 没有值]**&#x200B;视为值：

* 缺少数据本身对您的分析很有意义（例如登录前状态或未归因流量）。
* 您需要创建专门针对或排除这些情况的区段或计算量度。

相比之下，在需要基本的可见性缺少数据时，默认显示&#x200B;**[!UICONTROL 没有值]**&#x200B;更合适，这样不会因将其视为值而带来额外的逻辑和归因复杂性。

### 数值维度不支持值

对于数值维度，提供了多个配置选项。 在数据视图维度设置中，您可以配置除&#x200B;**[!UICONTROL 将“没有值”视为值]**&#x200B;之外的所有&#x200B;**[!UICONTROL 没有值]**&#x200B;选项。 您还可以通过选中自由格式表搜索筛选器中的复选框，管理数字维度的&#x200B;**[!UICONTROL 包括“没有值”]**。 创建区段时，您可以使用具有数值维度的&#x200B;**[!UICONTROL 存在]**&#x200B;或&#x200B;**[!UICONTROL 不存在]**&#x200B;运算符。

### 无值和物料级别维度

某些维度在数组中的项级别应用，而不是在事件的顶级应用。 例如，`productListItems.SKU`仅在该事件存在产品列表项时具有值。 数据粒度的这一差异改变了&#x200B;**[!UICONTROL 没有值]**&#x200B;的行为。

对于标准顶级维度，每当某个维度缺失或在其他情况下带有量度的事件上具有null值时，Customer Journey Analytics会将该维度置于&#x200B;**[!UICONTROL 无值]**&#x200B;存储段中。 项目级别维度取决于首先存在的项目。 如果某个事件携带某个量度，但缺少产品列表项，则Customer Journey Analytics没有将该量度附加到或将数据标记为&#x200B;**[!UICONTROL 无值]**&#x200B;的行。

Customer Journey Analytics不会为缺少或空的数组创建占位符或空行。 因此，您可以正确配置&#x200B;**[!UICONTROL 无值]**&#x200B;数据视图设置，但仍然无法在项目级别报表中看到&#x200B;**[!UICONTROL 无值]**&#x200B;条目，例如SKU细分。 缺少条目是数据粒度差异，而不是配置问题。 **[!UICONTROL 没有值]**&#x200B;设置控制现有行的显示方式，空数组表示在该数据粒度级别不存在任何行。

当项目级别&#x200B;**[!UICONTROL 没有值]**&#x200B;计数看起来低于预期时，在假定数据视图设置需要调整之前，请检查缺少数组数据是否说明了差距。

## 最佳实践

一旦识别出有问题的&#x200B;**[!UICONTROL 无值]**&#x200B;实例，您将需要制定和实施修正策略。 此补救可通过两种方式完成：

* 调整数据视图组件&#x200B;**[!UICONTROL 无值]**&#x200B;选项设置，或者
* 修复数据收集源中的问题。

请仔细选择您的方法，因为每种路径对快速修复和长期数据质量都有不同的含义。 您的实施遵循了一个有条不紊的过程，该过程在修复当前问题的同时防止了将来出现这些问题。 成功取决于规划、系统执行和持续监控。

以下是修正计划的主要战略注意事项：

### 防止出现无值问题

* 在处理数据之前对其进行验证
* 在适当时设置默认维度值（从不为人员ID）
* 记录需要&#x200B;**[!UICONTROL 没有值]**&#x200B;的情况
* 在数据收集点添加质量检查
* 监控数据模型的合规性
* 数据收集期间出现日志错误
* 为您的实施添加自动化测试
* 需要始终存在值的架构字段

### 验证报表中无值

* 创建隔离&#x200B;**[!UICONTROL 没有值]**&#x200B;模式的区段
* 生成可监控&#x200B;**[!UICONTROL 无值]**&#x200B;随时间变化的趋势的QA仪表板
* 设置跟踪&#x200B;**[!UICONTROL 无值]**&#x200B;卷中更改的警报
* 生成突出显示重大模式变化的自动化报告
* 跨相关维度交叉引用&#x200B;**[!UICONTROL 没有值]**&#x200B;模式
* 定期审查数据视图配置
* 维护更改您的&#x200B;**[!UICONTROL 无值]**&#x200B;策略的更改日志
* 为利益相关者创建标准操作程序和文档模板

## 结论

不是每个&#x200B;**[!UICONTROL 没有值]**&#x200B;条目都表示存在问题。 要正确解释&#x200B;**[!UICONTROL 没有值]**，需要了解您的Adobe Experience Platform和Customer Journey Analytics数据架构，以及用户如何在您的产品或站点中移动。 不要尝试消除&#x200B;**[!UICONTROL 无值]**&#x200B;的每个实例，而是建立文档化的组织范围规则，根据您自己的用户历程和业务案例区分预期的&#x200B;**[!UICONTROL 无值]**&#x200B;和有问题的&#x200B;**[!UICONTROL 无值]**。

>[!MORELIKETHIS]
>
>[在Adobe Customer Journey Analytics中处理&#x200B;**[!UICONTROL 无值]**&#x200B;的完整行动手册](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/the-complete-playbook-for-handling-no-value-in-adobe-cja-12769)
