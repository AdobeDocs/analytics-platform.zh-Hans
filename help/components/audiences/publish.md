---
title: 创建受众并将其发布到实时客户资料
description: 了解如何从Customer Journey Analytics发布受众
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# 创建和发布受众

本主题讨论如何将在Customer Journey Analytics(CJA)中发现的受众发布到 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=cn) ，用于客户定位和个性化。

## 创建受众

1. 要创建受众，您可以通过三种方式开始操作：

   | 创建方法 | 详细信息 |
   | --- | --- |
   | 从 **[!UICONTROL 组件] > [!UICONTROL 受众]** | 此时将打开“受众管理器”页面。 单击 **[!UICONTROL 创建受众]** 和 [!UICONTROL 受众生成器] 打开。 |
   | 从自由格式表中 | 右键单击自由格式表中的项目，然后选择 **[!UICONTROL 从选定范围中创建受众]**. 使用此方法可使用您在表格中选择的维度或维度项目预填充过滤器。 |
   | 在过滤器编辑UI中 | 选中显示 **[!UICONTROL 从此过滤器创建受众]**. 使用此方法可预填充过滤器。 |

   {style=&quot;table-layout:auto&quot;}

1. 配置受众。

   | 设置 | 描述 |
   | --- | --- |
   | [!UICONTROL 名称] | 受众的名称。 |
   | [!UICONTROL 标记] | 您希望为组织目的分配给受众的任何标记。 您可以使用预先存在的标记或输入新标记。 |
   | [!UICONTROL 描述] | 添加对受众的良好描述，以便将其与其他受众区分开来。 |
   | [!UICONTROL 刷新频率] | 要刷新受众的频率。<ul><li>您可以选择创建一次性受众（默认），该受众无需刷新，例如，这将有助于创建特定的一次性营销活动。</li><li>您可以选择其他刷新间隔。 对于4小时频率，受众数量限制为150个，因为此刷新率非常需要处理。 对于其他间隔，没有最大受众数。</li></ul> |
   | 过期日期 | 受众将停止刷新的时间。 默认为自创建日期起1年。 |
   | 刷新回顾时段 | 指定创建此受众时要在数据窗口中返回的距离。 最大值。 90天。 过期受众的处理方式与过期的计划报表类似 — 管理员会在计划过期前一个月收到一封电子邮件。 |
   | [!UICONTROL 一次性日期范围] | 希望发布一次性受众的日期范围。 |
   | [!UICONTROL 过滤器] | 过滤器是受众的主要输入。 您最多可以添加20个过滤器。 这些过滤器可以使用 `And` 或 `Or` 运算符。 |

   {style=&quot;table-layout:auto&quot;}

1. 解释数据预览。

   受众预览将显示在右边栏中。

   | 预览设置 | 描述 |
   | --- | --- |
   | 数据预览窗口 | 受众的日期范围。 |
   | 受众总人数 | 一个总数可高达1亿。 |
   | 受众规模限制 | 显示此受众的1亿限制还有多远。 |
   | 预计的受众返回 |  |
   | 预计的返回 | 概要数字…… |
   | 预览量度 |  |

   {style=&quot;table-layout:auto&quot;}


