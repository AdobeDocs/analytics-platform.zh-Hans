---
title: 如何在Customer Journey Analytics中配置Report Builder设置
description: 介绍如何设置离线模式、语言、截止日期以及故障排除设置。
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 95%

---

# Report Builder 设置

使用&#x200B;**设置**&#x200B;窗格可以配置应用程序级别的设置，例如 UI 显示的语言或者是否在离线模式下工作。这些设置会立即应用，并设定用于所有未来的会话，直至发生更改。

更改 Report Builder 设置

1. 单击&#x200B;**设置**&#x200B;图标。

1. 进行更改以启用离线模式、选择语言或者启用故障排除日志设置。

1. 单击&#x200B;**应用**。

   ![](./assets/image38.png)

## 离线模式

在离线模式下创建和编辑数据块时，不检索数据。相反，使用模拟数据，这样您就可以快速创建和编辑数据块而无需等待请求运行。在您重新在线时，*刷新数据块*&#x200B;命令或&#x200B;*刷新所有数据块*&#x200B;命令使用真实数据刷新您创建的数据块。

启用离线模式

1. 单击&#x200B;**设置**&#x200B;图标。

1. 选择&#x200B;**启用离线模式**。

1. 在&#x200B;**将量度数据显示为**&#x200B;字段中输入正整数。

1. 单击&#x200B;**应用**。

## 语言

您可以为 Report Builder UI 选择语言。所有支持的 Adobe Analytics 语言都可用。

选择在 Report Builder UI 中使用的语言

1. 单击“设置”。

1. 从&#x200B;**语言**&#x200B;下拉菜单中选择语言。

   ![](./assets/image39.png)

1. 单击&#x200B;**应用**。

## 故障排除

使用“故障排除”设置将所有客户端/服务器数据记录到本地文件。使用此选项帮助解决支持服务单。

要启用故障排除选项，请选择&#x200B;**将 Report Builder 请求记录到本地文件**。
