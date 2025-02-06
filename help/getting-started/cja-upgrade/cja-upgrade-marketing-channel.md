---
title: 创建Customer Journey Analytics的营销渠道派生字段
description: 了解如何为Customer Journey Analytics创建营销渠道派生字段
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 4%

---

# 创建Customer Journey Analytics的营销渠道派生字段 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="创建营销渠道派生的字段"
>abstract="派生字段在数据视图中创建。<br><br>使用默认营销渠道设置只需要几分钟；创建高度自定义的营销渠道设置可能需要几个小时。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

使用Analytics Source Connector时，营销渠道数据通过该连接器流入Customer Journey Analytics。 在传统的 Adobe Analytics 中配置营销渠道规则，其中不支持某些规则。有关详细信息，请参阅[使用营销渠道维度](/help/use-cases/aa-data/marketing-channels.md)。

要在使用Experience PlatformWeb SDK时在Customer Journey Analytics中使用营销渠道，您可以在数据视图中使用派生字段来为Customer Journey Analytics重新创建相同的营销渠道和处理规则。

1. 在Customer Journey Analytics中，选择要添加营销渠道的数据视图。

1. 在数据视图中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡。

1. 在左边栏中选择&#x200B;**[!UICONTROL 创建派生字段]**。

1. 在&#x200B;**[!UICONTROL 创建派生字段]**&#x200B;对话框中，从下拉菜单中选择&#x200B;**[!UICONTROL 函数模板]**。

   ![创建派生字段函数模板](assets/derived-field-create.png)

1. 将&#x200B;**[!UICONTROL 营销渠道]**&#x200B;模板拖动到空白画布上。

1. 自定义每个营销渠道的逻辑，以确保其与在Adobe Analytics环境中用于标识每个渠道的逻辑相匹配。

   您可以修改输出渠道名称或添加逻辑以标识特定于您的组织的其他渠道。

1. 在右列中，指定营销渠道的名称和描述。

1. 选择&#x200B;**[!UICONTROL 保存]**。

   您的新派生字段将添加到派生字段>容器中，作为数据视图左边栏中架构字段的一部分。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
