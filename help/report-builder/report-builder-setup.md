---
title: 如何在 Customer Journey Analytics 中设置 Report Builder
description: 介绍如何在Customer Journey Analytics中设置Report Builder
role: User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 065cf61d80ceb3c921ea666ba299e56fb044335b
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 26%

---

# Report Builder 设置

本文概述了在Microsoft Excel中使用适用于Customer Journey Analytics的Report Builder的要求。 以及如何安装和设置加载项。

## 要求

以下操作系统和Web浏览器支持适用于Customer Journey Analytics的Report Builder。

### macOS

- macOS 版本 10.x 或更高版本
- 所有 Excel 版本

### Windows

- Windows 10，版本 1904 或更高版本
- Excel 版本 2106 或更高版本

  所有 Windows 桌面 Excel 用户必须安装 Microsoft Edge Webview2 以使用插件。要安装，请执行以下操作：

   1. 转到 <https://developer.microsoft.com/en-us/microsoft-edge/webview2/>。
   1. 选择并下载适用于您的平台的&#x200B;**[!UICONTROL Evergreen Standalone Installer]**&#x200B;的适当版本。
   1. 运行安装程序并按照安装提示操作。

### Web Office

- 支持所有浏览器和版本。


## Report Builder Excel加载项

安装Report Builder Excel插件以使用适用于Customer Journey Analytics的Report Builder。 安装Report Builder Excel插件后，您可以从打开的Excel工作簿中访问Report Builder。

### 下载并安装 Report Builder 插件

下载并安装 Report Builder 插件

1. 启动 Excel 并打开新工作簿。

1. 从主菜单中选择&#x200B;**[!UICONTROL 插入]** > **[!UICONTROL 加载项]** > **[!UICONTROL 获取加载项]**。

1. 在“Office加载项”对话框中，选择&#x200B;**[!UICONTROL 存储]**&#x200B;选项卡。

1. 搜索`Report Builder`并选择&#x200B;**[!UICONTROL 添加]**。

1. 在“许可条款和隐私策略”对话框中，选择&#x200B;**[!UICONTROL 继续]**。

如果未显示&#x200B;**[!UICONTROL 商店]**&#x200B;选项卡：

1. 在Excel中，从主菜单中选择&#x200B;**[!UICONTROL 文件]** > **[!UICONTROL 帐户]** > **[!UICONTROL 管理设置]**。

1. 选中&#x200B;**[!UICONTROL 启用可选连接体验]**&#x200B;旁边的框。

1. 重新启动 Excel。

如果贵组织阻止对Microsoft Store的访问：

- 请联系您的IT或安全团队，请求批准使用Report Builder加载项。 获得批准后，在Office **[!UICONTROL 加载项]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 管理员托管]**&#x200B;选项卡。

  ![Office加载项对话框中的管理员管理选项卡。](./assets/image1.png){zoomable="yes"}

安装Report Builder加载项后，![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;图标将显示在&#x200B;**[!UICONTROL 主页]**&#x200B;选项卡下的Excel功能区中。

![Excel中的Report Builder图标](./assets/rb_app_icon.png){zoomable="yes"}


## 登录 Report Builder

为操作平台或浏览器安装了Report Builder for Excel插件后，请按照以下步骤登录Report Builder。

1. 打开 Excel 工作簿。

1. 选择![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;以启动Report Builder。

1. 从Adobe Report Builder工具栏中选择&#x200B;**[!UICONTROL 登录]**。

   ![单击“Report Builder登录”按钮。](./assets/rb_login.png){zoomable="yes"}

1. 输入您的Adobe帐户信息。 您的帐户信息应该与您的 Customer Journey Analytics 凭据匹配。

   ![您的登录图标和组织。](./assets/image4.png){zoomable="yes"}

登录之后，您的登录图标和组织将显示在面板的顶部。


## 切换组织

首次登录时，您将登录到分配给您的用户档案的默认组织或您作为登录流的一部分选择的组织。

1. 选择登录时显示的组织名称。

1. 从可用组织列表中选择组织。只列出您有访问权限的组织。

   ![您可以访问的组织列表。](./assets/image5.png){zoomable="yes"}

## 注销

要从Report Builder注销，请执行以下操作：

1. 保存对任何打开工作簿的更改。

1. 选择头像图标以显示您的用户配置文件。

   ![您的用户个人资料头像和“注销”按钮。](./assets/image6.png){zoomable="yes"}

1. 选择&#x200B;**[!UICONTROL 注销]**。
