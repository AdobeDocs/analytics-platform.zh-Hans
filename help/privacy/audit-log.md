---
title: 审核日志
description: 了解如何查看和管理 CJA 审核日志。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: 53d019f99cbf06ee97243121fbf46f6d3ee9f0a7
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 99%

---

# 审核日志

为了提高系统中执行的活动的透明度和可见性，Customer Journey Analytics (CJA) 允许您以“审核日志”的形式审核各种服务和功能的用户活动。这些日志形成审核记录，可以帮助解决问题，并帮助您的企业有效遵守公司数据管理政策和监管要求，例如“健康保险流通与责任法案”(HIPAA)。

从基本意义上讲，审核日志将说明&#x200B;**谁**&#x200B;执行了&#x200B;**什么**&#x200B;操作，以及在&#x200B;**什么时候**&#x200B;执行的。日志中记录的每个操作都包含元数据，这些元数据可指示操作类型、日期和时间、执行操作的用户的电子邮件 ID 以及与操作类型相关的其他属性。

本主题涵盖 CJA 中的审核日志，包括如何在 UI 中查看和管理它们。

## 访问审核日志

为您的组织启用该功能后，系统会在活动发生时自动收集审核日志。您无需手动启用日志收集。

要查看和导出审核日志，您必须已在 Audit Logs Access 中获得&#x200B;**[!UICONTROL 审核日志访问]**&#x200B;访问控制权限。要了解如何管理 CJA 功能的各项权限，请参阅[访问控制文档](/help/getting-started/cja-access-control.md)。

## 在 UI 中查看审核日志

在 CJA 中，导航到&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 审核日志]**。

默认显示今天和昨天的审核日志。

![审核日志](assets/audit_ui.png)

您可以通过转到右上角的列选择器来选择可见的列。

## 查看有关单个日志条目的信息

双击描述旁边的信息 (i) 按钮。

![审核日志](assets/info-button-audit.png)

将显示以下项目：

| 项目 | 描述 |
| --- | --- |
| 操作名称 | 以下是可能的操作列表： <ul><li>API 请求</li><li>批准</li><li>创建</li><li>编辑</li><li>导出</li><li>登录失败</li><li>登录成功</li><li>注销</li><li>组织更改</li><li>刷新</li><li>共享</li><li>转移</li><li>取消批准</li><li>取消共享</li></ul> |
| 描述 | 操作、组件类型（包含 ID）和其他值的摘要。 |
| 用户名 | 执行操作的用户。 |
| 组件类型 | 可能的组件类型包括： <ul><li>批注</li><li>受众</li><li>计算量度</li><li>连接</li><li>数据组</li><li>数据视图 （此组件类型包括维度和量度）</li><li>功能访问</li><li>过滤器</li><li>IMS 组织</li><li>移动</li><li>项目</li><li>报表</li><li>计划的项目</li><li>用户</li><li>用户组</li></ul> |
| IMS 组织 ID | 首次登录 Adobe Experience Cloud 时为您的实例分配的唯一 ID。格式应为：xxx@AdobeOrg。 |
| 用户 ID | 标识执行此操作的用户的唯一 ID。 |
| 创建日期 | 执行此操作的时间。 |
| 电子邮件 | 执行此操作的用户的电子邮件。 |
| 组件 ID | 标识正在对其执行操作的组件的唯一 ID。 |
| 日志 ID | 标识此日志条目的唯一 ID。 |
| 用户类型 | 可能的类型包括：IMS、OKTA |

### 筛选审核日志

选择漏斗图标（![过滤器](assets/filter-icon.png)）以显示过滤器控件列表，帮助缩小结果范围。仅显示最后 1,000 条记录，这与选择的各种过滤器无关。

![过滤器](assets/filters.png)

在 UI 中有以下过滤器可用于审核事件：

| 过滤器 | 描述 |
| --- | --- |
| [!UICONTROL 日期范围] | 通过选择不同的日期或通过在多个日期上拖动光标来选择日期范围，从而筛选不同的日期范围。默认情况下，选择今天和昨天的日期。 |
| [!UICONTROL 操作] | 对以下一个或多个操作进行筛选： <ul><li>API 请求</li><li>批准</li><li>创建</li><li>编辑</li><li>导出</li><li>登录失败</li><li>登录成功</li><li>注销</li><li>组织更改</li><li>刷新</li><li>共享</li><li>转移</li><li>取消批准</li><li>取消共享</li></ul> |
| [!UICONTROL 用户 ID] | 按用户 ID 筛选特定用户。通过选择用户名旁边的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 电子邮件] | 筛选特定用户的电子邮件地址。通过选择用户名旁边的信息 (i) 按钮可以找到电子邮件 ID。 |
| [!UICONTROL 组件 ID] | 筛选特定的组件 ID。通过选择所需组件的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 组件类型] | 筛选一个或多个组件类型： <ul><li>批注</li><li>受众</li><li>计算量度</li><li>连接</li><li>数据组</li><li>数据视图</li><li>功能访问</li><li>过滤器</li><li>IMS 组织</li><li>移动</li><li>项目</li><li>报表</li><li>计划的项目</li><li>用户</li><li>用户组</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 审核日志记录的事件类型

下表概述了审核日志针对哪些组件类型记录了哪些操作：

| 组件类型 | 操作 |
| --- | --- |
| [!UICONTROL 批注] | <ul><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 受众] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li><li>导出</li><li>刷新</li></ul> |
| [!UICONTROL 计算量度] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 连接] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
|  | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 日期范围] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 过滤器] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL IMS 组织] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 项目] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 报表] | <ul><li>API 请求</li></ul> |
| [!UICONTROL 计划的项目] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 用户] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 用户组] | <ul><li>API 请求</li><li>创建</li><li>删除</li><li>编辑</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 下载审核日志

您可以下载 CSV 或 JSON 格式的审核日志。应用的任何过滤器或选择的列都会反映在下载的文件中。

1. 单击屏幕右上方的&#x200B;**[!UICONTROL 下载]**。
1. 指定格式。
1. 再次单击&#x200B;**[!UICONTROL 下载]**。

## 在 API 中管理审核日志

您在 UI 中可以执行的所有操作也可以使用 API 调用来完成。有关详细信息，请参阅 [CJA API 参考文档](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)。
