---
description: 通过电子邮件发送Analysis Workspace项目，或者计划项目的提交时间。
keywords: Analysis Workspace
title: 通过电子邮件将Customer Journey Analytics数据发送给其他人
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 8eda6e9ed27ab458951cd4bd08f511987bc61eb0
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 63%

---

# 通过电子邮件将Customer Journey Analytics数据发送给其他人

您可以通过电子邮件将Customer Journey Analytics数据发送给选定的收件人来导出收件人数据。 您可以临时发送文件，也可以配置按计划发送的文件。 可以采用 CSV 或 PDF 格式发送文件。

应用于项目的所有标记都会自动应用于导出。

此外，还提供了导出Customer Journey Analytics数据的其他方法，如中所述 [导出概述](/help/analysis-workspace/export/export-project-overview.md).

## 立即发送文件 {#now}

要通过电子邮件立即将文件发送给收件人，请执行以下操作：

1. 单击 **[!UICONTROL 共享] > [!UICONTROL 导出文件]**.
1. 指定文件类型：
   * [!UICONTROL **CSV**]：如果您需要纯文本数据，请选择此选项。
   * [!UICONTROL **PDF**]：如果您希望下载的文件包含项目中所有显示（可见）的表格和可视化图表，请选择此选项。
1. （可选）添加要包含在电子邮件中的描述以说明正在接收的文件。
1. 添加收件人或组。也可以输入电子邮件地址。
1. （仅适用于 Healthcare Shield 客户）提供密码。请参阅“密码保护计划报告”部分。
1. 单击&#x200B;**[!UICONTROL 立即发送]**。
1. （可选）单击&#x200B;**[!UICONTROL 显示计划选项]**&#x200B;以指定发送计划。

![立即发送文件](assets/send-file-no-scheduling-options.JPG)

## 按计划发送文件 {#schedule}

要通过电子邮件按定期计划将文件发送给收件人，请执行以下操作：

1. 单击 **[!UICONTROL 共享] > [!UICONTROL 计划文件导出]**.
1. 指定文件类型（CSV 或 PDF）。
1. （可选）添加要包含在电子邮件中的说明，以阐述所发送的文件。
1. 添加收件人或组。也可以输入电子邮件地址。
1. （仅适用于 Healthcare Shield 客户）提供密码。请参阅“密码保护计划报告”部分。
1. 通过修改开始日期和结束日期输入值来指定计划发送文件的日期范围。结束日期必须在自创建或修改计划之日起的一年内。
1. 指定发送频率。每种频率均允许进行不同的自定义。
1. 单击&#x200B;**[!UICONTROL 按计划发送]**。

![](assets/send-file.JPG)

## 计划项目管理器 {#manager}

可以在 **[!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 计划项目]**&#x200B;下管理计划的 Analysis Workspace 项目。

在计划项目管理器中，您可以编辑和删除重复的项目计划。在搜索栏中搜索计划，或者使用左边栏中的过滤器选项搜索计划。您可以按标记、批准的计划、所有者等进行过滤。

| 字段 | 描述 |
| --- | --- |
| [!UICONTROL 收藏夹] | 选择星形图标将此计划加入收藏。 |
| [!UICONTROL 计划 ID] | 此 ID 主要用于调试用途。 |
| [!UICONTROL 标题和描述] | 此项目的标题和描述。 |
| [!UICONTROL 所有者] | 创建并拥有此项目的人。 |
| [!UICONTROL 标记] | （可选）标记是一种用于排列项目的好方法。 所有用户均可创建标记，并将一个或多个标记应用到项目。 但是，您只能查看自己拥有或者与您共享的项目的标记。 |
| [!UICONTROL 投放到] | 接收此计划项目的人。 |
| [!UICONTROL 到期日期] | 您可以将到期日期设置为最多一年，而不考虑调度频率。 |
| [!UICONTROL 频率] | 您希望将此计划项目发送给收件人的频率。 |
| [!UICONTROL 执行时间] | 在一天中发送此计划项目的时间。 |
| [!UICONTROL 查询次数] | 查询此项目的次数。 |

以下是计划项目管理器中的常见操作：

| 操作 | 描述 |
|---|---|
| **[!UICONTROL 编辑计划]** | 单击计划的标题以更新其发送设置。 |
| **[!UICONTROL 删除计划]** | 在列表中选择计划项目，然后从菜单中选择“删除”。这将删除项目的选定计划；但不会删除项目本身。 |
| **[!UICONTROL 添加标记]** | 在列表中选择计划项目，然后选择“标记”或“批准”以整理计划并使这些计划更易于搜索。 |
| **[!UICONTROL 查看失败的计划]** | 导航到左边栏中的“其他过滤器”>“失败”以查看已失败的计划。 |
| **[!UICONTROL 查看过期的计划]** | 导航到左边栏中的“其他过滤器”>“过期”以查看已过期的计划。单击计划的标题以设置新的投放计划。 |
| **[!UICONTROL 查看计划 ID]** | 导航到右上方的列选项，并将“计划 ID”列添加到表中。计划 ID 通常对调试有用。 |

计划项目管理器可显示特定用户已创建的项目。若应用程序中禁用此用户帐户，则会停止所有计划的投放。有关更多信息，请参阅 [计划项目](/help/components/scheduled-projects-manager.md).

## 密码保护计划项目 {#password}

>[!NOTE]
>
>密码保护计划项目的选项仅对已购买的Customer Journey Analytics客户显示 [Health Shield](https://business.adobe.com/solutions/experience-cloud-for-healthcare.html) 附加产品。

Adobe 使用密码来加密计划项目，无论它们是以 .pdf 还是 .csv 格式发送。

在您的公司购买并启用Healthcare Shield SKU后，会在以下情况下显示为计划项目创建密码的提示：

* 当有人创建一个新的计划项目时。

* 即将发送现有的计划项目时。当前计划的项目在密码保护设置完成之前处于禁用状态。 计划项目的所有者会收到一封电子邮件，通知他们此要求。

![密码保护](assets/password.png)

### 密码要求

密码要求符合Adobe标准，要求至少8个字符，其中至少一个数字和一个特殊字符。

### 密码保护新的计划项目

1. 保存项目后，转到 **[!UICONTROL 共享]** > **[!UICONTROL 立即发送文件]**，或 **[!UICONTROL 共享]** > **[!UICONTROL 按计划发送文件]**.
1. 在[立即发送文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hans#now)或[按计划发送文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hans#schedule)下面，按照上面的说明操作。

### 密码保护现有计划项目

在计划项目之前，项目所有者会收到类似于以下内容的电子邮件：

![电子邮件](assets/email-password.png)

1. 登录到Customer Journey Analytics。
1. 选择 **[!UICONTROL 查看计划项目]**.
1. 在&#x200B;**[!UICONTROL 编辑计划项目]**&#x200B;对话框中，输入密码，然后再输入一次。
1. 让计划项目的收件人知道此密码。 不要将密码分发给不是计划项目收件人的人。
