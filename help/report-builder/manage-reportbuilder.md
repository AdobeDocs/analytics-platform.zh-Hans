---
title: 如何在 Customer Journey Analytics 中使用 Report Builder 管理数据块
description: 描述如何使用 Report Builder 中的管理功能
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: e9856269ee07b7119f75b98489b47e1f35f7cf5f
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# 在 Report Builder 中管理数据块

您可以使用数据块管理器查看和管理工作簿中的所有数据块。数据块管理器提供搜索、过滤和排序功能，可让您快速定位特定数据块。选择一个或多个数据块后，可以对选中的数据块进行编辑、删除或刷新。

![图像](./assets/image52.png)

## 查看数据块

单击&#x200B;**管理**&#x200B;查看工作簿中所有数据块的列表。


![图像](./assets/image53.png)

数据块管理器列出工作簿中存在的所有数据块。 

![图像](./assets/image52.png)

## 对数据块列表进行排序

您可以按显示的列对数据块列表进行排序。例如，您可以按报告包、过滤器、日期范围和其他变量对数据块列表进行排序。

要对数据块列表进行排序，请单击列标题。

![图像](./assets/image54.png)

## 搜索数据块列表

使用搜索字段在数据块表中查找任何内容。 例如，您可以搜索数据块或报告包中包含的指标。 您还可以搜索出现在日期范围、修改日期或上次运行日期列中的日期。

![图像](./assets/image55.png)

## 编辑数据块

您可以编辑应用于一个或多个数据块的数据视图、日期范围或过滤器。

例如，您可以用一个或多个数据块中的新过滤器替换现有过滤器。

1. 选择要更新的数据块。您可以选中顶级复选框以选择所有数据块，也可以选择单个数据块。

   ![图像](./assets/image56.png)

1. 单击编辑图标以显示快速编辑窗口。

   ![图像](./assets/image58.png)

1. 选择过滤器链接以更新数据视图、日期范围或过滤器。

   ![图像](./assets/image59.png)

## 刷新数据块

单击刷新图标可刷新列表中的数据块。

<img src="./assets/refresh-icon.png" width="15%"/>

要验证数据块是否已刷新，请查看刷新状态图标。绿色圆圈中的复选标记 <img src="./assets/refresh-success.png" width="5%"/>表示数据块刷新成功。刷新失败的数据块会显示警告图标 <img src="./assets/refresh-failure.png" width="5%"/>.  这使得识别任何数据块是否有错误变得容易。


![图像](./assets/image512.png)

## 删除数据块

单击垃圾桶图标以删除选定的数据块。

## 分组数据块

您可以使用 **分组** 下拉菜单对数据块进行分组，也可以单击列标题。要按列对数据块进行排序，请单击列标题。要按组对数据块进行分组，请从&#x200B;**分组**&#x200B;下拉菜单中选择组名。例如，下面的屏幕截图显示了按“表”分组的数据块。它显示了按表 1 和 表 2 分组的数据块。这很有用，例如，在过滤器替换用例中。如果您对每个数据块应用了多个过滤器，则创建一个包含您要替换的所有数据块的组会很有帮助。然后，您可以轻松地一次性选择和编辑它们。

![image](./assets/group-data-blocks.png)

## 修改数据块管理器视图

您可以修改在“数据块管理器”窗口中可见的列。


单击列列表 <img src="./assets/image515.png" width="3%"/> 图标以选择在数据块管理器中列出的列。选择一个列名以显示该列。取消选择列名称以从视图中删除该列。

![图片](./assets/image516.png)
