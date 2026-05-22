---
title: 删除后果
description: 了解删除或重置Customer Journey Analytics或Experience Platform对象的影响。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
TQID: https://experienceleague.adobe.com/95ZvIc4JM3aNY2zO6ypn-KmLrIdZ8DZga4vrOcl9Yzs
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5cid: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: de8f8e06f074fdcb0219ce7286785d870c2093b4
workflow-type: tm+mt
source-wordcount: 997
ht-degree: 9%

---

# 删除和重置后果

删除或重置Customer Journey Analytics或Experience Platform对象确实有影响。 本文概述了这些含义。

## Customer Journey Analytics

在Customer Journey Analytics中删除连接、数据视图或数据集之前，请考虑以下含义：

| 操作 | 影响 |
| --- | --- |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 出现错误消息，其中指示：<ul><li>为已删除的连接创建的任何数据视图都不再有效。</li><li> 同样，任何依赖于已删除连接中的数据视图的Workspace项目都将停止运行。</li></ul><p>请注意，您无法删除符合以下条件的Customer Journey Analytics连接：</p><ul><li>绑定到您没有权限的Adobe Experience Platform沙盒。 即使您有权访问基于这些连接构建的数据视图，但在您获得基础Adobe Experience Platform沙盒的权限之前，您无法删除这些连接。</li><li>为与该连接关联的数据视图选择以下兼容性选项： **[!UICONTROL 在Adobe Journey Optimizer中设置为默认数据视图]**<p>有关此配置选项的详细信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[兼容性](/help/data-views/create-dataview.md#compatibility)。</p></li><li>在配置中使用以下任何服务：<ul><li>[受众分析](/help/connections/audience-analysis/audience-analysis-overview.md)：向Customer Journey Analytics提供受众数据以进行深入分析</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md)：提供有关内容使用情况以及对Customer Journey Analytics的影响的数据</li></ul><p>在删除连接之前，必须先删除或编辑使用此连接的配置。</p></li></ul> |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 从Customer Journey Analytics中的连接中删除数据集时，任何依赖该数据集的数据视图和项目都将不再有效。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据视图 | 当您在Customer Journey Analytics中删除数据视图时，Workspace项目中依赖于该数据视图的任何面板都将无法再正常运行。<p>请注意，您无法删除在配置中用于以下任何服务的Customer Journey Analytics数据视图：</p><ul><li>[受众分析](/help/connections/audience-analysis/audience-analysis-overview.md)：向Customer Journey Analytics提供受众数据以进行深入分析</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md)：提供有关内容使用情况以及对Customer Journey Analytics的影响的数据</li></ul><p>在删除数据视图之前，必须首先删除或编辑使用此数据视图的配置。</p></li></ul> |



## Experience Platform

在删除数据集或批次之前，或者在Experience Platform中重置或删除沙盒时，请考虑以下后果：

| 操作 | 影响 |
| --- | --- |
| 在[!UICONTROL Experience Platform]中删除数据集中的一个或多个记录 | 记录会从Customer Journey Analytics连接中删除，这些连接会将数据集定义为连接配置的一部分。 |
| 删除[!UICONTROL Experience Platform]中的数据集 | 在Experience Platform中，来自该数据集的数据流将停止到包含该数据集的任何连接。 自动从关联的 Customer Journey Analytics 连接删除来自该数据集的任何数据。 |
| 从[!UICONTROL Experience Platform]中的数据集中删除批次 | 如果从[!UICONTROL Adobe Experience Platform]数据集中删除了某个批次，则会从包含该特定批次的所有[!UICONTROL Customer Journey Analytics]连接中删除该批次。 [!UICONTROL Customer Journey Analytics] 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| 将批次&#x200B;**摄取到[!UICONTROL Customer Journey Analytics]时，从[!UICONTROL Experience Platform]**&#x200B;中删除批次 | 如果数据集中只有一个批次，则没有来自该批次的数据或来自该批次的部分数据出现在 [!UICONTROL Customer Journey Analytics] 中。 并且回滚该摄取。 例如，如果数据集中共有5个批次，且在删除第四个批次时已摄取其中3个批次，则这3个批次中的数据将显示在[!UICONTROL Customer Journey Analytics]中。 |
| 删除[!UICONTROL Experience Platform]中的查找数据集 | 虽然可以删除其他源连接器的数据集，但不支持删除[Analytics Classifications Source Connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)数据集。 如果您误删除了此类数据集，请联系客户关怀团队。 |
| 在Experience Platform中删除或重置沙盒 | 当您[删除Experience Platform沙盒](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox)时，该沙盒中的所有架构、数据集、批次、策略等也会被删除。 沙盒不再存在，以及沙盒标识符和沙盒名称。<br/>当您[重置Experience Platform沙盒](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox)时，将会删除该沙盒中的所有架构、数据集、批次、策略等。 虽然沙盒名称和权限保持不变，但在重置完成后沙盒标识符会更改。<br/><br/>Customer Journey Analytics使用沙盒标识符和沙盒名称将连接与沙盒关联。 因此： <ul><li>与已删除或重置沙盒关联的连接已删除。</li><li>基于已删除连接的数据视图（以及数据视图中的所有组件定义，如派生字段）都会被删除。</li><li>依赖已删除数据视图的组件将被删除。 例如，区段、计算量度、注释、警报、已发布受众和导出。</li><li>Workspace项目中引用已删除数据视图的面板变得不可用。 这些面板显示&#x200B;**[!UICONTROL 未知的数据视图]**&#x200B;错误。 移除这些面板，或者如果可能，将这些面板与现有数据视图关联。</li><li>您不应再使用查询服务或依赖于BI扩展的工具来查询Customer Journey Analytics中已存在的已删除连接中的（历史）数据。 最终，Adobe支持或工程人员会从Customer Journey Analytics中删除此数据。</li></ul>由于在Experience Platform中重置或删除沙盒将会产生重大影响，在重置或删除沙盒之前，请考虑以下事项：<ul><li>列出您的连接，以了解哪些连接属于哪些沙盒。</li><li>列出数据视图，以了解哪些数据视图与哪些连接相关联。</li><li>确定重要的Workspace项目，并了解这些项目在其面板中引用的数据视图。</li><li>识别与使用BI扩展的工具的集成，并了解这些集成所依赖的数据视图。</li></ul> |
