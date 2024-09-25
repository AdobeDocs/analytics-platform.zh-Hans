---
description: 如何向Customer Journey Analytics文档提问
title: Adobe Customer Journey Analytics 的 AI 助手
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: dae2282717d5d84862259d5b056fbfeb2d068cce
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# Adobe Customer Journey Analytics 的 AI 助手

AI助手是一种对话体验，允许从业人员快速执行任务。 任务是了解概念、排除问题还是搜索信息。 人工智能助理还允许非专家执行专家任务，并提高总体工作质量。

对Customer Journey AnalyticsAI助手进行Adobe Experience League文档培训。 当被问到问题时，AI Assistant会给出一个有助于快速学习的有用答案。

作为新手，您可以使用AI Assistant学习Customer Journey Analytics概念，并熟悉不熟悉的产品和功能。 作为经验丰富的用户，您可以使用AI Assistant提供更高级的用例或提示和技巧。

概念问题的一些示例包括：

* 批量摄取与流式摄取之间有何区别？
* Customer Journey Analytics的最佳用途是什么？
* 如何设置数据视图？

Customer Journey Analytics范围之外的问题，例如有关Adobe Target和Adobe Creative Cloud Suite等其他Adobe产品的问题，则无法回答。

用于Customer Journey Analytics的AI助手可用于所有产品层。

## 产品知识 {#knowledge}

产品知识检索模型是基于Customer Journey Analytics进行训练的。 其他功能（如数据分析）稍后将推出。

| 产品知识 | 示例 |
| --- | --- |
| 点式学习 | <ul><li>Adobe Analytics与Customer Journey Analytics之间有何区别？</li><li>如何构建计算量度？</li></ul> |
| 打开发现 | <ul><li>如何导出Workspace项目？</li><li>如何查找重复的Workspace组件？</li></ul> |
| 故障排除 | <ul><li>数据进入CJA需要多长时间？</li><li>Customer Journey Analytics连接中可以包含多少个派生字段？</li></ul> |

## 功能访问

以下参数控制对AI助手功能的访问：

* **解决方案访问**： AI助手在Customer Journey Analytics中可用，但在Adobe Analytics中不可用。 Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform应用程序中也提供了此功能。

* **合同访问权限**：如果您无法使用AI助手，请联系您组织的管理员或Adobe客户代表。 在您的组织可以使用AI助手之前，您必须同意某些与GenAI相关的法律条款。

* **权限**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 报告工具] **[!UICONTROL AI Assistant：产品知识]**&#x200B;权限决定了对此工具的访问权限。 [产品配置文件管理员](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中执行这些步骤：
   1. 导航到&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品配置文件]**
   1. 选择要为其提供[!UICONTROL AI助手：产品知识]访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**。
   1. 选择![编辑](/help/assets/icons/Edit.svg)以编辑&#x200B;**[!UICONTROL 报告工具]**。
   1. 选择![AddCircle](/help/assets/icons/AddCircle.svg)以将&#x200B;**AI助手：产品知识**&#x200B;添加到&#x200B;**[!UICONTROL 包含的权限项]**。

      ![添加权限](assets/ai-assistant-permissions.png)。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

有关详细信息，请参阅[访问控制](/help/technotes/access-control.md#access-control)。

## 在Customer Journey AnalyticsUI中访问AI助手

1. 要启动AI助手，请从Customer Journey AnalyticsUI中任何页面的顶部标题中选择AI助手图标。

   ![AI助手图标](assets/ai-asst1.png)

   在首次使用AI助手时，将显示免责声明，其中包含使用该助手的一些条款和条件。

1. 在提供的框中，询问AI助手的特定自然语言问题。

   ![问题框](assets/ai-asst2.png)

1. （可选）要显示源，请单击&#x200B;**[!UICONTROL 显示源]**，此时将显示通知答案的一个或多个文档源。

1. （可选）您还可以对任何给定答案的效用提供大拇指支持或大拇指反对的投票。

1. （可选）您可以标记不适当或有害内容的答案。
