---
title: 标准组件参考
description: 关于所有可添加到任何数据视图的标准组件的详细信息。
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6cabedc5ed58dac450577fc3505be5f95b7a959d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 91%

---

# 标准组件参考

Customer Journey Analytics 中的大多数维度和指标都基于您 Adobe Experience Platform 数据集中的架构元素。但是，无论使用什么连接，都有若干组件可添加到数据视图。

[!UICONTROL 标准组件]不是从数据集架构字段生成的组件，而是由系统生成的组件。必须具有某些系统组件以利于 Analysis Workspace 中的报表功能，而其他系统组件为可选。

![标准组件](assets/dataview-standard-components.png)

## 必需的标准组件 {#required}

默认情况下，将这些必需的标准组件添加到每个数据视图。它们对于 Customer Journey Analytics 提供的报表功能不可或缺。

### 标准维度

{{standard-dimensions}}


### 标准量度

{{standard-metrics}}


## 可选标准组件 {#optional}

可在&#x200B;**[!UICONTROL 数据视图]**>**[!UICONTROL 编辑数据视图]**>**[!UICONTROL 组件]**&#x200B;选项卡 >**[!UICONTROL 标准组件]**&#x200B;选项卡下找到可选标准组件。

| 组件名称 | 维度或量度 | 注释和值 |
| --- | --- | --- |
| [!UICONTROL 上午/下午] | 时间划分维度 | 上午或下午 |
| [!UICONTROL 批次 ID] | 维度 | [!UICONTROL 事件]所属的Experience Platform批次的标识符。 |
| [!UICONTROL 数据集 ID] | 维度 | [!UICONTROL 事件]所属的Experience Platform数据集的标识符。 |
| [!UICONTROL 日期] | 时间划分维度 | 1 日至 31 日 |
| [!UICONTROL 每周时间] | 时间划分维度 | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| [!UICONTROL 每年的某一天] | 时间划分维度 | 第 1 天至第 366 天 |
| [!UICONTROL 小时] | 时间划分维度 | 0 时至 23 时 |
| [!UICONTROL &#x200B; 月份] | 时间划分维度 | 一月 - 十二月 |
| [!UICONTROL 首次会话] | 量度 | 个人在报告窗口内定义的首次会话。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans#new-repeat) |
| [!UICONTROL 返回会话] | 量度 | 非个人首次会话的会话数。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans#new-repeat) |
| [!UICONTROL 人员 ID] | 维度 | Experience Platform 中定义的每个数据集架构，可以拥有自己定义的一个或多个身份标识集，并与命名空间关联。其中任何身份标识都可用作人员 ID。示例包括 Cookie ID、拼接 ID、用户 ID、跟踪代码等。[!UICONTROL 个人 ID] 维度是合并数据集的基础，并可在 Customer Journey Analytics 中标识独特访客。<p>可能的使用案例包括：<ul><li>创建针对特定人员ID值的区段，以将所有内容细分为该用户的行为。</li><li>调试：确保特定 Cookie ID（或特定客户 ID）的数据存在。</li><li>确定致电给呼叫中心的用户。</li></ul> |
| [!UICONTROL 人员 ID 命名空间] | 维度 | [!UICONTROL 人员 ID] 由哪种类型的 ID 组成。示例为：`email address`、`cookie ID`、`Analytics ID` |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 全球帐户 ID] | 维度 | [!UICONTROL 全球帐户 ID]，如果您在连接中使用全球帐户容器。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 帐户 ID] | 维度 | 在连接中使用帐户容器时的[!UICONTROL 帐户ID]。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 机会 ID] | 维度 | [!UICONTROL 机会 ID]，如果您在连接中使用机会容器。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 购买群组 ID] | 维度 | [!UICONTROL 购买群组 ID]，如果您在连接中使用购买群组容器。 |
| [!UICONTROL 季度] | 时间划分维度 | 第一季度、第二季度、第三季度和第四季度 |
| [!UICONTROL 重复会话] | 量度 | 非个人首次会话的会话数。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans#new-repeat) |
| [!UICONTROL 会话类型] | 维度 | 这个维度有两个值：1.[!UICONTROL 首次]和 2.返回。[!UICONTROL 首次]行项目包括已确定为个人的首次会话的所有行为（针对该维度的量度）。其他所有内容都包含在[!UICONTROL 返回]的行项目中（假设所有内容都属于一个会话）。如果量度不是任何会话的一部分，则它们将属于该维度的“不适用”分段。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans#new-repeat) |
| [!UICONTROL 每个事件逗留时间] | 维度 | 将[!UICONTROL 耗时]指标装入[!UICONTROL “事件”]桶。 |
| [!UICONTROL 每个会话逗留时间] | 维度 | 将[!UICONTROL 耗时]指标装入[!UICONTROL 会话]桶。 |
| [!UICONTROL 每人逗留时间] | 维度 | 将[!UICONTROL 耗时]指标装入[!UICONTROL 人员]桶。 |
| [!UICONTROL 周末]/[!UICONTROL 工作日] | 时间划分维度 | 周末或工作日 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[利用事件深度功能发现更深入的客户洞察](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947#M576)
>