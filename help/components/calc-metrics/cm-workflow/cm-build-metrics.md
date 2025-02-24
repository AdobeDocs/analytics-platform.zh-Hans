---
description: 计算量度生成器提供一个画布，可以将维度、量度、筛选器和函数拖放到画布上，以基于容器层次结构逻辑、规则和运算符创建自定义量度。通过此集成式开发工具，您可以生成并保存简单的计算量度或复杂的高级计算量度。
title: 生成计算量度
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 1ffe01609b3ab0d96b79cc9297dda9ccf25bcbb6
workflow-type: tm+mt
source-wordcount: '1501'
ht-degree: 11%

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


**[!UICONTROL 计算量度生成器]**&#x200B;对话框用于创建新计算量度或编辑现有计算量度。 该对话框的标题为&#x200B;**[!UICONTROL 新建计算量度]**&#x200B;或&#x200B;**[!UICONTROL 编辑从[[!UICONTROL 计算量度]管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)创建或管理的量度的计算量度]**。

>[!BEGINTABS]

>[!TAB 计算指标生成器]

![计算度量详细信息窗口，其中显示下一节中描述的字段和选项。](assets/calculated-metric-builder.png)

>[!TAB 创建或编辑计算量度]

![计算度量详细信息窗口，其中显示下一节中描述的字段和选项。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 指定以下详细信息（![Required](/help/assets/icons/Required.svg)为必要项）：

   | 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 数据视图]** | 您可以选择计算指标的数据视图。  您定义的计算指标基于所选的数据视图在Workspace项目中可用。 |
   | **[!UICONTROL 仅用于项目的量度]** | 编辑为单个项目创建的计算量度时，此对话框顶部会显示一个信息框，如[为单个项目创建计算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)中所述。 <p>如果要使该计算量度可用于所有项目，请选择选项&#x200B;**[!UICONTROL 使该量度可用于所有项目并将其添加到组件列表]**。</p> |
   | **[!UICONTROL 标题]** ![Required](/help/assets/icons/Required.svg) | 命名计算量度，例如`Conversion Rate`。 |
   | **[!UICONTROL 外部ID]** ![必需](/help/assets/icons/Required.svg) | 使用外部BI工具和BI扩展时计算量度的名称。 除非您覆盖该值，否则该值将自动定义为`undefined_xxx`。 |
   | **[!UICONTROL 描述]** | 提供筛选器的说明，例如`Calculated metric to define the conversion rate.`。无需说明计算量度的公式，因为该公式已在[!UICONTROL 摘要]中自动可用。 |
   | **[!UICONTROL 格式]** | 为计算量度选择格式：您可以选择介于&#x200B;**[!UICONTROL Decimal]**、**[!UICONTROL Time]**、**[!UICONTROL Percent]**&#x200B;和&#x200B;**[!UICONTROL Currency]**&#x200B;之间。 |
   | **[!UICONTROL 小数位]** | 指定所选格式的小数位数。 仅当选择的格式为“小数”、“货币”和“百分比”时才启用。 |
   | **[!UICONTROL 将上升趋势显示为]** | 指定计算量度的上升趋势显示为▲**[!UICONTROL 良好（绿色）]**&#x200B;还是▼**[!UICONTROL 不良（红色）]**。 |
   | **[!UICONTROL 货币]** | 指定计算指标的货币。 仅当选择的格式为货币时启用。 |
   | **[!UICONTROL 标记]** | 通过创建或应用一个或多个标记来组织计算量度。 开始键入，以查找您可以选择的现有标记。或按&#x200B;**[!UICONTROL ENTER]**&#x200B;添加新标记。 选择 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 以移除标记。 |
   | **[!UICONTROL 预览]** | 预览涵盖过去90天，是一种衡量您是否已正确定义指标的方法。 |
   | **[!UICONTROL 摘要]** | 显示计算指标定义的摘要。 <br/>例如：![事件](/help/assets/icons/Event.svg) **[!UICONTROL 总订单]** ![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 会话]**。 |
   | **[!UICONTROL 定义]** ![必需](/help/assets/icons/Required.svg) | 使用[定义生成器](#definition-builder)定义您的筛选器。 |

1. 要验证计算量度定义是否正确，请使用计算量度结果不断更新的&#x200B;**[!UICONTROL 预览]**。 **[!UICONTROL 预览]**&#x200B;涵盖过去90天，并持续评估计算指标的定义。

   **[!UICONTROL 产品兼容性]**&#x200B;指示计算度量是否可用于实验。 可能的值包括：
   * **[!UICONTROL Customer Journey Analytics中的所有位置]**：计算指标可在所有Customer Journey Analytics中使用。
   * **[!UICONTROL Customer Journey Analytics中的所有位置（不包括试验）]**：计算指标可在所有Customer Journey Analytics中使用，试验面板除外。

1. 选择：
   * **[!UICONTROL 保存]**&#x200B;以保存计算量度。
   * **[!UICONTROL 另存为]**&#x200B;以保存计算量度的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消对计算量度所做的任何更改或取消创建新计算量度。


## 定义生成器

您可以使用定义生成器将维度、量度、筛选器和函数拖放到容器层次结构逻辑、规则和运算符的基础上创建自定义量度。 在该结构中，您可以使用标准量度、Adobe定义的量度、计算量度、过滤器、维度和函数。 所有这些组件在计算量度生成器的组件面板中均可用。 此外，您可以在定义中使用运算符和容器。

![创建计算量度](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

在&#x200B;**[!UICONTROL 定义]**&#x200B;区域中，只有量度被定义为单个组件。 所有其他组件都定义为容器、包装量度或其他容器。 有关详细信息，请参阅[容器](#containers)。

### 量度

要添加量度，请执行以下操作：

* 将![事件](/help/assets/icons/Event.svg) **[!UICONTROL 量度]**&#x200B;组件从组件面板拖放到&#x200B;**[!UICONTROL 将量度、维度、维度项、筛选器和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。

当您在定义中使用计算量度时，计算量度是展开的。

要修改指标，请执行以下操作：

1. 在&#x200B;**[!UICONTROL 定义]**&#x200B;区域中选择量度组件中的![设置](/help/assets/icons/Setting.svg)。
1. 在弹出对话框中，您可以定义量度类型和归因模型。 请参阅[量度类型和归因](m-metric-type-alloc.md)。

要删除指标，请执行以下操作：

* 在量度中选择![关闭](/help/assets/icons/Close.svg)。

### 运算符

运算符允许您指定组件或容器之间的运算符。 运算符自动显示介于

* 容器中的两个或多个量度，
* 一个容器中的两个或多个容器，
* 容器中的一个或多个量度和一个或多个容器。

您可以选择︰

| 符号 | 运算符 |
|:---:|---|
| ![除](/help/assets/icons/Divide.svg) | 除（默认） |
| ![关闭](/help/assets/icons/Close.svg) | 乘 |
| ![删除](/help/assets/icons/Remove.svg) | 减 |
| ![添加](/help/assets/icons/Add.svg) | 添加 |

### 静态数字

您可以向计算指标定义添加静态数字。 添加静态数字：

* 从容器中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**。
* 选择&#x200B;**[!UICONTROL 静态数字]**。 此时将显示一个静态编号容器。
* 选择&#x200B;[!UICONTROL *单击以添加值*]&#x200B;并键入值。


### 容器

将维度、过滤器和函数作为容器添加到计算量度定义。 您还可以添加通用容器。 容器的作用类似于数学表达式，它们决定着运算的顺序。容器中的任何内容都将在下一个组件或容器之前进行处理。


#### 筛选器容器

使用筛选器容器的概念创建[筛选量度](metrics-with-segments.md)。 您可以使用过滤器或根据维度创建的过滤器来构建过滤器容器。

* 要从维度添加过滤器容器，请执行以下操作：

   1. 将![维度](/help/assets/icons/Dimensions.svg) **[!UICONTROL 维度]**&#x200B;组件从“组件”面板拖放到&#x200B;**[!UICONTROL 将量度、维度、维度项、筛选器和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定组件。
   1. 在&#x200B;**[!UICONTROL 从Dimension创建过滤器]**&#x200B;弹出窗口中，定义过滤器的条件。 从运算符列表中进行选择，然后选择一个值或输入一个值。 例如，**[!UICONTROL Month]** **[!UICONTROL 等于]** ![V形下降](/help/assets/icons/ChevronDown.svg) `Sep 2024`。
   1. 选择&#x200B;**[!UICONTROL 完成]**。 筛选器容器已添加到&#x200B;**[!UICONTROL 定义]**。


* 要从筛选器添加筛选器容器，您可以使用：

   * 将![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 筛选器]**&#x200B;组件从组件面板拖放到&#x200B;**[!UICONTROL 将量度、维度、维度项、筛选器和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定筛选器。
使用该筛选器的名称，自动将筛选器容器添加到**[!UICONTROL 定义]**。

   * 将![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 筛选器]**&#x200B;组件从组件面板拖放到通用容器上。 将该容器修改为过滤器容器。

   * 从容器中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**：

      1. 选择&#x200B;**[!UICONTROL 筛选器]**。 筛选器容器已添加到&#x200B;**[!UICONTROL 定义]**。
      1. 在新筛选器容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个筛选器。

  >[!TIP]
  >
  >您可以向容器添加多个过滤器。

  容器中的过滤器以过滤器组件命名。 例如，![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL Web会话]**。 选择![信息大纲](/help/assets/icons/InfoOutline.svg)以显示包含筛选器详细信息的弹出窗口。 在弹出窗口中，选择![编辑](/help/assets/icons/Edit.svg)以编辑筛选器定义。

要从容器中删除过滤器，请执行以下操作：

* 选择筛选器名称旁边的![关闭](/help/assets/icons/Close.svg)。

有关更多详细信息和示例，请参阅[过滤的量度](metrics-with-segments.md)。

#### 函数容器

要添加函数容器，您可以使用：

* 拖放：

   1. 将![函数](/help/assets/icons/Effect.svg) **[!UICONTROL 函数]**&#x200B;组件从组件面板拖放到&#x200B;**[!UICONTROL 将量度、维度、维度项、筛选器和/或函数拖放到此处]**。 您可以使用组件栏中的![搜索](/help/assets/icons/Search.svg)来搜索特定功能。
   1. 自动使用函数名称将函数容器添加到&#x200B;**[!UICONTROL 定义]**。

* 从容器中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**：

   1. 选择&#x200B;**[!UICONTROL 函数]**。
   1. 在容器中，从&#x200B;[!UICONTROL *选择……*]&#x200B;下拉菜单中选择一个函数。

函数容器以函数组件命名。 例如，![函数](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度）]**。 选择![信息大纲](/help/assets/icons/InfoOutline.svg)以显示包含函数详细信息的弹出窗口。 选择&#x200B;**[!UICONTROL 了解更多]**&#x200B;以了解有关该函数的更多信息。

有关如何使用函数以及哪些函数可用于创建计算量度的详细信息，请参阅[使用函数](cm-using-functions.md)。


#### 通用容器

要添加通用容器，请执行以下操作：

* 从容器中选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**
* 选择&#x200B;**[!UICONTROL 容器]**。 向&#x200B;**[!UICONTROL 定义]**&#x200B;添加了新的空泛型容器。 您可以使用通用容器在计算指标的定义中嵌套或创建层次结构。


#### 删除容器

要删除容器，请选择容器级别的![关闭](/help/assets/icons/Close.svg)。

>[!MORELIKETHIS]
>
>[使用函数](cm-using-functions.md)
>[过滤器](/help/components/filters/filters-overview.md)
>

