---
title: 通过Adobe Experience Platform Mobile SDK引入数据
description: 说明如何通过Adobe Experience Platform Mobile SDK和Edge Network将数据摄取到Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: fb48b031-e093-4490-b457-69dbb5debe8d
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 60%

---

# 通过Adobe Experience Platform Mobile SDK引入数据

本快速入门指南介绍如何使用Adobe Experience Platform Mobile SDK和Edge Network将移动应用程序跟踪数据直接摄取到Adobe Experience Platform。 然后将这些数据用于Customer Journey Analytics。

要完成此实施，您需要：

- 在 Adobe Experience Platform 中&#x200B;**设置模式和数据集** ，以定义要收集的数据的模型（模式）以及实际收集数据的位置（数据集）。

- **设置数据流** 以配置 Adobe Experience Platform Edge Network，将您收集的数据路由到您在 Adobe Experience Platform 中配置的数据集。

- **使用标记** 以轻松针对移动应用程序中的数据配置规则和数据元素。 然后确保数据发送到在 Adobe Experience Platform Edge Network 上配置的数据流。

- **部署和验证**。拥有一个可以迭代标签开发的环境，一旦所有内容都经过验证，就可以在您的生产环境中实时发布。

- 在 Customer Journey Analytics 中&#x200B;**设置连接**。此连接应（至少）包含 Adobe Experience Platform 数据集。

- 在 Customer Journey Analytics 中&#x200B;**设置数据视图**&#x200B;以定义要在 Analysis Workspace 中使用的量度和维度。

- 在 Customer Journey Analytics 中&#x200B;**设置一个项目**&#x200B;以构建报告和可视化图表。

>[!NOTE]
>
>本快速入门指南是一份简化的指南，介绍了如何将从应用程序收集的数据摄取到Adobe Experience Platform并在Customer Journey Analytics中使用。 强烈建议参考时研究附加信息。


## 设置模式和数据集

要将数据导入 Adobe Experience Platform，首先需要定义要收集的数据。引入 Adobe Experience Platform 的所有数据都必须符合标准的非规范化结构，以便下游功能和特性对其进行识别和操作。体验数据模型(XDM)是一种标准框架，它以架构的形式提供结构。

定义模式后，您可以使用一个或多个数据集来存储和管理数据集合。数据集是用于数据集合（通常是表）的存储和管理结构，其中包含架构（列）和字段（行）。

摄取到 Adobe Experience Platform 中的所有数据都必须符合预定义的模式，然后才能作为数据集保存。

### 设置模式

您希望使用移动应用程序跟踪用户档案中的一些最小数据，例如场景名称、标识。
您首先需要定义一个模式来模拟此数据。

设置您的模式：

1. 在 Adobe Experience Platform UI 的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 模式]**。

1. 选择 **[!UICONTROL 创建架构]**..
1. 在“创建模式”向导的“选择类”步骤中：

   1. 选择 **[!UICONTROL 体验事件]**.

      ![创建模式](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    Experience Event架构用于为 _行为_ 配置文件（如场景名称、要添加到购物车的按钮）的。 个人配置档案模式用于对个人配置档案&#x200B;_属性_（如姓名、电子邮件、性别）建模。

   1. 选择&#x200B;**[!UICONTROL 下一步]**。


1. 在 [!UICONTROL 命名和审核步骤] 的 [!UICONTROL 创建架构] 向导：

   1. 输入 **[!UICONTROL 架构显示名称]** （可选）a **[!UICONTROL 描述]**.

      ![命名您的模式](./assets/create-ee-schema-wizard-step-2.png)

   1. 选择&#x200B;**[!UICONTROL 完成]**。

1. 在示例架构的结构选项卡中：

   1. 在[!UICONTROL 字段组]中选择&#x200B;**[!UICONTROL + 添加]**。

      ![添加字段组](./assets/add-field-group-button.png)

      字段组是可重用的对象和属性集合，可让您轻松扩展模式。

   1. 在 [!UICONTROL 添加字段组] 对话框，选择 **[!UICONTROL AEP Mobile SDK ExperienceEvent]** 列表中的字段组。

      ![AEP移动生命周期详细信息字段组](./assets/select-aepmobilesdk-experienceevent.png)

      您可以选择预览按钮，以查看属于该字段组的字段的预览，例如 `application > name`。

      ![AEP移动生命周期详细信息字段组预览](./assets/aepmobilesdk-experienceevent-preview.png)

      选择&#x200B;**[!UICONTROL 返回]**&#x200B;关闭预览。

   1. 选择&#x200B;**[!UICONTROL 添加字段组]**。

1. 在[!UICONTROL 结构]面板中选择模式名称旁边的 **[!UICONTROL +]**。

   ![示例模式添加字段按钮](./assets/example-mobileschema-plus.png)

1. 在 [!UICONTROL 字段属性] 面板，输入 `identification` 作为 [!UICONTROL 字段名称]， **[!UICONTROL 标识]** 作为 [!UICONTROL 显示名称]，选择 **[!UICONTROL 对象]** 作为 [!UICONTROL 类型] 并选择 **[!UICONTROL ExperienceEvent Core v2.1]** 作为 [!UICONTROL 字段组].

   >[!NOTE]
   >
   >如果该字段组不可用，请查找另一个包含标识字段的字段组。 或 [创建新字段组](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) 和 [添加新标识字段](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (点赞 `ecid`， `crmId`，然后选择该新字段组。

   ![识别对象](./assets/identification-field-mobile.png)

   标识对象将标识功能添加到架构中。 对于您的情况，您希望使用Experience CloudID和电子邮件地址来识别使用移动应用程序的用户档案。 还有许多其他属性可用于跟踪您的人员标识（例如客户ID、忠诚度ID）。

   选择&#x200B;**[!UICONTROL 应用]**&#x200B;将此对象添加到您的模式中。

1. 选择刚刚添加的标识对象中的&#x200B;**[!UICONTROL ecid]**&#x200B;字段，选择&#x200B;**[!UICONTROL 标识]**&#x200B;和&#x200B;**[!UICONTROL 主要标识]** 和 **[!UICONTROL ECID]** 来自右侧面板中的 [!UICONTROL 标识命名空间] 列表。

   ![指定 ECID 作为身份](./assets/specify-identity-mobile.png)

   您将 Experience Cloud Identity 指定为 Adobe Experience Platform Identity 服务可用于组合（缝合）具有相同 ECID 的配置文件行为的主要身份。

   选择 **[!UICONTROL 应用]**。您会看到 ecid 属性中出现指纹图标。

1. 选择刚刚添加的标识对象中的&#x200B;**[!UICONTROL 邮件]**&#x200B;字段，选择&#x200B;**[!UICONTROL 标识]**&#x200B;和&#x200B;**[!UICONTROL 邮件]** 和 [!UICONTROL 标识命名空间] 列表中的 [!UICONTROL 字段属性] 面板。

    ![将电子邮件指定为标识](./assets/specify-email-identity-mobile.png)

   您将电子邮件地址指定为 Adobe Experience Platform Identity 服务可用于组合（拼接）配置文件行为的另一个标识。

   选择 **[!UICONTROL 应用]**。您会看到电子邮件属性中显示指纹图标。

   选择&#x200B;**[!UICONTROL 保存]**。

1. 选择显示模式名称的模式的根元素，然后选择 **[!UICONTROL 配置文件]** 开关。

   系统会提示您启用配置文件的模式。一旦启用，当数据被引入基于此模式的数据集中时，该数据将合并到实时客户配置文件。

   有关详细信息，请参阅[启用模式以在实时客户配置文件中使用](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile)。

   >[!IMPORTANT]
   >
   >    一旦您保存了为配置文件启用的模式，就不能再为配置文件禁用它。

   ![为配置文件启用模式](./assets/enable-for-profile.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存模式。

您已创建一个最小架构，用于为您可从移动应用程序中捕获的数据建模。 该模式允许使用 Experience Cloud Identity 和电子邮件地址来识别配置文件。通过为配置文件启用架构，您可以确保将从移动应用程序捕获的数据添加到实时客户配置文件。

除了行为数据之外，您还可以从移动应用程序捕获配置文件属性数据（例如订阅新闻通讯的配置文件详细信息）。

要捕获用户档案数据，您应：

- 基于 XDM 个人配置文件类创建模式。

- 将 Profile Core v2 字段组添加到模式中。

- 添加基于 Profile Core v2 字段组的标识对象。

- 将Experience CloudID定义为主标识符，将电子邮件定义为标识符。

- 为配置文件启用模式

请参阅[在 UI 中创建和编辑模式](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有关向模式添加和删除字段组和单个字段的更多信息。

### 设置数据集

使用您的模式，您已经定义了数据模型。现在，您必须定义结构以使用数据集存储和管理这些数据。

设置您的数据集

1. 在 Adobe Experience Platform UI 的左边栏中，选择[!UICONTROL 数据管理]中的&#x200B;**[!UICONTROL 数据集]**。

2. 选择&#x200B;**[!UICONTROL 创建数据集]**。

   ![创建数据集](./assets/create-dataset.png)

3. 选择&#x200B;**[!UICONTROL 使用模式创建数据集]**。

   ![使用模式创建数据集](./assets/create-dataset-from-schema.png)。

4. 选择您之前创建的模式，然后选择 **[!UICONTROL 下一个]**。

5. 为您的数据集命名并（可选）提供描述。

   ![数据集名称](./assets/name-your-datatest.png)

6. 选择&#x200B;**[!UICONTROL 完成]**。

7. 选择&#x200B;**[!UICONTROL 配置文件]**&#x200B;开关

   系统会提示您启用配置文件的数据集。启用后，数据集会使用其摄取的数据丰富实时客户配置文件。

   >[!IMPORTANT]
   >
   >    只有当数据集所依附的模式也为配置文件启用时，您才能为配置文件启用数据集。

   ![为配置文件启用模式](./assets/aepwebsdk-dataset-profile.png)

有关如何查看、预览、创建和删除数据集的更多信息，请参阅[数据集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hans)。以及如何为实时客户配置文件启用数据集。

## 设置数据流

数据流表示实施 Adobe Experience Platform Web 和移动 SDK 时的服务器端配置。使用 Adobe Experience Platform SDK 收集数据时，数据会发送到 Adobe Experience Platform Edge Network。它是确定数据转发到哪些服务的数据流。

在设置中，您希望将从移动应用程序中收集的数据发送到Adobe Experience Platform中的数据集。

设置您的数据流

1. 在 Adobe Experience Platform UI 的左边栏中，选择 [!UICONTROL 数据收藏集] 中的 **[!UICONTROL 数据流]**。

2. 选择&#x200B;**[!UICONTROL 新数据流]**。

3. 命名并描述您的数据流。从 [!UICONTROL 事件模式] 列表中选择您的模式。

   ![新数据流](./assets/new-datastream.png)

4. 选择&#x200B;**[!UICONTROL 保存]**。

5. 选择 **[!UICONTROL 添加服务]**。

6. 在 [!UICONTROL 添加服务屏幕]：

   1. 从 [!UICONTROL 服务] 列表中选择 **[!UICONTROL Adobe Experience Platform]**。

   2. 确保选择 **[!UICONTROL Enabled]**。

   3. 从 [!UICONTROL 事件数据集] 列表中选择您的数据集。

      ![数据流 AEP 服务](./assets/datastream-aep-service.png)

   4. 保留其他设置并选择 **[!UICONTROL 保存]** 以保存数据流。

您的数据流现在配置为将从移动应用程序收集的数据转发到Adobe Experience Platform中的数据集。

有关如何配置数据流和如何处理敏感数据的更多信息，请参阅[数据流概述](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html)。



## 使用标签

要在您的网站上实施代码以实际收集数据，请使用Adobe Experience Platform中的标记功能。 这一款标记管理解决方案，可让您在满足其他标记要求的同时部署代码。标记通过Adobe Experience Platform Mobile SDK扩展提供了与Adobe Experience Platform的无缝集成。

### 创建您的标记

1. 在 Adobe Experience Platform UI 的左边栏中，选择 [!UICONTROL 数据收藏集] 中的 **[!UICONTROL 标签]**。

2. 选择&#x200B;**[!UICONTROL 新属性]**。

   命名标记，选择 **[!UICONTROL 移动设备]**. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;继续。

   ![创建资产](./assets/create-mobile-property.png)

### 配置您的标签

创建标签后，您需要使用正确的扩展名对其进行配置，并根据您希望如何跟踪站点并将数据发送到 Adobe Experience Platform 配置数据元素和规则。

要配置，请从列表中选择新创建的标记 [!UICONTROL 标记属性].


#### **扩展**

将AdobePlatform Edge Network扩展添加到您的标记中，以确保您可以（通过数据流）将数据发送到Adobe Experience Platform。

要创建并配置Adobe Experience Platform Mobile SDK扩展，请执行以下操作：

1. 选择 **[!UICONTROL 扩展]** 在左边栏中。 您会看到移动核心扩展和配置文件扩展已经可用。

1. 在顶部栏中选择 **[!UICONTROL 目录]** 。

1. 搜索或滚动到 **[!UICONTROL Adobe Experience Platform边缘网络]** 扩展并选择 **[!UICONTROL 安装]** 在右窗格中安装。

1. 选择您的沙盒和您之前为您的[!UICONTROL 生产环境]和（可选）[!UICONTROL 暂存环境]和[!UICONTROL 创建的数据流开发环境]。

   ![AEP Mobile SDK扩展配置](./assets/aepmobilesdk-extension-datastream.png)

1. 输入您的 **[!UICONTROL Edge Network域]** 下 [!UICONTROL 域配置]. 通常使用 `<organizationName>.data.adobedc.net`.

1. 选择&#x200B;**[!UICONTROL 保存]**。

请参阅 [配置Adobe Experience Platform Edge Network扩展](https://developer.adobe.com/client-sdks/documentation/edge-network) 以了解更多信息。

您还需要从目录设置以下其他扩展：

- 身份。
- AEP保证。
- 同意。

请参阅 [配置标记属性](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/initial-configuration/configure-tags.html) 在Experience Platform的移动应用程序教程中，了解有关扩展及其配置的更多信息。

#### **数据元素**

数据元素是数据词典（或数据映射）的构建块。使用数据元素可跨市场营销和广告技术收集、组织和交付数据。您可以在标记中设置数据元素，该数据元素可从移动设备应用程序数据或事件中读取，并可用于将数据交付到Adobe Experience Platform中。

例如，要从移动设备应用程序中收集运营商名称。

要定义运营商名称数据元素，请执行以下操作：

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

2. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

3. 在[!UICONTROL 创建数据元素]对话框中：

   - 为数据元素命名，例如，`Carrier Name`。

   - 选择 **[!UICONTROL 移动核心]** 从 [!UICONTROL 扩展名] 列表。

   - 选择 **[!UICONTROL 运营商名称]** 从 [!UICONTROL 数据元素类型] 列表。


     ![使用页面信息创建日期元素](./assets/create-dataelement-mobile.png)

   - 选择&#x200B;**[!UICONTROL 保存]**。

您可以创建所需数量的数据元素，并在规则中使用它们。


#### **规则**

Adobe Experience Platform 中的标签遵循基于规则的系统。他们寻找用户交互和相关数据。如果满足您的规则中所列的标准，则规则会触发您已识别的扩展、脚本或客户端代码。您可以使用规则通过Adobe Experience Platform Edge Network扩展将数据发送到Adobe Experience Platform中（如XDM对象）。

例如，您希望在使用移动设备应用程序时（在前台）和不使用移动设备应用程序时（推送回后台）发送事件数据。

去定义规则

1. 选择左边栏中的&#x200B;**[!UICONTROL 规则]**。

2. 选择&#x200B;**[!UICONTROL 创建新规则]**。

3. 在[!UICONTROL 创建规则]对话框中：

   - 命名规则，例如`Application Status`。

   - 选择并在[!UICONTROL 事件]下方 **[!UICONTROL +添加]** 

   - 在[!UICONTROL 事件配置]对话框中：

      - 选择 **[!UICONTROL 移动核心]** 从 [!UICONTROL 扩展名] 列表。

      - 选择 **[!UICONTROL 前景]** 从 [!UICONTROL 事件类型] 列表。

      - 选择&#x200B;**[!UICONTROL 保留更改]**。

   - 单击 ![加号](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) 旁边 [!UICONTROL 移动核心 — 前台].

      - 选择 **[!UICONTROL 移动核心]** 从 [!UICONTROL 扩展名] 列表。

      - 选择 **[!UICONTROL 背景]** 从 [!UICONTROL 事件类型] 列表。

      - 选择&#x200B;**[!UICONTROL 保留更改]**。

   - 单击 ![加号](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg) 在下面添加 [!UICONTROL 操作]. 在[!UICONTROL 操作配置]对话框中：

      - 选择 **[!UICONTROL Adobe Experience Platform边缘网络]** 从 [!UICONTROL 扩展名] 列表。

      - 选择 **[!UICONTROL 将事件转发到Edge Network]** 从 [!UICONTROL 操作类型] 列表。

      - 选择&#x200B;**[!UICONTROL 保留更改]**。

   - 您的规则应如下所示：

     ![创建规则](assets/rule-appstatus.png)

   - 选择&#x200B;**[!UICONTROL 保存]**。

以上只是定义规则的示例，该规则会将包含应用程序状态的XDM数据发送到Adobe Edge网络和Adobe Experience Platform。

您可以在标记中以各种方式使用规则来操作变量（使用数据元素）。

有关详细信息，请参阅[规则](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/#configure-a-rule-to-forward-lifecycle-metrics-to-platform)。

### 生成并发布标签

在定义了数据元素和规则之后，您需要构建和发布标签。创建库生成时，必须将其分配给环境。然后，将会编译该内部版本的扩展、规则和数据元素，并将这些内容放入分配的环境。每个环境都提供了一个唯一的嵌入代码，从而允许您将其分配的内部版本集成到网站中。

要生成并发布您的标签：

1. 从左边栏中选择&#x200B;**[!UICONTROL 发布流]**。

2. 选择 **[!UICONTROL 选择工作库]**，然后选择&#x200B;**[!UICONTROL 添加库…]**。

3. 在[!UICONTROL 创建库]对话框中：

   - 命名库。

   - 选择&#x200B;**[!UICONTROL 开发（开发）]**  [!UICONTROL 环境] 列表。

   - 选择&#x200B;**[!UICONTROL + 添加所有更改的资源]**。

     ![发布文档库](./assets/build-library-mobile.png)

   - 选择&#x200B;**[!UICONTROL 保存并生成到开发]**。

   您的标记已保存，并为开发环境构建。 绿色圆点表示在开发环境中成功构建了标记。

4. 您可以选择&#x200B;**[!UICONTROL ...]** 重建库或将库移动到临时或生产环境。

Adobe Experience Platform标记支持从简单到复杂的发布工作流程，应该可以适应Adobe Experience Platform Edge Network的部署。

有关详细信息，请参阅 [发布概述](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration) 。


### 检索您的标签代码

最后，您需要在要跟踪的移动应用程序中使用标记。

要获取说明如何设置移动应用程序并在应用程序中使用标记的代码说明，请执行以下操作：

1. 选择左边栏中的&#x200B;**[!UICONTROL 环境]**。

2. 从环境列表中，选择正确的安装 ![盒子](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Box_18_N.svg) 按钮。

   在 [!UICONTROL 移动设备安装说明] 对话框，选择适当的平台([!UICONTROL iOS]， [!UICONTROL Android])。 然后使用副本 ![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) 按钮来设置和初始化移动设备应用程序，您需要使用每个相关的代码片段旁边的按钮：

   ![环境](./assets/environment-mobile.png)

3. 选择&#x200B;**[!UICONTROL 关闭]**。

您可能已根据部署Adobe Experience Platform Mobile SDK的位置选择其他环境（暂存、生产），而不是开发环境的代码。

有关详细信息，请参阅 [环境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) 。

## 部署和验证

您现在可以在移动应用程序中部署代码。 部署后，您的移动应用程序会开始将数据收集到Adobe Experience Platform中。

验证您的实现，在必要时进行更正，更正后，使用标签的发布工作流功能将其部署到您的暂存和生产环境中。

请参阅 [在移动应用程序中实施Adobe Experience Cloud教程](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html) 了解更多详细信息。

## 设置连接

要在 Customer Journey Analytics 中使用 Adobe Experience Platform 数据，您需要创建一个连接，其中包含因设置模式、数据集和工作流所产生的数据。

通过创建连接，您可以将 Adobe Experience Platform 中的数据集集成到工作区中。要报告这些数据集，您必须首先在Adobe Experience Platform和工作区中的数据集之间建立连接。

创建您的连接：

1. 在 Customer Journey Analytics UI 中，选择顶部导航中的&#x200B;**[!UICONTROL 连接]**。

2. 选择&#x200B;**[!UICONTROL 创建新连接]**。

3. 在[!UICONTROL 无标题连接]屏幕中：

   在[!UICONTROL 连接设置]中命名并描述您的连接。

   从[!UICONTROL 数据设置]中的[!UICONTROL 沙盒]列表中选择正确的沙盒，并从[!UICONTROL 平均每日事件数]列表中选定每日事件数。

   ![连接设置](./assets/cja-connections-1.png)

   选择&#x200B;**[!UICONTROL 添加数据集]**。

   在[!UICONTROL 添加数据集]的[!UICONTROL 选择数据集]步骤中：

   - 选择您之前创建的数据集和/或要包含在连接中的其他相关数据集(例如来自Adobe Journey Optimizer的推送跟踪体验事件数据和推送配置文件数据)

     ![添加数据集](./assets/cja-connections-ajopush.png)

   - 选择&#x200B;**[!UICONTROL 下一步]**。

   在[!UICONTROL 添加数据集]的[!UICONTROL 设置数据集]步骤中：

   - 对于每个数据集：

      - 在 Adobe Experience Platform 中，从在数据集模式中定义的可用身份中选择[!UICONTROL 人员 ID]。

      - 从[!UICONTROL 数据源类型]列表中选择正确的数据源。如果指定&#x200B;**[!UICONTROL 其他]**，则为您的数据源添加描述。

      - 根据您的首选项设置&#x200B;**[!UICONTROL 导入所有新数据]**&#x200B;和&#x200B;**[!UICONTROL 数据集回填现有数据]**。

     ![配置数据集](./assets/cja-connections-ajopushid.png)

   - 选择&#x200B;**[!UICONTROL 添加数据集]**。

   选择&#x200B;**[!UICONTROL 保存]**。

有关如何创建和管理连接以及如何选择和组合数据集的更多信息请参阅[连接概述](../connections/overview.md)。

## 设置数据视图

数据视图是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 它指定所有可在 Analysis Workspace 中找到的维度和量度，以及这些维度和量度从哪些列获取其数据。为准备 Analysis Workspace 中的报告而定义数据视图。

创建您的数据视图：

1. 在 Customer Journey Analytics UI 中，选择顶部导航中的&#x200B;**[!UICONTROL 数据视图]**。

2. 选择&#x200B;**[!UICONTROL 创建新数据视图]**。

3. 在[!UICONTROL 配置]步骤中：

   从[!UICONTROL 连接]列表中选择您的连接。

   名称并（可选）描述您的连接。

   ![数据视图配置](./assets/cja-dataview-1.png)

   选择&#x200B;**[!UICONTROL 保存并继续]**。

4. 在[!UICONTROL 组件]步骤中：

   将要包含的任何模式字段和/或标准组件添加到[!UICONTROL 量度]或[!UICONTROL 维度]组件框中。

   ![数据视图组件](./assets/cja-dataview-2-mobile.png)

   选择&#x200B;**[!UICONTROL 保存并继续]**。

5. 在[!UICONTROL 设置]步骤中：

   ![数据视图设置](./assets/cja-dataview-3.png)

   保持设置不变并选择&#x200B;**[!UICONTROL 保存并完成]**。

请参阅[数据视图概述](../data-views/data-views.md)，了解有关如何创建和编辑数据视图、哪些组件可供您在数据视图中使用以及如何使用过滤器和会话的更多信息设置。


## 设置项目

Analysis Workspace 是一个灵活的浏览器工具，允许您快速构建分析并基于数据共享见解。您可以使用工作区项目来组合数据组件、表和可视化，以制作分析并与组织中的任何人共享。

要创建您的项目：

1. 在 Customer Journey Analytics UI 中，选择顶部导航中的&#x200B;**[!UICONTROL 项目]**。

2. 选择左侧导航中的&#x200B;**[!UICONTROL 项目]**。

3. 选择&#x200B;**[!UICONTROL 创建项目]**。

   ![工作区项目](./assets/cja-projects-1.png)

   选择&#x200B;**[!UICONTROL 空白项目]**。

   ![工作区 – 空白项目](./assets/cja-projects-2.png)

4. 从列表中选择您的数据视图。

   ![工作区选择数据视图](./assets/cja-projects-3.png)

5. 要创建您的第一个报表，请开始将维度和量度拖放到 [!UICONTROL 自由格式表] 在 [!UICONTROL 面板] . 例如，拖动 `Events` 作为量度和 `Push Title` 作为维度，划分依据 `Event Type` 大致了解您的移动应用程序的推送通知以及发生的情况。

   ![工作区 – 第一份报告](./assets/cja-projects-5-mobile.png)

请参阅 [Analysis Workspace 概述](../analysis-workspace/home.md)，了解有关如何使用组件、可视化和面板创建项目和构建分析的更多信息。

>[!SUCCESS]
>
>您已完成所有步骤。 从定义要在 Adobe Experience Platform 中收集的数据（模式）和存储数据的位置（数据集）开始，您在 Edge Network 上配置了一个数据流，以确保数据可以转发到该数据集。然后，您定义和部署了包含扩展(Adobe Experience Platform Edge Network等)、数据元素和规则的标记，以便从移动应用程序中捕获数据并将该数据发送到数据流。 您在Customer Journey Analytics中定义了一个连接，以使用您的移动应用程序推送通知跟踪数据和其他数据。 通过数据视图定义，您可以指定要使用的维度和量度，最后，您创建了第一个项目，用于可视化和分析移动应用程序数据。
