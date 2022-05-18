---
title: 如何在Customer Journey Analytics中使用Report Builder管理数据块
description: 介绍如何在Report Builder中使用管理功能
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 01a9ff4e03e002da723c10500de6dec4444f951e
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---


# 在Report Builder中管理数据块

您可以使用数据块管理器查看和管理工作簿中的所有数据块。 数据块管理器提供搜索、过滤和排序功能，使您能够快速找到特定数据块。 选择一个或多个数据块后，您可以编辑、删除或刷新选定的数据块。

![image](./assets/image52.png)

## 查看数据块

单击 **管理** 查看工作簿中所有数据块的列表。


![图像](./assets/image53.png)

数据块管理器列出了工作簿中存在的所有数据块。 

![图像](./assets/image52.png)

## 对数据块列表进行排序

您可以按显示的列对数据阻止列表进行排序。 例如，您可以按报表包、过滤器、日期范围和其他变量对数据阻止列表进行排序。

要对数据阻止列表进行排序，请单击列标题。

![图像](./assets/image54.png)

## 搜索数据阻止列表

使用搜索字段查找数据块表中的任何内容。 例如，您可以搜索数据块或报表包中包含的量度。 您还可以搜索在日期范围、修改日期或上次运行日期列中显示的日期。

![图像](./assets/image55.png)

## 编辑数据块

您可以编辑数据视图、日期范围或应用于一个或多个数据块的过滤器。

例如，您可以在一个或多个数据块中将现有过滤器替换为新过滤器。

1. 选择要更新的数据块。

您可以选择顶级复选框以选择所有数据块，也可以选择单个数据块。

![图像](./assets/image56.png)

1. 单击编辑图标以显示“快速编辑”窗口。

![图像](./assets/image58.png)

1. 选择过滤器链接以更新数据视图、日期范围或过滤器。

![图像](./assets/image59.png)

## 刷新数据块

单击刷新图标可刷新列表中的数据块。

<img src="./assets/refresh-icon.png" width="15%"/>

要验证是否刷新了数据块，请查看刷新状态图标。 绿色圆圈中的复选标记 <img src="./assets/refresh-success.png" width="5%"/> 表示数据块刷新成功。 刷新失败的数据块将显示警告图标 <img src="./assets/refresh-failure.png" width="5%"/>.  这样便于识别是否有数据块出错。


![图像](./assets/image512.png)

## 删除数据块

单击垃圾桶图标以删除选定的数据块。

## 组数据块

单击列标题可对数据块进行分组，或从 **分组依据** *名称* 列表。

![图像](./assets/image514.png)

## 修改数据块管理器视图

您可以修改在“数据块管理器”窗口中显示的列。


单击列列表 <img src="./assets/image515.png" width="3%"/> 图标，以选择数据块管理器中列出的列。 选择列名称以显示列。 取消选择列名称可从视图中删除列。

![iamge](./assets/image516.png)
