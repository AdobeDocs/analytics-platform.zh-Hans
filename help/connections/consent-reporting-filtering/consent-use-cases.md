---
title: 同意报告和筛选用例
description: 探索在Customer Journey Analytics中报告访客同意策略成员资格并在摄取时过滤非同意访客的用例。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 4661a066f90991e6fb149c6909ef4a9f75cf02ac
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 0%

---

# 同意报告和筛选用例

同意报告和筛选可帮助您报告访客同意策略成员资格，并（可选）在数据进入Customer Journey Analytics之前排除非同意的访客。 有关概述信息，请参阅[同意报告和筛选概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

本文介绍了示例用例。 在查看这些内容之前，请熟悉以下注意事项，因为它们会影响您在报表中看到的结果。

## 报表注意事项

* **筛选适用于连接级别**：启用筛选时，配置连接下的所有数据视图将继承相同的行为。 您无法在一个连接下以不同的方式筛选一个数据视图。

* **筛选使用包含逻辑**：仅当访客与适用于启用的营销操作的所有同意策略匹配时，才会摄取访客的数据。 将排除缺少任何适用策略的访客。

* **排除的数据无法恢复**：由于过滤发生在摄取时，因此排除的数据不会存储在Customer Journey Analytics中。 以后更改配置不会恢复过去日期的排除数据。

* **同意策略成员资格来自配置文件数据集**：报告反映配置文件数据集的`consentPoliciesIDMap`字段中存在的同意策略成员资格。 访客必须在连接中具有对应的事件才能显示在报表中。

## 示例用例

### 用例1：报告同意情况，但不过滤数据

了解有多少访客匹配每个同意策略，然后再决定是否过滤，以回答类似下面的问题：

* _“有多少访客同意使用Analytics？”_
* _“哪些同意策略在访客中的覆盖范围最大且最少？”_

**配置流：**

1. 创建配置并选择沙盒、配置文件数据集以及包含同意策略成员资格数据的连接。

1. 保留&#x200B;**[!UICONTROL Analytics数据]**&#x200B;和&#x200B;**[!UICONTROL 数据科学数据]**&#x200B;过滤将切换。

1. 在Analysis Workspace中，使用&#x200B;**[!UICONTROL 策略名称]**&#x200B;维度和&#x200B;**[!UICONTROL 同意的访客]**&#x200B;量度构建自由格式表以查看每个策略的覆盖率。

使用这些见解确定是否启用筛选以及针对哪些营销操作。

### 用例2：从Analytics报表中排除非同意的访客

确保标准报表仅包含同意使用Analytics的访客，以回答以下问题：

* _“当我们仅报告同意的访客时，受众的行为如何？”_
* _“我们能否确保未经同意的访客数据从未进入我们的分析报表？”_

**配置流：**

1. 创建或编辑支持分析报表的连接配置。

1. 启用&#x200B;**[!UICONTROL Analytics数据]**&#x200B;过滤切换。

1. 确认配置。 此后，仅当访客与适用于Analytics营销操作的所有同意策略匹配时，Customer Journey Analytics才会摄取访客的数据。

由于过滤在摄取时进行，因此下游报表、导出和API会自动反映仅同意的访客，而无需更改报表时间。

### 用例3：单独过滤分析和数据科学用例

将不同的同意要求应用于标准报表和数据科学用例，以回答以下问题：

* _“在对机器学习应用更严格的同意的同时，我们能否在Analytics中包含更广泛的访客集？”_

**配置流：**

1. 创建或编辑相关连接的配置。

1. 启用&#x200B;**[!UICONTROL Analytics数据]**&#x200B;切换、**[!UICONTROL 数据科学数据]**&#x200B;切换或同时启用这两者，具体取决于每个用例的同意要求。

1. 确认配置。 Customer Journey Analytics会独立评估适用于每个已启用的营销操作的同意政策。

当您的组织对不同类别的数据使用应用不同的同意要求时，请使用此方法。
