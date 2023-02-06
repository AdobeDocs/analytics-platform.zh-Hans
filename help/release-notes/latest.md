---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b633e3e70c24d9b00b1ab2f80954ad698b12ce29
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 91%

---

# 当前的 Customer Journey Analytics (CJA)发行说明（2023 年 1 月）

**上次更新时间**：2023 年 2 月 6 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](/help/release-notes/releases.md) | [正式发布](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **更新CJA受众** | 创建受众后， [Adobe为每个新的CJA受众创建一个Experience Platform流区段](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). 只有在为流区段设置组织后，才会创建AEP流区段。 | 不适用 | 2023年2月3日 |
| **对象数组支持配置文件和查找数据集** | 配置文件数据集和查找数据集现在支持在 CJA 中使用的对象数组。 | 2023 年 1 月 11 日 | 2023 年 1 月 19 日 |
| **Workspace 中的文件夹** | 文件夹帮助您组织和分类项目以便更好地检索和访问。此外，通过共享&#x200B;**[!UICONTROL 公司]**&#x200B;文件夹，管理员可轻松地创建内容并与所有 Workspace 用户共享内容。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=zh-Hans) | 不适用 | 2023 年 1 月 11 日 |
| **默认登陆页面** | 2022 年早些时候引入的[新登陆页面](/help/getting-started/landing.md)在 **2023 年 1 月 11 日**&#x200B;将成为所有用户的默认体验。旧版登陆页面将被弃用，每个人都将必须使用新体验。 | 不适用 | 2023 年 1 月 11 日 |
| **项目管理器页面已弃用** | 随着新登陆页面的发布，我们弃用了 **[!UICONTROL 项目经理]**，如 **[!UICONTROL Customer Journey Analytics]** 中所列> **[!UICONTROL 组件]**。新的登录页面具有旧项目管理器页面的所有功能等等。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=zh-Hans#deprecate-pm-page) | 不适用 | 2023 年 1 月 11 日 |
| **在 Report Builder 中安排工作簿** | 在 Customer Journey Analytics 中，您可以创建计划以定期发送工作簿。现在，收件人可以定期收到您工作簿的最新更新。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html?lang=zh-Hans) | 不适用 | 2023 年 1 月 11 日 |
| **自动保存新项目** | Analysis Workspace 现在会自动保存新创建的项目。如果由于任何原因，在手动保存新创建的项目之前，您意外地失去了对该项目的访问权限，则现在可以使用项目的恢复版本。以前，项目只有在最初手动保存后才自动保存。[了解详情](/help/analysis-workspace/build-workspace-project/save-projects.md) | 不适用 | 2023 年 1 月 11 日 |
| **增强的用户偏好设置** | 您现在可以在用户级别配置其他偏好设置（在[!UICONTROL 组件]>[!UICONTROL 偏好设置]中）。 当您设置用户偏好设置时，您的选择会跨越您的项目、表格和可视化图表。偏好设置页面现在包含以下新选项卡，每个选项卡包含许多新的配置选项：<ul><li>自由格式表</li><li>可视化</ul>。此外，现在可以在&#x200B;**[!UICONTROL 整体]**&#x200B;和&#x200B;**[!UICONTROL 项目]**&#x200B;选项卡上使用更多首选项。<p>以前，其中许多偏好设置只能针对单个项目、表格和可视化图表进行配置。[了解详情](/help/analysis-workspace/user-preferences.md) | 不适用 | 2023 年 1 月 11 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-287349；AN-301684；AN-305491；AN-305769；AN-307912

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **改进的 IP 到地理位置映射** | 2022 年 9 月 29 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到经过改进的新数据集 (NetAcuity Pulse) 以进行 IP 到地理位置映射。Adobe Analytics 已推迟到 **2023 年 1 月 11 日**&#x200B;采用此新数据集。新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 [!UICONTROL Analytics Source Connector] 提供的 CJA 数据也将自动利用新映射。 |

{style=&quot;table-layout:auto&quot;}


## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)

* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
