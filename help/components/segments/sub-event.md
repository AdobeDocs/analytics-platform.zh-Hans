---
title: 子事件分析
description: 了解子事件分析如何让您在客户历程分析中筛选事件内的单个产品或其他容器，从而消除产品报表中的归因出血。
feature: Segmentation
hold: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: b4bec7c8e476bc2dbffce42bd52ff535b90dcb86
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 0%

---

# 子事件分析

{{release-limited-testing}}

通过子事件分析，可在比事件级别更精细的级别分析事件数据。 您可以对事件中的单个容器进行分段，而不是筛选整个事件。 例如：

- 按特定产品类别进行分段，不包括在同一订单中购买的所有其他产品
- 是否在内容分析数据中对特定资产类别进行分段？
- 在媒体分析数据中对特定媒体渠道进行分段。


在Customer Journey Analytics中，您可以在数据视图中定义要为其使用子事件分析的容器。 如果没有子事件分析，对容器项目属性进行分段将返回事件中的任何项目与容器项目属性匹配的所有事件。 结果是不正确的归因和夸大的收入量度。 子事件分析将过滤器范围限定为事件中的单个项目行，并解决了这些问题。

在子事件分析中，“排除”逻辑的行为与针对容器的标准事件级别排除的行为不同。 在容器中排除项目属性时，区段返回容器中有&#x200B;**项目**&#x200B;但不匹配排除条件的事件。 该区段不会返回不含任何项目的事件。


## 示例

您只想测量专业套件类别的收入。 如果没有子事件分析，应用专业套装细分将包括来自任何订单（事件）上的每项产品的收入，该订单（事件）至少包含一项具有专业套装类别的产品。 通过子事件分析，您可以将该过滤器范围限定为产品级别，并且只返回专业西装类别产品的收入。

您还需要测量除Men类别之外的所有其他类别的在线收入。

>[!BEGINTABS]

>[!TAB 事件分析]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 事件]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等于]** **[!UICONTROL 专业套装]**。

![显示产品类别专业套装的事件级别分段的面板](./assets/product-category-segmentation-events.png)

因此，至少包含一个&#x200B;**[!UICONTROL 专业套装]** **[!UICONTROL product_category]**&#x200B;的所有订单都将被考虑，这些订单中来自其他产品的收入包含在&#x200B;**[!UICONTROL 收入]**&#x200B;量度中。当您报告类别时，报告了&#x200B;**[!UICONTROL product_category]**&#x200B;的所有其他值，这些值属于包含&#x200B;**[!UICONTROL 专业套装]** **[!UICONTROL product_category]**&#x200B;产品的订单。

>[!TAB 子事件分析]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 产品]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等于]** **[!UICONTROL 专业套件]**。

![显示产品类别专业套装子事件级别分段的面板](./assets/product-category-segmentation-subevents.png)

因此，所有至少包含&#x200B;**[!UICONTROL 专业套装]** **[!UICONTROL product_category]**&#x200B;的订单都被考虑在内，并且只有属于&#x200B;**[!UICONTROL 专业套装]** **[!UICONTROL product_categorey]**&#x200B;的产品收入包含在&#x200B;**[!UICONTROL 收入]**&#x200B;指标中。当您报告类别时，仅报告&#x200B;**[!UICONTROL 专业套装]** **[!UICONTROL Rproduct_category]**。

>[!TAB 子事件分析（排除）]

在分段生成器中，或作为&#x200B;**[!UICONTROL 快速区段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 产品]**&#x200B;容器上&#x200B;**[!UICONTROL 排除]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等于]** **[!UICONTROL 专业套装]**。

![显示子点击级别的分段以排除产品类别门槛的面板](./assets/product-category-segmentation-subevents-exclude.png)

要在产品级别排除，应包含至少包含一个产品的事件，然后在该范围内应用子事件级别的排除。 此排除项与事件级别排除项不同，后者排除整个事件。

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
