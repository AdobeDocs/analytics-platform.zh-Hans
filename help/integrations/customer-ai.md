---
description: 了解 AEP 客户人工智能如何与 CJA 中的工作区集成。
title: 将客户人工智能与 CJA 集成
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 320b34ca171bb835aa3b4a9a981cc19b14060ad9
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 33%

---

# 将客户人工智能与 CJA 集成

[客户人工智能](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=zh-Hans)，作为 Adobe Experience Platform 智能服务的一部分，为营销人员提供了在个人层面生成客户预测的能力。

在影响因素的帮助下，客户人工智能可以告诉您客户可能会做什么以及为什么。此外，营销人员可以从客户人工智能预测和洞察中受益，通过提供最合适的优惠和消息传递来个性化客户体验。

Customer AI依赖于个人行为数据和用户档案数据来进行倾向评分。 Customer AI具有灵活性，可以接收多个数据源，包括Adobe Analytics、Adobe Audience Manager、消费者体验事件数据和体验事件数据。 如果您使用Experience Platform源连接器导入Adobe Audience Manager和Adobe Analytics数据，则模型会自动选取标准事件类型以对模型进行培训和评分。 如果您引入了自己的不含标准事件类型的体验事件数据集，则如果您希望在模型中使用任何相关字段，则需要将其映射为自定义事件或配置文件属性。 这可以在Experience Platform的Customer AI配置步骤中完成。&#x200B;

客户人工智能与 Customer Journey Analytics (CJA) 集成，从而可以在 CJA 中的数据视图和报告中利用启用客户人工智能的数据集。通过此集成，您可以

* **跟踪一段时间内某个用户区段的倾向得分**. 示例用例：酒店客户在酒店的音乐会场地购买展示票的可能性有多大？
* **分析哪些成功事件或属性与倾向得分相关联**.&#x200B;示例用例：我想了解与倾向得分相关的属性或成功事件。
* **在不同的评分运行中跟踪客户倾向的登录流程**. 示例用例：我想了解那些最初是低倾向用户的人，随着时间的推移，他们变成了高倾向用户&#x200B;。
* **查看倾向的分布**. 用例：我想了解倾向得分的分布情况，以便能够更准确地分配我的区段。&#x200B;示例：零售商希望以每件产品50美元的价格进行特定促销。 由于预算等原因，他们可能只想进行非常有限的升级。 他们分析数据并决定只定位其前80%以&#x200B;上的客户。
* **查看一段时间内特定同类群组完成操作的倾向**. 用例：我希望跟踪特定同类群组的一段时间。 这类似于第一个同类群组，但您可以随着时间跟踪特定同类群组&#x200B;。 酒店业示例：营销人员可以跟踪他们的青铜层与银层，或银层与黄金层随时间推移的变化。 然后，他们可以看到每个同类群组在一段时间内预订酒店的倾向。&#x200B;

## 工作流程

在使用 CJA 中的输出之前，请在 Adobe Experience Platform 中执行某些步骤。

### 步骤 1：配置客户人工智能实例

准备数据并部署所有凭据和模式后，请首先按照 [配置Customer AI实例](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=zh-Hans) 指南。

### 第 2 步：设置与客户人工智能数据集的 CJA 连接

在 CJA 中，您现在可以 [创建一个或多个连接](/help/connections/create-connection.md) 到已针对客户人工智能进行检测的 Experience Platform 数据集。每个预测（如“升级帐户的可能性”）等于一个数据集。 这些数据集将以“Customer AI Scores in EE Format - name_of_application”为前缀显示。

>[!IMPORTANT]
>
>如果在步骤1中的配置期间打开切换以为CJA启用得分，则每个Customer AI实例都有两个输出数据集。 一个输出数据集以配置文件XDM格式显示，一个以体验事件XDM格式显示。

![CAI 分数](assets/cai-scores.png)

![创建连接](assets/create-conn.png)

以下是CJA将作为现有或新数据集的一部分引入的XDM架构示例：

![CAI 模式](assets/cai-schema.png)

（请注意，该示例是一个配置文件数据集；同一组模式对象将成为 CJA 将获取的体验事件数据集的一部分。体验事件数据集将包括时间戳作为得分日期。）在此模型中得分的每个客户都会有一个分数、一个 scoreDate 等与他们相关联。

### 第 3 步：根据这些连接创建数据视图

在 CJA 中，您现在可以使用作为您建立的连接的一部分引入的维度（例如分数、分数日期、概率等）和指标继续[创建数据视图](/help/data-views/create-dataview.md)。

![创建数据视图](assets/create-dataview.png)

### 第 4 步：报告工作区中的 CAI 分数

在CJA工作区中，您现在可以创建新项目并提取可视化图表。

**趋势倾向得分**

以下是一个包含CAI数据的工作区项目示例，该示例在堆叠式条形图中显示用户区段的倾向&#x200B;得分随时间变化的趋势：

![分数桶](assets/workspace-scores.png)

**具有原因代码的表**

下表显示了区段为何具有高倾向或低倾向的原因代&#x200B;码：

![原因代码](assets/reason-codes.png)

**客户倾向的登入流**

此流程图显示客户倾向在不同评分运行时的登录流程&#x200B;:

![登入流量](assets/flow.png)

**倾向得分的分布**

此条形图显示倾向得分的分&#x200B;布：

![分发](assets/distribution.png)

**倾向重叠**

此维恩图显示了不同评分运行时的倾向重叠：

![倾向重叠](assets/venn.png)
