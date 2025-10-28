---
title: 拼接概述
description: 拼接概述
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 359fe2a718ccef816377083aceb2652b4a905072
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 74%

---

# 拼接概述

>[!NOTE]
>
>您必须具有 **Select** 包或更高版本（用于[基于字段的拼接](fbs.md)）或者 **Prime** 包或更高版本（用于[基于图形的拼接](gbs.md)）才能使用本节中描述的功能。如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

标识拼接（或简称为拼接）是一项强大的功能，可提升事件数据集对跨渠道分析的适用性。跨渠道分析是Customer Journey Analytics的主要用例。 该功能允许您根据通用标识符（人员ID）对不同渠道的多个数据集无缝地组合和运行报表。

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户通过台式计算机上的广告访问您的网站。 用户购买产品，但随后订单出现问题。 然后，用户致电客服团队以帮助解决问题。 通过跨渠道分析，您可以将呼叫中心事件归因于用户最初点击的广告。

然而，作为 Customer Journey Analytics 中连接的一部分的基于事件的数据集，并非全都填充了足够的数据以支持这种现成可用的归因方法。特别是，基于Web或基于移动设备的体验数据集通常没有可用于所有事件的实际人员ID信息。

拼接允许为一个数据集的行中的身份重新生成键值，以确保人员ID（拼接ID）在每个事件上均可用。 拼接查看来自经过身份验证和未经身份验证的会话的用户数据，以确定可用作拼接ID的通用人员ID值。 通过重新生成键值，可以将不同的记录解析为单个拼接ID，以供在人员级别，而不是设备或Cookie级别进行分析。

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

## 启用拼合

您可以通过两种方式启用拼合：

- [请求启用拼接](/help/stitching/use-stitching.md)
- [在连接界面中启用拼接](/help/stitching/use-stitching-ui.md) [!BADGE Beta]{type=Informative}

## 限制

>[!IMPORTANT]
>
>
>- 对源事件数据集架构所做的任何更改，也应同步应用到新的拼接数据集架构中。
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


## Journey Optimizer 数据集

拼接支持以下自动生成的 Journey Optimizer 数据集：

- AJO 历程步骤事件
- AJO 入站活动事件数据集
- AJO 表面数据集
- AJO 消息反馈事件数据集* AJO 推送跟踪体验事件数据集
- AJO 电子邮件跟踪体验事件数据集
- AJO BCC 反馈事件数据集
- AJO 实时活动反馈事件数据集
- AJO ExD 决策事件数据集

>[!MORELIKETHIS]
>
>[基于字段的拼合](fbs.md)
>>[基于图形的拼接](gbs.md)
>>[使用拼接](use-stitching.md)
>>[验证拼接](validate.md)
>>[关于拼接的常见问题解答](faq.md)

