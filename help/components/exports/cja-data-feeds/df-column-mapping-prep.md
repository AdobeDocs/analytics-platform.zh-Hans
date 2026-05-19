---
description: 了解如何准备将数据馈送列从Adobe Analytics映射到Customer Journey Analytics。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: 准备将数据馈送列从Adobe Analytics映射到Customer Journey Analytics
feature: Components
hide: true
exl-id: d0a9e697-1e48-4cfb-8613-2f932bf5015b
autotag-review: '2026-05-19T08:44:51.994Z'
TQID: 'https://experienceleague.adobe.com/0KbYVZ87QL4qh-5FfSRxpuEF4-xsqBTLwLCvKa-u9Mw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 1092
ht-degree: 3%

---

# 准备将数据馈送列从Adobe Analytics映射到Customer Journey Analytics

与Adobe Analytics相比，Customer Journey Analytics在确定可包含在数据馈送中的列方面提供了更灵活的架构。 大多数组织从Customer Journey Analytics导出的数据馈送列与从Adobe Analytics导出的数据馈送列有所不同。 这些差异是由于以下因素造成的：

* **[数据馈送架构架构](#schema-architecture)**： Adobe Analytics数据馈送列派生自Analytics变量，而Customer Journey Analytics数据馈送列派生自数据视图配置。

* **[数据处理](#data-processing)**： Adobe Analytics和Customer Journey Analytics之间存在基本的数据处理差异，尤其是许多Adobe Analytics列同时存在预处理列和后处理列。

* **[未使用的列](#unused-columns)**： Adobe Analytics包含超过1,100个数据馈送列。 大多数组织不使用所有正在导出的列的数据。

* **[跨渠道列](#cross-channel-columns)**： Customer Journey Analytics支持在Adobe Analytics中不可用的跨渠道数据（如呼叫中心数据）。

在开始将Adobe Analytics数据馈送列映射到Customer Journey Analytics数据馈送列之前，请查看以下部分以更好地了解这些影响映射的关键因素。

查看此信息后，按照计划保留在Customer Journey Analytics中的每个Adobe Analytics数据馈送列的映射说明进行操作，如[数据列引用](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)中所述。

## 数据馈送架构架构

与Adobe Analytics相比，Customer Journey Analytics在确定可在数据馈送中包含哪些列方面提供了更灵活的架构：

### Adobe Analytics架构

预定义的静态变量列表可用作数据馈送列。

包括所有列很容易，许多客户都会这样做，即使这些列中包含的数据在整个组织中都没有使用。

### Customer Journey Analytics架构

数据视图配置中包含的任何组件都可以作为数据馈送列包含。 有关每个潜在的Adobe Analytics数据馈送列的此过程的详细信息，请参阅[数据列引用](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

按照下表所述的任何一种方式，在数据视图配置中包括组件：

| 用于包含在数据视图配置中的方法 | 其他信息 |
|---------|----------|
| XDM架构字段在数据视图中作为组件进行管理 | XDM架构中存在的字段在数据视图中作为组件进行管理，之后它们会成为Customer Journey Analytics中的数据视图配置的一部分。 <p>Customer Journey Analytics XDM架构中默认可用的字段数可能会有所不同，具体取决于为Customer Journey Analytics实施收集数据的方式，如下所示：</p><ul><li>**新的Web SDK实施**：如果您的Customer Journey Analytics实施使用自定义架构，则Adobe Analytics数据馈送中存在的许多列可能在Customer Journey Analytics中不存在。 同样，Customer Journey Analytics可能包含Adobe Analytics数据馈送中不存在的字段。<p>如果可能，请咨询为您组织的Customer Journey Analytics实施构建XDM架构的团队或个人。 创建XDM架构时，做出了许多有关在Customer Journey Analytics中需要哪些Adobe Analytics字段的决策。 有关详细信息，请参阅[构建用于 Customer Journey Analytics 的架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。</p></li><li>**Analytics Source Connector实施**：默认情况下，许多数据馈送列存在一对一字段映射，因为Analytics Source Connector在XDM架构中使用Analytics Experience Event字段组。 有关哪些Adobe Analytics字段映射到此字段组中的字段的信息，请参阅Experience Platform文档中的[Analytics字段映射](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics)。</li></ul> |
| 组件是在数据视图中使用派生字段创建的 | 您可以直接在数据视图中创建组件，从而创建XDM架构中不可用的数据馈送列。 |

## 数据处理

Adobe Analytics和Customer Journey Analytics之间的数据处理差异会影响哪些数据馈送列可供导出，如下所示：

* **Adobe Analytics**：许多数据馈送字段作为两个单独的列导出：一个包含预处理数据，另一个包含预处理数据。 （后处理数据包括服务器端逻辑、处理规则、VISTA规则、维度持久性规则等。）

  由于Adobe Analytics在两个单独的列（一个用于预处理数据，一个用于后处理数据）中导出某些字段的数据，因此Adobe Analytics包含的数据馈送列比Customer Journey Analytics多。 映射字段时请牢记这一点。

* **Customer Journey Analytics**：字段在数据视图中创建后可用于数据馈送。 通常，Customer Journey Analytics数据视图中的字段仅包含处理后的数据。 但是，您通常可以通过在Adobe Analytics数据视图中创建字段的第二个版本并将其配置为在点击时过期来近似字段的Customer Journey Analytics预处理版本。

## 未使用的列

Adobe Analytics中有1,100多个数据馈送列可供导出。 在这些列中，并非所有列都会在您的Customer Journey Analytics数据馈送中使用。 这种差异并不表示您的Customer Journey Analytics数据馈送列不足。

确定您的组织使用的Adobe Analytics数据馈送列。 此操作将告知您的Customer Journey Analytics数据馈送中需要哪些列。 要确定要使用的列，请执行以下操作：

* **标识仅适用于Adobe Analytics的字段**： Adobe Analytics数据馈送中的某些列特定于Adobe Analytics的数据处理引擎，因此不适用于Customer Journey Analytics。 此类列的示例为`exclude_hit`和`hit_source`。

* **识别适用于您组织的字段**：虽然并非所有Adobe Analytics客户都会导出所有可用的列，但许多客户导出的列多于实际使用的列。

  在开始从Customer Journey Analytics导出数据馈送之前，您应该首先确定贵组织当前使用的Adobe Analytics数据馈送列，然后确保这些组件存在于您的Customer Journey Analytics数据视图配置中。 要收集此信息，请联系贵组织内使用Adobe Analytics数据馈送内容的团队或个人。

## 跨渠道列

Customer Journey Analytics支持跨渠道数据（例如呼叫中心数据），而这些数据在Adobe Analytics中不可用。 这些跨渠道字段是可以包含在Customer Journey Analytics数据馈送中的新列的示例，Adobe Analytics不支持这些列。

<!--

1. View the data views throughout your organization to make sure that corresponding dimensions are available. If a corresponding dimension does not exist in the data view, create it.

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view.

   

1. For each Adobe Analytics data feed field that is being used, ensure that a similar field exists in the XDM schema.

1. Verify that and that corresponding dimensions are available in the data view. If not, you need to create them. 

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 

## Map data feed columns from Adobe Analytics to Customer Journey Analytics

### Step 1 - Map the default columns included in Customer Journey Analytics

There are roughly 20 default fields included in all WebSDK implementations. 

Before you can map these default columns, make sure that your Customer Journey Analytics environment meets the following prerequisites:

* It uses a WebSDK implementation.

* The appropriate field groups that contain the default WebSDK fields are added to your XDM schema.If the field is not added to your schema, it is included in the payload, but ultimately dropped.

* Each default field must be curated as a component in a Customer Journey Analytics data view.

* The component settings in the data view must be equivalent to how Analytics treats it (Visit persistence or hit-level persistence).

To map the default dimensions:

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that are included by default

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

### Step 2: Discover which additional data feed columns your consumers use

There are over 1,100 data feed columns available to be exported in Adobe Analytics. While not all Adobe Analytics customers export all of the available columns, many customers export more than they actually use. 

Before you begin mapping data feed columns, you should first:

1. Contact the teams or individuals who consume data feed content and determine which data feed columns they use.

1. View the data views throughout your organization to see which dimensions are available. 

   These are the dimensions that are being used for reporting in Analysis Workspace. Any Adobe Analytics data feed column needs to be mapped to a corresponding dimension that exists within a Customer Journey Analytics data view. 


### Step 3 - Map each additional column

1. ...

1. ...

+++ View the Adobe Analytics data feed columns that could be mapped if they are included in your schema and data views

| Adobe Analytics column name | Column description | Data type |
| --- | --- | --- |
| **`accept_language`** | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| **`adload`** | Media ad loads | varchar(255) |
| **`aemassetid`** | A multi-value variable corresponding to Asset IDs (GUIDs) of a set of Adobe Experience Manager Assets. Increments Impression Events. | text |

+++

Notes below here. Ignore:

Do we group these columns by if you're using the WebSDK, or if you're using specific field groups.

Here's what is in Analytics, and here's what it maps to in CJA. Customers want us to "give them the mappings."

Some of these fields there is probably something like it that you could get in WebSDK. There will be some fields that aren't. Or some that are in AEP that aren't in here (like call center data).

We have an XDM field mappings to Analytics variables. "Adobe analytics XDM Var - first hit on Google." If you set your XDM payload to the given field on the left, it will automatically be associated to the Analytics variable on the right. But we're looking for a reverse mapping of this. 









If you're using ADC, you'll have the AA column name in there. We also have an ADC mapping doc page. (Analytics field mappings doc page maps the fields)



Make a table (or a section) that talks about fields that are new to CJA, like cross-channel fields (call center, etc.) 

The number of AA columns that they can map is not going to be that big (maybe 100). The number of columns that don't map will be huge.

## Data feed column reference

### Adobe Analytics data feed columns that are included by default in Customer Journey Analytics WebSDK implementations

### Adobe Analytics data feed columns that can be included in Customer Journey Analytics data feed

### Adobe Analytics data feed columns that don't apply to Customer Journey Analytics


### Columns, descriptions, and data types

Use this section to learn what data is contained in each column. Most implementations don't use every column, so this section can be referenced when determining which columns to include in a data feed export.

-->
