---
description: Analysis Workspace 中的异常检测使用一系列高级统计技术来确定是否应将观测到的情况视为异常。
title: 异常检测中使用的统计技术
feature: Anomaly Detection
exl-id: 7165e7a1-a04f-450e-bffd-e329adac6903
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 98%

---

# 异常检测中使用的统计技术

Analysis Workspace 中的异常检测使用一系列高级统计技术来确定是否应将观测到的情况视为异常。

根据报表中使用的日期粒度，特别针对每小时、每天、每周/每月异常检测，使用了 3 个不同的统计技术。下文概述了每种统计技术。

## 针对每天粒度的异常检测

对于每天粒度报表，算法考虑了多种重要因素以尽可能提供最精确的结果。首先，算法根据我们在两类模型（基于时间序列的模型或异常值检测模型，后者称为功能性过滤）中选择的可用数据，确定要应用的模型类型。

时间序列模型的选择基于 [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168) 描述的下列误差、趋势和季节性 (ETS) 类型组合。具体来讲，算法会尝试以下组合：

1. ANA（加性误差、无趋势、加性季节性）
1. AAA（加性误差、加性趋势、加性季节性）
1. MNM（乘性误差、无趋势、乘性季节性）
1. MNA（乘性误差、无趋势、加性季节性）
1. AAN（加性误差、加性趋势、无季节性）

算法通过选择具有最优平均绝对百分比误差 (MAPE) 的组合来测试每种组合的适用性。但如果最优时间序列模型的 MAPE 大于 15%，则采用功能性过滤。通常，重复度较高的数据（例如每周或每月）最适合使用时间序列模型。

完成模型选择后，算法接着根据假日和每年的季节性调整结果。对于假日，算法会执行相关检查，以确定报告日期范围内是否存在以下假日：

* 阵亡将士纪念日
* 7 月 4 日
* 感恩节
* 黑色星期五
* 网购星期一
* 12 月 24 至 26 日
* 1 月 1 日
* 12 月 31 日

这些假日的选择基于对许多客户数据点的广泛统计分析，旨在确定对客户最高值趋势影响最大的假日。虽然此列表没有囊括所有客户或业务周期内的假日，但我们发现，应用这些假日可以显著提升几乎所有客户数据集算法的整体性能。

选择了模型并确定了报告日期范围内的假日后，算法即会按照以下方式继续进行下一步：

1. 构建异常基准期 – 此期限最多可包含报告日期范围前的 35 天，以及 1 年以前的匹配日期范围（需要时还须考虑到闰年，并包含上一年不同日历日期可能出现的任何适用假日）。
1. 根据最新数据测试当前时间段（不包括上一年）的假日是否存在异常。
1. 如果当前日期范围内的假日存在异常，则基于上一年的假日（考虑前后 2 天），调整当前假日的预期值和置信区间。对当前假日的更正基于以下项的最低平均绝对百分比误差：

   1. 加性影响
   1. 剩性影响
   1. 按年差异

请注意，下面的示例明显提高了圣诞节和元旦的性能：

![两个折线图显示有无假日性能的性能变化。](assets/anomaly_statistics.png)

## 针对每小时粒度的异常分析

每小时数据同样依赖于每日粒度算法所用的时间序列算法。但是，此算法在很大程度上依赖于两个趋势模式：以 24 小时为周期以及以周末/工作日为周期。为了捕获这两种季节性影响，每小时算法使用上述相同方法分别为周末和工作日构建两个不同的模型。

每小时趋势的培训时间范围依赖于 336 小时的回顾窗口。

## 针对每周和每月粒度的异常检测

每周和每月趋势不会呈现与每日或每小时粒度所发现的相同每周或每日趋势，因此采用了单独的算法。对于每周和每月粒度，使用包含两个步骤的异常值检测方法，也就是 Generalized Extreme Studentized Deviate (GESD) 测试。此项测试在确定最大异常数量方面，同时考虑了预期的最大异常数量和调整后的箱线图方法（一种用于发现异常值的非参数方法）。这两个步骤是：

1. 调整后的箱线图功能：此功能确定给定输入数据中的最大异常数。
1. GESD 功能：应用至包含步骤 1 中输出内容的输入数据。

假日和按年季节性异常检测步骤接着从当年的数据中减去上一年的数据，然后使用上文中的两个步骤再次遍历该数据，以验证异常的发生是否存在季节性。上述每种日期粒度均使用 15 个回顾周期作为参照，其中包含选择的报告日期范围（15 个月或 15 周）及 1 年前的相应日期范围。