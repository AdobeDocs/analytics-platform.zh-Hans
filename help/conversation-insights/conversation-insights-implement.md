---
title: 实施对话分析
description: 了解如何检测代理应用程序或服务以进行对话分析。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: b29ee2f04a1775dca6a8fd93c3ac3050b67f0ceb
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 6%
---
# 实施对话分析

要将对话数据生成为XDM体验事件并确保这些对话体验事件最终在Adobe Experience Platform中作为数据集，请检测您的代理应用程序或服务以使用对话分析。

本文记录了所需的实施步骤。

>[!PREREQUISITES]
>
>* 您必须具有可用于收集数据的Experience Platform环境（组织和沙盒）。
>* 必须为实验代理和对话字段组启用您的Adobe组织。
>

## 架构和数据集

为主要对话事件配置数据集：提示、响应、反馈。 这些数据集可以基于相同的架构（例如，通用的对话分析架构），也可以基于单独的架构。
您可以为提示、响应和反馈定义单独的数据集，也可以将数据合并到数据集中。 例如，使用一个数据集进行提示和响应，使用另一个数据集进行反馈。 或者对所有对话事件使用单个数据集。

用于提示、响应和反馈数据集的架构必须使用必填字段组扩展XDM体验事件基本架构。 并且可以使用其他字段组扩展XDM体验事件基本架构。

### 代理信息字段组

**[!UICONTROL 代理信息]**&#x200B;字段组是必需的字段组，它使用`agenticExperience`对象。

+++ 详细信息

| 字段路径（点表示法） | 类型 | 示例值 | 注释 |
|---|---|---|---|
| `conciergeID` | 字符串 | `"concierge-abc123"` | **新建。** 调度器的唯一标识符 |
| `name` | 字符串 | `"Brand Concierge"` | 将一组代理组合起来的调度器的名称 |
| `version` | 字符串 | `"1.0.0"` | 将一组代理组合起来的调度器的版本 |
| `environment` | 字符串 | `"prod"` | 环境此事件源自（开发、暂存、生产） |
| `mode` | 字符串 | `"release"` | 代理所处的模式（测试、预览、发布） |
| `agents[]` | 数组 | 请参阅下面的代理对象 | 使用的代理数组 |
| `agents[].agentID` | 字符串 | `"agent-001"` | **新建。** 下面的`skills[].agentID`所引用的代理的唯一标识符 |
| `agents[].name` | 字符串 | `"Chatbot Assistant"` | 代理名称 |
| `agents[].version` | 字符串 | `"2.1.3"` | 代理版本 |
| `agents[].score` | 数字 | `0.92` | 在其返回值中的代理置信度分数 |
| `agents[].skills[]` | 数组 | 查看下面的技能对象 | **已弃用** — 请改用下面的顶级`skills[]`数组，该数组拥有技能调用的完整排序列表，并通过`agentID`将每个调用链接到其代理 |
| `agents[].skills[].name` | 字符串 | `"Intent Recognition"` | 技能名称（已弃用的数组） |
| `agents[].skills[].version` | 字符串 | `"1.0.0"` | 技能版本（已弃用的数组） |
| `agents[].skills[].score` | 数字 | `0.95` | 技能置信度分数(0-1)（已弃用的数组） |
| `agents[].skills[].parameters[]` | 数组 | 请参阅下面的参数 | 发送到技能的参数（键值对）（已弃用的数组） |
| `agents[].skills[].parameters[].key` | 字符串 | `"language"` | 参数键 |
| `agents[].skills[].parameters[].value` | 字符串 | `"en-US"` | 参数值 |
| `skills[]` | 数组 | 请参阅下面的技能调用对象 | **新，实验性。** 所有座席对此体验进行完整、有序的技能调用的列表。 替换已弃用的每个代理`agents[].skills[]`数组 |
| `skills[].skillID` | 字符串 | `"skill-intent-recognition"` | 调用的技能定义的标识符 |
| `skills[].skillInvocationID` | 字符串 | `"inv-9f2a-001"` | 此技能调用的唯一标识符，即使与重新投放一致。 在合并下游技能阵列时，重复数据消除是关键 |
| `skills[].name` | 字符串 | `"Intent Recognition"` | 调用的技能的名称 |
| `skills[].version` | 字符串 | `"1.0.0"` | 所调用技能的版本 |
| `skills[].agentID` | 字符串 | `"agent-001"` | 调用此技能的代理的标识符，与`agents[].agentID`相关。 由于子代理并行运行，分组关键使用者用于在代理内排序技能 |
| `skills[].invocationSource` | 字符串 | `"main"` | 由主代理循环(`main`)或子代理(`subagent`)调用 |
| `skills[].score` | 数字 | `0.95` | 匹配技能所得的分数 |
| `skills[].failed` | 布尔值 | `false` | 表示技能执行失败的标记 |
| `skills[].errorReason` | 字符串 | `"timeout"` | 在`failed`为true时技能失败的原因 |
| `skills[].sequenceNumber` | 整数 | `1` | 在单个代理执行中单调递增此技能调用的索引 — 不是全局性的，因为子代理并行运行。 使用者按`agentID`、`sequenceNumber`、`timestamp`进行分页排序。 可选 |
| `skills[].timestamp` | 字符串（日期时间） | `"2026-09-11T00:03:15Z"` | 启用该技能的时间，ISO 8601 UTC。 在`sequenceNumber`之后使用的排序键。 生成者应始终填充此内容 |
| `skills[].skillSource` | 字符串 | `"inline"` | 如何将技能定义传递到运行时： `inline` （内联加载到上下文中）或`deferred` （按需加载） |
| `skills[].executionContext` | 字符串 | `"inline"` | 执行与呼叫代理相关的技能的位置： `inline`或`forked`（在分支的子代理上下文中运行） |
| `skills[].reasoning.narration` | 字符串 | `"Recognized an intent to verify a geography fact"` | 为什么调用此技能的自然语言解释 |
| `skills[].parameters[]` | 数组 | 请参阅下面的参数 | 传递到技能的参数 |
| `skills[].parameters[].key` | 字符串 | `"language"` | 参数键 |
| `skills[].parameters[].value` | 字符串 | `"en-US"` | 参数值 |

+++

要实施使用数据传播代理信息字段组的事件，您应确保：

* 代理配置

  * 每个代理都有一个唯一的agentID、名称和版本组合。
  * 代理得分在`0.0`和`1.0`之间标准化。
  * 使用`agentID`按技能调用引用座席。

* 技能调用

  * 在所有座席中，每个技能呼叫仅发出一个条目，而不是在每个座席下嵌套技能。
  * 填充skillInvocationID，以便下游混合可以删除重复的重投放事件。
  * 正确订购消费者。 按`agentID`分组，然后按`sequenceNumber`排序，回退到`timestamp`。 需要排序，因为子代理可以并行执行
  * 使用`invocationSource`和`executionContext`区分主代理和子代理技能，以及内联与分支执行。
  * 避免使用已弃用的`agents[].skills[]`数组。 如果您以前使用过该数组，请将该数组视为只读对象。

* 技能参数

  * 参数使用Adobe XDM键值数据类型，并将常用参数类型用于语言设置、阈值、模型配置。 例如：`"key":"language", "value":"en-US"`。

+++ 代理信息字段组的用法示例 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### “对话事件”字段组

**[!UICONTROL 对话事件]**&#x200B;字段组是必填字段组，并使用`conversation`对象。

对话对象捕获以下项的数据：

#### 对话

唯一的`conversationID`标识对话。 例如：`conversationID = "conv-001"`。 架构还支持`conversationName`。 描述对话整体上下文的可读名称，如： `France Geography Q&A`。

`conversationID`允许将所有相关的转化事件分组到相同的对话体验中。

#### 翻转

轮次是对话中的一个交互周期。

`turnID`唯一的`turnID`标识转弯。 例如：

`conversationID = "conv-001"`
`turnID = "turn-001"`

同一`conversationID`和`turnID`用于关联与该转向关联的提示、响应和反馈。 这种关联适用于单独交付或最终位于不同数据集的记录。


#### 提示

提示是提交给代理的输入。 在大多数客户情景中，此输入是用户的问题、请求、说明或消息。

提示使用以下表示形式： `conversation.prompt`

重要的提示字段包括：

| 字段 | 含义 |
|---|---|
| `prompt.source` | 产生提示的人员或内容，通常是最终用户。 |
| `prompt.raw[]` | 一个或多个原始内容区段。 |
| `prompt.raw[].text` | 实际的提示文本或内容。 |
| `prompt.raw[].purpose` | 内容的用途，如用户输入或链接。 |

一个提示可以包含多个原始区段。 例如，用户输入文本并包含一个URL。

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### 响应

响应是指代理或其他响应方返回的内容。

`conversation.response`唯一的`responseID`表示响应。

重要的响应字段包括：

| 字段 | 含义 |
|---|---|
| `response.source` | 产生响应的人员或人员。 |
| `response.raw[]` | 一个或多个响应内容区段 |
| `response.raw[].text` | 响应文本或内容。 |
| `response.raw[].purpose` | 内容区段的目的。 |

记录的源类型包括：

| 来源 | 含义 |
|---|----|
| `bot` | 自动代理响应。 |
| `canned` | 预定义或模板化的响应。 |
| `concierge` | 人体代理反应。 |
| `end-user` | 人工生成的内容（如果适用）。 |

#### 反馈

反馈是用户对交互的明确评估或反应。

反馈结构包括： `conversation.feedback`。

示例：

* `feedback.raw[].text: "Great help"`
* feedback.rating.score： 1
* feedback.rating.classification： &quot;Thumbs Up&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

记录的评分范围是`-1.0`到`1.0`。

可以使用以下项将反馈事件表示为仅反馈事件： `eventType = "conversation.feedback"`。

当反馈应用于特定回合时，请保留相应的`conversationID`和`turnID`，以便对话搅拌器能够将反馈与相关交互相关联。


#### 信号

信号是对会话内容的结构化分析观察。 信号提取服务提取信号。

信号包含以下字段。

| 字段 | 含义 |
|---|----|
| `scope` | 用于派生信号的输入范围，如转换或会话至今。 |
| `name` | 信号标识符，例如主题、意图、音调或情绪。 还支持产品定义的信号名称。 |
| `type` | 值类型：字符串、数字或布尔值。 |
| `values[]` | 与信号相关的一个或多个值。 |
| `stringValue` | 字符串信号值，例如意图、音调或主题。 |
| `numberValue` | 数字信号值，如情绪分数。 |
| `booleanValue` | 真/假信号值。 |
| `confidence` | 信号值中的可选生产者置信度，通常介于0和1之间。 |
| `qualifiers[]` | 向信号值添加上下文的可选描述符。 |
| `metadata[]` | 可选的制造者定义的键/值元数据。 |


信号提取服务填充信号数据集的`signals`对象。

已弃用以前的`signals[].attributes.{subjects,intents,tones,sentiment}`容器。

#### 对话

有关对话对象的完整详细信息，请参阅下文。

+++ 详细信息 

| 字段路径（点表示法） | 类型 | 示例值 | 注释 |
|---|---|---|---|
| `conversationID` | 字符串 | `"conv-001"` | 将多个轮流分组 |
| `conversationName` | 字符串 | `"France Geography Q&A"` | **新建。** 为对话提供的名称，该名称表示对话的整体上下文 |
| `turnID` | 字符串 | `"turn-001"` | 此回合的唯一ID |
| `prompt.source` | 字符串 | `"end-user"` | Source提示，其他选项可能包括缓存值、固定值等。 |
| `prompt.raw[]` | 数组 | 请参阅下面的原始对象 | 原始提示数据 |
| `prompt.raw[].text` | 字符串 | `"What is the capital of France?"` | 实际文本内容 |
| `prompt.raw[].purpose` | 字符串 | `"User Input"` | 此文本段的用途 |
| `response.source` | 字符串 | `"bot"` | Source响应 |
| `response.raw[]` | 数组 | 请参阅下面的原始对象 | 原始响应数据 |
| `response.raw[].text` | 字符串 | `"The capital of France is Paris."` | 响应文本内容 |
| `response.raw[].purpose` | 字符串 | `"main"` | 响应区段的用途，其他选项可能包括链接、图片等。 |
| `feedback.source` | 字符串 | `"end-user"` | Source反馈 |
| `feedback.raw[]` | 数组 | 请参阅下面的原始对象 | 原始反馈数据 |
| `feedback.raw[].text` | 字符串 | `"Great help"` | 反馈文本 |
| `feedback.raw[].purpose` | 字符串 | `"free-form text"` | 对于反馈区段，其他选项可能包括屏幕截图、媒体等。 |
| `feedback.rating.score` | 数字 | `1` | 数值评级得分从–1.0到1.0 |
| `feedback.rating.classification` | 字符串 | `"Thumbs Up"` | 评级分类 |
| `feedback.rating.reasons[]` | 数组 | `["Accurate", "Quick response"]` | 评级原因数组 |
| `signals[]` | 数组 | 请参阅下面的信号对象 | 基于此事件和迄今为止的对话派生的信号。 每个条目都是一个具有自己作用域的命名信号 |
| `signals[].scope` | 字符串 | `"turn"` | 从中派生这组信号的输入范围（轮换、会话至今、最后N个轮换、反馈） |
| `signals[].attributes` | 对象 | 请参阅以下属性 | **已弃用。** 信号属性的容器。 每个属性都是一个对象，其中包含一个或多个值。 这是为了满足支持用于生成信号的ML/代理信息量的预期需要。 |
| `signals[].attributes.subjects` | 对象 | 请参阅以下主题 | **已弃用。** 主题容器 |
| `signals[].attributes.subjects.values[]` | 数组 | 请参阅下面的主题值 | **已弃用。** 主题值数组 |
| `signals[].attributes.subjects.values[].phrase` | 字符串 | `"product pricing"` | **已弃用。** 从限定范围的输入中提取的短语或关键词 |
| `signals[].attributes.subjects.values[].qualifiers[]` | 数组 | `["important", "urgent"]` | **已弃用。** 短语的限定符列表 |
| `signals[].attributes.intents` | 对象 | 查看以下意图 | **已弃用。** 意图容器 |
| `signals[].attributes.intents.values[]` | 数组 | `["make a purchase", "learn more"]` | **已弃用。** 从范围输入派生的意图 |
| `signals[].attributes.tones` | 对象 | 查看下面的色调 | **已弃用。** 色调容器 |
| `signals[].attributes.tones.values[]` | 数组 | `["thrilled", "contemplative"]` | **已弃用。** 从范围输入派生的色调 |
| `signals[].attributes.sentiment` | 对象 | 请参阅下面的情绪 | **已弃用。** 情绪容器 |
| `signals[].attributes.sentiment.value` | 数字 | `0.71` | **已弃用。** 得分从–1（负）到1（正）表示情绪 |
| `signals[].name` | 字符串 | `"sentiment"` | **新**（替换已弃用的`attributes`容器）。 此信号的标识符，例如“主体”、“意图”、“色调”、“情绪”或任何制作者定义的名称 — 制作者可以添加新的信号类型而无需架构更改 |
| `signals[].type` | 字符串 | `"number"` | **新建。** 此信号值（`string`、`number`或`boolean`）的数据类型 — 告知使用者在`values[]`的每个条目上填充了哪个类型的值字段 |
| `signals[].values[]` | 数组 | 请参阅下面的值对象 | 此信号的一个或多个值 |
| `signals[].values[].stringValue` | 字符串 | `"curious"` | 当`type`为“字符串”时填充 — 一个分类值，例如意图、音调或提取的短语 |
| `signals[].values[].numberValue` | 数字 | `0.71` | 当`type`为“数字”（例如，情绪分数从–1到1或强度）时填充 |
| `signals[].values[].booleanValue` | 布尔值 | `true` | 当`type`为“boolean”（真/假标志）时填充 |
| `signals[].values[].confidence` | 数字 | `0.9` | **新建。** 生产者分配给此值的置信度，从0到1 |
| `signals[].values[].qualifiers[]` | 数组 | `["important", "urgent"]` | 此值的其他描述符，与关键字类似，但更有意义 |
| `signals[].values[].metadata[]` | 数组 | 请参阅下面的参数 | **新建。** 生成器为此值定义的元数据作为键/值对，例如有关生成信号的ML/代理的上下文 |

+++




### 其他字段组

您可以将可选字段组添加到用于提示、响应和反馈数据集的架构中。 例如：

* **Web详细信息**&#x200B;字段组。 用于捕获对话嵌入到的网页的详细信息。
* **Commerce详细信息**&#x200B;字段组。 用于捕获对话中提到的推荐产品的产品详细信息。



客户负责制作源对话事件。 Adobe平台随后执行信号提取和数据混合。 客户不需要执行信号提取或混合服务。

本文档介绍了Conversation Insights MVP输入要求和当前代理模式更新。 它不包括Conversation Insights 1.0功能或更高版本的要求。

### 事件类型

您需要为每个对话事件设置`eventType` （字符串）的以下值之一：

| 数值 | 说明 |
|---|---|
| `conversation turn` | 带提示和回应的完整对话翻转 |
| `conversation recommendation` | 基于对话的推荐 |
| `conversation feedback` | 仅反馈事件 |


### Source类型

您需要为事件中的每个`prompt`、`response`或`feedback`对象设置`source`的以下值之一：

| 值 | 描述 |
|---|---|
| `end-user` | 人工用户输入 |
| `bot` | 自动代理响应 |
| `canned` | 预定义/模板化响应 |
| `concierge` | 人体代理反应 |

### 用途类型（原始文本）

您需要为`prompt`、`response`或`feedback`对象中`raw`对象的任何元素的`purpose`特性设置以下值之一。

| 值 | 描述 |
|---|---|
| `User Input` | 主要用户输入 |
| `main` | 主要响应内容 |
| `advertisement` | 促销内容 |
| `citation` | 引用/源链接 |
| `link` | 外部链接 |
| `image` | 图像引用 |
| `enum picker` | 结构化反馈选择 |


### 示例

请参阅下面的示例，了解在各种场景中Conversation Event字段组的用法。

+++ 详细信息 

>[!BEGINTABS]

>[!TAB 转换事件示例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB 响应事件示例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB 反馈事件示例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB 产品推荐事件示例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## 数据收集

为对话分析使用以下数据收集策略。


### 事件类型

您的代理应用程序或服务会尽快发送事件。 确保应用程序或服务在发送带有事件时可用信息的提示之前不会等待响应。

这项建议意味着：

* 提示、响应和反馈对象是独立填充的，不应强制它们成为单个事件的一部分。
* 数据集间应存在多个具有相同`conversationID`和`turnID`的事件。

### 事件关联

代理应用程序或服务必须在所有相关事件中保留稳定的标识符。

| 字段路径 | 描述 |
|---|---|
| `conversation.conversationID` | 整个对话的唯一标识符。 |
| `conversation.turnID` | 对话中单个回合的唯一标识符。 |
| `_id` | 体验事件记录标识符。 |
| `timestamp` | 事件发生的时间。 |
| `eventType` | 标识对话事件的类型。 |

* 同一`conversationID`必须用于属于同一对话的所有事件。

* 同一`turnID`必须用于提示、响应以及与同一转向关联的任何反馈。 提示、响应和反馈数据集中可以存在多个具有相同`turnID`的事件。

代理应用程序或服务会生成ID，这些ID在重试或重新交付期间保持稳定。 这允许下游处理正确关联事件并避免意外重复事件。

## 信号提取

信号提取发生在数据收集之后。 您的代理应用程序或服务不会填充其他信号。

+++ 带有信号的示例转换事件

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## 数据混合

对话混合器服务将来自提示、响应、反馈和信号事件数据集的事件合并到专用的混合对话事件数据集中。 该数据集在Customer Journey Analytics中用作连接的一部分。 该数据集中的组件将添加到您为对话分析配置指定的数据视图。
