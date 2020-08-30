---
description: Analysis Workspace 中的无障碍支持功能
title: Analysis Workspace 中的辅助功能
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 100%

---


# Analysis Workspace 中的辅助功能

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

了解 Adobe Analytics 的首要分析工具 [!UICONTROL Analysis Workspace] 中的无障碍支持。

无障碍是指让患有失明、视力欠佳、认知困难、行动不便等残障人士都可以使用产品。软件产品的无障碍功能示例包括：屏幕阅读器支持、图形的对等文本、键盘快捷键、将显示颜色更改为高对比度等。

[!UICONTROL Analysis Workspace] 提供了一些易于使用的工具，包括：

## 使用键盘导航[!UICONTROL 工作区]

[!UICONTROL Analysis Workspace] 中的导航方式包括自上而下，以及从左至右。以下导航元素有助于促进无障碍功能：

* `F6` 键会启用地标快捷键
* `Tab` 键可在各个元素之间移动。
* 我们应用焦点指示器，以便近视的键盘用户能够清楚地了解当前具有焦点的 UI 元素。指示器是指选定元素周围的蓝色边框。

   ![焦点指示器](assets/focus-indicator.png)

### 键盘导航进行拖放交互操作

[!UICONTROL Analysis Workspace] 是用于执行拖放操作的用户界面。但是，用户可以改用键盘添加组件：

1. 跳到左边栏中的组件。
1. 按 `Enter` 键选择。
1. 使用箭头键，导航到要放置组件的区域。
1. 按 `Enter` 键放置组件。

### 键盘快捷键（热键）

[!UICONTROL Analysis Workspace] 提供丰富的[键盘快捷键](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，以体验更顺畅的工作流程。下面列出了导航、创建分析和获取大众化洞察信息的一些常用快捷键。

#### 导航

| 快捷键 | 操作 |
|---|---|
| Alt + Shift + 1 / 2 / 3 | 跳到不同的边栏：[!UICONTROL 面板]、[!UICONTROL 可视化图表]或[!UICONTROL 组件] |
| Alt + 向左/向右箭头键 | 在面板之间导航 |
| Alt + M | 折叠/展开所有面板 |
| Alt + Ctrl + M | 折叠/展开活动面板 |
| Ctrl + / | 搜索左边栏 |

#### 创建分析

| 快捷键 | 操作 |
|---|---|
| Alt + 1 | 新建自由格式表 |
| Ctrl + Shift + C | 新建计算量度 |
| Ctrl + Shift + D | 新建日期范围 |
| Ctrl + Shift + E | 新建区段 |
| Ctrl + Z | 撤消 |
| 按住 Shift 键（在面板的区段拖放区域中） | 创建[下拉过滤器](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### 大众化

| 快捷键 | 操作 |
|---|---|
| Ctrl + S | 保存 |
| Ctrl + Shift + G | 策划 |
| Ctrl + G | 共享 |
| Alt + Shift + S | 计划 |
| Alt + L | 获取项目链接 |
| Ctrl + Shift + B | 下载 PDF |

## 支持屏幕阅读器和屏幕放大镜

屏幕阅读器会读取计算机屏幕上显示的文本。此外，它还会读取无障碍标签或属性中提供的非文本信息，例如应用程序中的按钮标签或图像描述。

## 调色板和对比度

[!UICONTROL Analysis Workspace] 致力于符合 WCAG 2.1 AA 合规性标准，包括对颜色对比度的要求。

此外，用户还可以在&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 项目设置]** > [项目调色板](/help/analysis-workspace/build-workspace-project/color-palettes.md)下为项目设置各自的首选调色板。

## 组件构建器中的必填字段验证

如果构建组件，会在您保存必填字段时验证这些字段。如果必填字段未通过验证，则会使用红色列出，并带有错误图标。会出现关于需要修复的问题的书面说明。

完全组件验证后，按 `Save` 可关闭生成器。

![错误验证](assets/error-validation.png)

## 支持操作系统无障碍功能

Analysis Workspace 支持内置的 MS Windows 和 macOS 无障碍功能，例如高对比度模式、粘性键以及慢速键/滤镜键。此外，它还向操作系统提供关于用户界面的信息，以支持使用辅助技术进行交互操作，包括屏幕阅读器，例如 macOS 上的 VoiceOver 以及 Windows 上的 NVDA 等。