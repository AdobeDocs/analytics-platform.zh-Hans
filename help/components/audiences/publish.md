---
title: 创建受众并将受众发布到实时客户档案
description: 了解如何从 Customer Journey Analytics 发布受众
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 7d21f6816412b45b795d223d351d4b48bd679c6d
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 50%

---

# 创建并发布受众

本主题讨论如何在Adobe Experience Platform中创建并将在Customer Journey Analytics中识别的受众发布到[实时客户个人资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)，以实现客户定位和个性化。

阅读此[概述](/help/components/audiences/audiences-overview.md)，了解Customer Journey Analytics受众的概念。

## 创建和发布受众 {#create}

1. 要开始创建和发布受众，请执行以下操作之一：

   | 创建方法 | 详细信息 |
   | --- | --- |
   | 从主要&#x200B;**[!UICONTROL 组件] > [!UICONTROL 受众]**&#x200B;菜单 | “受众管理器”页面将打开。单击&#x200B;**[!UICONTROL 创建受众]**，然后将打开[!UICONTROL 受众生成器]。 |
   | 通过自由格式表 | 右键单击自由格式表中的项目并选择&#x200B;**[!UICONTROL 从所选内容创建受众]**。 使用此方法时会用您在表中选择的维度或维度项目预填充过滤器。 |
   | 通过过滤器创建/编辑 UI | 选中显示&#x200B;**[!UICONTROL 从此过滤器创建受众]**&#x200B;的框。使用此方法时会预填充过滤器。 |

   {style="table-layout:auto"}

   <!-- add beneath the Freeform table row above: | From within a Journey canvas visualization | Right-click a node in a Journey canvas visualization and select **[!UICONTROL Create audience]**. Using this method pre-populates the filter with the dimension or dimension item you selected in the table. | -->

1. 生成受众。

   在发布受众之前，请配置这些设置。

   ![下一节中介绍的创建受众倾斜设置的屏幕截图。](assets/create-audience.png)

   | 设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 名称] | 受众的名称。 |
   | [!UICONTROL 标记] | 出于组织目的而要分配给受众的任何标记。您可以使用预先存在的标记或输入新标记。 |
   | [!UICONTROL 描述] | 添加合适的受众描述以将受众与其他人区分开来。 |
   | [!UICONTROL 刷新频率] | 您刷新受众所要采用的频率。<ul><li>您可以选择创建不需要刷新的一次性受众（默认）。例如，这可能有助于特定的一次性营销活动。</li><li>您可以选择其他刷新间隔。对于4小时的刷新频率，受众刷新限制为75至150次，具体取决于您的Customer Journey Analytics权限。</li></ul> |
   | 过期日期 | 当受众将停止刷新时。默认值为创建日期开始 1 年。对过期受众的处理方法与过期的计划报告类似——管理员在受众过期前一个月会收到一封电子邮件。 |
   | 刷新回顾时段 | 指定创建此受众时要在数据窗口中返回多远。最多为 90 天。 |
   | [!UICONTROL 一次性日期范围] | 您希望在其中发布一次性受众的日期范围。 |
   | [!UICONTROL 过滤器] | 过滤器是受众的主要输入。您最多可以添加 20 个过滤器。这些过滤器可以与 `And` 或 `Or` 运算符相连。 |
   | [!UICONTROL 查看样本 ID] | 受众中的 ID 示例。使用搜索栏搜索 ID 示例。 |

   {style="table-layout:auto"}

1. 解释数据预览。

   受众预览显示在右边栏中。它允许您对所创建的受众进行总结分析。

   ![显示受众摘要分析的数据预览屏幕截图。](assets/data-preview.png)

   | 预览设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 数据预览]窗口 | 受众的日期范围。 |
   | [!UICONTROL 总人数] | 该受众中总人数的汇总。可高达 20 亿人。 如果您的受众超过 20 亿人，则必须先缩小受众规模，然后才能发布。 |
   | [!UICONTROL 受众规模限制] | 显示受众人数离 2000 万的上限还有多远。 |
   | [!UICONTROL 预计会返回的受众] | 此设置对于重新定位该受众中那些返回您的网站、移动应用程序或其他渠道（换言之，再次出现在此数据集中的）的客户非常有用。 <p>在这里，您可以为可能返回的估计客户数选择时间范围（未来 7 天、未来 2 周、下个月）。 |
   | [!UICONTROL 预计会返回] | 该数字为您提供了在您从下拉列表中选择的时间范围内返回的客户的估计数量。我们通过观察该受众的历史流失率来预测这一数字。 |
   | [!UICONTROL 预览量度] | 通过此设置，您可以查看特定量度，以查看该受众为此量度做出的贡献是否不成比例，例如[!UICONTROL 收入]或[!UICONTROL 平均网站逗留时间。]它提供了度量的聚合计数，以及它所代表的总数的百分比。您可以选择数据视图中可用的任何量度。 |
   | [!UICONTROL 命名空间包含] | 与受众中的人关联的特定命名空间。例如 ECID、CRM ID、电子邮件地址等。 |
   | [!UICONTROL 沙盒] | 受众所在的 [Experience Platform sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 沙盒。当您将此受众发布到平台时，您只能在这个沙盒的范围内使用它。 |

   {style="table-layout:auto"}

1. 双击受众配置，然后单击&#x200B;**[!UICONTROL 发布]**。

   如果一切顺利，您会收到一条确认消息，确认已发布受众。此受众只需一两分钟就能出现在 Experience Platform 中。（即使是拥有数百万成员的受众，也不会超过 5 分钟的时间。）

1. 在同一条消息中单击&#x200B;**[!UICONTROL 在 AEP 中查看受众]**，则可进入 Adobe Experience Platform 中的 [Segment UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hans)。有关详细信息，请参阅下文。

## 创建和发布受众后会发生什么？ {#after-audience-created}

在Customer Journey Analytics中创建和发布受众后，该受众可在Experience Platform中使用。 仅当您的组织设置为流式分段时，才会创建Adobe Experience Platform流式区段。

* Platform中的受众共享与Customer Journey Analytics受众相同的名称/描述，但名称后将附加Customer Journey Analytics受众ID，以确保其唯一。
* 对Customer Journey Analytics中的受众名称或描述所做的任何更改都会反映在Platform中。
* 如果在Customer Journey Analytics中删除了某个受众，则该受众将继续在Platform中可用。

## 延迟注意事项 {#latency}

在受众发布之前、期间和之后的多个时间点，可能会出现延迟。 以下是对可能出现的延迟情况的概述。

![受众发布的延迟，如本节所述。](assets/latency-diagram.svg)

| # | 延迟点 | 延迟持续时间 |
| --- | --- | --- |
| 未显示 | Adobe Analytics到Analytics源连接器(A4T) | 最多 30 分钟 |
| 1 | 将数据摄取到数据湖（从Analytics源连接器或其他源） | 最多 90 分钟 |
| 2 | 将数据从Experience Platform数据湖摄取到Customer Journey Analytics | 最多 90 分钟 |
| 3 | 将受众发布到实时客户个人资料，包括自动创建流区段，并允许区段准备好接收数据。 | 几秒钟 |
| 4 | 受众的刷新频率 | <ul><li>一次性刷新（延迟小于 5 分钟）</li><li>每 4 小时、每天、每周、每月刷新一次（延迟与刷新率密切相关） |
| 5 | 在Adobe Experience Platform中创建目标：激活新区段 | 1-2 小时 |

{style="table-layout:auto"}

## 在Experience Platform中使用Customer Journey Analytics受众 {#audiences-aep}

Customer Journey Analytics会从已发布的受众中获取所有命名空间和ID组合，并将其以流式传输到实时客户个人资料(RTCP)中。 Customer Journey Analytics根据配置连接时选择作为[!UICONTROL 人员ID]的内容，将受众发送到设置了主标识的Experience Platform。

然后，RTCP 会检查每个命名空间/ID 组合，并查找可能包含它的个人资料。个人资料其实就是由所链接的命名空间、ID 和设备组成的集群。如果它找到配置文件，则会将命名空间和ID作为区段成员资格属性添加到此配置文件中的其他ID。 例如，可以跨其所有设备和渠道定位<user@adobe.com>。 如果未找到相关的个人资料，则会创建一份新的个人资料。

要在Platform中查看Customer Journey Analytics受众，请执行以下操作：

>[!AVAILABILITY]
>
>以下步骤中描述的功能处于版本的有限测试阶段，可能尚未在您的环境中可用。 如果这些步骤与您在环境中看到的不匹配，请改用以下步骤：转到&#x200B;[!UICONTROL **区段**] > [!UICONTROL **创建区段**] > [!UICONTROL **受众**]&#x200B;选项卡> [!UICONTROL **CJA受众**]。
>
>当该功能正式发布时，将删除此说明。有关Customer Journey Analytics发布过程的信息，请参阅[Customer Journey Analytics功能发布](/help/release-notes/releases.md)。

1. 在左边栏中展开&#x200B;[!UICONTROL **客户**]，然后选择&#x200B;[!UICONTROL **受众**]。<!-- is there a folder called "Customer Journey Analytics? -->

1. 选择&#x200B;[!UICONTROL **浏览**]&#x200B;选项卡。

   左侧面板中的![受众选项](assets/audiences-aep.png)

1. 要查找您从Customer Journey Analytics发布的受众，请执行以下任一操作：

   * 按&#x200B;[!UICONTROL **Origin**]&#x200B;列对表进行排序，以查看将&#x200B;[!UICONTROL **Customer Journey Analytics**]&#x200B;显示为源的受众。

   * 选择过滤器图标。

   * 使用搜索字段。

有关在Platform中使用受众的更多信息，请参阅Experience Platform文档的[区段生成器UI指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html)中的[受众](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#audiences)部分。


## 常见问题解答 {#faq}

关于受众发布的常见问题。

+++**如果用户不再是Customer Journey Analytics中的受众成员，会发生什么情况？**

在这种情况下，系统会从Customer Journey Analytics向Experience Platform发送退出事件。

+++

+++**如果删除Customer Journey Analytics中的受众会发生什么情况？**

删除Customer Journey Analytics受众后，该受众将不再出现在Experience PlatformUI中。 然而，在 Platform 中并没有删除和该受众相关联的个人资料。

+++

+++**如果 RTCDP 中不存在相应的配置文件，是否会创建新的配置文件？**

是的，会的。

+++

+++**Customer Journey Analytics是将受众数据作为管道事件发送，还是作为同样发送到数据湖的平面文件发送？**

Customer Journey Analytics通过管道将数据流式传输到RTCP中，并且这些数据还会收集到数据湖中的系统数据集中。

+++

+++**Customer Journey Analytics发送了哪些标识？**

在[连接设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)中指定的任何标识/命名空间对。 具体来说，用户选择要用作其“个人 ID”的字段时的步骤。

+++

+++**选择什么 ID 作为主要标识？**

请参阅上面的内容。我们只为每个Customer Journey Analytics“人员”发送一个身份。

+++

+++**RTCP是否也处理Customer Journey Analytics消息？ Customer Journey Analytics是否可以通过受众共享将身份添加到配置文件身份图？**

否。我们只为每个“人”发送一个标识，因此 RTCP 不会使用任何图边。

+++

+++**在一天中的哪个时间进行每日、每周和每月的刷新？ 每周的哪一天进行刷新？**

刷新时间基于原始受众的发布时间和锚点到当天时间（以及星期或月）。

+++

+++**用户是否可以配置每日、每周和每月的刷新时间？**

不可以，用户无法配置它们。

+++


## 后续步骤

* 若要管理该受众，请转到[管理 UI](/help/components/audiences/manage.md)。
