---
title: 拼接概述
description: 拼合概述
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: c27d5f44243e2cda252ac6a484a70964f0999dfc
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 15%

---

# 拼接概述

>[!NOTE]
>
>您必须具有&#x200B;**Select**&#x200B;程序包或更高版本（适用于[基于字段的拼接](fbs.md)）或&#x200B;**Prime**&#x200B;程序包或更高版本（适用于[基于图形的拼接](gbs.md)），才能使用本节中介绍的功能。 如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

身份拼接（或简单地说，拼接）是一项强大的功能，可以提高事件数据集进行跨渠道分析的适用性。 跨渠道分析是Customer Journey Analytics可以处理的主要用例，允许您基于通用标识符（人员ID）对不同渠道的多个数据集无缝组合和运行报表。

当您合并具有相似人员 ID 的数据集时，将跨设备和渠道进行归因。例如，用户首先通过台式计算机上的广告访问了您的网站。该用户在下单时遇到了问题，随后致电客服团队以请求其帮助解决此问题。通过跨渠道分析，您可以将呼叫中心事件归因于最初点击的广告。

很遗憾，并非所有Customer Journey Analytics中连接的基于事件的数据集都会填充足够的数据，以便开箱即用地支持此归因。 特别是，基于Web或基于移动设备的体验数据集通常没有可用于所有事件的实际人员ID信息。

拼接允许为一个数据集行中的身份重新生成键，确保人员ID（拼接ID）在每个事件上可用。 拼接查看来自经过身份验证和未经身份验证的会话的用户数据，以确定可用作拼接ID的通用临时ID（人员ID）值。 通过重新生成键值，可将不同的记录解析为单个拼合ID，以供在人员级别，而不是设备或Cookie级别进行分析。

Customer Journey Analytics支持两种类型的拼接：[基于字段的拼接](fbs.md)和[基于图形的拼接](gbs.md)。

## 先决条件

>[!IMPORTANT]
>
>如果不满足所有先决条件，则可能会导致无法正确进行跨渠道分析。

在使用拼合之前，请确保贵组织已做好以下准备：

- 拼接包括合并的经过身份验证的用户数据和未经身份验证的用户数据。 在激活事件数据集的拼合之前，请确保遵守适用的法律和法规，包括获取必要的最终用户权限。 请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。

- 将所需数据导入Adobe Experience Platform：

   - 有关Adobe Analytics数据，请参阅[在Customer Journey Analytics中利用Adobe Analytics报表包数据](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。
   - 有关其他类型的数据，请参阅 Adobe Experience Platform 文档中的[创建架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/tutorials/create-schema-ui)和[摄取数据](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/home)。

如果在定义Customer Journey Analytics连接过程中将一个或多个拼合数据集与其他数据集（例如呼叫中心数据）相结合，您将受益于跨渠道分析。 此连接配置假定其他那些数据集在每行上均已包含一个人员ID，与拼接ID类似。


## 限制

>[!IMPORTANT]
>
>
>- 将您对源事件数据集架构所做的任何更改也应用于新拼接的数据集架构，否则这会断开拼接的数据集。
>
>- 如果删除源数据集，则拼接的数据集将停止处理并被系统删除。
>
>- 数据使用标签不会自动传播到拼接的数据集架构。 如果您已将数据使用标签应用于源数据集架构，则需要手动将这些数据使用标签应用于拼接的数据集架构。 有关详细信息，请参阅[在Experience Platform中管理数据使用标签](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/data-governance/labels/overview)。

拼接是一项具有突破性的强大功能，但其使用方式存在限制。

- 仅支持事件数据集。不支持其他数据集，例如查找数据集。
- 拼接不会以任何方式转换用于拼接的字段。 拼接使用指定字段中的值，因为该值存在于数据湖内的未拼接数据集中。
- 拼接过程区分大小写。例如，如果字段中有时出现“Bob”一词，有时出现“BOB”一词，则这些id将被视为两个不同的人。

请确保不要将拼合与以下内容混淆：

- 两个或更多数据集的合并。 拼接仅适用于一个数据集。 数据集合并是设置Customer Journey Analytics连接并在该连接的所选数据集中选择相同的人员ID的结果。

- 两个数据集的连接。 在Customer Journey Analytics中，连接通常用于Analysis Workspace中的查找或分类。 尽管拼接使用连接功能，但过程本身涉及的连接还不止于。

>[!MORELIKETHIS]
>
>[基于字段的拼合](fbs.md)
>[基于图形的拼接](gbs.md)
>[使用拼接](use-stitching.md)
>[有关拼接](faq.md)的常见问题解答

