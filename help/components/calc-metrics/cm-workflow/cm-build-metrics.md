---
description: 计算量度生成器提供了一个画布，用于拖放维度、量度、区段和函数，以基于容器层次结构逻辑、规则和运算符创建自定义量度。通过这个集成的开发工具，可生成并保存简单的计算量度或复杂的高级计算量度。
title: 生成计算量度
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 96%

---

# 生成计算量度 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="产品兼容性"
>abstract="表示此计算量度可用于 Customer Journey Analytics，例如 Analysis Workspace、Report Builder 等。某些计算量度无法与试验相结合。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="在实验中使用计算量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="更改外部 ID 可能会影响计算量度在外部源（例如商业智能工具）中的显示方式"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics 提供了一个画布，用于拖放维度、量度、区段和函数，以根据容器层次结构逻辑、规则和运算符创建自定义量度。通过这种集成式开发工具，您可以生成并保存简单或复杂的计算量度。

## 开始生成计算量度

您可以使用计算量度生成器来创建或编辑计算量度。以这种方式创建时，计算量度可在组件列表中使用，然后可在整个组织的项目中使用。或者，您可以快速创建仅适用于创建它的项目的计算量度，如[量度](/help/components/apply-create-metrics.md)中[为单个项目创建计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)所述。

访问计算度量生成器开始创建可在组件列表中使用的计算度量。

1. 通过以下任一方式访问计算度量生成器：

   * 在 Analysis Workspace 中，打开一个项目，然后选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 创建量度]**。
   * 在 Analysis Workspace 中，打开一个项目，然后选择左边栏中&#x200B;[!UICONTROL **量度**]&#x200B;分区旁边的&#x200B;**加号**&#x200B;图标。
   * 在 [!DNL Customer Journey Analytics] 中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**，然后选择位于计算量度页面顶部的 **[!UICONTROL + 添加]**。

1. 继续[计算量度生成器面积图](#areas-of-the-calculated-metrics-builder)。

## 计算量度构建器的区域

**[!UICONTROL 计算量度生成器]**&#x200B;对话框用于创建新的或编辑现有的计算量度。对于您在[[!UICONTROL 计算量度]管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)中创建或管理的量度，该对话框的标题为&#x200B;**[!UICONTROL 新建计算量度]**&#x200B;或&#x200B;**[!UICONTROL 编辑计算量度]**。

>[!BEGINTABS]

>[!TAB 计算量度生成器]

![计算量度详情窗口，其中显示下一节所述的字段和选项。](assets/calculated-metric-builder.png)

>[!TAB 创建或编辑计算量度]

![计算量度详情窗口，其中显示下一节所述的字段和选项。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 指定以下详细信息（![Required](/help/assets/icons/Required.svg)为必要项）：

   | 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 数据视图]** | 您可以选择计算量度的数据视图。您定义的计算量度可根据所选的数据视图在工作区项目中使用。 |
   | **[!UICONTROL 仅限于项目的量度]** | 当您编辑为单个项目创建的计算量度时，此对话框顶部会出现一个信息框，如[为单个项目创建计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)中所述。 <p>如果您希望将此计算量度用于所有项目，请选择以下选项：**[!UICONTROL 将此量度提供给所有项目并将其添加到组件列表中]**。</p> |
   | **[!UICONTROL 标题]**![必填](/help/assets/icons/Required.svg) | 为计算量度命名，例如，`Conversion Rate`。 |
   | **[!UICONTROL 外部 ID]** ![必填](/help/assets/icons/Required.svg) | 使用外部 BI 工具和 BI 扩展时计算量度的名称。除非您覆盖该值，否则该值将会自动定义为 `undefined_xxx`。 |
   | **[!UICONTROL 描述]** | 提供对区段的描述，例如：`Calculated metric to define the conversion rate.` 无需描述计算量度的公式，因为[!UICONTROL 摘要]中已自动提供该公式。 |
   | **[!UICONTROL 格式]** | 选择计算量度的格式：您可以选择&#x200B;**[!UICONTROL 小数]**、**[!UICONTROL 时间]**、**[!UICONTROL 百分比]**&#x200B;和&#x200B;**[!UICONTROL 货币]**。 |
   | **[!UICONTROL 小数位]** | 指定所选格式的小数位数。仅当选择的格式为十进制、货币和百分比时启用。 |
   | **[!UICONTROL 将上升趋势显示为]** | 指定计算量度的上升趋势是否显示为 ▲ **[!UICONTROL 良好（绿色）]**&#x200B;或 ▼ **[!UICONTROL 不良（红色）]**。 |
   | **[!UICONTROL 货币]** | 指定计算量度的货币。仅当选择的格式为货币时才启用。 |
   | **[!UICONTROL 标记]** | 通过创建或应用一个或多个标记来组织计算量度。开始键入，以查找您可以选择的现有标记。或者按&#x200B;**[!UICONTROL 输入]**&#x200B;键添加新的标记。选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以移除标记。 |
   | **[!UICONTROL 预览]** | 预览涵盖过去 90 天的情况，并且可以衡量您是否正确定义了量度。 |
   | **[!UICONTROL 摘要]** | 显示计算量度定义的摘要。<br/>例如：![事件](/help/assets/icons/Event.svg) **[!UICONTROL 总订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话]**。 |
   | **[!UICONTROL 定义]**![必填](/help/assets/icons/Required.svg) | 使用[定义生成器](#definition-builder)来定义区段。 |

1. 要验证您的计算量度定义是否正确，请使用不断更新的计算量度结果&#x200B;**[!UICONTROL 预览]**。**[!UICONTROL 预览]**&#x200B;涵盖过去 90 天，并会持续评估计算量度的定义。

   **[!UICONTROL 产品兼容性]**&#x200B;表示计算量度是否可用于实验。可能的值包括：
   * **[!UICONTROL Customer Journey Analytics 中的任何地方]**：计算量度可用于整个 Customer Journey Analytics。
   * **[!UICONTROL Customer Journey Analytics 中的所有地方（不包括实验）]**：计算量度可用于除实验面板之外的所有 Customer Journey Analytics 部分。

1. 选择:
   * **[!UICONTROL 保存]**&#x200B;以保存计算量度。
   * **[!UICONTROL 另存为]**&#x200B;以保存计算量度的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消您对计算量度所做的任何更改，或者取消创建新的计算量度。


## 定义生成器

您可以使用定义生成器来拖放维度、量度、区段和函数，以根据容器层级结构逻辑、规则和运算符来创建自定义量度。在该构造中，您可以使用标准度量、Adobe 定义的度量、计算度量、区段、维度和函数。所有这些组件都可以从计算量度生成器中的组件面板中获得。此外，您还可以在定义中使用运算符和容器。

![创建计算量度](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

在&#x200B;**[!UICONTROL 定义]**&#x200B;区域中，仅会将量度定义为单一组件。所有其他组件都会被定义为容器、包装量度或其他容器。有关更多信息，请参阅[容器](#containers)。

### 量度

要添加量度：

* 将![事件](/help/assets/icons/Event.svg)**[!UICONTROL 量度]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。

当您使用计算量度作为定义的一部分时，计算量度将会展开。

要修改量度：

1. 在![定义](/help/assets/icons/Setting.svg)区域中的量度组件中选择&#x200B;**[!UICONTROL 设置]**。
1. 在弹出对话框中，您可以定义量度的类型和归因模型。请参阅[量度类型和归因](m-metric-type-alloc.md)。

要删除量度：

* 在量度中选择![关闭](/help/assets/icons/Close.svg)。

### 运算符

运算符允许您指定组件或容器之间的运算符。运算符自动出现在

* 容器中的两个或多个量度，
* 容器中的两个或多个容器，
* 容器中的一个或多个量度以及一个或多个容器。

您可以选择︰

| 符号 | 运算符 |
|:---:|---|
| ![除](/help/assets/icons/Divide.svg) | 除（默认） |
| ![关闭](/help/assets/icons/Close.svg) | 乘 |
| ![删除](/help/assets/icons/Remove.svg) | 减 |
| ![加](/help/assets/icons/Add.svg) | 加 |

### 静态数字

您可以向计算量度定义中添加一个静态数字。要添加一个静态数字：

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**。
* 选择&#x200B;**[!UICONTROL 静态数字]**。出现静态数字容器。
* 选择&#x200B;[!UICONTROL *单击以添加值*]&#x200B;并输入一个值。


### 容器

您可以将维度、区段和函数作为容器添加到计算量度定义中。您还可以添加通用容器。容器的作用类似于数学表达式，它们决定着运算的顺序。容器内的任何内容都会在下一个组件或容器之前得导出理。


#### 区段容器

您可以使用区段容器的概念来创建[分段量度](metrics-with-segments.md)。您可以使用区段或者使用从某个维度创建的区段来构建区段容器。

* 要从某个维度添加区段容器：

   1. 将![维度](/help/assets/icons/Dimensions.svg) **[!UICONTROL 维度]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。
   1. 在&#x200B;**[!UICONTROL 从Dimension创建区段]**&#x200B;弹出窗口中，定义区段的条件。 从运算符列表中选择，并选择一个值或输入一个值。例如，**[!UICONTROL 月份]****[!UICONTROL 等于]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`。
   1. 选择&#x200B;**[!UICONTROL 完成]**。现在，**[!UICONTROL 定义]**&#x200B;中添加了一个区段容器。


* 要从某个区段添加区段容器，您可以使用：

   * 将![分段](/help/assets/icons/Segmentation.svg)**[!UICONTROL 区段]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定区段。使用区段的名称，区段容器被自动添加到&#x200B;**[!UICONTROL 定义]**&#x200B;中。

   * 将![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]**&#x200B;组件从组件面板拖放到通用容器上。 该容器变成了一个区段容器。

   * 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**：

      1. 选择&#x200B;**[!UICONTROL 区段]**。 现在，**[!UICONTROL 定义]**&#x200B;中添加了一个区段容器。
      1. 在新区段容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个区段。

  >[!TIP]
  >
  >您可以在一个容器中添加多个区段。

  容器中的区段以区段组件命名。例如，![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web 会话]**。选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 可显示一个包含区段详细信息的弹出窗口。在这个弹出窗口中，选择![编辑](/help/assets/icons/Edit.svg)可编辑区段定义。

要从容器中移除某个区段：

* 选择区段名称旁边的![关闭](/help/assets/icons/Close.svg)。

有关更多详细信息和示例，请参阅[分段量度](metrics-with-segments.md)。

#### 函数容器

要添加函数容器，您可以使用：

* 拖放：

   1. 将 ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL 函数]**&#x200B;组件从组件面板拖放到 **[!UICONTROL 将量度、维度、维度项、区段和/或函数拖放到此处]**。您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定函数。
   1. 使用函数的名称自动将函数容器添加到&#x200B;**[!UICONTROL 定义]**。

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**：

   1. 选择&#x200B;**[!UICONTROL 函数]**。
   1. 在容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个函数。

函数容器以函数组件命名。例如，![函数](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度）]**。选择 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 来显示一个带有函数详细信息的弹出窗口。选择&#x200B;**[!UICONTROL 了解更多]**，以了解有关该函数的更多信息。

请参阅[使用函数](cm-using-functions.md)，了解有关如何使用函数以及可以使用哪些函数来创建计算量度的详细信息。


#### 通用容器

要添加通用容器：

* 从容器内选择 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 添加]**
* 选择&#x200B;**[!UICONTROL 容器]**。**[!UICONTROL 定义]**&#x200B;中添加了一个新的空容器。您可以使用通用容器在计算量度的定义中嵌套或创建层级结构。


#### 删除容器

要删除容器，请在容器级别选择![关闭](/help/assets/icons/Close.svg)。

>[!MORELIKETHIS]
>
>[使用函数](cm-using-functions.md)
>[区段](/help/components/filters/filters-overview.md)
>

