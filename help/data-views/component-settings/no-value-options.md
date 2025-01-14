---
title: 无值选项组件设置
description: 决定如果维度为空该如何处理该维度。
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 93%

---

# 无值选项组件设置 {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="无值选项"
>abstract="配置当维度中无值存在时的默认行为。"

<!-- markdownlint-enable MD034 -->


通过无值选项，可决定 Analysis Workspace 如何处理数据集中的事件包含指标，但维度不包含值的情况。可选择此维度项的名称，完全隐藏它，甚至可将其视为实际值。

![无值选项](../assets/no-value-options.png)

## 设置 {#settings}

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 如果显示，则将“无值”称为] | 一个文本字段，通过它，可将&#x200B;**[!UICONTROL 无值]**&#x200B;维度项重命名为其他名称。 |
| [!UICONTROL 默认不显示“无值”] | 不在报表中显示此值。与此维度无关的指标在报表中不可见。 |
| [!UICONTROL 默认显示“无值”] | 在报表中显示此值。 |
| [!UICONTROL 将“无值”视为值] | 将数据中的空白值替换为您在[!UICONTROL 如果显示，则将“无值”称为]下指定的文本。例如，如果以“移动设备类型”作为维度，则可将&#x200B;**[!UICONTROL 无值]**&#x200B;项重命名为“桌面”。将此字段更改为自定义值时，将该自定义值视为合法的字符串值。因此，如果将“Red”值输入到此字段中，则字符串“Red”在数据自身中存在的任何实例均滚入您已指定的同一行项下方。 |

{style="table-layout:auto"}

## 博客帖子

以下是一篇关于[在Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339)中处理“无值”的相关博客文章。
