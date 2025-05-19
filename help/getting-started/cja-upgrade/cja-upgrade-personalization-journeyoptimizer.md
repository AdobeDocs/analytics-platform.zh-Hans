---
title: 将个性化对象与 Adobe Journey Optimizer 结合使用
description: 了解如何将个性化对象与 Adobe Journey Optimizer 结合使用
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5086ac6e-5bee-4f0f-b7e5-a3d9bd8a1332
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 100%

---

# 将个性化对象与 Adobe Journey Optimizer 结合使用 {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="为 Adobe Journey Optimizer 使用个性化对象"
>abstract="通过利用受到监督的机器学习和深度学习领域的先进技术，业务用户（营销人员）可以使用个性化优化功能定义业务目标，并利用他们的客户数据来训练面向业务的模型，以提供个性化产品建议并使 KPI 最大化。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

通过利用受到监督的机器学习和深度学习领域的先进技术，业务用户（营销人员）可以使用个性化优化功能定义业务目标，并利用他们的客户数据来训练面向业务的模型，以提供个性化产品建议并使 KPI 最大化。

1. 关注 Journey Optimizer Guide 中[个性化优化模型](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model)中的信息。

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->
