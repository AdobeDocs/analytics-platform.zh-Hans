---
title: 创建 Analytics 源连接器并映射字段
description: 了解如何创建Analytics源连接器和映射字段
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 24%

---

# 创建 Analytics 源连接器并映射字段 {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="创建 Analytics 源连接器"
>abstract="使用 Analytics 源连接器摄取报告包数据，以用于 Customer Journey Analytics。<br><br>使用默认设置创建 Analytics 源连接器只需几分钟。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="创建 Analytics 源连接器并映射架构字段"
>abstract="源连接器需要知道如何将 Adobe Analytics 字段映射到您组织的架构。使用此界面向源连接器提供该映射。此步骤是将历史数据添加到 Customer Journey Analytics 的一部分。<br><br>此步骤所需的时间在很大程度上取决于您必须映射的维度和量度的数量。这一步并不难，但是它很繁琐且重复。预计数据流映射大约需要一周的时间才能完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 了解Analytics Source Connector如何将历史数据引入Customer Journey Analytics

您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可以用作Customer Journey Analytics中的历史数据。

此过程假定您希望[创建一个自定义架构以用于您的Customer Journey Analytics Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，因为您需要一个针对贵组织和您使用的特定Platform应用程序的需求而定制的简化架构。

要使用Analytics Source Connector将历史数据引入Customer Journey Analytics，您需要：

1. [为 Analytics 源连接器创建一个自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 如果您还没有Analytics源连接器，请创建Analytics源连接器并将字段映射到您的自定义Web SDK架构，如下所述。

   或

   如果您已有Analytics源连接器，请将源连接器中的[字段映射到您的自定义Web SDK架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [将 Analytics 源连接器数据集添加到连接](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 创建 Analytics 源连接器并映射字段

创建自定义架构后，您需要创建Adobe Analytics源连接器以用于历史数据。 (有关创建源连接器的更全面的一般准则，请参阅[在UI中创建Adobe Analytics源连接](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-hans)。)

要创建用于历史数据的Adobe Analytics源连接器，请执行以下操作：

1. 在Platform UI的左边栏中的&#x200B;**[!UICONTROL 连接]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 源]**。

1. 从[!UICONTROL 分类]列表中选择 **[!UICONTROL Adobe 应用程序]**

1. 在Adobe Analytics拼贴中选择&#x200B;**[!UICONTROL 添加数据]**。

   ![已选择源的Adobe Experience Platform窗口，同时突出显示Adobe应用程序和添加数据。](./assets/sources-overview.png)

1. 选择&#x200B;**[!UICONTROL 报表包]**，然后从报表包列表中选择包含要在Customer Journey Analytics中使用的历史数据的报表包。

   显示“报表包”列表的![Adobe Experience Platform窗口](./assets/report-suites.png)

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 选择&#x200B;**[!UICONTROL 自定义架构]**，然后选择您在[中创建的架构创建包含Adobe Analytics字段组的自定义架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 将每个Adobe Analytics维度映射到自定义架构维度。

   1. 在&#x200B;**[!UICONTROL 映射标准字段]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 自定义]**&#x200B;选项卡。

   1. 选择&#x200B;**[!UICONTROL 添加新映射]**。

   ![映射架构字段](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL Source字段]**&#x200B;中，从“Adobe Analytics ExperienceEvent模板”字段组中选择一个Adobe Analytics字段。 然后，在&#x200B;**[!UICONTROL 目标字段]**&#x200B;中，选择XDM架构中要将其映射到的自定义字段。

      由于Adobe Analytics和XDM之间固有的架构差异，并非所有AppMeasurement字段在XDM中都拥有相应的字段。

   1. 为您用于在Adobe Analytics中收集数据的Adobe Analytics ExperienceEvent Template字段组中的每个字段重复此过程。

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 命名数据流并（可选）提供描述。

   ![Adobe Experience Platform窗口，突出显示数据流详细信息部分](./assets/dataflow-detail.png)

1. 选择屏幕右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 查看连接，然后选择&#x200B;**[!UICONTROL 完成]**。

   ![Adobe Experience Platform窗口突出显示“连接”和“数据类型”部分以供审阅](./assets/review.png)

   创建连接后，将自动创建数据流以使用报表包中的Adobe Analytics数据填充数据集。 数据流最多可摄取13个月的生产沙盒的历史数据。 非生产沙盒中的回填限制为三个月。

   如果您使用Analytics Source Connector将历史数据引入Customer Journey Analytics Web SDK实施，则需要将此自动创建的数据集添加到您为Web SDK实施创建的连接。

{{upgrade-final-step}}
