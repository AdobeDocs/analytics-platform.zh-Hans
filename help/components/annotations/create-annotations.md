---
title: 创建注释
description: 如何在工作区中创建注释。
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 24%

---

# 创建注释

默认情况下，只有管理员可以创建注释。 用户有权查看注释，类似于用户查看其他组件的方式（如过滤器、计算量度等）。

但是，管理员可以通过Admin Console向用户授予&#x200B;**[!UICONTROL 编辑CJA Workspace访问权限]**&#x200B;中&#x200B;**[!UICONTROL 报告工具]**&#x200B;的&#x200B;**[!UICONTROL 注释创建]**&#x200B;权限。 有关详细信息，请参阅[用户级访问控制](/help/technotes/access-control.md#user-level-access)。

可通过以下方式创建注释：

![创建注释](assets/create-annotation.png)

* ??在主界面中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;并选择&#x200B;**[!UICONTROL 注释]**。 从[[!UICONTROL 注释]管理器](/help/components/annotations/manage-annotations.md)中选择![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]。
* ??在Workspace项目中，从可视化图表的上下文菜单中，选择&#x200B;**[!UICONTROL 从所选内容创建注释]**。
* ??在Workspace项目中，从折线图的上下文菜单中，选择&#x200B;**[!UICONTROL 注释选定内容]**。
* ??在Workspace项目中，从菜单中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 创建注释]**。
* ??在Workspace项目中，使用快捷键&#x200B;**[!UICONTROL ctrl+shift+o]** (Windows)或&#x200B;**[!UICONTROL shift+command+o]** (macOS)

要定义注释，请使用[[!UICONTROL 注释生成器]](#annotation-builder)：

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 注释生成器 {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="注释详细信息"
>abstract="注释使您能够有效地将上下文数据的细微差别和见解传达给贵组织。 它们可让您将日程表活动与特定维度/量度关联起来。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="范围"
>abstract="您可以利用范围来自定义将要注释的数据。计算量度和区段不会自动继承其定义中使用的组件的注释。您可以将新的计算量度添加到现有注释的范围部分。新的区段需要新的注释。"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 注释生成器]**&#x200B;对话框用于创建新注释或编辑现有注释。 该对话框的标题为&#x200B;**[!UICONTROL 新建批注]**&#x200B;或&#x200B;**[!UICONTROL 编辑批注]**，用于从[[!UICONTROL 批注]管理器](/help/components/annotations/manage-annotations.md)创建或管理的批注。


>[!BEGINTABS]

>[!TAB 注释生成器]

![显示下一节中描述的字段和选项的注释详情窗口。](assets/annotation-builder.png)

>[!TAB 创建/编辑注释]

![显示下一节中描述的字段和选项的注释详情窗口。](assets/create-edit-annotation.png)

>[!ENDTABS]

1. 指定以下详细信息（![必需](/help/assets/icons/Required.svg)为必需）：

   | 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 数据视图]** | 您可以选择注释的数据视图。 您定义的注释可基于选定的数据视图在Workspace项目中作为注释使用。 当您启用[!UICONTROL 应用于所有数据视图]时，此选择被撤销。 |
   | **[!UICONTROL 仅用于项目的注释]** | 一个信息框，用于说明您创建的注释仅在您正在处理的Workspace项目中可见。 启用&#x200B;**[!UICONTROL 使此注释对您的所有项目可用]**，以使该注释对所有项目可见。 仅当您从Workspace项目中创建注释时，此信息框才可见。 |
   | **[!UICONTROL 标题]** ![必填](/help/assets/icons/Required.svg) | 命名注释，例如`Needs further investigation`。 |
   | **[!UICONTROL 描述]** | 提供批注的说明，例如，`We never expected such a fluctuation in numbers.`。 |
   | **[!UICONTROL 标记]** | 通过创建或应用一个或多个标记来组织注释。 开始键入以查找您可以选择的现有标记。 或按&#x200B;**[!UICONTROL Enter]**&#x200B;添加新标记。 选择![CrossSize75](/help/assets/icons/CrossSize75.svg)以删除标记。 |
   | **[!UICONTROL 应用的日期]** ![必需](/help/assets/icons/Required.svg) | 选择要使注释可见的日期或日期范围。 使用快捷方式创建注释时，注释默认为一天的数据范围。 使用可视化图表中的选定内容创建批注时，批注会根据可视化图表所属面板的日期范围默认为数据范围。 |
   | **[!UICONTROL 颜色]** | 将颜色应用于注释。注释以选定的颜色出现在项目中。颜色可用于对注释进行分类，例如公共假日、外部活动、跟踪问题等。 |
   | **[!UICONTROL 范围]** | 从组件面板中拖放触发注释的量度。 例如，人员、会话和事件。 然后，从组件面板中拖放充当过滤器的任何维度或过滤器以确定是否显示注释。 如果不指定范围，注释将应用于您的所有数据。 <br/>您有两个选项：<ul><li>**[!UICONTROL 这些量度中的任意一个都存在]**：拖放最多10个触发注释显示的量度。<br/>例如，收入量度已停止收集特定日期范围的数据。 将收入量度拖动到此框中。</li><li>**[!UICONTROL 使用所有这些筛选器]**：拖放最多10个用于筛选注释是否显示的维度或筛选器。</li></ul><p><p>**注意：**&#x200B;任何应用于组件、随后用作计算指标或筛选器定义的一部分的注释，均不自动继承该注释。 还必须将所需的计算量度添加到范围部分才能显示注释。但是，应为要用相同信息进行注释的任何过滤器创建新的注释。 例如，在特定日期将注释应用于[!UICONTROL 订单]。 然后，在相同日期范围的某个计算指标中使用[!UICONTROL 订单]。新的计算指标不会自动显示订单的注释。 还将计算量度添加到范围部分以便显示该注释。 |
   | **[!UICONTROL 应用于所有数据视图]** | 默认情况下，注释应用于原始数据视图。通过选中此框，您可以在公司内的所有数据视图中应用注释。 |

   {style="table-layout:auto"}

1. 选择
   * **[!UICONTROL 保存]**&#x200B;以保存注释。
   * **[!UICONTROL 另存为]**&#x200B;以保存注释的副本。
   * **[!UICONTROL 删除]**&#x200B;以删除批注。
   * **[!UICONTROL 取消]**&#x200B;以取消对注释所做的任何更改或取消创建新注释。
