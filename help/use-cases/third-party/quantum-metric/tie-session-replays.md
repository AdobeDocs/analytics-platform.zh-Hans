---
title: 系数量度会话重播到Customer Journey Analytics中的数据
description: 链接量子量度会话会重播CJA数据，以便更好地了解“内容”背后的“原因”。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: a03505aeb56f99b28f50819765a496705876b89c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 2%

---

# 系数量度会话重播到Customer Journey Analytics中的数据

通过将Quantum Metric会话重播与CJA数据关联，客户可以更好地了解“内容”背后的“原因”。  Workspace可用于发现存在摩擦的会话，然后单击超链接会话ID以在Quantum Metric中浏览会话重放。  通过此数据，可查看会话中的行为并更好地了解导致消费者摩擦的因素。  通过与CJA绑定的会话重播，您可以捕获体验中有关客户行为的关键上下文。

## 先决条件

这些步骤假定您使用Adobe Experience Platform数据收集中的标记。 如果您的组织不使用标记，则可以调整这些数据收集方法，以便手动实施Web SDK。

有关详细信息，请参阅[Quantum量度标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)文档。

## 步骤1：创建架构字段以容纳量子度量会话ID

此使用案例需要专用架构字段才能将数据发送到。 您可以在架构中的任意所需位置创建此字段，然后根据需要对其进行命名。 如果您的组织对名称或位置没有首选项，则会提供示例值。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 架构]**。
1. 从列表中选择所需的架构。
1. 选择所需对象旁边的![添加字段图标](/help/assets/icons/AddCircle.svg)图标。 例如，在`Implementation Details`旁边。
1. 在右侧，输入所需的[!UICONTROL 名称]。 例如，`qmSessionId`。
1. 输入所需的[!UICONTROL 显示名称]。 例如，`Quantum Metric session ID`。
1. 选择[!UICONTROL 类型]作为&#x200B;**[!UICONTROL 字符串]**。
1. 选择&#x200B;**[!UICONTROL 保存]**。

## 步骤2：使用量度标记扩展捕获量度会话ID

按照以下步骤将量子量度会话ID附加到您发送到Adobe Experience Platform的数据。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到&#x200B;**[!UICONTROL 数据收集]** > **[!UICONTROL 标记]**。
1. 选择所需的标记属性。
1. 选择&#x200B;**[!UICONTROL 数据元素]**，然后选择&#x200B;**[!UICONTROL 添加数据元素]**。
1. 设置以下设置：
   * **[!UICONTROL 名称]**： `Quantum Metric session ID`
   * **[!UICONTROL 扩展]**： [!UICONTROL 核心]
   * **[!UICONTROL 数据元素类型]**： [!UICONTROL 自定义代码]
1. 选择&#x200B;**[!UICONTROL 打开编辑器]**&#x200B;按钮并粘贴以下代码：

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. 选择&#x200B;**[!UICONTROL 保存]**。

## 步骤3：将数据元素映射到所需的XDM架构字段

现在，数据元素具有获取所需值的逻辑，请将数据元素映射到XDM对象。

1. 在tag属性中，选择&#x200B;**[!UICONTROL 数据元素]**，然后选择包含XDM对象的数据元素。
1. 在此数据元素的右列中，导航到创建架构字段时建立的路径。
1. 将该值设置为由百分比符号包围的数据元素的名称。 例如，`%Quantum Metric session ID%`。
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 添加库，然后将更改发布到生产环境。

如果您的XDM对象已包含在发送事件操作配置中，那么在发布更改后，您将开始看到数据。

>[!NOTE]
>
>有时Web SDK的运行速度会比Quantum Metric代码更快。 在这些情况下，会话ID会在后续点击时发送。 如果访客跳出，则在这些实例中不会收集会话ID。

## 步骤3：添加量子度量会话ID作为可用维度

您的实施发布上述更改后，编辑现有数据视图，在Customer Journey Analytics中将会话ID添加为可用维度。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL 数据视图]**。
1. 选择所需的现有数据视图。
1. 在左侧找到量子度量会话ID字段，并将其拖动到中心的维度区域。
1. 在右窗格中，将[persistence](/help/data-views/component-settings/persistence.md)设置设置为`Session`。
1. 选择&#x200B;**[!UICONTROL 保存]**。

## 步骤4：配置Analysis Workspace以适应会话ID维度

在Workspace中创建自由格式表并进行配置，以便会话ID值直接链接到Quantum Metric。

1. 登录到[experience.adobe.com](https://experience.adobe.com)。
1. 导航到Customer Journey Analytics，然后在顶部菜单中选择&#x200B;**[!UICONTROL Workspace]**。
1. 选择现有项目，或创建项目。
1. 创建[自由格式表](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 将会话ID维度拖动到Workspace画布。
1. 右键单击维度列标题，然后选择&#x200B;**[!UICONTROL 为所有维度项目创建超链接]**。
1. 选择&#x200B;**[!UICONTROL 创建自定义URL]**。
1. 粘贴以下URL结构：

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 单击&#x200B;**[!UICONTROL 创建]**。

现在，每个会话ID都是一个可单击的链接。 有关向Analysis Workspace维度项目添加超链接的详细信息，请参阅[在自由格式表中创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。

## 步骤5：从Customer Journey Analytics查看会话

找到要探究会话重放的有趣区段后，您可以将其应用于包含会话ID链接的面板。 该表返回该区段中的所有会话，您可以单击其中的任何会话以在量子度量中进一步探讨。

有关详细信息，请参阅[Quantum量度上的会话重播企业指南](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay)。 您还可以联系您的Quantum Metric客户支持代表，或通过[Quantum Metric客户请求门户](https://community.quantummetric.com/s/public-support-page)提交请求。
