---
title: 转换数据集以进行B2B查找
description: 描述如何转换特定B2B查找架构的数据集中的数据
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: eef9b420f1016254dece0a916b82bc99e2ca866e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# 转换数据集以进行B2B查找

要支持对B2B数据（包括客户、机会、营销列表和营销活动）进行基于人员的查找，需要转换B2B查找数据集。

此转换仅适用于包含B2B查找架构数据的数据集，它基于以下类：

* [XDM业务帐户人员关系](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM业务机会人员关系](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM商业营销列表成员](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM商业营销活动成员](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>每个id最多有10,000个项目。 此限制意味着对于任何给定人员ID，您只能拥有10,000个帐户、10,000个机会、10,000个营销列表或10,000个营销活动。


要为此类数据集启用转换，请执行以下操作：

![启用转换数据集](assets/transform-dataset.gif)

* 请确保为&#x200B;**[!UICONTROL 键]**&#x200B;和&#x200B;**[!UICONTROL 匹配键]**&#x200B;选择正确的标识符，例如`personKey.sourceKey`。

* 选择用于导入新数据和数据集回填的选项。

* 为B2B查找选择&#x200B;**[!UICONTROL 转换数据集]**。

  此选项会转换数据集，以便在B2B场景下用于基于人员的查找。


  >[!IMPORTANT]
  >
  >打开连接后，如果保存连接，转换将不可逆。 保存连接后，您无法修改数据集的转换设置，除非删除该数据集并将其再次添加到连接中。

要为已属于现有连接的一个或多个数据集启用转换：

1. 从连接中删除数据集。
1. 保存连接。
1. 为数据集启用转换时，将数据集添加到连接。

## 背景信息

对于基于上述四个架构类的架构，未转换的数据集可以包含单个人员标识符的多行。 基于人员的查找仅与该人员标识符的最近匹配项，从而无法基于适当的人员ID查找帐户、商机、营销列表或营销活动。

该转换会修改四个架构类（下图中的橙色）中每个架构类的数据集，以便为每个人员标识符在查找数据集（下图中的粉红色）中的相关数据（帐户、机会、营销列表或营销活动）创建（对象）数组。 此转换允许正确使用基于人员ID的查找。

![B2B架构](./assets/b2b-schemas.svg)
