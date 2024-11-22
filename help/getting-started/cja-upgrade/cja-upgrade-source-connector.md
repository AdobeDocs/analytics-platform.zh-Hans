---
title: 创建 Analytics 源连接器并映射字段
description: 了解如何创建Analytics源连接器和映射字段
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 0a47796a8b673ef7074a4f9fe865ff59fcf50aab
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 8%

---

# 创建 Analytics 源连接器并映射字段

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

## 了解Analytics Source Connector可怎样将历史数据引入Customer Journey Analytics

您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可用作Customer Journey Analytics中的历史数据。

此过程假设在升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)时您要[创建XDM架构，因为您需要一个根据您的组织需求以及您使用的特定Platform应用程序量身定制的简化架构。

要使用Analytics Source Connector将历史数据纳入Customer Journey Analytics，您需要：

1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 如果您还没有Analytics Source Connector，请创建Analytics Source Connector并将字段映射到XDM架构，如下所述。

   或

   如果您已有Analytics源连接器，请将源连接器中的[字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [将 Analytics 源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 创建 Analytics 源连接器并映射字段

创建XDM架构后，您需要创建Adobe Analytics源连接器以用于历史数据。 (有关创建源连接器的更全面的一般准则，请参阅[在UI中创建Adobe Analytics源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。)

要创建用于历史数据的Adobe Analytics源连接器，请执行以下操作：

1. 在Platform UI的左边栏中的&#x200B;**[!UICONTROL 连接]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 源]**。

1. 从[!UICONTROL 分类]列表中选择 **[!UICONTROL Adobe 应用程序]**

1. 在Adobe Analytics拼贴中选择&#x200B;**[!UICONTROL 添加数据]**。

   ![Adobe Experience Platform窗口，其中已选择源，并突出显示了Adobe应用程序和添加数据。](./assets/sources-overview.png)

1. 选择&#x200B;**[!UICONTROL 报表包]**，然后从报表包列表中选择包含要在Customer Journey Analytics中使用的历史数据的报表包。

   显示“报表包”列表的![Adobe Experience Platform窗口](./assets/report-suites.png)

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 选择&#x200B;**[!UICONTROL 自定义架构]**，然后选择您在[中创建的XDM架构创建包括Adobe Analytics字段组](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 将每个Adobe Analytics维度映射到自定义XDM架构维度。

   1. 在&#x200B;**[!UICONTROL 映射标准字段]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 自定义]**&#x200B;选项卡。

   1. 选择&#x200B;**[!UICONTROL 添加新映射]**。

   ![映射架构字段](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL Source字段]**&#x200B;中，从“Adobe Analytics ExperienceEvent模板”字段组中选择一个Adobe Analytics字段。 然后，在&#x200B;**[!UICONTROL 目标字段]**&#x200B;中，选择要将其映射到的XDM字段。

      由于AppMeasurement和XDM之间固有的架构差异，并非所有Adobe Analytics字段在XDM中都拥有相应的字段。

   1. 为您用于在Adobe Analytics中收集数据的Adobe Analytics ExperienceEvent Template字段组中的每个字段重复此过程。

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 命名数据流并（可选）提供描述。

   ![Adobe Experience Platform窗口，突出显示数据流详细信息部分](./assets/dataflow-detail.png)

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 查看连接，然后选择&#x200B;**[!UICONTROL 完成]**。

   ![Adobe Experience Platform窗口突出显示“连接”和“数据类型”部分以供审阅](./assets/review.png)

   创建连接后，将自动创建数据流以使用报表包中的Adobe Analytics数据填充数据集。 数据流最多可摄取13个月的生产沙盒的历史数据。 非生产沙盒中的回填限制为三个月。

   如果您使用Analytics Source Connector将历史数据引入Customer Journey AnalyticsWeb SDK实施，则需要将此自动创建的数据集添加到您为Web SDK实施创建的连接。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
