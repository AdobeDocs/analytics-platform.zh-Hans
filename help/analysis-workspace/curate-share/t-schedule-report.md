---
description: 通过电子邮件发送 Analysis Workspace 项目，或者计划发送项目的时间。
keywords: Analysis Workspace
title: 计划项目
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 7ef67276dabca2afdc9e3e799aab5eb5d93d22fd
workflow-type: ht
source-wordcount: '740'
ht-degree: 100%

---

# 计划项目

从工作区的&#x200B;**“共享”菜单**&#x200B;中，您可以通过电子邮件将 Analysis Workspace 项目发送给选定的收件人。可以采用 CSV 或 PDF 格式发送文件。

## 立即发送文件 {#now}

要通过电子邮件立即将文件发送给收件人，请执行以下步骤：

1. 单击&#x200B;**共享 > 立即发送文件**。
1. 指定文件类型（CSV 或 PDF）。
1. （可选）添加要包含在电子邮件中的说明，以阐述所发送的文件。
1. 添加收件人或组。也可以输入电子邮件地址。
1. （仅适用于 Healthcare Shield 客户）提供密码。请参阅“密码保护计划报告”部分。
1. 单击&#x200B;**立即发送**。
1. （可选）单击&#x200B;**显示计划选项**&#x200B;以指定发送计划。

![立即发送文件](assets/send-file-no-scheduling-options.JPG)

## 按计划发送文件 {#schedule}

要通过电子邮件按重复计划将文件发送给收件人，请执行以下操作：

1. 单击&#x200B;**共享 > 按计划发送文件**。
1. 指定文件类型（CSV 或 PDF）。
1. （可选）添加要包含在电子邮件中的说明，以阐述所发送的文件。
1. 添加收件人或组。也可以输入电子邮件地址。
1. （仅适用于 Healthcare Shield 客户）提供密码。请参阅“密码保护计划报告”部分。
1. 通过修改开始日期和结束日期输入值来指定计划发送文件的日期范围。结束日期必须在自创建或修改计划之日起的一年内。
1. 指定发送频率。每种频率均允许进行不同的自定义。
1. 单击&#x200B;**按计划发送**。

![](assets/send-file.JPG)

## 计划项目管理器 {#manager}

可以在 **Analytics > 组件 > 计划项目**&#x200B;下管理计划的 Analysis Workspace 项目。

在计划项目管理器中，您可以编辑和删除重复的项目计划。在搜索栏中搜索计划，或者使用左边栏中的过滤器选项搜索计划。您可以按标记、批准的计划、所有者等进行过滤。

以下是计划项目管理器中的常见操作：

| 操作 | 描述 |
|---|---|
| **编辑计划** | 单击计划的标题以更新其发送设置。 |
| **删除计划** | 在列表中选择计划项目，然后从菜单中选择“删除”。这将删除项目的选定计划；但不会删除项目本身。 |
| **添加标记** | 在列表中选择计划项目，然后选择“标记”或“批准”以整理计划并使这些计划更易于搜索。 |
| **查看失败的计划** | 导航到左边栏中的“其他过滤器”>“失败”以查看已失败的计划。 |
| **查看过期的计划** | 导航到左边栏中的“其他过滤器”>“过期”以查看已过期的计划。单击计划的标题以设置新的发送计划。 |
| **查看计划 ID** | 导航到右上方的列选项，并将“计划 ID”列添加到表中。计划 ID 通常对调试有用。 |

计划项目管理器可显示特定用户已创建的项目。若应用程序中禁用此用户帐户，则会停止所有计划的提交。

## 密码保护计划项目 {#password}

>[!NOTE]
>
>密码保护计划项目的选项仅显示给购买了 [Healthcare Shield](https://business.adobe.com/solutions/experience-cloud-for-healthcare.html) 附加产品的 CJA 客户。

Adobe 使用密码来加密计划项目，无论它们是以 .pdf 还是 .csv 格式发送。

在您的公司购买并启用 Healthcare Shield SKU 后，将会在两种情况下弹出为计划项目创建密码的提示：

* 当有人创建一个新的计划项目时。

* 即将发送现有的计划项目时。在设置好密码保护之前，当前计划的项目将被禁用。计划项目的所有者将为此收到一封电子邮件。

![密码保护](assets/password.png)

### 密码要求

密码要求符合 Adobe 标准，要求至少 8 个字符，并且其中至少有一个数字和一个特殊字符。

### 密码保护新的计划项目

1. 保存项目后，转到&#x200B;**[!UICONTROL 分享]** > **[!UICONTROL 立即发送文件]**，或[!UICONTROL 分享] > **[!UICONTROL 按计划发送文件]**。
1. 在[立即发送文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hans#now)或[按计划发送文件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hans#schedule)下面，按照上面的说明操作。

### 密码保护现有计划项目

在项目计划的时间之前，项目的所有者将收到类似于以下内容的电子邮件：

![电子邮件](assets/email-password.png)

1. 登录回到 Customer Journey Analytics。
1. 单击&#x200B;**[!UICONTROL 查看计划项目]**。
1. 在&#x200B;**[!UICONTROL 编辑计划项目]**&#x200B;对话框中，输入密码，然后再输入一次。
1. （仅）让计划项目的接收者知道此密码。


