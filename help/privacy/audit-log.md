---
title: 审核日志
description: 了解如何查看和管理 Customer Journey Analytics 审核日志。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 9ed7b541ebb1a89b286040c4ea96025b08029499
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 97%

---

# 审核日志 {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="用户 ID"
>abstract="在包含所需用户的日志条目上单击“信息”按钮即可找到用户 ID。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="组件 ID"
>abstract="在包含所需组件的日志条目上单击“信息”按钮即可找到组件 ID。"

<!-- markdownlint-enable MD034 -->


为了提高系统中执行的活动的透明度和可见性，Adobe Customer Journey Analytics 允许您以“审核日志”的形式审核各种服务和功能的用户活动。这些日志形成审核记录，可以帮助解决问题，并帮助您的企业有效遵守公司数据管理政策和监管要求，例如“健康保险流通与责任法案”(HIPAA)。

从基本意义上讲，审核日志将说明&#x200B;**谁**&#x200B;执行了&#x200B;**什么**&#x200B;操作，以及在&#x200B;**什么时候**&#x200B;执行的。日志中记录的每个操作都包含元数据，这些元数据可指示操作类型、日期和时间、执行操作的用户的电子邮件 ID 以及与操作类型相关的其他属性。

本主题涵盖 Customer Journey Analytics 中的审核日志，包括如何在 UI 中查看和管理它们。

## 访问审核日志

为您的组织启用该功能后，系统会在活动发生时自动收集审核日志。您无需手动启用日志收集。

要查看和导出审核日志，您必须已在 Audit Logs Access 中获得&#x200B;**[!UICONTROL 审核日志访问]**&#x200B;访问控制权限。要了解如何管理 Customer Journey Analytics 功能的各项权限，请参阅[访问控制文档](../technotes/access-control.md)。

## 在 UI 中查看审核日志

在 Customer Journey Analytics 中，导航至&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 审核日志]**。

默认显示今天和昨天的审核日志。

![突出显示今天和昨天的审核日志。](assets/audit_ui.png)

您可以通过转到右上角的列选择器来选择可见的列。

## 查看有关单个日志条目的信息

双击描述旁边的信息 (i) 按钮。

![突出显示信息按钮的审核日志。](assets/info-button-audit.png)

以下项目显现：

* **[!UICONTROL 操作名称]**：所采取的操作。可能的值包括：
   * API_REQUEST：任何操作都会触发后端 API 请求。显示有关 API 请求的详细信息。
   * APPROVE：执行了“审批”操作。
   * CREATE：执行了“创建”操作。
   * DELETE：执行了“删除”操作。
   * EDIT：执行了“编辑”操作。
   * 禁运：当您在[报告活动管理器](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests)中限制请求时，该操作将记录在禁运下的审核日志中。
   * EXPORT：执行了“导出”操作。
   * ORG_CHANGE：执行了组织变更操作。
   * REFRESH：执行了“刷新”操作。
   * SHARE：执行了“分享”操作。
   * TRANSFER：执行了“转移”操作。
   * UNAPPROVE：执行了“未批准”操作。
   * UNSHARE：执行了“取消共享”操作。
* **[!UICONTROL 创建日期]**：采取行动的日期和时间。
* **[!UICONTROL 描述]**：对操作的总结。
* **[!UICONTROL 用户名]**：采取该操作的用户。有时，用户名可能会缺失。考虑使用[产品使用情况](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/tools/product-usage/usage-overview)功能，因为其始终包含登录用户名。
* **[!UICONTROL 电子邮件]**：执行该操作的用户的电子邮件地址。
* **[!UICONTROL 组件名称]**：用户对其采取操作的组件。
* **[!UICONTROL 组件类型]**：组件的类型。可能的值包括：
   * ANNOTATION
   * AUDIENCE
   * CALCULATED_METRIC
   * CONNECTION
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTER
   * IMS_ORG
   * MOBILE
   * PROJECT (Workspace)
   * REPORT
   * SCHEDULED_PROJECT
   * USER
   * USER_GROUP
* **[!UICONTROL 组件 ID]**：用户执行操作的组件的 ID。
* **[!UICONTROL IMS 组织 ID]**：组织的 IMS ID，格式为 `ABC123@AdobeOrg`。
* **[!UICONTROL 日志 ID]**：身份标识此日志条目的唯一 ID。
* **[!UICONTROL 用户 ID]**：用于识别执行该操作的用户的唯一 ID。
* **[!UICONTROL 用户类型]**：使用的身份验证类型。有效的值包括：
   * IMS
   * OKTA

### 筛选审核日志

选择漏斗图标（![过滤器](assets/filter-icon.png)）以显示过滤器控件列表，帮助缩小结果范围。仅显示最后 1,000 条记录，这与选择的各种过滤器无关。

![显示在日期范围内显示的过滤器的审核日志。](assets/filters.png)

在 UI 中有以下过滤器可用于审核事件：

| 过滤器 | 描述 |
| --- | --- |
| [!UICONTROL 日期范围] | 通过选择不同的日期或通过在多个日期上拖动光标来选择日期范围，从而筛选不同的日期范围。默认情况下，选择今天和昨天的日期。 |
| [!UICONTROL 操作] | 根据上面列出的任何操作名称进行过滤。 |
| [!UICONTROL 用户 ID] | 按用户 ID 筛选特定用户。通过选择用户名旁边的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 电子邮件] | 筛选特定用户的电子邮件地址。通过选择用户名旁边的信息 (i) 按钮可以找到电子邮件 ID。 |
| [!UICONTROL 组件 ID] | 筛选特定的组件 ID。通过选择所需组件的信息 (i) 按钮可以找到用户 ID。 |
| [!UICONTROL 组件类型] | 根据上面列出的任何组件类型进行过滤。 |

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
| [!UICONTROL 报告] | <ul><li>API 请求</li></ul> |
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

您在 UI 中可以执行的所有操作也可以使用 API 调用来完成。若要了解更多信息，请查看 [Customer Journey Analytics API 参考文档](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)。
