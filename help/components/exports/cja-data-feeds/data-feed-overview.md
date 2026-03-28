---
description: 了解如何使用数据馈送从Customer Journey Analytics中获取原始数据。 了解使用数据馈送的前提条件以及下一步该怎么做。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Analytics 数据馈送概述
feature: Components
hide: true
hidefromtoc: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 50b82943d4c59f612240ffc8d83a8a08f09b8331
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# 数据馈送概述

数据馈送是从Customer Journey Analytics中获取原始数据的有效方法。 此原始数据可在 Adobe 以外的其他平台中使用，具体所用平台由您的组织自行决定。数据在每小时结束时以小时为单位分批发送，或者在每天结束时以天为单位分批发送。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求。

* 包含被摄取到Adobe Customer Journey Analytics中的数据的有效实施。<!-- For more information, see Data ingestion overview - add link -->
* 您的帐户是Analytics产品管理员，或者属于有权访问数据馈送的产品配置文件。<!--???-->
* 在Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS上配置的存储桶。<!--Which cloud providers do we support??-->
* （旧版：仅旧版FTP和SFTP目标类型需要）有可用的FTP站点和凭据（您的组织提供的FTP凭据）。<!--Delete???-->

## 在Customer Journey Analytics和Adobe Analytics中比较数据馈送

Customer Journey Analytics中的数据馈送功能与Adobe Analytics不同。 有关详细信息，请参阅[比较Customer Journey Analytics和Adobe Analytics中的数据馈送](/help/components/exports/cja-data-feeds/df-comparison.md)。


## 后续步骤

以下资源可帮助您了解获取数据馈送的基本工作流。了解基本工作流后，您可以与组织内的团队合作，将原始数据存储或纳入到数据库中。

* 数据馈送最佳实践<!--add link-->：创建和管理数据馈送的最佳实践。
* 创建数据馈送<!--add link-->：有关创建数据馈送的技术详细信息，详细说明了各个字段
* 管理数据馈送<!--add link-->：了解有关导览数据馈送界面的详细信息
* 数据馈送内容<!--add link-->：了解压缩文件中包含的内容
* 数据列定义<!--add link-->：所有可用列的完整列表。

<!-- Is this still the output users can download from the destination? I aske Jun. -->

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在数据馈送界面中导航](https://video.tv.adobe.com/v/3428569?captions=chi_hans&quality=12&learn=on){target="_blank"}，获取演示视频。

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

查看 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [查找您的数据馈送 ID](https://video.tv.adobe.com/v/3418478?captions=chi_hans&quality=12&learn=on){target="_blank"}，获取演示视频。

>[!ENDSHADEBOX]
