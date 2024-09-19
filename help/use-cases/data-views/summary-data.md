---
title: 在Customer Journey Analytics中使用摘要数据
description: 使用说明有关如何将摘要数据带入Customer Journey Analytics的所有详细信息
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 80139806-618a-46ff-b2c4-32d7bb85a526
source-git-commit: e6f57b03689bd9aaaec12c13fc95da5b079b901e
workflow-type: tm+mt
source-wordcount: '5187'
ht-degree: 8%

---

# 使用摘要数据

此用例可帮助您了解如何在报告和分析中使用摘要数据。 用例详细说明了在Customer Journey Analytics中使用摘要数据所需的所有步骤：

- 在Experience Platform中[摄取](#ingest)摘要数据和其他数据源。
- 为摘要数据和其他数据源设置[连接](#connection)。
- 配置[数据视图](#data-view)以组合数据源。
- 在[Workspace](#workspace)中报告和分析合并的数据。

用例提供了概要数据、事件数据和查找数据的示例数据。 所有数据都包含随机值。

## 摄取

对于此用例，您使用以下示例摘要数据，其中显示了在Facebook上运行营销活动的摘要数据。

+++摘要数据

| _id | campaign_name | 成本 | 印象 | campaign_id | network | ad_group | timestamp |
|---|---|---:|---:|---|---|---|---|
| 1 | 123营销活动 | 100 | 5000 | abc123 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 2 | 123营销活动 | 50 | 4000 | def123 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 3 | 123营销活动 | 125 | 6000 | ghi123 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 4 | 456营销活动 | 25 | 2500 | abc456 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 5 | 456营销活动 | 10 | 1000 | def456 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 6 | 456营销活动 | 115 | 5500 | ghi456 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 7 | 789营销活动 | 200 | 9000 | abc789 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 8 | 789营销活动 | 20 | 2000 | def789 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 9 | 789营销活动 | 225 | 12000 | ghi789 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 10 | 987营销活动 | 125 | 10000 | abc987 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 11 | 987营销活动 | 120 | 15000 | def987 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 12 | 987营销活动 | 315 | 22500 | ghi987 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 13 | 654营销活动 | 325 | 20000 | abc654 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 14 | 654营销活动 | 320 | 25000 | def654 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 15 | 654营销活动 | 315 | 22500 | ghi654 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 16 | 321营销活动 | 25 | 2000 | abc321 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 17 | 321营销活动 | 20 | 2500 | def321 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 18 | 321营销活动 | 15 | 2250 | ghi321 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |

[！[数据下载](/help/assets/icons/DataDownload.svg)](./assets/summary-data.csv)

+++

要在Customer Journey Analytics、报表中或在Workspace中分析数据时使用摘要数据，您需要

- Experience Platform中的摘要模式，
- Experience Platform中的摘要数据集，
- 配置为使用摘要数据集的Customer Journey Analytics连接，
- Customer Journey Analytics数据视图，已使用摘要数据的指标和维度正确配置。

您可以将此概要数据与事件数据的数据集和查找数据的数据集结合使用。

+++事件数据

事件数据在示例事件数据集中可用。 示例数据如下所示：

| timestamp | _id | page_name | person_id | tracking_code | 订单 | revenue_amont |
|---|---:|---|---|---|---:|---:|
| 2024-07-18T19:15:39+00:00 | 1 | 主页 | person-1abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 2 | 确认页面 | person-1abc123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 3 | 主页 | person-2def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 4 | 主页 | person-3ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 5 | 确认页面 | person-3ghi123 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 6 | 主页 | person-4abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 7 | 主页 | person-5def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 8 | 主页 | person-6ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 9 | 确认页面 | person-6ghi456 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 10 | 主页 | person-7abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 11 | 主页 | person-8def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 12 | 主页 | person-9ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 13 | 确认页面 | person-9ghi789 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 14 | 主页 | person-10abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 15 | 主页 | person-11def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 16 | 主页 | person-12ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 17 | 主页 | person-13abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 18 | 主页 | person-14def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 19 | 主页 | person-15ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 20 | 确认页面 | person-15ghi654 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 21 | 主页 | person-16abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 22 | 主页 | person-17def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 23 | 主页 | person-18ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 24 | 主页 | person-19abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 25 | 主页 | person-20def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 26 | 主页 | person-21ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 27 | 确认页面 | person-21ghi123 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 28 | 主页 | person-22abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 29 | 主页 | person-23def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 30 | 主页 | person-24ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 31 | 主页 | person-25abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 32 | 确认页面 | person-25abc789 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 33 | 主页 | person-26abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 34 | 主页 | person-27def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 35 | 主页 | person-28ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 36 | 主页 | person-29abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 37 | 确认页面 | person-29abc654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 38 | 主页 | person-30def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 39 | 主页 | person-31ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 40 | 主页 | person-32abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 41 | 主页 | person-33ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 42 | 确认页面 | person-33ghi456 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 43 | 主页 | person-34abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 44 | 主页 | person-35def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 45 | 主页 | person-36ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 46 | 确认页面 | person-36ghi789 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 47 | 主页 | person-37abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 48 | 主页 | person-38def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 49 | 主页 | person-39ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 50 | 主页 | person-40abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 51 | 确认页面 | person-40abc654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 52 | 主页 | person-41def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 53 | 主页 | person-42ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 54 | 主页 | person-43abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 55 | 主页 | person-44def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 56 | 主页 | person-45ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 57 | 主页 | person-46abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 58 | 确认页面 | person-46abc123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 59 | 主页 | person-47def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 60 | 主页 | person-48ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 61 | 主页 | person-49abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 62 | 主页 | person-50def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 63 | 主页 | person-51ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 64 | 主页 | person-52abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 65 | 确认页面 | person-52abc789 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 66 | 主页 | person-53abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 67 | 主页 | person-54def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 68 | 主页 | person-55ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 69 | 确认页面 | person-55ghi987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 70 | 主页 | person-56abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 71 | 主页 | person-57def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 72 | 确认页面 | person-57def123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 73 | 主页 | person-58ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 74 | 主页 | person-59abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 75 | 确认页面 | person-59abc456 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 76 | 主页 | person-60def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 77 | 主页 | person-61ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 78 | 主页 | person-62abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 79 | 确认页面 | person-62abc789 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 80 | 主页 | person-63def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 81 | 主页 | person-64ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 82 | 主页 | person-65abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 83 | 确认页面 | person-65abc987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 84 | 主页 | person-66def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 85 | 主页 | person-67ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 86 | 主页 | person-68abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 87 | 主页 | person-69def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 88 | 主页 | person-70ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 89 | 主页 | person-71abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 90 | 确认页面 | person-71abc321 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 91 | 主页 | person-72def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 92 | 主页 | person-73ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 93 | 主页 | person-74abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 94 | 主页 | person-75def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 95 | 主页 | person-76ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 96 | 主页 | person-77abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 97 | 确认页面 | person-77abc456 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 98 | 主页 | person-78def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 99 | 主页 | person-79ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 100 | 主页 | person-80abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 101 | 主页 | person-81abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 102 | 确认页面 | person-81abc987 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 103 | 主页 | person-82def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 104 | 主页 | person-83ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 105 | 主页 | person-84abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 106 | 主页 | person-85def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 107 | 确认页面 | person-85def654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 108 | 主页 | person-86ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 109 | 主页 | person-87abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 110 | 主页 | person-88ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 111 | 主页 | person-89abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 112 | 确认页面 | person-89abc789 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 113 | 主页 | person-90def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 114 | 主页 | person-91ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 115 | 主页 | person-92abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 116 | 确认页面 | person-92abc987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 117 | 主页 | person-93def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 118 | 主页 | person-94ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 119 | 主页 | person-95abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 120 | 主页 | person-96def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 121 | 确认页面 | person-96def654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 122 | 主页 | person-97ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 123 | 主页 | person-98abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 124 | 主页 | person-99def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 125 | 主页 | person-100ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 126 | 主页 | person-101abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 127 | 主页 | person-102def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 128 | 确认页面 | person-102def123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 129 | 主页 | person-103ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 130 | 主页 | person-104abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 131 | 主页 | person-105def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 132 | 主页 | person-106ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 133 | 主页 | person-107abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 134 | 主页 | person-108abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 135 | 确认页面 | person-108abc987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 136 | 主页 | person-109def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 137 | 主页 | person-110ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 138 | 确认页面 | person-110ghi987 |  |  |  |
| 2024-07-18T19:15:39+00:00 | 139 | 主页 | person-111def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 140 | 主页 | person-112def987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 141 | 确认页面 | person-112def987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 142 | 主页 | person-113ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 143 | 主页 | person-114abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 144 | 主页 | person-115def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 145 | 确认页面 | person-115def654 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 146 | 主页 | person-116ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 147 | 主页 | person-117abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 148 | 主页 | person-118def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 149 | 确认页面 | person-118def321 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 150 | 主页 | person-119ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 151 | 主页 | person-120abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 152 | 主页 | person-121def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 153 | 主页 | person-122ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 154 | 主页 | person-123abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 155 | 主页 | person-124def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 156 | 确认页面 | person-124def456 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 157 | 主页 | person-125ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 158 | 主页 | person-126abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 159 | 主页 | person-127abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 160 | 主页 | person-128def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 161 | 主页 | person-129ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 162 | 主页 | person-130abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 163 | 确认页面 | person-130abc654 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 164 | 主页 | person-131def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 165 | 主页 | person-132ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 166 | 主页 | person-133abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 167 | 主页 | person-134ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 168 | 确认页面 | person-134ghi456 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 169 | 主页 | person-135abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 170 | 主页 | person-136def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 171 | 主页 | person-137ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 172 | 主页 | person-138abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 173 | 确认页面 | person-138abc987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 174 | 主页 | person-139def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 175 | 主页 | person-140ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 176 | 主页 | person-141abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 177 | 主页 | person-142def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 178 | 确认页面 | person-142def654 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 179 | 主页 | person-143ghi654 | ghi654 |  |  |

[![数据下载](/help/assets/icons/DataDownload.svg)](./assets/event-data.csv)

+++

+++ 查找数据

查找数据在示例查找数据集中可用。 示例数据如下所示：

| _id | tracking_code | ad_group | campaign_name |
|---|---|---|---|
| 1 | abc123 | abc-adgroup | 123营销活动 |
| 2 | def123 | def-adgroup | 123营销活动 |
| 3 | ghi123 | ghi-adgroup | 123营销活动 |
| 4 | abc456 | abc-adgroup | 456营销活动 |
| 5 | def456 | def-adgroup | 456营销活动 |
| 6 | ghi456 | ghi-adgroup | 456营销活动 |
| 7 | abc789 | abc-adgroup | 789营销活动 |
| 8 | def789 | def-adgroup | 789营销活动 |
| 9 | ghi789 | ghi-adgroup | 789营销活动 |
| 10 | abc987 | abc-adgroup | 987营销活动 |
| 11 | def987 | def-adgroup | 987营销活动 |
| 12 | ghi987 | ghi-adgroup | 987营销活动 |
| 13 | abc654 | abc-adgroup | 654营销活动 |
| 14 | def654 | def-adgroup | 654营销活动 |
| 15 | ghi654 | ghi-adgroup | 654营销活动 |
| 16 | abc321 | abc-adgroup | 321营销活动 |
| 17 | def321 | def-adgroup | 321营销活动 |
| 18 | ghi321 | ghi-adgroup | 321营销活动 |

[![DataDownload](/help/assets/icons/DataDownload.svg)下载示例查找数据](./assets/lookup-data.csv)
+++

>[!INFO]
>
>未提供有关为事件和查找数据设置架构和数据集的更多详细信息。 此设置假定为常识，并遵循与查找数据相同的步骤。
>


### 摘要架构

摘要数据需要Experience Platform的摘要架构。 摘要架构是使用XDM摘要量度作为其基类的架构。

要在Experience Platform中创建概要架构，请执行以下操作：

1. 从中选择&#x200B;**[!UICONTROL Experience Platform]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从左边栏中选择&#x200B;**[!UICONTROL 架构]**。
1. 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 创建架构]**。
1. 在&#x200B;**[!UICONTROL 创建架构]**&#x200B;对话框中选择&#x200B;**[!UICONTROL 手动]**。 然后使用&#x200B;**[!UICONTROL 选择]**&#x200B;继续。
1. 在&#x200B;**[!UICONTROL 架构]** > **[!UICONTROL 创建架构]**&#x200B;向导的&#x200B;**[!UICONTROL 选择类]**&#x200B;步骤中，从&#x200B;**[!UICONTROL 为此架构]**&#x200B;选项选择基类&#x200B;**[!UICONTROL 其他]**。
1. 从列表中选择&#x200B;**[!UICONTROL XDM摘要量度]**（或使用![搜索](/help/assets/icons/Search.svg)字段进行搜索），然后选择&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 架构]** > **[!UICONTROL 创建架构]**&#x200B;向导的&#x200B;**[!UICONTROL 名称和审阅]**&#x200B;步骤中，输入&#x200B;**[!UICONTROL 架构显示名称]**，例如`Example Summary Data Schema`和可选描述。 选择&#x200B;**[!UICONTROL 完成]**&#x200B;以完成此步骤。

此时将显示基础摘要架构的结构，并使用摘要数据的字段进行扩充。 使用字段组将字段添加到架构。

要添加字段组，其中包含用于示例数据的字段：

1. 选择&#x200B;**[!UICONTROL 字段组]**&#x200B;中的![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**。
1. 在&#x200B;**[!UICONTROL 添加字段组]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 新建字段组]**。
1. 输入字段组的&#x200B;**[!UICONTROL 显示名称]**，例如`Example Summary Data`。 （可选）提供描述。
1. 选择&#x200B;**[!UICONTROL 添加字段组]**。
1. 返回架构结构用户界面。 在&#x200B;**[!UICONTROL 字段组]**&#x200B;中选择新的&#x200B;**[!UICONTROL 示例摘要数据]**。
1. 选择架构名称&#x200B;**[!UICONTROL 示例摘要数据架构]**&#x200B;旁边的![AddCircle](/help/assets/icons/AddCircle.svg)。 将打开一个&#x200B;**[!UICONTROL 字段属性]**&#x200B;面板，允许您添加字段的详细信息。
   1. 输入&#x200B;**[!UICONTROL 字段名称]**： `campaign_id`
   1. 输入&#x200B;**[!UICONTROL 显示名称]**： `campaign_id`
   1. 从&#x200B;**[!UICONTROL 选择数据类型]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 类型]**： **[!UICONTROL 字符串]**
   1. 确保已选择&#x200B;**[!UICONTROL 分配给]** **[!UICONTROL 字段组]**，并从下拉列表中选择&#x200B;**[!UICONTROL 示例摘要数据]**。
   1. 向下滚动到底部，然后选择&#x200B;**[!UICONTROL 应用]**。
1. 对摘要数据的其他字段重复上一步骤。 有关正确的值，请参阅下表。

   | 字段名称 | 显示名称 | 类型 | 字段组 |
   |---|---|---|---|
   | `ad_group` | `ad_group` | 字符串 | 示例摘要数据 |
   | `campaign_name` | `campaign_name` | 字符串 | 示例摘要数据 |
   | `cost` | `cost` | 双线 | 示例摘要数据 |
   | `impression` | `impression` | 整数 | 示例摘要数据 |
   | `network` | `network` | 字符串 | 示例摘要数据 |

1. 要将&#x200B;**[!UICONTROL 示例摘要数据]**&#x200B;字段组保存为架构的一部分，请选择&#x200B;**[!UICONTROL 保存]**。 当架构成功保存时，您将看到一条确认消息。

您现在已定义了一个架构，详述了概要数据的模型。 类似于下面的内容。

![摘要数据架构示例](../assets/example-summary-schema.png)





### 摘要数据集

要将摘要数据存储在Experience Platform中，您首先需要创建数据集，然后将摘要数据上传到数据集中。

要创建数据集，请执行以下操作：

1. 从中选择&#x200B;**[!UICONTROL Experience Platform]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从左边栏中选择&#x200B;**[!UICONTROL 数据集]**。
1. 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 创建数据集]**。
1. 在&#x200B;**[!UICONTROL 数据集]** > **[!UICONTROL 创建数据集]**&#x200B;屏幕中，选择&#x200B;**[!UICONTROL 从架构创建数据集]**。
1. 在&#x200B;**[!UICONTROL 工作流]** > **[!UICONTROL 从架构]**&#x200B;向导中创建数据集的&#x200B;**[!UICONTROL 选择架构]**&#x200B;步骤中，![搜索](/help/assets/icons/Search.svg)以搜索并选择您的&#x200B;**[!UICONTROL 示例摘要数据架构]**。
1. 选择&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 工作流]** > **[!UICONTROL 从架构创建数据集]**&#x200B;向导的&#x200B;**[!UICONTROL 配置数据集]**&#x200B;步骤中：
   1. 输入数据集的&#x200B;**[!UICONTROL 名称]**，例如： `Example Summary Data Dataset`。 （可选）提供描述。
   1. 选择&#x200B;**[!UICONTROL 完成]**。

您将看到一个显示新数据集详细信息的屏幕。

要将示例数据上传到此数据集，请执行以下操作：

1. 从中选择&#x200B;**[!UICONTROL Experience Platform]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从左边栏中选择&#x200B;**[!UICONTROL 工作流]**。
   1. 从&#x200B;**[!UICONTROL 工作流]**&#x200B;屏幕中的&#x200B;**[!UICONTROL 数据摄取]**&#x200B;选项中选择&#x200B;**[!UICONTROL 将CSV映射到XDM架构]**。
   1. 从&#x200B;**[!UICONTROL 将CSV映射到XDM架构]**&#x200B;面板中选择&#x200B;**[!UICONTROL 启动]**。
1. 在&#x200B;**[!UICONTROL 工作流]** > **[!UICONTROL 将CSV映射到XDM架构]**&#x200B;向导的&#x200B;**[!UICONTROL 数据流详细信息]**&#x200B;步骤中：
   1. 为&#x200B;**[!UICONTROL 目标数据集]**&#x200B;选择&#x200B;**[!UICONTROL 现有数据集]**。
   1. 从下拉列表中选择&#x200B;**[!UICONTROL 示例摘要数据数据集]**。
   1. 选择&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 工作流]** > **[!UICONTROL 将CSV映射到XDM架构]**&#x200B;向导的&#x200B;**[!UICONTROL 选择数据]**&#x200B;步骤中：
   1. 将包含CSV格式摘要数据的文件拖放到&#x200B;**[!UICONTROL 拖放文件]**。 或者，使用&#x200B;**[!UICONTROL 选择文件]**&#x200B;选择您的文件。
   1. 请确保&#x200B;**[!UICONTROL 数据格式]**&#x200B;和&#x200B;**[!UICONTROL 分隔符]**&#x200B;具有示例数据的正确值。 例如，**[!UICONTROL 已分隔]**&#x200B;作为&#x200B;**[!UICONTROL 数据格式]**，**[!UICONTROL 已分隔]**&#x200B;作为&#x200B;**[!UICONTROL 分隔符]**。
   1. 摘要数据的样本（10条记录）显示在&#x200B;**[!UICONTROL 样本数据]**&#x200B;中。
   1. 选择&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 工作流]** > **[!UICONTROL 将CSV映射到XDM架构]**&#x200B;向导的&#x200B;**[!UICONTROL 映射]**步骤中：
   ![示例数据集映射](../assets/example-dataset-mapping.png)
   1. 检查&#x200B;**[!UICONTROL Source数据]**&#x200B;的所有数据字段是否正确映射到架构中对应的&#x200B;**[!UICONTROL 目标字段]**。 对于示例数据，不会报告任何错误，因为您明确命名了架构中的字段，类似于示例数据中的字段名称。 否则，您可以使用此屏幕来更正映射。
   1. 您可以选择选择![齿轮](/help/assets/icons/Gear.svg) **[!UICONTROL 验证]**&#x200B;以（再次）验证数据。
   1. 您可以选择选择![预览](/help/assets/icons/Preview.svg) **[!UICONTROL 预览数据]**&#x200B;打开对话框，预览加载到数据集中的数据后。
   1. 选择&#x200B;**[!UICONTROL 完成]**。

在&#x200B;**[!UICONTROL 源]** > **[!UICONTROL 数据流 — XX/XX/XXXX， XX：XX XX]**&#x200B;中，将显示您的上传状态。 刷新以查看上载的更新。 成功后，示例数据将加载到Experience Platform中。




## 连接

要在Customer Journey Analytics中使用示例数据，请创建一个连接，其中包含来自Experience Platform的示例摘要数据数据集。


1. 从中选择&#x200B;**[!UICONTROL Customer Journey Analytics]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从顶部菜单中选择&#x200B;**[!UICONTROL 连接]**。
1. 选择&#x200B;**[!UICONTROL 创建新连接]**。
1. 在&#x200B;**[!UICONTROL 连接]** > **[!UICONTROL 无标题连接]**&#x200B;中：
   1. 输入&#x200B;**[!UICONTROL 连接名称]**，例如`Example Connection Using Summary Data`。
   1. 从沙盒下拉列表中选择包含您创建的数据集和其他要包含的数据集的沙盒。
   1. 从&#x200B;**[!UICONTROL 平均每日事件数]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 小于100万]**。
   1. 选择&#x200B;**[!UICONTROL 添加数据集]**。
   1. 在&#x200B;**[!UICONTROL 添加数据集]**&#x200B;向导的&#x200B;**[!UICONTROL 选择数据集]**&#x200B;步骤中：
      1. 搜索![搜索](/help/assets/icons/Search.svg)并选择&#x200B;**[!UICONTROL 示例摘要数据数据集]**、**[!UICONTROL 示例事件数据数据集]**&#x200B;和&#x200B;**[!UICONTROL 示例查找数据数据集]**。
      1. 选择&#x200B;**[!UICONTROL 下一步]**。
   1. 在&#x200B;**[!UICONTROL 添加数据集]**&#x200B;向导的&#x200B;**[!UICONTROL 数据集设置]**&#x200B;步骤中：

      1. 对于&#x200B;**[!UICONTROL 示例事件数据数据集]**：

         1. 确认&#x200B;**[!UICONTROL 人员ID]** (`person_id`)和&#x200B;**[!UICONTROL 时间戳]**&#x200B;的选择正确。
         1. 从&#x200B;**[!UICONTROL 数据源类型]**&#x200B;中选择&#x200B;**[!UICONTROL Web数据]**。
         1. 启用&#x200B;**[!UICONTROL 导入所有新数据]**。
         1. 启用&#x200B;**[!UICONTROL 回填所有现有数据]**。

      1. 对于&#x200B;**[!UICONTROL 示例查找数据数据集]**：

         1. 选择&#x200B;**[!UICONTROL tracking_code]**&#x200B;作为&#x200B;**[!UICONTROL Key]**，选择&#x200B;**[!UICONTROL tracking_code（事件数据集）]**&#x200B;作为&#x200B;**[!UICONTROL 匹配]**&#x200B;键。
         1. 从&#x200B;**[!UICONTROL 数据源类型]**&#x200B;中选择&#x200B;**[!UICONTROL Web数据]**。
         1. 启用&#x200B;**[!UICONTROL 导入所有新数据]**。
         1. 启用&#x200B;**[!UICONTROL 回填所有现有数据]**。

      1. 对于&#x200B;**[!UICONTROL 示例摘要数据数据集]**：

         1. 确认&#x200B;**[!UICONTROL 时间戳]**&#x200B;和&#x200B;**[!UICONTROL 时区]**&#x200B;的选择正确。
         1. 启用&#x200B;**[!UICONTROL 导入所有新数据]**。
         1. 启用&#x200B;**[!UICONTROL 回填所有现有数据]**。

      1. 选择&#x200B;**[!UICONTROL 添加数据集]**。

1. 在&#x200B;**[!UICONTROL 连接]** > **[!UICONTROL 使用摘要数据的连接示例]**&#x200B;连接屏幕中，选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存连接。

数据集中的数据会添加到Customer Journey Analytics，这可能需要几个小时。 所以，请在继续之前耐心等待。

一段时间后，验证数据集中的数据是否已正确加载到Customer Journey Analytics中。

1. 从中选择&#x200B;**[!UICONTROL Customer Journey Analytics]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从顶部菜单中选择&#x200B;**[!UICONTROL 连接]**。
1. 选择您的连接，例如&#x200B;**[!UICONTROL 使用摘要数据的连接示例]**。
1. 在&#x200B;**[!UICONTROL 连接]** > **[!UICONTROL 使用摘要数据的连接示例]**&#x200B;详细信息中选择适当的数据范围。
   1. 选择![日历](/help/assets/icons/Calendar.svg)，然后选择&#x200B;**[!UICONTROL 最近7天]**。
   1. 选择&#x200B;**[!UICONTROL 应用]**。

在&#x200B;**[!UICONTROL 数据集]**&#x200B;的列表中，已添加&#x200B;**[!UICONTROL 记录]**&#x200B;列中的值应确认来自数据集的数据现在已成为Customer Journey Analytics的一部分。

![摘要数据的连接示例](../assets/example-connection-summary-data.png)

## 数据视图

为了确保能够在Workspace中报告正确的数据，您需要创建一个包含相关量度和维度的数据视图。

1. 从中选择&#x200B;**[!UICONTROL Customer Journey Analytics]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**。
1. 选择&#x200B;**[!UICONTROL 创建新数据视图]**。
1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;中，浏览向导屏幕以配置数据视图。
   1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;的&#x200B;**[!UICONTROL 配置]**&#x200B;步骤中：
      1. 从&#x200B;**[!UICONTROL 设置]**&#x200B;中选择连接 | **[!UICONTROL 连接]**。 例如，**[!UICONTROL 使用摘要数据的连接示例]**。
      1. 为您的数据视图输入&#x200B;**[!UICONTROL 名称]**，例如`Example Data View Using Summary Data`。
      1. 保留所有其他设置。
      1. 选择&#x200B;**[!UICONTROL 保存并继续]**。
   1. 在&#x200B;**[!UICONTROL 数据视图]** > **[!UICONTROL 使用摘要数据的示例数据视图的**[!UICONTROL &#x200B;组件&#x200B;]**步骤中]**：
      1. 将以下组件添加到“Dimension和量度”列表。 请注意，为清楚起见，组件名称是从其默认名称修改的，在组件面板的&#x200B;**[!UICONTROL 组件设置]**&#x200B;中使用&#x200B;**[!UICONTROL 组件名称]**（在右侧）。

         **指标**

         | 组件名称 | 数据集 | 架构数据类型 | 架构路径 |
         |---|---|---|---|
         | 成本 | 示例摘要数据数据集 | 双线 | *_tenant*.cost |
         | 展示次数 | 示例摘要数据数据集 | 整数 | *_tenant*.impression |
         | 订单数 | 示例事件数据数据集 | 整数 | *_tenant*.订单 |
         | 收入 | 示例事件数据数据集 | 双线 | *_tenant*.revenue_amount |

         **维度**

         | 组件名称 | 数据集 | 架构数据类型 | 架构路径 |
         |---|---|---|---|
         | 广告组（查找） | 示例查找数据集 | 字符串 | *_tenant*.ad_group |
         | 广告组（摘要） | 示例摘要数据数据集 | 字符串 | *_tenant*.ad_group |
         | 营销活动 ID | 示例摘要数据集 | 字符串 | *_tenant*.campaign_id |
         | 营销活动名称（查找） | 示例查找数据集 | 字符串 | *_tenant*.campaign_name |
         | 营销活动名称（摘要） | 示例摘要数据数据集 | 字符串 | *_tenant*.campaign_name |
         | 网络 | 示例摘要数据数据集 | 字符串 | *_tenant*.network |
         | 页面名称 | 示例事件数据数据集 | 字符串 | *_tenant*.page_name |
         | 人员 ID | 示例事件数据数据集 | 字符串 | *_tenant*.person_id |
         | 跟踪代码（事件） | 示例事件数据数据集 | 字符串 | *_tenant*.tracking_code |
         | 跟踪代码（查找） | 示例查找数据集 | 字符串 | *_tenant*.tracking_code |

      1. 在&#x200B;**[!UICONTROL 事件]**&#x200B;列表中选择&#x200B;**[!UICONTROL Dimension（事件）]**&#x200B;维度。 在组件面板中：

         ![跟踪代码摘要数据](../assets/tracking-code-summary-data.png)
         1. 展开![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要数据组]**。
         1. 启用&#x200B;**[!UICONTROL 创建分组]**。
         1. 从&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 促销活动ID]**。 此步骤可确保正确组合事件数据和摘要数据以便进行报告。
         1. 您可以选择在报表&#x200B;]**中启用**[!UICONTROL &#x200B;隐藏。 [!UICONTROL 在报表中隐藏]确保所选维度（[!UICONTROL 促销活动ID]）在Analysis Workspace和其他Customer Journey Analytics报表工具中隐藏。 如果已启用此选项，则可以验证选项：
            1. 在&#x200B;**[!UICONTROL 营销活动]**&#x200B;列表中选择&#x200B;**[!UICONTROL DimensionID]**&#x200B;维度。
            1. 您注意到现在已在&#x200B;**[!UICONTROL 组件设置]**&#x200B;中自动启用&#x200B;**[!UICONTROL 隐藏报表中的组件]**。

      1. 创建新的派生字段，例如`Campaign Name (Lookup Derived Field)`，以确保您可以使用示例查找数据数据集中的“促销活动名称（查找）”维度在Workspace中报告。

         营销活动名称](../aa-data/../assets/summary-derived-field.png)的![派生字段

         1. 为&#x200B;**[!UICONTROL 值]**&#x200B;选择&#x200B;**[!UICONTROL campaign_id]**。
         1. 从&#x200B;**[!UICONTROL 查找数据集]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL 示例查找数据数据集]**。
         1. 从&#x200B;**[!UICONTROL 匹配键]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL tracking_code]**。
         1. 从&#x200B;**[!UICONTROL 要返回的值]**&#x200B;下拉菜单中选择&#x200B;**[!UICONTROL campaign_name]**。
         1. 选择&#x200B;**[!UICONTROL 保存]**。

      1. 将新创建的派生字段&#x200B;**[!UICONTROL 促销活动名称（查找派生字段）]**&#x200B;添加到&#x200B;**[!UICONTROL Dimension]**&#x200B;组件列表。

      1. 在&#x200B;**[!UICONTROL Dimension]**&#x200B;列表中选择&#x200B;**[!UICONTROL 促销活动名称（查找）]**&#x200B;维度。 在组件面板中：

         ![派生字段摘要数据组](../assets/derived-field-summary-data-group.png)

         1. 展开![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要数据组]**。
         1. 启用&#x200B;**[!UICONTROL 创建分组]**。
         1. 从&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 促销活动名称（查找派生字段）]**。 此步骤确保示例查找数据数据集中的促销活动名称（查找）可以在报表中安全使用(请参阅[Workspace](#workspace))。

      1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;列表中选择&#x200B;**[!UICONTROL 收入]**&#x200B;指标。 在组件面板中：

         ![收入摘要数据](../assets/revenue-summary-data.png)
         1. 展开![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 归因]**。
            1. 从&#x200B;**[!UICONTROL 归因模型]**&#x200B;下拉列表中选择![AttributionLastTouch](/help/assets/icons/AttributionLastTouch.svg) **[!UICONTROL Last Touch]**。
            1. 从&#x200B;**[!UICONTROL 回顾窗口]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 30天]**。
         1. 展开![V形](/help/assets/icons/ChevronDown.svg) **格式**。
            1. 从&#x200B;**[!UICONTROL 格式]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 货币]**。
            1. 从&#x200B;**[!UICONTROL 小数位]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 2]**。

      1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;列表中选择&#x200B;**[!UICONTROL 订单]**&#x200B;指标。 在组件面板中：

         ![订单摘要数据](../assets/orders-summary-data.png)
         1. 展开![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 归因]**。
            1. 从&#x200B;**[!UICONTROL 归因模型]**&#x200B;下拉列表中选择![AttributionLastTouch](/help/assets/icons/AttributionLastTouch.svg) **[!UICONTROL Last Touch]**。
            1. 从&#x200B;**[!UICONTROL 回顾窗口]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 30天]**。
         1. 展开![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 格式]**。
            1. 从&#x200B;**[!UICONTROL 格式]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL 十进制]**。
            1. 从▲2}将上升趋势显示为&#x200B;]**下拉列表中选择良好（绿色）]**。**[!UICONTROL **[!UICONTROL 

      1. 选择&#x200B;**[!UICONTROL 保存并继续]**。

   1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;的&#x200B;**[!UICONTROL 设置]**&#x200B;步骤中：
      1. 将所有设置保留为其默认值。
      1. 选择&#x200B;**[!UICONTROL 保存并完成。]**

您现在已设置数据视图，以便正确报告摘要数据。


## 工作区

要报告您的摘要数据，请在Analysis Workspace中创建一个新项目。

1. 从中选择&#x200B;**[!UICONTROL Customer Journey Analytics]**   ![应用](/help/assets/icons/Apps.svg)   应用程序切换器。
1. 从顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择&#x200B;**[!UICONTROL 创建项目]**。
1. 从包含用于创建空白Workspace项目的选项的对话框中选择&#x200B;**[!UICONTROL 空白Workspace项目]**。
1. 选择&#x200B;**[!UICONTROL 创建]**。

您看到一个带有[!UICONTROL 自由格式]面板的空画布，它包含一个空的[!UICONTROL 自由格式表]。

1. 确保为面板选择的数据视图是指包含摘要数据配置的数据视图。 例如，**[!UICONTROL 使用摘要数据的示例数据视图。]**
1. 确保该数据范围对您要报告的数据有效。 例如：**[!UICONTROL 最近2个月]**。
1. 从&#x200B;**[!UICONTROL Dimension]**&#x200B;中拖动&#x200B;**[!UICONTROL 跟踪代码（事件）]**&#x200B;并将维度拖放到空的自由格式表中。
1. 将&#x200B;**[!UICONTROL 订单]**&#x200B;从&#x200B;**[!UICONTROL 指标]**&#x200B;拖放到&#x200B;**[!UICONTROL 事件]**&#x200B;列以替换自由格式表中的该列。
1. 从&#x200B;**[!UICONTROL 量度]**&#x200B;中拖动&#x200B;**[!UICONTROL 收入]**，并放置要作为附加列添加到自由格式表的量度。
1. 从&#x200B;**[!UICONTROL 量度]**&#x200B;中拖动&#x200B;**[!UICONTROL 展示次数（摘要）]**，并放置要作为附加列添加到自由格式表的量度。
1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;中拖动&#x200B;**[!UICONTROL 成本（摘要）]**，然后拖放指标以添加为自由格式表的附加列。
1. 要保存项目，请选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 保存]**，然后为您的项目提供一个名称。 例如，`Example Project Using Summary Data`。

您希望使用报告摘要数据的强大功能并报告每次展示成本和广告支出回报率(ROAS)。 要报告这些指标，您必须创建两个计算指标。

1. 选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**。
1. 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;以添加新的计算量度。
   1. 为&#x200B;**[!UICONTROL 名称]**&#x200B;指定`Cost per Impression`。
   1. 为&#x200B;**[!UICONTROL 格式]**&#x200B;选择&#x200B;**[!UICONTROL 货币]**。
   1. 为&#x200B;**[!UICONTROL 小数位]**&#x200B;指定`4`。
   1. 使用![事件](/help/assets/icons/Event.svg) **[!UICONTROL 成本（摘要）]** **[!UICONTROL ÷]** **[!UICONTROL 展示次数（摘要）]**&#x200B;作为&#x200B;**[!UICONTROL 定义]**。
   1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;以添加另一个新的计算量度。
   1. 为&#x200B;**[!UICONTROL 名称]**&#x200B;指定`Return on Ad Spend`。
   1. 为&#x200B;**[!UICONTROL 格式]**&#x200B;选择&#x200B;**[!UICONTROL 货币]**。
   1. 为&#x200B;**[!UICONTROL 小数位]**&#x200B;选择`2`。
   1. 使用![事件](/help/assets/icons/Event.svg) **[!UICONTROL 收入（最近联系） | 30天)]** **[!UICONTROL −]** ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 成本（摘要）]**&#x200B;作为&#x200B;**[!UICONTROL 定义]**。
   1. 选择&#x200B;**[!UICONTROL 保存]**。

将计算量度添加到报表中。

1. 从&#x200B;**[!UICONTROL 指标]**&#x200B;中拖动&#x200B;**[!UICONTROL 每次展示成本]** ![计算器](/help/assets/icons/Calculator.svg)并放置指标，以将其添加为自由格式表的附加列。
   1. 选择![设置](/help/assets/icons/Setting.svg)列设置。
      1. 禁用&#x200B;**[!UICONTROL 百分比]**。
1. 从&#x200B;**[!UICONTROL 量度]**&#x200B;中拖动&#x200B;**[!UICONTROL 广告支出回报]** ![计算器](/help/assets/icons/Calculator.svg)并放置量度，以将其添加为自由格式表的附加列。
   1. 选择![设置](/help/assets/icons/Setting.svg)列设置。
      1. 禁用&#x200B;**[!UICONTROL 百分比]**。
      1. 启用&#x200B;**[!UICONTROL 条件格式]**。
         1. 选择&#x200B;**[!UICONTROL 自动生成]**。
         1. 选择首选的&#x200B;**[!UICONTROL 条件格式调色板]**。
   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存您的项目。

如果要报告促销活动名称而不是跟踪代码（事件），请执行以下步骤：

1. 复制&#x200B;**[!UICONTROL 摘要数据报表]**&#x200B;自由格式表可视化图表。
1. 将重复的可视化图表重命名为`Summary Data Report (using Campaign Name)`。
1. 将![Switch](/help/assets/icons/Switch.svg)的&#x200B;**[!UICONTROL 跟踪代码（事件）]**&#x200B;维度替换为&#x200B;**[!UICONTROL 促销活动名称（查找）]**&#x200B;维度。

由于您创建的派生字段以及促销活动名称（查找）的摘要数据组组件配置，因此您可以正确报告促销活动名称（查找）。 查看[数据视图](#data-view)。

您的最终项目应该如下所示。

![使用摘要数据的示例项目，显示带有摘要数据报告的摘要数据面板](../assets/summary-workspace.png)


>[!MORELIKETHIS]
>
>[摘要数据](/help/data-views/summary-data.md)
>[摘要数据组组件设置](/help/data-views/component-settings/summary-data-group.md)
