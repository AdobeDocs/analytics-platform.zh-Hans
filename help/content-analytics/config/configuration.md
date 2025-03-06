---
title: 配置内容分析
description: 有关如何配置内容分析的概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---

# 配置内容分析

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

Content Analytics的配置包括以下步骤：

内容分析的![配置](../assets/aca-configuration.svg)

1. 使用Content Analytics [引导式配置](guided.md)向导引导您完成设置Content Analytics配置的先决条件所需的所有步骤。 您可以保存配置并稍后返回。
1. 在对配置值感到满意后，您可以实施配置。 此实施会根据您在向导中配置的内容，创建所有必需的工件。 创建、更新或选择以下工件：
   * 自定义历程分析
      * 已选择[数据视图](/help/data-views/data-views.md)。
      * 已选择[连接](/help/connections/overview.md)，它自动派生自所选的数据视图。
   * Experience Platform
      * 沙盒已选中，并自动从连接派生。 沙盒中已启用必要的工作流和服务。
      * 在沙盒中选择Content Analytics架构。 如果不可用，则会创建必要的架构。
      * 在沙盒上选定的Content Analytics数据集。 如果不可用，则会创建必要的数据集。
   * 数据收集
      * 在数据流中创建数据流并配置Experience Platform服务以将数据流式传输到Content Analytics体验事件数据集。
      * 创建标记属性时，会将Adobe Content Analytics扩展配置为使用配置向导中的正确沙盒、数据流和其他配置选项。
1. 仅当[手动发布](manual.md)标记属性时，Content Analytics才会有效部署和激活。

1. 您只能使用[引导式配置](guided.md)向导对已实施的配置进行某些有限的更改。 例如，更改[数据视图](/help/data-views/data-views.md)。
1. 您可以通过关联标记属性中的[Adobe Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)对已实施的配置进行其他更改。
1. 仅当[手动重新发布](manual.md) Tag属性时，才能有效部署和激活步骤4和5中的配置修改。


在配置Content Analytics之前，请确保满足以下先决条件：


>[!PREREQUISITES]
>
>* 您已将Content Analytics中使用的功能服务的用户代理和IP地址添加到允许列表。 用户代理字符串为`AdobeFeaturization/1.0`。
>* 您具有Customer Journey Analytics产品管理员角色，该角色具有管理连接和管理数据集合的附加权限。 所需的Experience Platform权限包括：
>  
>   | 类别 | 权限 | 描述 |
>   |---|---|---|
>   | [!UICONTROL 数据收集] | 查看数据流 | 对数据流的只读访问权限。 |
>   | [!UICONTROL 数据收集] | 管理数据流 | 有权读取、创建、编辑和删除数据流。 |
>   | [!UICONTROL 数据建模] | [!UICONTROL 查看架构] | 对架构和相关资源的只读访问权限。 |
>   | [!UICONTROL 数据建模] | [!UICONTROL 管理架构] | 有权读取、创建、编辑和删除架构和相关资源。 |
>   | [!UICONTROL 数据管理] | [!UICONTROL 查看数据集] | 对数据集和架构的只读访问权限。 |
>   | [!UICONTROL 数据管理] | [!UICONTROL 管理数据集] | 有权读取、创建、编辑和删除数据集。 架构的只读访问权限。 |
>   | [!UICONTROL 数据获取] | [!UICONTROL 管理源] | 有权读取、创建、编辑和禁用源。 |
>   | [!UICONTROL Identity Management] | [!UICONTROL 查看身份命名空间] | 对身份命名空间的只读访问。 |
>
>* 您仔细考虑了以下重要配置选项：
>
>   * 您的站点适合体验报告？ 只有在满足以下条件时，才可能生成正确的体验报表：
>   * 网站内容仅由URL驱动。
>   * 您网站上的页面可使用页面URL重现，并且您了解哪些可选URL参数可促进体验。
>* 您已清楚地了解要捕获哪些页面的内容参与分析和见解。
>* 您已清楚地了解要捕获内容参与分析和见解的资产（类型）。
>


>[!MORELIKETHIS]
>
>* [引导式配置](guided.md)
>* [手动配置](manual.md)
>* [访问控制](/help/technotes/access-control.md)
>


