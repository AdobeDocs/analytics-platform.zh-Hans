---
title: 无值选项组件设置
description: 决定如果维度为空该如何处理该维度。
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 1a696662f10fddd42f3bbdbb79a6e735bf203bdf
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 53%

---

# 无值选项组件设置 {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="无值选项"
>abstract="配置当维度中无值存在时的默认行为。"

<!-- markdownlint-enable MD034 -->


[!UICONTROL 无值选项]允许您确定Analysis Workspace如何处理数据集中的事件包含量度但维度不包含值的情况。 可选择此维度项的名称，完全隐藏它，甚至可将其视为实际值。

![无值选项](../assets/no-value-options.png)

## 设置 {#settings}

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 如果显示，则将“无值”称为]** | 一个文本字段，通过它，可将&#x200B;**[!UICONTROL 无值]**&#x200B;维度项重命名为其他名称。 |
| **[!UICONTROL 默认情况下不显示“无值”]** | 不在报表中显示此值。与此维度无关的指标在报表中不可见。 |
| **[!UICONTROL 默认显示“无值”]** | 在报表中显示此值。 |
| **[!UICONTROL 将“没有值”视为值]** | （数字维度不支持）将数据中的空白值替换为您在[!UICONTROL 下指定的文本如果显示，则将“无值”称为]。 例如，如果以“移动设备类型”作为维度，则可将&#x200B;**[!UICONTROL 无值]**&#x200B;项重命名为“桌面”。将此字段更改为自定义值时，将该自定义值视为合法的字符串值。因此，如果将“Red”值输入到此字段中，则字符串“Red”在数据自身中存在的任何实例均滚入您已指定的同一行项下方。 |

## 数值维度支持“无值” {#numeric}

使用数值作为维度时，您可以

* 在数据视图中配置“无值”选项。 请注意，除&#x200B;**[!UICONTROL 将“没有值”视为值]**&#x200B;外，上述所有配置设置均受支持。
* 在Workspace的自由格式表中，对数值维度使用&#x200B;**[!UICONTROL 包括“没有值”]**。
* 在筛选器生成器中，使用具有数值维度的&#x200B;**[!UICONTROL 存在]**&#x200B;或&#x200B;**[!UICONTROL 不存在]**&#x200B;运算符。


>[!MORELIKETHIS]
>
>以下是一篇关于[在Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339)中处理“无值”的相关博客文章。

