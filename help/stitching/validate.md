---
title: 在Customer Journey Analytics中验证身份拼合
description: 了解如何在Customer Journey Analytics中验证身份拼合。 在拼合之前和之后测量身份验证率和身份识别。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: b9b73926-6502-4a48-ba73-c784f80950d3
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 0%

---

# 验证拼接

[身份拼接](/help/stitching/overview.md)（或简单地拼接）的目标是提高事件数据集对跨渠道分析的适用性。 当数据集中的所有数据行都包含所需的可用最高顺序标识时，即可实现此提升。 此提升允许您：

* 创建以人员为中心的报表，同时不排除匿名人员。
* 将多个设备连接到单个人员。
* 跨渠道连接人员。

本文概述了用于测量一个或多个新创建的拼接数据集的提升度并确信拼接会带来这些好处的分析方法。

分析方法涉及管理员通常可访问的[数据视图组件设置](/help/data-views/component-settings/overview.md)。 这些方法还要求在Analysis Workspace项目中工作的分析人员创建计算指标和可视化图表。

虽然这些分析方法可用于基于字段的拼接和基于图形的拼接，但某些元素可能不在数据集中，尤其是在基于图形的拼接场景中。 这些缺少的元素可能会导致难以直接在Analysis Workspace中计算提升。

>[!NOTE]
>
>一个或多个数据集的（验证）拼合最终有助于更好地分析和见解。 但是，本文不讨论Customer Journey Analytics配置的整体价值，该配置将Experience Platform中的所有数据集与相同的身份命名空间对齐。 所有这些数据集完美地结合在一起，可在整个客户历程中执行分析。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [拼接启用和验证](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/visitor-id/stitching-enablement-and-validation){target="_blank"}。

>[!ENDSHADEBOX]



## 连接验证中的拼接

本节详细介绍如何验证已在“连接”界面中启用的拼接。

### 连接建议

要验证您在“连接”界面中启用的拼接，请为&#x200B;**[!UICONTROL 数据集回填]**&#x200B;选择一个有代表性的短时段。 例如，一周。

在下面的示例中，您需要拼合事件数据集。 您已设置一个测试连接，可在其中添加事件数据集。 对于该数据集，您将&#x200B;**[!UICONTROL ECID]** **[!UICONTROL 命名空间]**&#x200B;定义为&#x200B;**[!UICONTROL 永久ID]**，将&#x200B;**[!UICONTROL 访客哈希电子邮件地址(directMarketing.hashedEmail)]**&#x200B;定义为&#x200B;**[!UICONTROL 人员ID]**。 要验证此拼合，请为小时间范围（2026年1月24日 — 2026年2月10日）定义&#x200B;**[!UICONTROL 数据集回填]**。 您可以使用该小窗口验证拼合是否按预期工作。

![拼接配置](/help/stitching/assets/stitching-config.png)

### 数据视图先决条件

对于拼接验证，您需要确保已在数据视图中定义拼接数据集中的所有必需维度和量度。 根据您之前定义的连接创建数据视图。 在数据视图配置的&#x200B;**[!UICONTROL 组件]**&#x200B;步骤中，您需要：

* 将&#x200B;**[!UICONTROL 量度和维度]**&#x200B;中的&#x200B;**[!UICONTROL 身份命名空间]**&#x200B;作为维度添加到&#x200B;**[!UICONTROL 维度]**&#x200B;列表。

  ![身份标识命名空间](/help/stitching/assets/identity-namespace.png)


* 从&#x200B;**[!UICONTROL 架构字段]**&#x200B;中选择您定义为事件人员ID的&#x200B;**[!UICONTROL 访客哈希电子邮件地址标识符]**。 将字段作为维度添加到&#x200B;**[!UICONTROL 维度]**&#x200B;列表，并将作为量度添加到&#x200B;**[!UICONTROL 量度]**&#x200B;列表。 将指标的&#x200B;**[!UICONTROL 组件名称]**&#x200B;修改为`Email set`。

  ![电子邮件标识符](/help/stitching/assets/email-identifier.png)

确保保存数据视图。

### 创建Workspace项目

在Workspace中，创建一个新项目并使用自由格式表显示您为测试拼合配置而定义的日期范围的&#x200B;**[!UICONTROL 电子邮件集]**&#x200B;指标。 此自由格式表显示在拼接之前具有电子邮件地址的事件。

![拼合概述自由格式表 — 电子邮件集](/help/stitching/assets/workspace-emailset.png)

要查看在拼合过程后设置了电子邮件地址的事件，请定义计算量度`Email stitched namespace`。 该计算量度会查看&#x200B;**[!UICONTROL 具有等于经过哈希处理的电子邮件命名空间]**&#x200B;的&#x200B;**[!UICONTROL 身份命名空间]**&#x200B;的事件`email_lc_sha256`。

![拼接概述 — 电子邮件拼接的命名空间计算量度](/help/stitching/assets/cm-email-stitched-namespace.png)

如果将新的计算量度&#x200B;**[!UICONTROL 电子邮件拼接的命名空间]**&#x200B;添加到自由格式表，您会看到拼接过程后现在具有电子邮件地址的事件数量有所增加。

![拼合概述自由格式表 — 电子邮件集并拼合](/help/stitching/assets/workspace-emailset-stitched.png)

当您定义两个额外的计算指标时，可以获得进一步的见解。

* **[!UICONTROL 电子邮件身份验证率]**。 此计算量度可确定拼接过程之前的身份验证率。

  ![电子邮件身份验证率计算量度定义](/help/stitching/assets/cm-email-authentication-rate.png)

* **[!UICONTROL 拼接身份验证率]**。 此计算量度可确定拼合过程后的身份验证率。

  ![拼接身份验证率计算量度定义](/help/stitching/assets/cm-stitched-authentication-rate.png)

将这两个额外的计算量度添加到您的自由格式表中，此时，您可以看到拼接事件的数量增加。

![拼合概述自由格式表 — 已通过身份验证](/help/stitching/assets/workspace-authenticated.png)

若要获得更多见解，可向自由格式表添加另外两个计算指标（**[!UICONTROL 百分比增加]**&#x200B;和&#x200B;**[!UICONTROL 提升]**），以查看拼合配置的影响。

![拼合概述自由格式表 — 经过身份验证的提升](/help/stitching/assets/workspace-authenticated-lift.png)



## 请求拼接验证

本节详细介绍如何验证您从Adobe请求的拼合。 此方法已弃用，但可能仍有使用此方法拼合的数据集。

### 数据视图先决条件

对于拼接验证测量计划，您需要确保已在数据视图中定义拼接数据集中的所有必需维度和量度。 验证是否已将`stitchedID.id`和`stitchedID.namespace.code`字段添加为维度。 虽然拼接的数据集是原始数据集的精确副本，但拼接过程会向数据集中添加以下两个新列：

* 使用`stitchedID.namespace.code`定义&#x200B;**[!UICONTROL 拼接的命名空间]**&#x200B;维度。 此维度包含行被提升为的标识的命名空间，例如`Email`或`Phone`。 或拼接过程回退到的命名空间，如`ECID`。
  ![拼接的命名空间维度](/help/stitching/assets/stitchednamespace-dimension.png)

* 使用`stitchedID.id`定义&#x200B;**[!UICONTROL 拼接ID值]**&#x200B;维度。 此维度包含标识的原始值。 例如：经过哈希处理的电子邮件、经过哈希处理的手机、ECID。 此值与&#x200B;**[!UICONTROL 拼接的命名空间]**&#x200B;一起使用。
  ![拼接ID维度](/help/stitching/assets/stitchedid-dimension.png)


此外，您需要添加两个基于维度中值的拼接量度。

1. 使用包含拼接数据集中的人员ID的字段配置指标，以定义是否设置了人员ID。 即使您使用基于图形的拼合，也可添加此人员ID，因为人员ID有助于建立基线。 如果人员ID未包含在数据集中，则您的基线为0%。

   在下面的示例中，`personalEmail.address`用作标识，用于创建&#x200B;**[!UICONTROL _Email集]**&#x200B;量度。
   ![电子邮件集指标](/help/stitching/assets/emailset-metric.png)

1. 使用`stitchedID.namespace.code`字段创建&#x200B;**[!UICONTROL 电子邮件拼接命名空间]**&#x200B;量度。 请确保在组件设置[中指定](/help/data-views/component-settings/include-exclude-values.md)包括排除值，以便只考虑尝试将数据行提升到的命名空间的值。
   1. 选择&#x200B;**[!UICONTROL 设置包括/排除值]**。
   1. 选择&#x200B;**[!UICONTROL 如果满足所有条件]**&#x200B;作为&#x200B;**[!UICONTROL 匹配]**。
   1. 将&#x200B;**[!UICONTROL Equals]** `email`指定为&#x200B;**[!UICONTROL 标准]**&#x200B;以选择已提升到电子邮件命名空间的事件。

   ![电子邮件拼接的命名空间指标](/help/stitching/assets/emailstitchednamespace-metric.png)

### 拼接维度

将这两个维度都添加到数据视图后，在Analysis Workspace中使用[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)检查每个维度包含的数据。

在&#x200B;**[!UICONTROL 拼接的命名空间]**&#x200B;维度表中，您通常看到每个数据集的两行。 一行表示拼接过程何时必须使用回退方法(ECID)。 另一行显示与所需身份命名空间（电子邮件）关联的事件。

对于&#x200B;**[!UICONTROL 拼接ID值]**&#x200B;维度表，您会看到来自事件的原始值。 在此表中，您会看到值在永久ID和所需人员ID之间振荡。

![检查拼接的维度](/help/stitching/assets/check-data-on-stitching.png)


### 以设备为中心或以人员为中心的报告机制

创建连接时，必须定义用于人员ID的字段或标识。 例如，在Web数据集上，如果您选择设备ID作为人员ID，那么您将创建以设备为中心的报表，并失去将此数据与其他离线渠道联接的功能。 如果您选择跨渠道字段或身份（例如电子邮件），则在发生任何未经身份验证的事件时将会丢失。 要了解这种影响，您需要弄清楚有多少流量未经身份验证，以及有多少流量经过身份验证。

1. 创建计算量度&#x200B;**[!UICONTROL 个未验证事件以及总计]**。 在规则生成器中定义规则，如下所示：
   ![个未验证事件超过总计](/help/stitching/assets/calcmetric-unauthenticatedeventsovertotal.png)

1. 根据您之前定义的&#x200B;**[!UICONTROL _Email set]**&#x200B;量度创建计算量度&#x200B;**[!UICONTROL 电子邮件身份验证率]**。 在规则生成器中定义规则，如下所示：
   ![电子邮件身份验证率](/help/stitching/assets/calcmetric-emailauthenticationrate.png)

1. 使用&#x200B;**[!UICONTROL Unauthenticated事件对总计]**&#x200B;个计算量度以及&#x200B;**[!UICONTROL 电子邮件身份验证率]**&#x200B;个计算量度来创建一个[圆环图](/help/analysis-workspace/visualizations/donut.md)可视化图表。 该可视化图表显示数据集中未经身份验证和经过身份验证的事件数。

   ![标识详细信息](/help/stitching/assets/identification-details.png)



### 拼接识别率

您想要测量拼合前后的标识识别性能。 为此，请另外创建三个计算指标：

1. 一个&#x200B;**[!UICONTROL 拼接身份验证率]**&#x200B;计算量度，用于计算在事件总数中，拼接命名空间设置为所需身份的事件数。 在设置数据视图时，您创建了一个&#x200B;**[!UICONTROL 电子邮件拼接的命名空间]**&#x200B;量度，该量度包括一个只有在事件的命名空间设置为电子邮件时才计数的过滤器。 计算量度使用此&#x200B;**[!UICONTROL 电子邮件拼接的命名空间]**&#x200B;量度来指示具有所需标识的数据的百分比。
   ![拼接身份验证率计算量度](/help/stitching/assets/calcmetric-stitchedauthenticationrate.png)

1. 一个&#x200B;**[!UICONTROL 百分比增加]**&#x200B;计算量度，用于计算当前标识率与拼接标识率之间的原始百分比变化。
   ![百分比增加计算量度](/help/stitching/assets/calcmetric-percentincrease.png)

1. 一个&#x200B;**[!UICONTROL 提升]**&#x200B;计算量度，用于计算当前标识率与拼接标识率之间的提升。
   ![提升计算量度](/help/stitching/assets/calcmetric-lift.png)


### 结论

如果您将所有数据合并到一个Analysis Workspace自由格式表中，则可以开始查看拼合提供的影响和值，包括：

* 当前身份验证率：已具有正确人员ID的事件数在事件总数中的基线。
* 拼接身份验证率：在事件总数中，具有正确人员ID的新事件数。
* 百分比增加：原始百分比从拼接身份验证速率减去基线当前身份验证速率增加。
* 提升：相对于基准当前身份验证率的百分比变化。

![标识性能](/help/stitching/assets/identification-performance.png)


## 关键要点

本文的核心内容在于，拼接验证和分析可帮助您：

* 通过比较当前与拼接率，提供身份验证有效性的全面自定义视图。
* 通过百分比增加和提升量度，启用对改进的清晰测量。
* 帮助确定实施拼合对用户身份验证的真正影响。
* 创建标准化方式以跨团队传达身份验证性能。
* 允许做出有关身份验证策略和优化的数据驱动型决策。

这些指标一起为利益相关者全面展示了Customer Journey Analytics拼接如何影响身份验证成功率和整体人员识别性能。
