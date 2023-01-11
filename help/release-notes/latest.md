---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9276b7ed4465c85703e942e02adde2d024cf43ca
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 44%

---

# 当前Customer Journey Analytics(CJA)发行说明（2023年1月）

**上次更新**:2023年1月5日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](/help/release-notes/releases.md) | [正式发布](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Workspace 中的文件夹** | 文件夹可帮助您组织和分类项目，以便更好地检索和访问。 此外，共享 **[!UICONTROL 公司]** 利用文件夹，管理员可以轻松创建内容并与所有工作区用户共享。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html) | 不适用 | 2023 年 1 月 11 日 |
| **默认登陆页面** | 的 [新登陆页面](/help/getting-started/landing.md) 2022年早些时候引入的体验，将成为 **2023年1月11日**. 旧版登陆页面将被弃用，每个人都需要使用新体验。 | 不适用 | 2023 年 1 月 11 日 |
| **在Report Builder中计划工作簿** | 在Customer Journey Analytics中，您可以创建计划以定期发送工作簿。 现在，收件人可以定期接收工作簿的最新更新。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | 不适用 | 2023 年 1 月 11 日 |
| **自动保存新项目** | Analysis Workspace现在可自动保存新创建的项目。 如果您出于任何原因，在手动保存之前意外失去了对新创建项目的访问权限，则现在可以使用项目的恢复版本。 以前，只有在最初手动保存项目后，才会自动保存项目。 [了解详情](/help/analysis-workspace/build-workspace-project/save-projects.md) | 不适用 | 2023 年 1 月 11 日 |
| **增强的用户首选项** | 您现在可以在用户级别配置其他首选项(在 [!UICONTROL 组件] > [!UICONTROL 首选项])。 设置用户首选项时，您的选择会跨项目、表和可视化图表进行。 “首选项”页面现在包含以下新选项卡，每个选项卡都包含许多新配置选项：<ul><li>自由格式表</li><li>可视化图表>/li></ul>。此外，现在还提供了 **[!UICONTROL 常规]** 和 **[!UICONTROL 项目]** 选项卡。<p>以前，其中许多首选项只能针对单个项目、表和可视化图表进行配置。 [了解详情](/help/analysis-workspace/user-preferences.md) | 不适用 | 2023 年 1 月 11 日 |

{style=&quot;table-layout:auto&quot;}

## 修复

AN-287349;AN-301684;AN-305491;AN-305769;AN-307912

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **改进了 IP 到地理位置的映射** | 2022 年 9 月 29 日 | Adobe 的 IP 查找供应商 Digital Element 正在升级到经过改进的新数据集 (NetAcuity Pulse) 以进行 IP 到地理位置映射。Adobe Analytics已将此新数据集的采用推迟到 **2023年1月11日**. 新的数据库将比以前的版本更准确。 当采用新数据库时，一些 IP 到地理位置的映射将发生变化/改进。<p> 通过 [!UICONTROL Analytics Source Connector] 提供的 CJA 数据也将自动利用新映射。 |

{style=&quot;table-layout:auto&quot;}


## 相关资源

* [以前的 2022 年 CJA 发行说明](/help/release-notes/2022.md)

* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)

* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)

* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)

* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
