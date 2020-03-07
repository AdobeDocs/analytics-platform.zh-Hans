---
title: 客户旅程分析功能支持
description: 客户旅程分析功能与Adobe Analytics功能集的对比。
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# 客户旅程分析功能支持

下表列出了Adobe Analytics中支持、部分支持或不支持的功能，这些功能在客户旅程分析(CJA)中。 随着功能添加到CJA，这些列表会随时间而改变。

## 完全支持的功能／组件

| 功能 | 注释 |
| --- | --- |
| 量度 | CJA利用体验数据模型(XDM)并支持无限量度量度，且不与传统Analytics的自定义成功事件关联。 请注意，一些标准指标已从传统的Analytics中更名为：访客=人员，访问=会话，点击=事件。 |
| 维度 | CJA利用XDM并支持无限维度，且不与传统Analytics的自定义成功事件关联。 |
| 列表变量／列表属性 | CJA利用XDM并支持不限数量的列表变量 |
| 日期范围 | 计划提供自定义日历支持。 |
| 计算量度 | 请注意，传统Analysis Workspace中的任何现有计算量度都不会移植到CJA。 |
| 区段 | 现在称为“过滤器”-请注意，传统Analysis Workspace中的任何现有区段都不会移植到CJA。 |
| 归因 IQ | 完全支持 |
| 项目特选 | 完全支持 |
| 项目链接 | 完全支持 |
| 日期比较 | 完全支持 |
| 虚拟报表包 | 现在称为 [数据视图](/help/data-views/create-dataview.md)。 |
| VRS组件特选 | 现在是数据视图的一部分。 |
| 报表时间处理 | CJA仅依赖于报告时间处理。 |
| GDPR删除 | 请注意，GDPR现在与Adobe Experience Platform协同处理- CJA继承了Experience Platform对基础数据集所做的任何数据更改。 |

## 受支持，但有注意事项

| 功能 | 注释 |
| --- | --- |
| 产品变量 | 当前可用于报告符合体验事件架构的数据的产品变量（特别是使用productListItems对象）。 |
| 可视化图表 | 除地图可视化外，所有可视化均受支持。 |
| AAM受众 | 如果客户使用Analytics Data Connector数据集，则此数据将是ADC数据的一部分。 |
| 项目共享 | 项目共享仅在CJA用户之间受支持- CJA与传统Analysis Workspace之间不存在项目共享。 |
| 自定义会话化 | 支持除移动后台点击之外的所有自定义会话化功能。 |
| eVar持久性设置 | eVar不再是CJA的一部分。 但是，持久性设置现在是数据视图的一部分，可用于所有维。 请记住，持久性是基于报告时间处理而非数据收集处理。 这意味着所有持久性都将基于报告日期范围而不是整个数据。 |
| 分类 | 现在称为“查找数据集”，它们不会从传统Analytics自动导入。 在CJA中提供之前，必须将它们上传到AEP。 |
| 客户属性 | 现在称为“配置文件数据集”，它们不会从Experience Cloud自动导入，但必须先上传到AEP，然后才能在CJA中使用。 |

## 部分支持

| 功能 | 注释 |
| --- | --- |
| 开箱即用的Analysis Workspace维度（例如浏览器类型、引用类型、营销渠道、访问次数等） | CJA本身不提供这些维度。 对于使用Analytics Data Connector(ADC)的客户，其中一些维度可用，但并非全部。 请参阅我们的 [文档，其中ADC支持Analytics变量](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)。 |
| 面板 | 完全支持空白面板、归因面板和自由格式面板。 不支持区段比较。 |
| 促销 eVar | 销售eVar只能与基于ADC的数据集配合使用，除非它们严格符合相同的XDM架构（与上述产品列表限制类似）。 |
| 机器人过滤 | 对于基于Analytics Data Connector(ADC)的数据集，应用机器人过滤。 其他数据集的常规机器人过滤逻辑不由Experience Platform或CJA执行。 |
| 处理规则 | 对于基于ADC的数据集，仍然应用处理规则。 |
| 跨设备身份拼接 | 客户只能通过Query Service对数据进行“一次”拼接，或者当前必须在Experience Platform数据获取之前将此逻辑应用于数据。 |

## 当前不支持，但已计划

| 功能 | 注释 |
| --- | --- |
| 异常检测 | 已计划提供支持。 |
| 贡献分析 | 已计划提供支持。 |
| 区段 IQ | 已计划提供支持。 |
| 细分发布（将细分从Workspace发送到Experience Cloud） | 已计划提供支持。 |
| 用户权限／数据访问控制 | CJA中的所有用户都具有相同的访问控制——这意味着所有用户都有权访问所有连接、数据视图等。 基本上，所有用户都是CJA中的管理员级用户。 计划于2020年提供支持。 |
| CSV下载 | 已计划提供支持。 |
| 计划报告／项目 | 已计划提供支持。 |
| 警报 | 已计划提供支持。 |
| 自定义日历 | 已计划提供支持。 |
| 营销渠道 | 已计划提供支持。 |
| PDF导出 | 已计划提供支持。 |
| 报告API访问 | 已计划提供支持——仅在API 2.0中提供。 |
| 通过设备图进行ID拼接 | 已计划提供支持。 |

## 尚未计划支持

| 功能 | 注释 |
| --- | --- |
| A4T | 尚未计划提供支持。 |
| Video Analytics | 尚未计划提供支持。 |
| Advertising Cloud | 尚未计划提供支持。 |
| Report Builder（Excel插件） | 尚未计划提供支持。 |
| Activity Map | 尚未计划提供支持。 |
| 分类规则生成器 | 尚未计划提供支持。 |
| 摘要数据源 | 尚未计划提供支持。 |
| 实时报告 | 尚未计划提供支持。 |

## 将永远不受支持

| 功能 | 注释 |
| --- | --- |
| 使用跨设备合作伙伴的人员指标 |  |
| 报告和分析仪表板 |  |
| 报告和分析书签 |  |
| 报告和分析目标 |  |
| Reports &amp; Analytics日历事件 |  |
| Ad Hoc Analysis |  |
| Data Warehouse 报表 | Adobe Experience Platform Query Service将是CJA中这些用例的新界面。 |
| Mobile Services |  |
| 数据馈送 |  |
