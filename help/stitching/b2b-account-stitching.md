---
title: B2B帐户拼接
description: 了解Customer Journey Analytics中的B2B帐户拼合如何通过帐户信息丰富事件数据集，并支持对B2B数据进行完整的旅程分析。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2: id: d3f42e9e-bb51-4077-a732-358b801d8b29id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 11156e1f2db094595cc3333ccb0b896037da4715
workflow-type: tm+mt
source-wordcount: 1178
ht-degree: 2%

---

# B2B帐户拼接

B2B帐户拼接使用帐户信息丰富了您的事件数据集，并支持在Customer Journey Analytics中对整个客户历程进行完整分析。 当事件缺少帐户ID（Customer Journey Analytics B2B edition需要帐户ID进行摄取）时，帐户拼接将使用您提供的[人员到帐户映射数据集](#prerequisites)自动派生和添加该信息。

如果没有帐户拼合，则在引入期间会丢弃任何不包含帐户ID的事件。 帐户拼接可在每个事件中查找与人员关联的帐户，并在事件被摄取时添加帐户ID以追溯该事件，从而消除此障碍。

>[!NOTE]
>
>在配置功能之前，B2B帐户拼接要求您有权使用环境中的[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)。

帐户拼接对数据集执行以下操作：

* **提升人员身份**：使用身份图将每个事件上的人员ID提升到配置的身份命名空间。
* **添加缺少的帐户信息**：对于包含人员ID的事件，[人员到帐户的映射](#prerequisites)用于派生和添加帐户信息。 有关事件本身的任何帐户信息均用作回退方法。

## 先决条件

在启用B2B帐户拼接之前，请在Adobe Experience Platform中准备以下数据集：

| 数据集 | 必需 | 描述 |
|---|---|---|
| **个人帐户数据集** | 必需 | 至少包含人员ID（具有命名空间）和帐户ID的查找（记录，非时间序列）数据集。 这些ID用于派生人员与帐户的关系映射。 |

>[!IMPORTANT]
>
>**[!UICONTROL 个人对帐户]**&#x200B;数据集中的人员ID字段必须在架构中标记为标识。

## 启用帐户拼接 {#enable-account-stitching}

您可以在连接级别启用和配置B2B帐户拼接，然后对该连接中的单个事件数据集激活帐户拼接。

### 配置B2B拼接设置 {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="配置B2B帐户拼接"
>abstract="选择&#x200B;**[!UICONTROL 打开B2B拼接配置]**&#x200B;以配置B2B帐户拼接。 如果尚未保存连接，则该配置将标记为&#x200B;**[!UICONTROL _未保存的更改_]**。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="人员标识符命名空间"
>abstract="选择您希望将任何人员ID提升到的人员标识符命名空间，例如电子邮件。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="人员到帐户数据集"
>abstract="选择将人员ID映射到帐户ID的查找数据集。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="人员"
>abstract="在数据集中选择包含人员ID的字段。 该字段必须标记为标识，并且不能与&#x200B;**[!UICONTROL 帐户]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="帐户"
>abstract="在数据集中选择包含帐户ID的字段。 该字段不能与&#x200B;**[!UICONTROL 人员]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="开始时间"
>abstract="选择指示人员与帐户关系何时生效的时间戳字段。"
>additional-url=""
additional-url=""


1. 在Customer Journey Analytics中，导航到&#x200B;**[!UICONTROL 连接]**&#x200B;和[创建新连接](/help/connections/create-connection.md#create-a-connection)或[编辑现有连接](/help/connections/create-connection.md#edit-a-connection)。

1. 在&#x200B;**[!UICONTROL 连接设置]**&#x200B;中，将&#x200B;**[!UICONTROL 主ID]**&#x200B;设置为![正在生成](/help/assets/icons/Building.svg) **[!UICONTROL 帐户]**。

1. 选择&#x200B;**[!UICONTROL 打开B2B拼接配置]**。

   ![B2B帐户标题配置](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >以前为未保存的连接配置的B2B拼接配置指示有&#x200B;**[!UICONTROL _未保存的更改_]**。 无法为之前配置的B2B拼接配置修改&#x200B;**[!UICONTROL 可选容器]**。

1. 在&#x200B;**[!UICONTROL B2B拼接配置]**&#x200B;对话框中：

   ![B2B拼接配置](assets/b2b-stitching-configuration.png)

   1. 配置&#x200B;**[!UICONTROL 人员]**&#x200B;部分：

      * 选择您希望将任何人员ID提升到的&#x200B;**[!UICONTROL 人员标识符命名空间]**，例如&#x200B;**[!UICONTROL 电子邮件]**。 此字段为必填字段。

   1. 在&#x200B;**[!UICONTROL Person to Account]**&#x200B;下配置&#x200B;**[!UICONTROL 帐户]**&#x200B;部分。

      | 字段 | 必需 | 描述 |
      |---|:---:|---|
      | **[!UICONTROL 个人到帐户数据集]** | ![必需](/help/assets/icons/Required.svg) | 选择将人员映射到帐户的查找（记录或非时间序列数据集）。 |
      | **[!UICONTROL 人员]** | ![必需](/help/assets/icons/Required.svg) | 在数据集中选择包含人员ID的字段。 该字段必须标记为标识，并且不能与&#x200B;**[!UICONTROL 帐户]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。 |
      | **[!UICONTROL 帐户]** | ![必需](/help/assets/icons/Required.svg) | 在数据集中选择包含帐户ID的字段。 该字段不能与&#x200B;**[!UICONTROL 人员]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。 |
      | **开始时间** | | 选择指示人员与帐户关系何时生效的时间戳字段。 |

      >[!NOTE]
      >
      >如果在加载字段选项时发生错误，下拉菜单将显示为空，并且每个受影响的字段下方会显示一个错误指示符。 请验证您的数据集架构并重试。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以关闭&#x200B;**[!UICONTROL B2B拼接配置]**&#x200B;对话框并返回连接设置。

   1. **[!UICONTROL _未保存的更改_]**&#x200B;指示器显示在&#x200B;**打开B2B拼接配置**&#x200B;按钮旁边，直到您[保存](#save)连接。


### 对事件数据集启用B2B拼合


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="启用人员帐户拼合"
>abstract="如果启用，此数据集将使用B2B帐户拼接。 选择所需的&#x200B;**[!UICONTROL 人员ID]**&#x200B;以根据人员到帐户数据集查找帐户ID。<br/>如果已禁用，此数据集&#x200B;*不会*&#x200B;使用B2B帐户拼接，您必须改为选择所需的&#x200B;**[!UICONTROL 帐户ID]**。"
>additional-url=""
additional-url=""


在连接级别配置B2B拼接后，必须为要拼接的每个事件数据集单独启用B2B帐户拼接。

1. 在连接设置中，选择&#x200B;**[!UICONTROL 添加数据集]**&#x200B;或打开现有事件数据集的设置。<br/>有关详细信息，请参阅[添加数据集](/help/connections/create-connection.md#add-datasets)或[编辑数据集](/help/connections/create-connection.md#edit-a-dataset)。

1. 对于要为其配置B2B帐户拼接的特定事件数据集，请切换&#x200B;**[!UICONTROL 启用人员到帐户的拼接]**。

>[!BEGINTABS]

>[!TAB 于]

当&#x200B;**[!UICONTROL 启用人员到帐户拼接]**&#x200B;为&#x200B;**于**&#x200B;时，您已为数据集配置了B2B帐户拼接。

* 需要配置人员ID。 该人员ID用于根据[人员对帐户数据集](#prerequisites)查找帐户ID。
* 帐户ID的配置是可选的。

![B2B帐户正在拼接](assets/b2b-event-dataset-stitching-on.png)上的事件数据集

>[!TAB 关]

当&#x200B;**[!UICONTROL 启用人员到帐户拼接]**&#x200B;为&#x200B;**关**&#x200B;时，您已&#x200B;*不*&#x200B;为数据集配置了B2B帐户拼接。

* 需要配置帐户ID。
* 人员ID的配置是可选的。

![B2B帐户拼合关闭的事件数据集](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### 保存

配置B2B拼接配置并完成添加或编辑数据集后，选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存连接。

>[!IMPORTANT]
>
>保存连接后，B2B拼接配置将变得不可更改。 要在保存后查看设置，请选择&#x200B;**打开B2B拼接配置**。 所有字段将以只读状态显示。 此外，如果在Experience Platform中删除了用于[人员到帐户映射](#prerequisites)的数据集，则此连接将被删除。

## 数据更新计划

帐户拼接每天从您的[人员到帐户数据集](#prerequisites)中派生标识映射，并使用此信息更新允许按以下计划拼接的数据集：

| 重播 | 频率 | 数据窗口 |
|---|---|---|
| 短期 | 每周 | 最近 7 天 |
| 长期 | 按月 | 最近 3 个月 |

## 隐私和数据卫生

帐户拼接遵循个人身份的标准隐私和卫生请求，与B2C拼接行为一致。 如果之后通过隐私或卫生请求删除了人员ID，则使用身份图执行的关联拼合会被撤销。

通过拼接添加到事件的B2B实体（如帐户ID、帐户ID和全局帐户ID）不会作为隐私或卫生请求的一部分删除。 这些值不包含个人身份信息，因此不存在删除这些值的法律义务。

>[!MORELIKETHIS]
>
>* [拼接概述](overview.md)
>* [配置B2B的连接](../connections/create-connection.md)
>* [有关拼合的常见问题解答](faq.md)

