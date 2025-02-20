---
title: 配置内容分析
description: 有关如何配置内容分析的概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: cea253d3b1da080e6735989d59cc6eda44afc203
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%

---

# 配置内容分析

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}


要为贵组织配置内容分析，请使用内容分析[引导式配置](guided.md)。 配置向导将指导您完成设置Content Analytics自动配置的先决条件所需的所有步骤。

## 先决条件

在配置Content Analytics之前，请确保满足以下先决条件：

* 您已将Content Analytics中使用的功能服务的用户代理和IP地址添加到允许列表。 用户代理字符串为`AdobeFeaturization/1.0`。
* 您具有Customer Journey Analytics产品管理员角色，该角色具有管理连接和管理数据集合的附加权限。 所需的Experience Platform权限包括：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 数据收集] | 查看数据流 | 对数据流的只读访问权限。 |
  | [!UICONTROL 数据收集] | 管理数据流 | 有权读取、创建、编辑和删除数据流。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 查看架构] | 对架构和相关资源的只读访问权限。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 管理架构] | 有权读取、创建、编辑和删除架构和相关资源。 |
  | [!UICONTROL 数据管理] | [!UICONTROL 查看数据集] | 对数据集和架构的只读访问权限。 |
  | [!UICONTROL 数据管理] | [!UICONTROL 管理数据集] | 有权读取、创建、编辑和删除数据集。 架构的只读访问权限。 |
  | [!UICONTROL 数据获取] | [!UICONTROL 管理源] | 有权读取、创建、编辑和禁用源。 |
  | [!UICONTROL Identity Management] | [!UICONTROL 查看身份命名空间] | 对身份命名空间的只读访问。 |

* 您仔细考虑了以下重要配置选项：

   * 您的站点适合体验报告？ 只有在满足以下条件时，才可能生成正确的体验报表：
      * 网站内容仅由URL驱动。
      * 您网站上的页面可使用页面URL重现，并且您了解哪些可选URL参数可促进体验。
   * 您已清楚地了解要捕获哪些页面的内容参与分析和见解。
   * 您已清楚地了解要捕获内容参与分析和见解的资产（类型）。


>>
[!MORELIKETHIS]
>>
* [访问控制](/help/technotes/access-control.md)
>


