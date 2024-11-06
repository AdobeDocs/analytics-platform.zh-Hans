---
title: 使用标记实施用于Customer Journey Analytics的Web SDK
description: 了解如何使用标记来实施适用于Customer Journey Analytics的Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# 使用标记实施用于Customer Journey Analytics的Web SDK

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

您可以使用Adobe Experience Platform中的标记功能在您的网站上实施代码以收集数据。 这一款标记管理解决方案，可让您在满足其他标记要求的同时部署代码。标签使用 Adobe Experience Platform Web SDK 扩展提供与 Adobe Experience Platform 的无缝集成。

## 创建您的标记

1. 在 Adobe Experience Platform UI 的左边栏中，选择 [!UICONTROL 数据收藏集] 中的 **[!UICONTROL 标签]**。

2. 选择&#x200B;**[!UICONTROL 新属性]**。

   为标签命名，选择 **[!UICONTROL Web]** 并输入域名。选择&#x200B;**[!UICONTROL 保存]**&#x200B;继续。

   ![创建资产](assets/create-property.png)

## 配置您的标签

创建标记后，必须使用正确的扩展对其进行配置，并根据要跟踪网站并将数据发送到Adobe Experience Platform的方式配置数据元素和规则。

从 [!UICONTROL 标签属性] 列表中选择您新创建的标签以将其打开。


### **扩展**

为确保您能够将数据发送到Adobe Experience Platform（通过数据流），请将Adobe平台Web SDK扩展添加到您的标记中。

创建并配置 Adobe Experience Platform Web SDK。

1. 选择左边栏中的&#x200B;**[!UICONTROL 扩展]**。

1. 在顶部栏中选择 **[!UICONTROL 目录]**。

1. 搜索或滚动到 Adobe Experience Platform Web SDK 扩展，然后选择 **[!UICONTROL 安装]** 进行安装。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. 选择您的沙盒和您之前为您的[!UICONTROL 生产环境]和（可选）[!UICONTROL 暂存环境]和[!UICONTROL 创建的数据流开发环境]。

   ![AEP Web SDK 扩展配置](assets/aepwebsk-extension-datastreams.png)

   选择&#x200B;**[!UICONTROL 保存]**。

有关详细信息，请参阅[配置 Adobe Experience Platform Web SDK 扩展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html)。

Web SDK本身包含[!UICONTROL Adobe Experience Cloud ID服务]，因此您无需将ID服务扩展添加到标记中。

### **数据元素**

数据元素是数据词典（或数据映射）的构建块。使用数据元素可跨市场营销和广告技术收集、组织和交付数据。您可以在标记中设置从数据层读取的数据元素，并可用于将数据传送到 Adobe Experience Platform。

有不同类型的数据元素。您首先设置一个数据元素来捕获访客在您的网站上查看的页面名称。

定义页面名称数据元素：

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

2. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

3. 在[!UICONTROL 创建数据元素]对话框中：

   - 为数据元素命名，例如，`Page Name`。

   - 从[!UICONTROL 扩展]列表中选择&#x200B;**[!UICONTROL 核心]** 

   - 从 [!UICONTROL 数据元素类型]列表中选择&#x200B;**[!UICONTROL 页面信息]**。

   - 从[!UICONTROL 属性] 列表中选择&#x200B;**[!UICONTROL 标题]** 

     ![使用页面信息创建日期元素](assets/create-dataelement-1.png)

     或者您可以使用数据层变量中的值，例如 `pageName` 和 [!UICONTROL JavaScript 变量]数据元素类型来定义数据元素。

     ![使用页面信息创建数据元素](assets/create-dataelement-2.png)

   - 选择&#x200B;**[!UICONTROL 保存]**。

您现在想要设置一个引用 Experience Cloud ID 的数据元素，该 ID 由 Adobe Experience Platform Web SDK 自动提供，可通过 Experience Cloud ID 服务扩展使用。

要定义 ECID 数据元素：

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

2. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

3. 在[!UICONTROL 创建数据元素]对话框中：

   - 为数据元素命名，例如，`ECID`。

   - 从[!UICONTROL 扩展] 列表中选择 **[!UICONTROL Experience Cloud ID 服务]**。

   - 从 [!UICONTROL 数据元素类型]列表中选择&#x200B;**[!UICONTROL ECID]**。

     ![ECID 数据元素](assets/ecid-dataelement.png)

   - 选择&#x200B;**[!UICONTROL 保存]**。

最后，您现在希望将任何特定的数据元素映射到先前定义的模式。您可以定义另一个数据元素，它提供 XDM 模式的表示。

要定义 XDM 对象数据元素：

1. 选择左边栏中的&#x200B;**[!UICONTROL 数据元素]**。

2. 选择&#x200B;**[!UICONTROL 添加数据元素]**。

3. 在[!UICONTROL 创建数据元素]对话框中：

   - 为数据元素命名，例如，`XDM - Page View`。

   - 从 [!UICONTROL 扩展]列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

   - 从[!UICONTROL 数据元素类型]列表中选择 **[!UICONTROL XDM 对象]**。

   - 从您的[!UICONTROL 沙盒]列表中选择沙盒。

   - 从您的[!UICONTROL 模式]列表中选择模式。

   - 将模式中定义的 `identification > core > ecid` 属性映射到 ECID 数据元素。选择圆柱体图标可以轻松地从数据元素列表中拾取 ECID 数据元素。

     ![拾取 ECID 数据元素](assets/pick-ecid-dataelement.png)

     ![映射 ECID 数据元素](assets/map-ecid.png)


   - 将模式中定义的`web > webPageDetails > name` 属性映射到页面名称数据元素。

     ![映射页面名称数据元素](assets/map-pagename.png)

   - 选择&#x200B;**[!UICONTROL 保存]**。


### **规则**

Adobe Experience Platform 中的标签遵循基于规则的系统。他们寻找用户交互和相关数据。如果满足您的规则中所列的标准，则规则会触发您已识别的扩展、脚本或客户端代码。您可以使用规则使用 Adobe Experience Platform Web SDK 扩展将数据（如 XDM 对象）发送到 Adobe Experience Platform。

去定义规则

1. 选择左边栏中的&#x200B;**[!UICONTROL 规则]**。

1. 选择&#x200B;**[!UICONTROL 创建新规则]**。

1. 在[!UICONTROL 创建规则]对话框中：

   - 命名规则，例如`Page View`。

   - 选择并在[!UICONTROL 事件]下方 **[!UICONTROL +添加]** 

   - 在[!UICONTROL 事件配置]对话框中：

      - 从[!UICONTROL 扩展]列表中选择&#x200B;**[!UICONTROL 核心]** 

      - 从[!UICONTROL 事件类型] 列表中选择&#x200B;**[!UICONTROL 加载的窗口]** 

        ![规则 – 事件配置](assets/event-windowloaded-pageview.png)

      - 选择&#x200B;**[!UICONTROL 保留更改]**。



   - 选择并在[!UICONTROL 操作]下方 **[!UICONTROL +添加]** 

   - 在[!UICONTROL 操作配置]对话框中：

      - 从 [!UICONTROL 扩展]列表中选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

      - 从[!UICONTROL 操作类型] 列表中选择&#x200B;**[!UICONTROL 发送事件]** 

      - 从 [!UICONTROL 类型]列表中选择&#x200B;**[!UICONTROL web.webpagedetails.pageViews]**。

      - 选择[!UICONTROL  XDM 数据]旁边的圆柱体图标，然后从数据元素列表中选择&#x200B;**[!UICONTROL XDM - 页面视图]**。

     ![规则 – 操作配置](assets/action-pageview-xdm.png)

      - 选择&#x200B;**[!UICONTROL 保留更改]**。

   - 您的规则应如下所示：

     ![创建规则](assets/rule-pageview.png)

1. 选择&#x200B;**[!UICONTROL 保存]**。

以上只是定义规则的一个示例，该规则会将XDM数据（包含来自其他数据元素的值）发送到Adobe Experience Platform。

您可以在标记中以各种方式使用规则来操作变量（使用数据元素）。

有关详细信息，请参阅[规则](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=zh-Hans)。

## 生成并发布标签

定义数据元素和规则后，必须构建和发布标记。 创建库生成时，必须将其分配给环境。然后，将会编译该内部版本的扩展、规则和数据元素，并将这些内容放入分配的环境。每个环境都提供了一个唯一的嵌入代码，从而允许您将其分配的内部版本集成到网站中。

要生成并发布您的标签：

1. 从左边栏中选择&#x200B;**[!UICONTROL 发布流]**。

2. 选择 **[!UICONTROL 选择工作库]**，然后选择&#x200B;**[!UICONTROL 添加库…]**。

3. 在[!UICONTROL 创建库]对话框中：

   - 命名库。

   - 选择&#x200B;**[!UICONTROL 开发（开发）]**  [!UICONTROL 环境] 列表。

   - 选择&#x200B;**[!UICONTROL + 添加所有更改的资源]**。

     ![发布文档库](assets/create-library-aep.png)

   - 选择&#x200B;**[!UICONTROL 保存并生成到开发]**。

   您的标记已保存，并为开发环境构建。 绿色圆点表示在开发环境中成功构建了标记。

4. 您可以选择&#x200B;**[!UICONTROL ...]** 重建库或将库移动到临时或生产环境。

   ![发布 – 生成文档库](assets/build-library.png)

Adobe Experience Platform 标签支持简单到复杂的发布工作流，这些工作流应适合您部署 Adobe Experience Platform Web SDK。

有关详细信息，请参阅 [发布概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) 。


## 检索您的标签代码

最后，您必须在要跟踪的网站上安装标记，这表示要在网站模板的标题标记中放置代码。

要获取引用标签的代码，请执行以下操作：

1. 选择左边栏中的&#x200B;**[!UICONTROL 环境]**。

1. 从环境列表中，选择正确的安装（框）按钮。

   在 [!UICONTROL Web 安装说明]对话框中，选择脚本代码旁边的复制按钮，其内容如下：

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![环境](assets/environment.png)

1. 选择&#x200B;**[!UICONTROL 关闭]**。

   您可以根据部署 Adobe Experience Platform Web SDK 的位置选择另一个环境（暂存、生产），而不是开发环境的代码。

   有关详细信息，请参阅 [环境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) 。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
