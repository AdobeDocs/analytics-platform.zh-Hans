---
title: 将 XDM 数据收集逻辑添加到您的标记中
description: 了解如何将XDM数据收集逻辑添加到标记中
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 35%

---

# 将 XDM 数据收集逻辑添加到您的标记中 {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="将 XDM 数据收集逻辑添加到您的标记中"
>abstract="在您的网站上安装加载器标记后，您可以添加规则和数据元素来填充 XDM 对象，然后发送给 Adobe。Adobe 建议维护一个解决方案设计文档来跟踪标记的配置方式。<br><br>这一步工作量很大，因为要为您的属性设置所有分析逻辑。预计需要花费一个月或更长的时间来建立正确的标记规则、测试它们并将它们部署到您的网站上。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics到Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)为您的组织动态生成的升级步骤进行操作。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

在[创建标记并添加Web SDK扩展](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)后，您必须根据您希望跟踪网站并将数据发送到Adobe Experience Platform的方式，使用数据元素和规则对其进行配置。 为标记配置数据元素和规则后，即可构建和发布该标记。

## 配置数据元素

数据元素是数据词典（或数据映射）的构建块。使用数据元素可跨市场营销和广告技术收集、组织和交付数据。您可以在标记中设置从数据层读取的数据元素，并可用于将数据交付到Adobe Experience Platform。 （有关数据元素的更多信息，请参阅标记文档中的[数据元素](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/data-elements)。）

以下各节介绍了建议的数据元素以及您可以配置的其他常见数据元素。

数据元素有多种类型。 您可能需要配置的两个常见数据元素：一个用于捕获访客在您的网站上查看的页面名称，另一个用于捕获访问您网站的每个人员的Experience Cloud ID。

配置这两个数据元素后，您可以为要捕获的特定数据配置其他数据元素。

最后，在定义所有所需的数据元素后，您需要将数据元素分配给您之前创建的[架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。 为此，您需要定义一个XDM数据元素，以提供XDM架构的表示形式。

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### 创建建议的数据元素

以下各节介绍如何创建适用于大多数组织的通用数据元素。

#### Page name数据元素

适用于大多数组织的通用数据元素是用于捕获人员正在查看的页面名称的数据元素。

要创建页面名称数据元素，请执行以下操作：

1. 使用您的Adobe ID凭据登录experience.adobe.com 。

1. 在Adobe Experience Platform中，转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 在&#x200B;**[!UICONTROL 标记属性]**&#x200B;页面上，从属性列表中选择新创建的标记以将其打开。

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

1. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

1. 在&#x200B;**[!UICONTROL 创建数据元素]**&#x200B;对话框中，指定以下信息：

   * **[!UICONTROL 名称]**：数据元素的名称。 例如：`Page Name`。

   * **[!UICONTROL 扩展]**：从列表中选择&#x200B;**[!UICONTROL 核心]**。

   * **[!UICONTROL 数据元素类型]**：从列表中选择&#x200B;**[!UICONTROL 页面信息]**。

   * **[!UICONTROL 属性]**：从列表中选择&#x200B;**[!UICONTROL 标题]**。

     ![使用页面信息创建日期元素](assets/create-dataelement-1.png)

     或者您可以使用数据层变量中的值，例如 `pageName` 和 [!UICONTROL JavaScript 变量]数据元素类型来定义数据元素。

     ![使用页面信息创建数据元素](assets/create-dataelement-2.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

   您现在想要设置一个引用 Experience Cloud ID 的数据元素，该 ID 由 Adobe Experience Platform Web SDK 自动提供，可通过 Experience Cloud ID 服务扩展使用。

1. 继续使用[ECID数据元素](#ecid-data-element)。

#### ECID数据元素

适用于大多数组织的通用数据元素是一个数据元素，可捕获访问您网站的每个人的Experience Cloud ID。

要创建ECID数据元素，请执行以下操作：

1. 使用您的Adobe ID凭据登录experience.adobe.com 。

1. 在Adobe Experience Platform中，转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。

1. （视情况而定）安装Experience Cloud ID服务扩展（如果尚未安装）：

   1. 选择左边栏中的&#x200B;**[!UICONTROL 扩展]**。

   1. 默认情况下已选择&#x200B;**[!UICONTROL 已安装]**&#x200B;选项卡。 如果列出了&#x200B;**[!UICONTROL Experience Cloud ID服务]**&#x200B;磁贴，请跳至步骤5。

   1. 如果未列出&#x200B;**[!UICONTROL Experience Cloud ID服务]**&#x200B;拼贴，请选择&#x200B;**[!UICONTROL 目录]**&#x200B;选项卡。

   1. 在搜索字段中，搜索&#x200B;**[!UICONTROL Experience Cloud ID服务]**，然后在该磁贴出现时选择该磁贴

   1. 选择&#x200B;**[!UICONTROL 安装]** > **[!UICONTROL 保存]**。

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

1. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

1. 在&#x200B;**[!UICONTROL 创建数据元素]**&#x200B;对话框中，指定以下信息：

   * **[!UICONTROL 名称]**：数据元素的名称。 例如：`ECID`。

   * **[!UICONTROL 扩展]**：从列表中选择&#x200B;**[!UICONTROL Experience Cloud ID服务]**。

   * **[!UICONTROL 数据元素类型]**：从列表中选择&#x200B;**[!UICONTROL ECID]**。

     ![ECID 数据元素](assets/ecid-dataelement.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 继续[创建其他数据元素](#create-additional-data-elements)。

### 创建其他数据元素

为要收集的每种类型的数据创建一个数据元素。 使用[Page name数据元素](#page-name-data-element)和[ECID数据元素](#ecid-data-element)中描述的相同过程创建每个其他数据元素。

您创建的数据元素在架构中应具有关联字段。

常见数据元素因行业和业务要求而异。 考虑以下按行业划分的常见数据元素：

**零售数据元素**

* 产品

* 购物车加货

* 结账

**财务数据元素**

* 交易 ID

* 交易日期

* 服务类型

**医疗保健数据元素**

* 提供程序ID

* 访问日期

* 处理类型

在创建组织实施所需的所有数据元素后，请继续使用[XDM对象数据元素](#xdm-object-data-element)。

### XDM对象数据元素

最后，您现在希望将您创建的任何数据元素映射到您之前创建的[架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。 为此，请定义一个可提供XDM架构表示形式的XDM对象数据元素。

要定义 XDM 对象数据元素：

1. 使用您的Adobe ID凭据登录experience.adobe.com 。

1. 在Adobe Experience Platform中，转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

1. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

1. 在&#x200B;**[!UICONTROL 创建数据元素]**&#x200B;对话框中，指定以下信息：

   * **[!UICONTROL 名称]**：数据元素的名称。 例如：`XDM - Page View`。

   * **[!UICONTROL 扩展]**：从列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

   * **[!UICONTROL 数据元素类型]**：从列表中选择&#x200B;**[!UICONTROL XDM对象]**。

   * **[!UICONTROL 沙盒]**：从列表中选择您的沙盒。

   * **[!UICONTROL 架构]**：从列表中选择您的架构。

1. 将架构中定义的 `identification > core > ecid` 属性映射到 ECID 数据元素。选择圆柱体图标可以轻松地从数据元素列表中拾取 ECID 数据元素。

   ![拾取 ECID 数据元素](assets/pick-ecid-dataelement.png)

   ![映射 ECID 数据元素](assets/map-ecid.png)

1. 将架构中定义的`web > webPageDetails > name` 属性映射到页面名称数据元素。

   ![映射页面名称数据元素](assets/map-pagename.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 继续[配置规则](#configure-rules)。

## **配置规则**

Adobe Experience Platform 中的标签遵循基于规则的系统。他们寻找用户交互和相关数据。如果满足您的规则中所列的标准，则规则会触发您已识别的扩展、脚本或客户端代码。您可以使用规则使用 Adobe Experience Platform Web SDK 扩展将数据（如 XDM 对象）发送到 Adobe Experience Platform。

去定义规则

>[!NOTE]
>
>以下步骤是定义规则的示例，该规则会将XDM数据（包含来自其他数据元素的值）发送到Adobe Experience Platform。
>
>您可以在标记中以各种方式使用规则来操作变量（使用数据元素）。
>
>有关详细信息，请参阅[规则](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=zh-Hans)。

1. 使用您的Adobe ID凭据登录experience.adobe.com 。

1. 在Adobe Experience Platform中，转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。

1. 选择左边栏中的&#x200B;**[!UICONTROL 规则]**。

1. 选择&#x200B;**[!UICONTROL 添加规则]**。

1. 在&#x200B;**[!UICONTROL 创建规则]**&#x200B;对话框中，指定以下信息：

   * **[!UICONTROL 名称]**：规则的名称。 例如：`Page View`。

   * **[!UICONTROL 事件]**：选择&#x200B;**[!UICONTROL +添加]**。 然后，在&#x200B;**[!UICONTROL 事件配置]**&#x200B;对话框中，指定以下信息。 完成后，选择&#x200B;**[!UICONTROL 保留更改]**。

      * **[!UICONTROL 扩展]**：从列表中选择&#x200B;**[!UICONTROL 核心]**。

      * **[!UICONTROL 事件类型]**：从列表中选择&#x200B;**[!UICONTROL 已加载窗口]**。

        ![规则 – 事件配置](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 操作]**：选择&#x200B;**[!UICONTROL +添加]**。 然后，在[!UICONTROL 操作配置]对话框中，指定以下信息。 完成后，选择&#x200B;**[!UICONTROL 保留更改]**。

      * **[!UICONTROL 扩展]**：从列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

      * **[!UICONTROL 操作类型]**：从列表中选择&#x200B;**[!UICONTROL 发送事件]**。

      * **[!UICONTROL 类型]**：从列表中选择&#x200B;**[!UICONTROL Web网页详细信息页面查看次数]**。

      * **[!UICONTROL XDM数据]**：选择圆柱体图标，然后从数据元素列表中选择&#x200B;**[!UICONTROL XDM — 页面视图]**。

        ![规则 – 操作配置](assets/action-pageview-xdm.png)

        您的规则应如下所示：

        ![创建规则](assets/rule-pageview.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

1. 对要添加到网站中的每个规则重复此过程。

   有关规则的更多信息，请参阅标记文档中的[规则](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/rules)。

1. 继续[生成并发布您的标记](#build-and-publish-your-tag)。

## 构建和发布您的标记

定义数据元素和规则后，必须构建和发布标记。 创建库生成时，必须将其分配给环境。然后，将会编译该内部版本的扩展、规则和数据元素，并将这些内容放入分配的环境。每个环境都提供了一个唯一的嵌入代码，从而允许您将其分配的内部版本集成到网站中。

Adobe Experience Platform标记支持从简单到复杂的发布工作流程，这些工作流程应该可以适应Adobe Experience Platform Web SDK的部署。 有关详细信息，请参阅 [发布概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) 。

要生成并发布您的标签：

1. 使用您的Adobe ID凭据登录experience.adobe.com 。

1. 在Adobe Experience Platform中，转到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。

1. 从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。

1. 从左边栏中选择&#x200B;**[!UICONTROL 发布流]**。

1. 选择&#x200B;**[!UICONTROL 添加库]**。

1. 在&#x200B;**[!UICONTROL 创建库]**&#x200B;对话框中，指定以下信息：

   * **[!UICONTROL 名称]**：库的名称。

   * **[!UICONTROL 环境]**：从列表中选择&#x200B;**[!UICONTROL 开发（开发）]**。

1. 选择&#x200B;**[!UICONTROL + 添加所有更改的资源]**。

   ![发布文档库](assets/create-library-aep.png)

1. 选择&#x200B;**[!UICONTROL 保存并生成到开发]**。

   您的标记已保存并为开发环境构建。 绿色圆点表示在开发环境中成功构建了标记。

1. 您可以选择&#x200B;**[!UICONTROL ...]** 重建库或将库移动到临时或生产环境。

   ![发布 – 生成文档库](assets/build-library.png)
