---
title: 在报告活动管理器中取消报告请求
description: 了解如何使用报告活动管理器诊断和修复在报告高峰期出现的容量问题。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 7%

---

# 在报告活动管理器中取消报告请求

{{release-limited-testing}}

此 [!UICONTROL 报告活动管理器] 使管理员能够快速诊断和取消报表请求，以修复在报表高峰期出现的报表容量问题。

取消报告请求时，请考虑以下事项：

* 您可以取消特定请求，取消来自特定用户的所有请求，或取消与特定项目相关的所有请求。

* 在取消请求时，您还可以选择限制给定时间期的后续请求。

* 在以下情况下，您无法取消请求： [!UICONTROL **用户**] 请求的列显示为 [!UICONTROL **无法识别**]. 如果发生这种情况，则意味着用户所在的登录公司您没有管理权限。

有关报表活动管理器的更多信息，包括主要优势和权限要求，请参阅 [报表活动管理器概述](/help/reporting-activity-manager/reporting-activity-overview.md).

## 取消特定请求

您可以取消占用大量报告容量的单个请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **请求**] 选项卡，然后选择一个或多个请求。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请启用选项，以 [!UICONTROL **限制后续请求**]，然后从以下选项中选择：

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

您可以取消与一个或多个用户关联的所有请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **用户**] 选项卡，然后选择一个或多个用户。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 来自x个用户的报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请启用选项，以 [!UICONTROL **限制后续请求**]，然后从以下选项中选择：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **用户和项目**] | 将暂时限制选定用户向关联项目提出任何报告请求。 |
   | [!UICONTROL **用户**] | 将暂时限制选定用户提出任何报告请求。 |
   | [!UICONTROL **项目**] | 与选定用户关联的项目将被限制于任何用户发出的任何报告请求。 |
   | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!--double-check this--> <p>设置限制后，不能提前删除限制。</p> |

   {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   Analysis Workspace中会显示通知，告知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 按项目取消请求

您可以取消与一个或多个项目关联的所有请求。

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

1. 选择要取消报告请求的连接。 <!--double-check this step-->

   有关此页面上可用数据的更多信息，请参阅 [在报告活动管理器中查看报告活动](/help/reporting-activity-manager/reporting-activity.md).

1. 选择 [!UICONTROL **项目**] 选项卡，然后选择一个或多个项目。

   <!-- add screenshot -->

1. 选择 [!UICONTROL **取消请求**].

   此 [!UICONTROL **取消 _x_ 来自x个项目的报表请求**] 对话框随即显示。

1. 取消消息字段显示取消请求时向用户显示的消息。 提供了默认消息。 您可以更新默认消息以提供其他详细信息。

1. （可选）要限制给定时间段的将来请求，请启用选项，以 [!UICONTROL **限制后续请求**]，然后从以下选项中选择：

   | 选项 | 函数 |
   |---------|----------|
   | [!UICONTROL **用户和项目**] | 选定项目将被暂时限制在相关用户发出的任何报告请求之外。 |
   | [!UICONTROL **用户**] | 将限制与所选项目关联的用户提出任何报告请求。 |
   | [!UICONTROL **项目**] | 选定项目将被暂时限制于任何用户发出的任何报告请求中。 |
   | [!UICONTROL **限制进行**] | 选择限制请求的时长。 您可以选择1分钟（默认）、5分钟、10分钟、15分钟或30分钟。 <!--double-check this--> <p>设置限制后，不能提前删除限制。</p> |

   {style="table-layout:auto"}

1. 选择 [!UICONTROL **继续取消操作**].

   Analysis Workspace中会显示通知，告知用户请求已被取消。 有关这如何在Analysis Workspace中显示的更多信息，请参阅 [用户访问已取消报告时的体验](#experience-when-users-access-a-cancelled-report).

## 用户访问已取消报告时的体验

<!-- Update for CJA and AA -->

在Analysis Workspace中，当用户尝试访问管理员已取消的报告时，会看到以下消息：

![cancel-user-notice](assets/cancel-user-facing.png)