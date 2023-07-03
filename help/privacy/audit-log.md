---
title: 审核日志
description: 了解如何查看和管理Customer Journey Analytics审核日志。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 67%

---

# 审核日志

为了提高系统中所执行活动的透明度和可见性，Adobe Customer Journey Analytics允许您以“审核日志”的形式审核各种服务和功能的用户活动。 这些日志形成审核记录，可以帮助解决问题，并帮助您的企业有效遵守公司数据管理政策和监管要求，例如“健康保险流通与责任法案”(HIPAA)。

从基本意义上讲，审核日志将说明&#x200B;**谁**&#x200B;执行了&#x200B;**什么**&#x200B;操作，以及在&#x200B;**什么时候**&#x200B;执行的。日志中记录的每个操作都包含元数据，这些元数据可指示操作类型、日期和时间、执行操作的用户的电子邮件 ID 以及与操作类型相关的其他属性。

本主题介绍Customer Journey Analytics中的审核日志，包括如何在UI中查看和管理它们。

## 访问审核日志

为您的组织启用该功能后，系统会在活动发生时自动收集审核日志。您无需手动启用日志收集。

要查看和导出审核日志，您必须已在 Audit Logs Access 中获得&#x200B;**[!UICONTROL 审核日志访问]**&#x200B;访问控制权限。要了解如何管理Customer Journey Analytics功能的各个权限，请参阅 [访问控制文档](../admin/cja-access-control.md).

## 在 UI 中查看审核日志

在Customer Journey Analytics中，导航到 **[!UICONTROL 工具]** > **[!UICONTROL 审核日志]**.

默认显示今天和昨天的审核日志。

![审核日志](assets/audit_ui.png)

您可以通过转到右上角的列选择器来选择可见的列。

## 查看有关单个日志条目的信息

双击描述旁边的信息 (i) 按钮。

![审核日志](assets/info-button-audit.png)

将显示以下项目：

* **[!UICONTROL 操作名称]**：采取的操作。 可能的值包括：
   * API请求
   * 批准
   * 创建
   * DELETE
   * 编辑
   * 导出
   * 组织更改
   * 刷新
   * 共享
   * 转移
   * 取消批准
   * 取消共享
* **[!UICONTROL 创建日期]**：执行操作的日期和时间。
* **[!UICONTROL 描述]**：操作摘要。
* **[!UICONTROL 用户名]**：执行操作的用户。
* **[!UICONTROL 电子邮件]**：执行操作的用户的电子邮件地址。
* **[!UICONTROL 组件名称]**：用户对其执行操作的组件。
* **[!UICONTROL 组件类型]**：组件的类型。 可能的值包括：
   * 注释
   * AUDIENCE
   * CALCULATED_METRIC
   * 连接
   * 数据组
   * 数据视图
   * DATASET_STITCHING
   * DATE_RANGE
   * 功能访问
   * FILTER
   * IMS组织
   * 移动设备
   * 项目
   * 报告
   * 计划项目
   * 用户
   * 用户组
* **[!UICONTROL 组件Id]**：用户对其执行操作的组件的ID。
* **[!UICONTROL IMS组织ID]**：组织的IMS ID，采用格式 `ABC123@AdobeOrg`.
* **[!UICONTROL 日志ID]**：标识此日志条目的唯一ID。
* **[!UICONTROL 用户ID]**：标识执行操作的用户的唯一ID。
* **[!UICONTROL 用户类型]**：使用的身份验证类型。 有效的值包括：
   * IMS
   * OKTA

### 筛选审核日志

选择漏斗图标（![过滤器](assets/filter-icon.png)）以显示过滤器控件列表，帮助缩小结果范围。仅显示最后 1,000 条记录，这与选择的各种过滤器无关。

![过滤器](assets/filters.png)

在 UI 中有以下过滤器可用于审核事件：

| 过滤器 | 描述 |
| --- | --- |
| [!UICONTROL 日期范围] | 通过选择不同的日期或通过在多个日期上拖动光标来选择日期范围，从而筛选不同的日期范围。默认情况下，选择今天和昨天的日期。 |
| [!UICONTROL 操作] | 筛选上面列出的任何操作名称。 |
| [!UICONTROL 用户 ID] | 按用户 ID 筛选特定用户。通过选择用户名旁边的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 电子邮件] | 筛选特定用户的电子邮件地址。通过选择用户名旁边的信息 (i) 按钮可以找到电子邮件 ID。 |
| [!UICONTROL 组件 ID] | 筛选特定的组件 ID。通过选择所需组件的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 组件类型] | 筛选上面列出的任何组件类型。 |

{style="table-layout:auto"}

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

{style="table-layout:auto"}

## 下载审核日志

您可以下载 CSV 或 JSON 格式的审核日志。应用的任何过滤器或选择的列都会反映在下载的文件中。

1. 单击屏幕右上方的&#x200B;**[!UICONTROL 下载]**。
1. 指定格式。
1. 再次单击&#x200B;**[!UICONTROL 下载]**。

## 在 API 中管理审核日志

您在 UI 中可以执行的所有操作也可以使用 API 调用来完成。请参阅 [Customer Journey AnalyticsAPI参考文档](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) 了解更多信息。
