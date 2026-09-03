---
title: Customer Journey Analytics预发行说明
description: 查看最新的Customer Journey Analytics预发行说明
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 81%

---

# Adobe Customer Journey Analytics预发行说明

>[!IMPORTANT]
>
>本文档旨在作为当月发行说明的&#x200B;**预览**。 版本项目可能会发生更改，并且可能会在最终版本中添加或删除。

这些发行说明涵盖 2025 年 6 月 2 日至 7 月 15 日的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。

有关Adobe Experience Platform及其其他应用程序的发行说明，请参阅以下文档：

* [Adobe Experience Platform](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [联合受众构成](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 左侧面板不再在鼠标悬停时打开和关闭** | Analysis Workspace 中的左侧面板用于将组件、面板和可视化图表等元素添加到您的项目中。 将鼠标悬停在最左侧的一个图标上以临时打开左侧面板，这个选项不再可用。 现在，只需单击其中一个图标即可保持面板打开，然后单击相同的图标可将其关闭。 |  | 2025 年 6 月 2 日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition 提供有助于推动收入增长的可操作的帐户洞察，帮助 B2B 公司协调其营销活动、销售和产品团队。 帐户是数据模型的中心，因此所有分析都集中在帐户历程上。 在基于人员及时间的事件之上添加一层新实体（帐户、机会和购买群组），可以创建 B2B 营销活动和收入生命周期的完整图景。 [了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025 年 6 月 18 日 |
| **Report Builder 中对安全目标的支持** | Report Builder 插件中已添加新的导出目标。 支持以下云存储目标： <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 2025 年 6 月 18 日 |
| **新预览体验** | 预览面板用于预览区段、计算量度等，现在使用水平条形图可视化图表而不是圆环图可视化图表。 |  | 2025 年 6 月 18 日 |
| **修改了归因模型对话框** | 您现在可以在归因模型对话框中分别定义容器和时段。 |  | 2025 年 6 月 18 日 |
| **连接图** | 全新的[连接映射界面](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-connections/create-connection#connection-map)现已推出，可用于以可视化方式展示您的连接配置。 |  | 2025 年 6 月 18 日 |
| **在 Analysis Workspace 项目中添加和查看评论** | Analysis Workspace 中新增的[评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)可让您在 Analysis Workspace 项目的上下文中分享洞察和提出问题。 这可以简化有关数据的讨论，使对话保持在正在讨论的数据范围内。 您可以 <ul><li>对任何您有权访问的 Analysis Workspace 项目进行评论</li><li>对可视化图表中的特定点进行评论，也可以对项目进行一般性评论</li><li>标记其他用户以通知他们您的评论</li><li>管理现有评论（编辑、固定、解决等）</li></ul>Customer Journey Analytics 管理员可以[在组织级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)。 项目所有者可以[在项目级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)。 |  | 2025 年 6 月 25 日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |
