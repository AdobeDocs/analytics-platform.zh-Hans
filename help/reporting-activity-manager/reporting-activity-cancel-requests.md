---
title: 在报告活动管理器中取消报告请求
description: 了解如何使用报告活动管理器诊断和修复在报告高峰期出现的容量问题。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 1680e6115a75a0dd78f07aa0bb409b19b3585a78
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 8%

---

# 在报告活动管理器中取消报告请求

{{release-limited-testing}}

此 [!UICONTROL 报告活动管理器] 使管理员能够快速诊断和取消报表请求，以修复在报表高峰期出现的报表容量问题。

取消报告请求时，请考虑以下事项：

* 您可以取消特定请求，取消来自特定用户的所有请求，或取消与特定项目相关的所有请求。

* 在取消请求时，您还可以选择限制给定时间期的后续请求。

  当您限制后续请求时，该操作记录在 [审核日志](/help/privacy/audit-log.md) 以“禁运”为行动名称。

* 在以下情况下，您无法取消请求： [!UICONTROL **用户**] 请求的列显示为 [!UICONTROL **无法识别**]. 如果发生这种情况，则意味着用户所在的登录公司您没有管理权限。

有关报表活动管理器的更多信息，包括主要优势和权限要求，请参阅 [报表活动管理器概述](/help/reporting-activity-manager/reporting-activity-overview.md).

## 取消特定请求

您可以取消占用大量报告容量的单个请求。 取消请求时，您可以选择在给定时间段内进一步限制请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **请求**] 选项卡，然后选择一个或多个请求。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请执行以下操作：

   1. 启用该选项 [!UICONTROL **限制后续请求**].

      ![限制后续请求](assets/restrict-subsequent-requests.png)

   1. 从以下选项中进行选择：

      | 选项 | 函数 |
      |---------|----------|
      | [!UICONTROL **用户和项目**] | 将暂时限制与所选请求关联的用户运行关联项目的报告请求。 |
      | [!UICONTROL **用户**] | 与所选请求相关的用户将会被暂时限制提交任何报告请求。 |
      | [!UICONTROL **项目**] | 与所选请求相关的项目将会被暂时限制提交所有报告请求。 |
      | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!-- double-check this --><p>设置限制后，不能提前删除限制。</p> |

      {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   Analysis Workspace中会显示通知，告知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 按用户取消请求

您可以取消与一个或多个用户关联的所有请求。 在取消与某个用户相关联的请求时，您可以选择进一步限制该用户在给定时间段内的请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **用户**] 选项卡，然后选择一个或多个用户。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 来自x个用户的报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请执行以下操作：

   1. 启用该选项 [!UICONTROL **限制后续请求**]

      ![按用户限制后续请求](assets/restrict-subsequent-requests-user.png)

   1. 从以下选项中进行选择：

      | 选项 | 函数 |
      |---------|----------|
      | [!UICONTROL **用户和项目**] | 将暂时限制选定用户向关联项目提出任何报告请求。 <p>这是限制最少的选项。</p> |
      | [!UICONTROL **用户**] | 将暂时限制选定用户提出任何报告请求。 |
      | [!UICONTROL **项目**] | 与选定用户关联的项目将被限制于任何用户发出的任何报告请求。 |
      | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!--double-check this--> <p>设置限制后，不能提前删除限制。</p> |

      {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   Analysis Workspace中会显示通知，告知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 按项目取消请求

您可以取消与一个或多个项目关联的所有请求。 在取消与项目关联的请求时，您可以选择进一步限制在给定时间段内与该项目关联的请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **项目**] 选项卡，然后选择一个或多个项目。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 来自x个项目的报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请执行以下操作：

   1. 启用该选项 [!UICONTROL **限制后续请求**].

      ![按项目限制后续请求](assets/restrict-subsequent-requests-project.png)

   1. 从以下选项中进行选择：

      | 选项 | 函数 |
      |---------|----------|
      | [!UICONTROL **用户和项目**] | 选定项目将被暂时限制在相关用户发出的任何报告请求之外。<p>这是限制最少的选项。</p> |
      | [!UICONTROL **用户**] | 将限制与所选项目关联的用户提出任何报告请求。 |
      | [!UICONTROL **项目**] | 选定项目将被暂时限制于任何用户发出的任何报告请求中。 |
      | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!--double-check this--> <p>设置限制后，不能提前删除限制。</p> |

      {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   Analysis Workspace中会显示通知，告知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 按应用程序取消请求

您可以取消与一个或多个应用程序关联的所有请求。 在取消与应用程序关联的请求时，您可以选择进一步限制在给定时间段内与该应用程序关联的请求。

应用程序包括：

* Analysis Workspace UI
* 工作区计划项目
* Report Builder
* 生成器 UI：区段、计算量度、注释、受众等。
* 来自2.0 API的API调用
* 智能警报
* 完整表导出
* 与任何人共享链接
* 引导式分析
* 查询Analytics报表引擎的任何其他应用程序

要按应用程序取消请求，请执行以下操作：

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **应用程序**] 选项卡，然后选择一个或多个应用程序。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 来自x个项目的报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请执行以下操作：

   1. 启用该选项 [!UICONTROL **限制后续请求**]

      ![按应用程序限制后续请求](assets/restrict-subsequent-requests-application.png)

   1. 从以下选项中进行选择：

      | 选项 | 函数 |
      |---------|----------|
      | [!UICONTROL **用户和项目**] | 选定的应用程序将被暂时限制在相关用户和项目提出的任何报告请求之外。<p>这是限制最少的选项。</p> |
      | [!UICONTROL **用户**] | 与选定应用程序关联的用户将无法提出任何报告请求。 |
      | [!UICONTROL **项目**] | 与所选应用程序关联的项目将限制于任何用户发出的任何报告请求。 |
      | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!--double-check this--> <p>设置限制后，不能提前删除限制。</p> |

      {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   通知显示在应用程序中(例如在Analysis Workspace中)，通知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 用户访问已取消报告时的体验

在Analysis Workspace中，当用户尝试访问受取消影响的报表或可视化图表时，会看到以下消息：

### 项目消息

当用户尝试访问受取消影响的项目时，他们会看到一条消息，通知他们报告暂时受限：

![项目取消消息](assets/workspace-canceled-report.png)

### 可视化上的消息

当用户尝试访问受取消影响的可视化图表时，他们会看到一条消息，通知他们报告的数据处理暂时受限：

![可视化图表取消消息](assets/workspace-cancelled-visualization.png)
