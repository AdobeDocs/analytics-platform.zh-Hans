---
title: 审核日志
description: 了解如何查看和管理CJA审核日志。
source-git-commit: a866dec61df93bf730529a2d7513b4d76bab6694
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---


# 审核日志

>[!NOTE]
>
>此功能当前正在进行[小范围测试](/help/release-notes/releases.md)。

为了提高系统中所执行活动的透明度和可见性，Customer Journey Analytics(CJA)允许您以“审核日志”的形式审核各种服务和功能的用户活动。 这些日志形成了一个审核跟踪，可帮助解决问题，并帮助您的企业有效遵守公司数据管理政策和法规要求，如健康保险流通和责任法案(HIPAA)。

从基本意义上讲，审核日志会告知 **who** 执行 **什么** 操作和 **when**. 日志中记录的每个操作都包含元数据，这些元数据指示操作类型、日期和时间、执行操作的用户的电子邮件ID，以及与操作类型相关的其他属性。

本主题介绍CJA中的审核日志，包括如何在UI中查看和管理这些日志。

## 访问审核日志

为贵组织启用该功能后，会在发生活动时自动收集审核日志。 您无需手动启用日志收集。

要查看和导出审核日志，您必须获得 **[!UICONTROL 审核日志访问]** 在Adobe控制台中访问控制权限。 要了解如何管理CJA功能的各个权限，请参阅 [访问控制文档](/help/getting-started/cja-access-control.md).

## 在UI中查看审核日志

在CJA中，导航到 **[!UICONTROL 工具]** > **[!UICONTROL 审核日志]**.

默认显示今天和昨天的审核日志。

![审核日志](assets/audit_ui.png)

您可以通过转到右上方的列选择器来选择哪些列可见。

## 查看有关单个日志条目的信息

双击描述旁边的信息(i)按钮。

![审核日志](assets/info-button-audit.png)

显示了以下项目：

| 项目 | 描述 |
| --- | --- |
| 操作名称 | 以下是可能的操作列表： <ul><li>API_Request</li><li>批准</li><li>创建</li><li>编辑</li><li>导出</li><li>登录失败</li><li>Login_successful</li><li>注销</li><li>Org_change</li><li>刷新</li><li>共享</li><li>转移</li><li>取消批准</li><li>不共享</li></ul> |
| 描述 | 操作、组件类型（具有ID）和其他值的摘要。 |
| 用户名 | 执行操作的用户。 |
| 组件类型 | 可能的组件类型包括： <ul><li>批注</li><li>受众</li><li>计算量度</li><li>连接</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>筛选器</li><li>IMS_Org</li><li>移动</li><li>项目</li><li>报表</li><li>计划项目</li><li>用户</li><li>User_Group</li></ul> |
| IMS 组织 ID | 首次登录Adobe Experience Cloud时为实例提供的唯一ID。 应采用以下格式：xxx@AdobeOrg。 |
| 用户 ID | 标识执行此操作的用户的唯一ID。 |
| 创建日期 | 执行此操作时。 |
| 电子邮件 | 执行操作的用户的电子邮件。 |
| 组件 ID | 唯一ID，用于标识要操作的组件。 |
| 日志 ID | 标识此日志条目的唯一ID。 |
| 用户类型 | 可能的类型包括：IMS、OKTA |

### 筛选审核日志

选择漏斗图标(![过滤器](assets/filter-icon.png))以显示筛选器控件列表，以帮助缩小结果范围。 只显示最后1,000条记录，而不考虑选择的各种过滤器。

![筛选条件](assets/filters.png)

以下过滤器可用于UI中的审核事件：

| 过滤器 | 描述 |
| --- | --- |
| [!UICONTROL 日期范围] | 通过选择不同的日期或通过拖动光标跨多个日期选择日期范围，对不同日期范围进行过滤。 默认情况下，将选择今天和昨天的日期。 |
| [!UICONTROL 操作] | 过滤以下一个或多个操作： <ul><li>API_Request</li><li>批准</li><li>创建</li><li>编辑</li><li>导出</li><li>登录失败</li><li>Login_successful</li><li>注销</li><li>Org_change</li><li>刷新</li><li>共享</li><li>转移</li><li>取消批准</li><li>不共享</li></ul> |
| [!UICONTROL 用户 ID] | 按用户ID对特定用户进行过滤。 用户ID可以通过选择用户名旁边的信息(i)按钮来找到。 |
| [!UICONTROL 电子邮件] | 根据特定用户的电子邮件地址进行过滤。 通过选择用户名旁边的“信息(i)”按钮，可以找到电子邮件。 |
| [!UICONTROL 组件 ID] | 按特定组件ID进行过滤。 通过为所需组件选择信息(i)按钮，可以找到用户ID。 |
| [!UICONTROL 组件类型] | 根据一个或多个组件类型进行筛选： <ul><li>批注</li><li>受众</li><li>计算量度</li><li>连接</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>筛选器</li><li>IMS_Org</li><li>移动</li><li>项目</li><li>报表</li><li>计划项目</li><li>用户</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 审核日志记录的事件类型

下表概述了审核日志记录哪些组件类型的操作：

| 组件类型 | 操作 |
| --- | --- |
| [!UICONTROL 批注] | <ul><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 受众] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li><li>导出</li><li>刷新</li></ul> |
| [!UICONTROL 计算量度] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 连接] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
|  | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 日期范围] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 过滤器] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL IMS组织] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 项目] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 报表] | <ul><li>API_Request</li></ul> |
| [!UICONTROL 计划项目] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 用户] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |
| [!UICONTROL 用户组] | <ul><li>API_Request</li><li>创建</li><li>删除</li><li>编辑</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 下载审核日志

您可以下载CSV或JSON格式的审核日志。 应用的任何过滤器或选定的列都会反映在下载的文件中。

1. 单击 **[!UICONTROL 下载]** 中。
1. 指定格式。
1. 单击 **[!UICONTROL 下载]** 再次。

## 在API中管理审核日志

您可以在UI中执行的所有操作也可以使用API调用来完成。 请参阅 [CJA API参考文档](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) 以了解更多信息。