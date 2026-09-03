---
title: Report Builder中受限制的标签
description: 了解Report Builder中受限制的标签。
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 42%

---

# Report Builder 中受到限制的标签

通常，Customer Journey Analytics中与数据治理相关的设置继承自Experience Platform。 Customer Journey Analytics与Experience Platform数据管理之间的集成允许标记敏感Customer Journey Analytics数据和实施隐私政策。

在Experience Platform使用的数据集上创建的隐私标签和策略可以在Customer Journey Analytics数据视图工作流中显示。 这些标签阻止或警告从敏感字段创建量度和维度的用户。 有关数据集的更多信息，请参阅[数据集概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/catalog/datasets/overview)。

此外，从 Customer Journey Analytics 导出数据时（通过报告、导出、API 等），将添加警告或标签，以通知用户报告包含需要以特定方式处理的敏感信息。

此集成允许您管理合规性。 组织中的数据管理员可以设置策略以限制使用。 因此，您的 Customer Journey Analytics 用户可以更自信地使用数据，因为他们知道此等数据使用符合数据管理员定义的策略。

有关更多信息，请参阅[ Customer Journey Analytics 和数据治理](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-privacy/privacy-overview)。

## 查看受限制的数据

Customer Journey Analytics中出现了两个Adobe定义的策略，这些策略影响报表、下载和共享：

* 强制分析策略
* 强制下载策略

遵循这些策略的组件呈灰显状态，并且确实有![InfoOutline](/help/assets/icons/InfoOutline.svg)图标。 当您将鼠标悬停在信息图标上时，会显示一条注释，以指示以下内容：**[!UICONTROL 策略已应用于此字段，因此禁止使用此数据]**。

有关详细信息，请参阅[标签和策略](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance)。


![指示禁止使用数据的策略注释。](assets/restricted-label.png){zoomable="yes"}


## 更新包含受限数据的报表

如果用户创建的 Report Builder 报告中的数据元素后来受到限制，则在刷新报告时，会显示一条错误消息。

![稍后限制数据元素之后显示的错误消息。](assets/error-restricted-data.png){width="100%" zoomable="yes"}
