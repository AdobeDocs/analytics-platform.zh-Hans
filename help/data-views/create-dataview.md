---
title: 创建数据视图
description: 您可以调整以创建或编辑数据视图的所有设置。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 81%

---

# 创建数据视图

创建数据视图涉及根据架构元素创建量度和维度或利用标准组件。大多数架构元素可以是维度或量度，具体取决于您企业的要求。 将架构元素拖动到数据视图后，右侧会显示相应选项，您可以在其中调整维度或量度在CJA中的操作方式。

## 配置数据视图数值和容器

1. 在 Customer Journey Analytics 中，转到&#x200B;**[!UICONTROL 数据视图]**&#x200B;选项卡。
2. 单击&#x200B;**[!UICONTROL 添加]**&#x200B;以创建新数据视图，并配置其设置。

![新建数据视图](assets/new-data-view.png)

| 设置 | 描述/用例 |
| --- | --- |
| [!UICONTROL 连接] | 此字段会将数据视图链接到您之前已建立的连接，其中包含一个或多个 Adobe Experience Platform 数据集。 |
| [!UICONTROL 名称] | 必须为数据视图命名。 |
| [!UICONTROL 描述] | 不强制要求提供详细描述，但建议提供。 |
| [!UICONTROL 时区] | 选择您要在哪个时区中显示您的数据。 |
| [!UICONTROL 标记] | [!UICONTROL 标记让您可以将数据视图组织成不同的类别。] |
| [!UICONTROL 容器] | 您可以在此重命名您的容器，以确定它们在基于此数据视图的任何 Workspace 项目中如何显示。[!UICONTROL 容器]用在筛选器和流失/流量等场合，以定义范围或上下文的宽窄。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=zh-Hans#filter-containers) |
| [!UICONTROL 人员容器名称是…] | [!UICONTROL 人员]（默认）。[!UICONTROL 人员]容器包含指定时间段内访客的每次访问和页面查看。您可以将此容器重命名为“用户”或您喜欢的任何其他名称。 |
| [!UICONTROL 会话容器名称是…] | [!UICONTROL 会话]（默认）。通过[!UICONTROL 会话]容器可以识别页面交互、促销活动或特定会话的转化。您可以将此容器重命名为“访问”或您喜欢的任何其他名称。 |
| [!UICONTROL 事件容器名称是…] | [!UICONTROL 事件]（默认）。[!UICONTROL 事件]容器定义要在筛选器中包含或排除的页面事件。 |

接下来，您可以根据架构元素创建量度和维度。您也可以使用标准组件。

## 根据架构元素创建量度和维度

1. 在 [!UICONTROL Customer Journey Analytics] > [!UICONTROL 数据视图]中，单击[!UICONTROL 组件]选项卡。

![“组件”选项卡](assets/components-tab.png)

您可以在左上角看到[!UICONTROL 连接]，其中包含数据集及其下方的[!UICONTROL 架构字段]。请记住以下事项：

* 已添加的组件是所需的标准组件（系统生成的）。
* 默认情况下，Adobe 应用&#x200B;**[!UICONTROL 包含数据]**&#x200B;筛选器，因此只有包含数据的架构字段会出现。如果您要查找不包含数据的字段，则删除该筛选器。

1. 下面，将架构字段（例如 [!UICONTROL pageTitle]）从左边栏拖入“量度”或“维度”部分中。

   您可以将同一架构字段拖入“量度”或“维度”部分中多次，并以不同方式配置同一维度或量度。
例如，从 **[!UICONTROL pageTitle]** 字段中，您可以通过重命名右侧的&#x200B;**[!UICONTROL 组件名称]**&#x200B;来创建一个名为“产品页面”的维度以及另一个“错误页面”等。从 **[!UICONTROL pageTitle]** 字段中，您还可以根据字符串值创建量度。例如，您可以创建一个或多个&#x200B;**[!UICONTROL 订单]**&#x200B;量度，其中包含不同的归因设置和不同的添加/排除值。

   ![选项卡3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >您可以从左边栏拖入整个架构字段文件夹，这些文件夹会自动分类为传统部分。 字符串字段最终位于[!UICONTROL Dimension]部分，而数字位于[!UICONTROL 量度]部分。 或者，您也可以单击&#x200B;**[!UICONTROL 添加所有]**，并添加所有架构字段。

1. 选择相应组件后，您会在右侧看到许多设置。使用下述设置配置该组件。

## 使用[!UICONTROL 复制]功能

复制量度或维度，然后修改特定设置，这是从单个架构字段创建多个量度或维度的简单方法。在右上角该量度或维度的名称下选择[!UICONTROL 复制]设置。然后修改新的量度或维度，并将其保存在一个描述更贴切的名称下。

![复制](assets/duplicate.png)

## 筛选架构字段和维度/量度

您可以按以下数据类型筛选左边栏中的架构字段：

![过滤器字段](assets/filter-fields.png)

您还可以按数据集筛选，以及按某个架构字段是否包含数据或是否为标识筛选。默认情况下，我们会对所有数据视图应用&#x200B;**[!UICONTROL 包含数据]**&#x200B;筛选器。

![筛选其他](assets/filter-other.png)

## 向数据视图添加全局过滤器

您可以添加应用于整个数据视图的过滤器。 此过滤器适用于您在工作区中运行的任何报表。

1. 单击[!UICONTROL 数据视图]中的[!UICONTROL 设置]选项卡。
1. 将筛选器从左边栏中的列表拖到[!UICONTROL 添加筛选器]字段。
