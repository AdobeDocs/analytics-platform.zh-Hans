---
title: 在Customer Journey Analytics中分析同意策略数据
description: 了解如何使用同意策略维度、量度和模板来报告Analysis Workspace中的访客同意策略成员资格。
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# 分析同意策略数据

您可以将同意策略数据从Experience Platform配置文件数据集摄取到Customer Journey Analytics连接。

在您[创建同意报告和筛选配置](/help/connections/consent-reporting-filtering/consent-configure.md)后，同意策略数据将作为已配置连接下数据视图中的新组件提供。 如果您有权访问存在这些组件的数据视图，则可以在Analysis Workspace中的任意位置使用这些组件。

## 同意策略组件

同意报告将以下组件添加到您的数据视图。 这些组件从配置文件数据集中的`consentPoliciesIDMap`字段读取，策略名称和描述来自同意策略查找数据集。

### 维度

| 维度 | 描述 |
|---------|----------|
| **[!UICONTROL 同意策略ID]** | 访客匹配的同意策略的标识符。 |
| **[!UICONTROL 策略名称]** | 同意策略查询数据集中的同意策略的友好名称。 |
| **[!UICONTROL 策略说明]** | 同意策略的描述，来自同意策略查找数据集。 |

### 量度

| 量度 | 描述 |
|---------|----------|
| **[!UICONTROL 经同意的访客]** | 与同意策略匹配的访客数。 |
| **[!UICONTROL 经同意的事件]** | 与符合同意策略的访客关联的事件数。 |
| **[!UICONTROL 唯一的同意政策]** | 在报告窗口中表示的不同同意政策的数量。 |

### 派生字段

派生字段引用`consentPoliciesIDMap`字段以提取同意策略ID。 您可以使用此派生字段作为其他基于同意的维度的基础。 有关派生字段的详细信息，请参阅[派生字段](/help/data-views/derived-fields/derived-fields.md)。

## 在Analysis Workspace中使用同意策略组件

要报告同意策略成员资格，请执行以下操作：

1. 在Analysis Workspace中，打开一个使用为同意报表配置的数据视图的项目。

1. 从“组件”面板中，将同意策略维度（如&#x200B;**[!UICONTROL 策略名称]**）拖动到自由格式表中。

1. 向表添加同意量度，如&#x200B;**[!UICONTROL 同意的访客]**。

1. 按任何其他维度（如页面或渠道）划分结果，以了解同意访客的行为。

## 使用同意策略分析模板

当为同意报表配置数据视图时，Customer Journey Analytics会自动在Analysis Workspace中提供同意策略分析模板。 此模板为报告访客同意策略成员资格提供了一个起点。

有关如何访问模板的信息，请参阅[访问并运行模板](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)。
