---
title: 将 Analytics 源连接器数据集添加到连接
description: 了解如何将Analytics源连接器数据集添加到连接
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 9%

---

# 禁用 AppMeasurement 数据收集 {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="禁用 AppMeasurement 数据收集"
>abstract="在Web SDK数据完全正常使用的情况下，请与您的开发人员团队合作，从您的网站或资产中删除AppMeasurement.js。<br><br>从网站中删除AppMeasurement只需几分钟的时间，但需要工程团队的时间才能完成。 但是，请确保您的Analytics用户使用的是Customer Journey Analytics，而不是Adobe Analytics；如果您尚未这样做，则让每个人迁移的这一公告过程可能需要显着长的时间。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

<!-- need to work on this -->

* **标记：**&#x200B;禁用Adobe Analytics扩展

* **AppMeasurment：**&#x200B;替换AppMeasurement.js库s=newobject
