---
description: 介绍 Customer Journey Analytics 的持续功能发布策略
title: Customer Journey Analytics 功能发布
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 44a140fdd5069cbe806f694377802215bcf50b31
workflow-type: ht
source-wordcount: '359'
ht-degree: 100%

---

# Customer Journey Analytics 功能发布

Customer Journey Analytics 版本在持续交付模型上运行，该模型允许采用可扩展的分阶段方法进行功能部署。

## 发布策略

[!UICONTROL Analysis Workspace] 使用功能标志（又称为“切换”）控制新功能的可见性，从而允许在完全发布之前进行受控规模测试。此发布策略包括以下阶段：

* **开始推出**：通过 Adobe 内部用户的有限测试开始推出分阶段发布。然后，此发布在两个月内从 0% 到 100% 提供给客户。由于分阶段推出在 Experience Cloud 组织级别进行，因此组织中所有授权用户都可以获得相同的体验。

* **正式发布 (GA)**：此功能对 100% 授权的 Experience Cloud 组织可用，且功能发布已完成。

对于每个功能发布，从 RTP 到 GA 的时间表可能会有所不同。目标是缩短发布时间，以便能够在发布开始 (RTP) 后的 2 个月内，功能将达到 GA 阶段。

## 功能标记

功能标记用于在发布过程中控制新功能的可见性。Adobe 建议将 `app.launchdarkly.com` 添加到防火墙的[允许列表](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-Hans)，以在发布过程中获得出色体验。到达 GA 后不久，将删除该标记。

您可以随时在&#x200B;**帮助 > 关于 Workspace > 活动功能标记**&#x200B;下查看活动功能标记。

## 优点

分阶段发布使 Adobe 能够更好地扩展软件部署过程，并确保功能在正式发布之前得到全面强化。它还允许功能一经可用即可发布，而不用遵循固定的月度发布时间期限。

## 常见问题解答

| 问题 | 回答 |
| --- | --- |
| 我是否可以请求提前访问某个功能？ | 不会。不会授予提前访问权限。<br>如果您想要提前测试 Analytics 概念，我们建议您试用 [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=zh-Hans)，就我们行业领先的创新技术提供反馈。 |
| 此发布策略是否会影响我对功能的访问？ | 不会。一旦某个功能达到 GA 阶段，您将有权访问该功能，前提是它包含在您的 Analytics 程序包中。 |
