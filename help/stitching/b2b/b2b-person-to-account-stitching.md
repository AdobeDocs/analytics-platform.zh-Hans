---
title: B2B人员与帐户拼接
description: 了解Customer Journey Analytics中的“B2B人员到帐户”拼合如何通过帐户信息丰富事件数据集，并支持对B2B数据进行完整的旅程分析。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: e3936b74ba4b4cf23e1b7235e545091a8cb546ed
workflow-type: tm+mt
source-wordcount: 2116
ht-degree: 19%

---

# B2B人员与帐户拼接

B2B帐户拼接使用帐户身份丰富了您的事件数据集，并支持在Customer Journey Analytics中跨整个客户历程进行完整分析。 当事件缺少帐户ID（Customer Journey Analytics B2B edition摄取时需要帐户ID）时，人员与帐户拼接将使用您提供的[人员与帐户映射数据集](#prerequisites)自动派生和添加该信息。

如果没有人员来拼接帐户，则任何不包含帐户ID的事件将在引入期间被丢弃。 人员与帐户拼合通过查找与每个事件中的人员关联的帐户来解决此限制，在事件被摄取时添加帐户ID并且追溯。

>[!NOTE]
>
>B2B帐户拼接人员要求您有权在环境中使用[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)，然后才能配置功能。

人员与帐户拼接对数据集执行以下操作：

* **提升人员标识**：与[B2C拼接方法](/help/stitching/overview.md)类似，您将配置一个包含永久人员ID的字段。 使用身份图，每个事件上的永久人员ID均从配置的人员标识符命名空间提升为人员ID。
* **添加缺少的帐户标识**：获取事件的人员ID信息后，[人员到帐户的映射](#prerequisites)用于派生和添加帐户标识信息。 事件本身的任何可用帐户标识均用作回退方法。

## B2B人员与帐户如何拼合

为了说明B2B人员与帐户之间的拼接如何工作，下面显示的数据集用作起点。

### 基本事件数据集

在Customer Journey Analytics B2B edition中，忽略此非拼接示例事件数据集中没有帐户ID的事件，并且不摄取(![DeleteOutline](/help/assets/icons/DeleteOutline.svg))。

| 操作 | 时间戳 | 持久 ID | 帐户 ID | 人员 ID | 事件类型 |
|:---:|--:|--|---|---|---|
| ![数据添加](/help/assets/icons/DataAdd.svg) | 1/3/25 | 1234 | Adobe | matt@adobe.com | Page view |
| ![筛选删除](/help/assets/icons/DeleteOutline.svg) | 1/3/25 | 5678 |  | | |
| ![数据添加](/help/assets/icons/DataAdd.svg) | 3/4/25 | 9012 | 普遍性 | cory@sky.com |  |
| ![数据添加](/help/assets/icons/DataAdd.svg) | 3/7/25 | 4321 | Sky | emily@sky.com | 呼叫中心 |
| ![筛选删除](/help/assets/icons/DeleteOutline.svg) | 5/5/25 | 6106 | | carmen@adobe.com |  |
| ![数据添加](/help/assets/icons/DataAdd.svg) | 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | |
| ![筛选删除](/help/assets/icons/DeleteOutline.svg) | 6/2/25 | 1111 |  | | |

B2B人员与帐户拼合使用以下操作可防止忽略且不摄取事件：

* [提升人员身份](#elevate-person-identities)。
* [添加缺少的帐户身份](#add-missing-account-identitiers)。


### 提升人员身份

+++ 详细信息

为了支持B2B人员与帐户拼接，您可以提供人员与帐户映射数据集。 例如：

| CRM ID | 帐户 ID |
|---|---|
| 12hsd123 | Adobe |
| f82jsd32 | Sky |
| hg2023m2 | Sky |
| b978bbw9 | 普遍性 |
| fs453ghi | Adobe |

使用基于图形的拼合来提升该人员到帐户的映射数据集。 例如，您提供电子邮件作为要使用的命名空间。 结果是更新了人员ID较高的人员 — 帐户映射数据集。

| CRM ID | 提升的人员ID | 帐户 ID |
|---|---|---|
| 12hsd123 | matt@adobe.com | Adobe |
| f82jsd32 | emily@sky.com | Sky |
| hg2023m2 | cory@sky.com | Sky |
| b978bbw9 | cassidy@ubiquity.com | 普遍性 |
| fs453ghi | carmen@adobe.com | Adobe |

基于图形的拼接还用于提升体验事件数据集中的人员ID。 例如，查看&#x200B;**emily@adobe.com**&#x200B;的更新值。

基于图形的拼接还用于提升体验事件数据集中的人员ID。 例如，将永久ID (ECID)字段配置为在[启用数据集](#enable-b2b-person-to-account-stitching-on-event-datasets)上的拼合时用作永久人员ID。 基于`5678`作为ECID值，`emily@adobe.com`作为电子邮件值，`emily@adobe.com`在相关事件中设置为提升的人员ID。

| 时间戳 | 持久 ID | 原始帐户ID | 原始人员ID | 提升的人员ID |
|--|--|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | matt@adobe.com |
| 1/3/25 | 5678 |  | | **emily@adobe.com** |
| 3/4/25 | 9012 | 普遍性 | cory@sky.com | cory@sky.com |
| 3/7/25 | 4321 | Sky | emily@sky.com | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | carmen@adobe.com |
| 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 111 | 111 |


+++

### 添加缺少的帐户标识符

+++ 详细信息

人员到帐户数据集可再次用于提升体验事件数据集中的帐户ID。 例如，查看emily@sky.com的添加值&#x200B;**Sky**&#x200B;和carmen@adobe.com的&#x200B;**Adobe**。 以及cory@sky.com的更新值&#x200B;**Sky**（来自Ubiquity）。

| 时间戳 | 持久 ID | 原始帐户ID | 原始人员ID | 提升的帐户ID | 提升的人员ID |
|---|---|---|---|---|---|
| 1/3/25 | 1234 | Adobe | matt@adobe.com | Adobe | matt@adobe.com |
| 1/3/25 | 5678 | | | **天空** | **emily@sky.com** |
| 3/4/25 | 9012 | 普遍性 | cory@sky.com | **天空** | cory@sky.com |
| 3/7/25 | 4321 | Sky | emily@sky.com | Sky | emily@sky.com |
| 5/5/25 | 6106 | | carmen@adobe.com | **Adobe** | carmen@adobe.com |
| 6/1/25 | 8989 | 普遍性 | cassidy@ubiquity.com | 普遍性 | cassidy@ubiquity.com |
| 6/2/25 | 1111 |  | 1111 |  | 1111 |

+++

### 结果

此示例显示了B2B人员到帐户的拼合如何根据您作为输入提供的人员到帐户映射数据集，使用缺失的人员标识符或缺失且不正确的帐户标识符更新您的体验事件数据。


## 先决条件

在启用B2B人员帐户拼接之前，请在Adobe Experience Platform中准备以下数据集：

| 数据集 | 必需 | 描述 |
|---|---|---|
| **个人帐户数据集** | 必需 | 至少包含人员ID（具有命名空间）和帐户ID的查找（记录，非时间序列）数据集。 这些ID用于派生人员与帐户的关系映射。 |

>[!IMPORTANT]
>
>**[!UICONTROL 个人对帐户]**&#x200B;数据集中的人员ID字段必须在架构中标记为标识。

## 启用人员到帐户拼接 {#enable-account-stitching}

您首先需要在连接级别启用和配置B2B拼接。 当为连接配置B2B拼接时，您可以激活“人员”以考虑对该连接中的单个事件数据集进行拼接。

### 将B2B人员配置为帐户拼接设置 {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="配置B2B拼接"
>abstract="选择&#x200B;**[!UICONTROL 打开B2B拼接配置]**&#x200B;以将B2B人员与帐户拼接进行配置。 如果连接尚未保存，该配置会标记为&#x200B;**[!UICONTROL _未保存的更改_]**。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="人员标识符命名空间"
>abstract="为您的报告选择最相关的人员身份标识命名空间。 例如，电子邮件。 任何启用了&#x200B;**[!UICONTROL 人员到帐户拼接]**&#x200B;的事件数据集都会将永久人员ID提升到此人员标识符命名空间。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="人员到帐户数据集"
>abstract="选择用于将人员 ID 映射到帐户 ID 的查找数据集。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="人员 ID"
>abstract="选择数据集中包含人员 ID 的字段。 此字段的命名空间可以与选定的人员标识符命名空间不同或相同。 如果两者不同，就需要在身份标识图中将这两个命名空间关联在一起。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="帐户 ID"
>abstract="选择数据集中包含唯一帐户标识符值的字段。 启用了&#x200B;**[!UICONTROL “人员到帐户”拼接]**&#x200B;的任何事件数据集的行中都会提供帐户 ID 信息。"

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="开始时间"
>abstract="选择一个时间戳字段，用于指示人员到帐户关系何时生效。"


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_mapping_creation_time"
>title="映射创建时间"
>abstract="或者，也可以选择“人员到帐户”映射的创建日期和时间的字段。 适合某个人在一段时间内切换多个帐户的情况。"


1. 在Customer Journey Analytics中，导航到&#x200B;**[!UICONTROL 连接]**&#x200B;和[创建新连接](/help/connections/create-connection.md#create-a-connection)。

1. 在&#x200B;**[!UICONTROL 连接设置]**&#x200B;中，将&#x200B;**[!UICONTROL 主ID]**&#x200B;设置为![正在生成](/help/assets/icons/Building.svg) **[!UICONTROL 帐户]**。

1. 请确保选择要在B2B连接中使用的&#x200B;**[!UICONTROL 可选容器]**。 将B2B人员保存到帐户拼接配置后，就无法修改这些容器的选择。

1. 选择&#x200B;**[!UICONTROL 打开B2B拼接配置]**。

   ![B2B帐户标题配置](../assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >以前配置的B2B人员帐户拼接未保存连接的配置指示有&#x200B;**[!UICONTROL _未保存的更改_]**。 您不能将以前配置的B2B人员的&#x200B;**[!UICONTROL 可选容器]**&#x200B;修改为帐户拼接配置。

1. 在&#x200B;**[!UICONTROL B2B拼接配置]**&#x200B;对话框中：

   ![B2B人员到帐户拼接配置](../assets/b2b-stitching-configuration.png)

   1. 配置&#x200B;**[!UICONTROL 人员]**&#x200B;部分：

      * 为您的报表选择最相关的人员身份命名空间，如电子邮件。 任何启用了人员到帐户拼合的事件数据集都会将永久人员ID提升到此人员标识符命名空间。 此字段为必填字段。

   1. 在&#x200B;**[!UICONTROL Person to Account]**&#x200B;下配置&#x200B;**[!UICONTROL 帐户]**&#x200B;部分。

      | 字段 | 必需 | 描述 |
      |---|:---:|---|
      | **[!UICONTROL 个人到帐户数据集]** | ![必需](/help/assets/icons/Required.svg) | 选择将人员映射到帐户的查找（记录或非时间序列数据集）。 |
      | **[!UICONTROL 人员 ID]** | ![必需](/help/assets/icons/Required.svg) | 选择数据集中包含人员 ID 的字段。 该字段必须标记为标识，并且不能与&#x200B;**[!UICONTROL 帐户ID]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。 |
      | **[!UICONTROL 帐户 ID]** | ![必需](/help/assets/icons/Required.svg) | 选择数据集中包含帐户 ID 的字段。 该字段不能与&#x200B;**[!UICONTROL 人员ID]**&#x200B;字段或&#x200B;**[!UICONTROL 开始时间]**&#x200B;字段相同。 |
      | **映射创建时间** | | 或者，也可以选择“人员到帐户”映射的创建日期和时间的字段。 适合某个人在一段时间内切换多个帐户的情况。<br/><br/>**示例**（当选择&#x200B;**update_date**&#x200B;字段时）：<table><thead><tr><th>update_date</th><th>人员</th><th>account</th></tr></thead><tbody><tr><td>20260401</td><td>a@b.com</td><td>Apple</td></tr><tr><td>20260501</td><td>a@b.com</td><td>Adobe</td></tr></tbody></table><ul><li>对于2026年5月1日之前在&#x200B;**[!UICONTROL update_date]**&#x200B;字段中具有时间戳的所有事件： a@b.com已映射到Apple。</li><li>对于2026年5月1日或之后在&#x200B;**[!UICONTROL update_date]**&#x200B;字段中具有时间戳的所有事件： a@b.com已映射到Adobe。</li></ul>未指定映射时间时，将使用词典第一帐户。 当两个不同的帐户名称具有完全相同的&#x200B;**[!UICONTROL update_date]**&#x200B;值并且指定了映射创建时间时，也会使用此相同的算法。 |

      >[!NOTE]
      >
      >如果在加载字段选项时发生错误，下拉菜单将显示为空，并且每个受影响的字段下方会显示一个错误指示符。 请验证您的数据集架构并重试。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以关闭&#x200B;**[!UICONTROL B2B拼接配置]**&#x200B;对话框并返回连接设置。

   1. **[!UICONTROL _未保存的更改_]**&#x200B;指示器显示在&#x200B;**打开B2B拼接配置**&#x200B;按钮旁边，直到您[保存](#save)连接。

### 启用B2B人员以考虑对事件数据集进行拼合


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="启用人员到帐户拼接"
>abstract="启用后，此数据集将使用 B2B“人员到帐户”拼接。 **[!UICONTROL 永久人员ID]**&#x200B;值将提升为配置的&#x200B;**[!UICONTROL 人员标识符命名空间]**&#x200B;中的值，然后用于根据人员到帐户数据集查找帐户ID。<br/>如果禁用，此数据集就不会使用 B2B“人员到帐户”拼接，在这种情况下您就要选择一个必需的&#x200B;**[!UICONTROL 帐户 ID]**。"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/b2b/b2b-person-to-account-stitching#configure-b2b-stitching-settings" text="将B2B人员配置为帐户拼接设置"

在连接级别配置B2B拼接后，必须启用B2B人员以针对要拼接的每个事件数据集单独考虑拼接。

1. 在连接设置中，选择&#x200B;**[!UICONTROL 添加数据集]**&#x200B;或打开现有事件数据集的设置。<br/>有关详细信息，请参阅[添加数据集](/help/connections/create-connection.md#add-datasets)或[编辑数据集](/help/connections/create-connection.md#edit-a-dataset)。

1. 对于要为其配置B2B人员帐户拼接的特定事件数据集，请切换&#x200B;**[!UICONTROL 启用人员帐户拼接]**。

>[!BEGINTABS]

>[!TAB 于]

当&#x200B;**[!UICONTROL 启用人员到帐户拼接]**&#x200B;为&#x200B;**于**&#x200B;时，您已将B2B人员配置为帐户拼合数据集。

* 需要配置人员ID。 该人员ID用于根据[人员对帐户数据集](#prerequisites)查找帐户ID。
* 帐户ID的配置是可选的。

![B2B人员在](../assets/b2b-event-dataset-stitching-on.png)上的事件数据集上进行帐户拼合

>[!TAB 关]

当&#x200B;**[!UICONTROL 启用人员到帐户拼接]**&#x200B;为&#x200B;**关**&#x200B;时，您&#x200B;*未*&#x200B;将B2B人员配置为帐户拼接数据集。

* 需要配置帐户ID。
* 人员ID的配置是可选的。

![B2B人员到帐户拼接事件数据集](../assets/b2b-event-dataset-stitching-off.png)

>[!ENDTABS]


### 保存

在将B2B人员配置为帐户拼接配置并完成添加或编辑数据集后，选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存连接。

>[!IMPORTANT]
>
>保存连接后，B2B人员到帐户的拼接配置将变得不可更改。 要在保存后查看设置，请选择&#x200B;**打开B2B拼接配置**。 所有字段均以只读状态显示。 此外，如果在Experience Platform中删除了用于[人员到帐户映射](#prerequisites)的数据集，则会删除拼合配置，并且连接将进入无效状态，并在用户界面中显示警告消息。

## 数据更新计划

帐户拼接每天从您的[人员到帐户数据集](#prerequisites)中派生标识映射，并使用此信息更新启用按照以下计划进行短期和长期拼接的数据集：

| 重播 | 频率 | 数据窗口 |
|---|---|---|
| 短期 | 每周 | 最近 7 天 |
| 长期 | 按月 | 最近3个月（Prime包）<br/>最近6个月（Ultimate包） |

## 隐私和数据卫生

帐户拼接遵循个人身份的标准隐私和卫生请求，与B2C拼接行为一致。 如果之后通过隐私或卫生请求删除了人员ID，则使用身份图执行的关联拼合会被撤销。

在隐私或卫生请求期间，不会删除通过拼接添加到事件的B2B实体，如帐户ID、帐户ID和全局帐户ID。 这些值不包含个人身份信息，因此不存在删除这些值的法律义务。

>[!MORELIKETHIS]
>
>* [拼接概述](../overview.md)
>* [配置B2B的连接](/help/connections/create-connection.md)
>* [有关拼合的常见问题解答](../faq.md)

