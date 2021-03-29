---
title: Customer Journey Analytics中数据视图的用例
description: 在Customer Journey Analytics中展示数据视图的灵活性和强大功能的多种用例
translation-type: tm+mt
source-git-commit: 7db2474bf3cd16863c597295399a262c328172dc
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 0%

---


# 数据视图使用案例

Adobe

## 从pageTitle（字符串）模式字段创建订单量度

例如，在创建视图时，您可以从作为字符串的[!UICONTROL pageTitle]模式字段创建[!UICONTROL Orders]量度。 以下是步骤：

1. 在“组件”选项卡上，将[!UICONTROL pageTitle]拖到[!UICONTROL 包含的组件]下的[!UICONTROL Metrics]部分。
   ![](assets/use-case1a.png)
1. 现在，突出显示您刚拖入的量度，并将其重命名在右侧[!UICONTROL 组件设置]下：
   ![](assets/orders.png)
1. 打开右侧的[!UICONTROL 包含/排除值]对话框，并指定以下内容：
   ![](assets/orders2.png)

   “确认”短语表示这是订单。 在查看所有符合这些条件的页面标题后，将对每个实例计为“1”。 结果是新量度（而非计算量度）。 它可与Attribution IQ、过滤器及其他您可以使用标准量度的地方配合使用。
1. 您可以进一步指定此量度的归因模型，如[!UICONTROL 上次触摸]，并且[!UICONTROL 会话]的[!UICONTROL 回顾窗口]。
您还可以从同一字段创建另一个[!UICONTROL Orders]量度，并为它指定不同的归因模型，如[!UICONTROL First Touch]和不同的[!UICONTROL 回顾窗口]，如[!UICONTROL 30天]。

## 从一个模式字段创建多个维

## 使用整数作为维

34点

包括分摊