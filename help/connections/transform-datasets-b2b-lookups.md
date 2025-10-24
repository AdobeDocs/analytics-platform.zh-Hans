---
title: 转换数据集以进行 B2B 查找
description: 描述如何转换特定B2B查找架构的数据集中的数据
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: d1097ca5f981623283a7d02200d5023548046429
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 4%

---

# 转换数据集以进行 B2B 查找

为了支持对B2B数据（包括客户、机会、营销列表和营销活动）进行基于人员的查找，转换B2B查找数据集可以提高数据准确性。

此转换仅适用于包含B2B查找架构数据的数据集，它基于以下类：

* [XDM业务帐户人员关系](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM业务机会人员关系](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM商业营销列表成员](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM商业营销活动成员](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>每个id最多有10,000个项目。 此限制意味着对于任何给定人员ID，您只能拥有10,000个帐户、10,000个机会、10,000个营销列表或10,000个营销活动。

>[!PREREQUISITES]
>
>要使摄取正常工作，必须验证B2B查找数据集是否已为以下字段（如B2B查找架构中所定义）填充数据：
>
>| 包含符合架构的数据集 | 填充了数据的字段 |
>|---|---|
>| XDM 业务帐户人员关系 | `accountPersonID` |
>| XDM业务机会人员 | `opportunityPersonID` |
>| XDM业务营销列表 | `marketingListMemberID` |
>| XDM 商业营销活动成员 | `campaign.sourceKey` |
>

要为B2B查找数据集启用转换，请执行以下操作：

![启用转换数据集](/help/connections/assets/transform.gif)

* 验证每个数据集的&#x200B;**[!UICONTROL 键]**&#x200B;和&#x200B;**[!UICONTROL 匹配键]**&#x200B;的建议值。 如果更改建议值的值，您将看到要求您继续的警告。 您必须确保：

   * 您为&#x200B;**Key**&#x200B;选择的值基于人员ID数据类型。
   * 您为&#x200B;**匹配键**&#x200B;选择的值被定义为事件数据集的主标识字段。

* 选择用于导入新数据和数据集回填的选项。

* 为B2B查找选择&#x200B;**[!UICONTROL 转换数据集]**。

  此选项会转换数据集，以便在B2B场景下用于基于人员的查找。


  >[!IMPORTANT]
  >
  >打开连接后，如果保存连接，转换将不可逆。 您无法修改键、匹配键和转换数据集配置。 您只能删除、添加然后重新配置数据集。

要为已属于现有连接的一个或多个数据集启用转换：

1. 从连接中删除数据集。
1. 保存连接。
1. 为数据集启用转换时，将数据集添加到连接。

## 背景信息

对于基于上述四个架构类的架构，未转换的数据集可以包含单个人员标识符的多行。 基于人员的查找仅与该人员标识符的最近匹配项，从而无法基于适当的人员ID查找帐户、商机、营销列表或营销活动。

该转换会修改四个架构类（下图中的橙色）中每个架构类的数据集，以便为每个人员标识符在查找数据集（下图中的粉红色）中的相关数据（帐户、机会、营销列表或营销活动）创建（对象）数组。 此转换允许正确使用基于人员ID的查找。

![B2B架构](./assets/b2b-schemas.svg)
