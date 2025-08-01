---
title: 拼接概述
description: 拼接概述
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 50599b36d333cae3735c6d4fd1b0af6fcabe9177
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 97%

---

# 拼接概述

>[!NOTE]
>
>您必须具有 **Select** 包或更高版本（用于[基于字段的拼接](fbs.md)）或者 **Prime** 包或更高版本（用于[基于图形的拼接](gbs.md)）才能使用本节中描述的功能。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

标识拼接（或简称为拼接）是一项强大的功能，可提升事件数据集对跨渠道分析的适用性。跨渠道分析是 Customer Journey Analytics 可以处理的主要用例，允许您基于常用标识符（人员 ID）对来自不同渠道的多个数据集的报告无缝进行组合和运行。

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户首先通过台式计算机上的广告访问了您的网站。该用户在下单时遇到了问题，随后致电客服团队以请求其帮助解决此问题。通过跨渠道分析，您可以将呼叫中心事件归因于最初点击的广告。

然而，作为 Customer Journey Analytics 中连接的一部分的基于事件的数据集，并非全都填充了足够的数据以支持这种现成可用的归因方法。特别是，基于网页或基于移动的体验数据集通常没有所有事件可用的实际人员 ID 信息。

拼接方法允许在一个数据集的行内重新生成身份标识键值，确保每个事件都有可用的人员 ID（拼接 ID）。拼接方法会查看来自经过身份验证和未经身份验证的会话的用户数据，以确定可用作拼接 ID 的常用临时 ID（人员 ID）值。这种重新生成键值的方法可将不同的记录解析为单个拼接 ID，以在人员级别而非设备或 Cookie 级别上进行分析。

Customer Journey Analytics 支持两种类型的拼接：[基于字段的拼接](fbs.md)和[基于图形的拼接](gbs.md)。

## 先决条件

>[!IMPORTANT]
>
>如果不能满足所有先决条件，就可能导致无法正确执行跨渠道分析。

在使用拼接之前，请确保您的组织已做好以下准备：

- 拼接包括将经过身份验证和未经身份验证的用户数据合并起来。在启用对事件数据集进行拼接之前，请确保遵守任何适用的法律和法规，包括获取必要的最终用户权限。请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。

- 将所需数据导入 Adobe Experience Platform：

   - 有关 Adobe Analytics 数据，请查阅[在 Customer Journey Analytics 中使用 Adobe Analytics 报告包数据](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。
   - 有关其他类型的数据，请参阅 Adobe Experience Platform 文档中的[创建架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/create-schema-ui)和[摄取数据](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)。

如果您在定义 Customer Journey Analytics 连接时将一个或多个拼接数据集与其他数据集（例如呼叫中心数据）相结合，您将受益于跨渠道分析。此连接配置假定那些其他数据集的每一行已经包含一个人员 ID，与拼接 ID 的情况类似。


## 限制

>[!IMPORTANT]
>
>
>- 将您对源事件数据集架构所做的任何更改也应用于新拼接的数据集架构。
>
>- 如果移除源数据集，拼接的数据集将停止处理，并被系统移除。
>
>- 数据使用情况标签不会自动传播到拼接的数据集架构。如果您将数据使用情况标签应用于源数据集架构，就需要将这些数据使用情况标签手动应用于拼接的数据集架构。请参阅[管理 Experience Platform 中的数据使用情况标签](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/labels/overview)，了解更多信息。

拼接是一项具有突破性的强大功能，但其使用方式存在限制。

- 仅支持事件数据集。不支持其他数据集，例如查找数据集。
- 拼接不以任何方式改变用于拼接的字段。拼接使用数据湖中非拼接数据集中存在的指定字段中的值。
- 拼接过程区分大小写。例如，如果字段中有时出现“Bob”一词，有时出现“BOB”一词，这两个 ID 会被视为单独的两人。

确保不要将拼接与以下方法混淆：

- 将两个或多个数据集合并。拼接仅适用于一个数据集。数据集的合并是由于设置 Customer Journey Analytics 连接并在此连接中所选的各数据集中选择相同的人员 ID 而发生。

- 将两个数据集连接。在 Customer Journey Analytics 中，连接通常用于在 Analysis Workspace 中查找或分类。拼接使用了连接功能，但拼接过程本身不只涉及到连接。

>[!MORELIKETHIS]
>
>[基于字段的拼接](fbs.md)
>&#x200B;>[基于图形的拼接](gbs.md)
>&#x200B;>[使用拼接](use-stitching.md)
>&#x200B;>[验证拼接](validate.md)
>&#x200B;>[关于拼接的常见问题解答](faq.md)

