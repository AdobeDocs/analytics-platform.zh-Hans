---
description: Analysis Workspace 中的数据词典允许用户对 Analysis Workspace 中的各种组件进行编目和跟踪，包括组件的预期用途、批准情况、重复情况等等。
title: 数据词典概述
feature: Components
role: User, Admin
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 90%

---

# 数据词典概述

{{release-limited-testing}}

Analysis Workspace 中的数据词典可帮助用户和管理员跟踪并更好地了解其 Analytics 环境中的组件。

Analytics 管理员负责整理有关数据词典中每个组件的信息，并将其提供给用户。

## 对用户的好处

数据词典帮助用户更好地了解他们可用的每个组件。

数据词典中可用的信息包括：

* 组件的功能和预期用途

* 通常与您正在查看的组件一起使用的组件

* 与您正在查看的组件相似的组件

* 组件是否经系统管理员批准

有关如何访问数据字典及其包含的信息的详细信息，请参阅[查看数据词典中的组件信息](/help/components/data-dictionary/view-data-dictionary.md)。

## 对管理员的好处

数据词典帮助系统管理员跟踪和管理其 Analytics 环境中的组件。

以下是 Analytics 管理员可以使用数据词典的一些方式：

* 识别需要合并的重复组件。

* 识别未收集任何数据的组件，以便更新或删除它们。

* 确定尚未批准的组件。

* 直接在 Analysis Workspace 中更新组件描述。对数据词典中组件描述所做的任何更新都会反映在报告包中。

   同样，对报告包中组件描述所做的任何更新都会反映在 Analysis Workspace 中。

   有关在 Analysis Workspace 或报告包中添加组件描述的更多信息，请参阅[添加组件描述](/help/components/add-component-descriptions.md)。

## 访问数据词典

您可以在 Analysis Workspace 中通过以下任何方式访问数据词典：

* 来自左边栏中的&#x200B;**数据词典**&#x200B;图标。

   ![来自左边栏中的“数据词典”图标](assets/data-dictionary-access-icon.png)

* 来自组件信息弹出框内的&#x200B;**数据词典**&#x200B;图标。

   ![信息弹出窗口中的“数据词典”图标](assets/data-dictionary-access-infopopover.png)
   <!--update screenshot; this was taken from a mock-->

* 从菜单：[!UICONTROL **帮助**] > [!UICONTROL **数据词典**]。

有关数据词典中提供的不同选项的详细信息，请参阅[查看数据词典中的组件信息](/help/components/data-dictionary/view-data-dictionary.md)。

## 更新和整理数据词典

Customer Journey Analytics管理员负责为其组织维护健康的数据字典，如中所述 [监测数据字典运行状况](/help/components/data-dictionary/monitor-data-dictionary-health.md).

在此过程中，CJA管理员可以编辑数据字典中有关每个组件的信息，如中所述 [编辑数据字典中的组件条目](/help/components/data-dictionary/edit-entries-data-dictionary.md).

## 移动、最小化或关闭数据词典

当您打开数据词典时（如[访问数据词典](#access-the-data-dictionary)中所述），它显示为 Analysis Workspace 顶部的一个窗口。

您可以通过以下任何方式操作“数据词典”窗口：

* 将其拖动到 Analysis Workspace 中的任何区域

   如果您关闭并重新打开 Analysis Workspace，“数据词典”窗口将保留在您上次移动它的位置上。<!--True?-->

* 将其最小化

   最小化时，数据词典在 Analysis Workspace 的右下角显示为蓝色选项卡。

   当您选择蓝色选项卡时，数据词典将打开您最近查看的组件。

* 将其关闭
