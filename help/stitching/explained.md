---
title: 拼合的工作原理
description: 了解拼合的概念
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 28%

---

# 拼合的工作原理

拼合至少会对给定数据集中的数据执行两次传递：

* **实时拼合**：尝试在每次点击进入时拼合点击。 数据集中从未登录的全新设备通常不会在此级别拼接。但已识别的设备会立即拼接。

* **重播拼合**：根据已了解的唯一标识符“重播”数据。 在这个阶段，连接中的新设备会被拼接。Adobe 提供以下两个重播时间间隔：
   * **每日**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   * **每周**：数据每周重播一次，回顾时间范围为7天。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。不过，一周之内的数据无法拼接。

* **隐私（可选）**：在收到与隐私相关的请求时，除了删除请求的身份外，还必须撤消该身份在未经身份验证的事件之间的任何拼合。

不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经验证及已验证的访问。一旦识别出设备，就会从该时间点开始对其进行实时拼合。 无论多长时间，都会跨拼合的数据处理隐私请求。

## 步骤1：实时拼合

实时拼接会尝试在收集时将每个事件与已知设备和渠道进行拼接。 请考虑以下示例，其中Bob将不同的事件记录为事件数据集的一部分。

*收集数据当天显示的数据：*

| 事件 | 时间戳 | 永久性ID (Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 |

{style="table-layout:auto"}

<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Stitched ID after live stitch | Call enter Person ID | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visits your site on a desktop, unauthenticated | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `2` (246 and Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `2` (246 and Bob) |
| `4` | `3579` | - | - | `3579` | Bob accesses your site on a mobile device, unauthenticated | `3` (246, Bob, and 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `3` (246, Bob, and 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `3` (246, Bob, and 3579) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `3` (246, Bob, and 3579) |
-->

新设备上未经身份验证和经过身份验证的事件都将计为单独的人员（临时）。已识别设备上的未经身份验证的事件将实时拼合。

当标识自定义变量与设备关联时，归因起作用。 在以上示例中，除事件1、8、9和10之外的所有其他事件都将进行实时拼合(它们都使用 `Bob` 标识符)。 实时拼合“解析”活动4、6和12的拼合ID。

## 步骤 2：重播拼接

重放拼合会定期（每周一次或每天一次，具体取决于所选的回看窗口）根据它现在识别的设备重新计算历史数据。 如果设备最初在未经身份验证的情况下发送数据，然后登录，则重播拼合会将那些未经身份验证的事件与正确的人员关联起来。 下表与上表所示的数据相同，但根据重播数据显示了不同的数字。

*重播后的相同数据：*

| 事件 | 时间戳 | 永久性ID (Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 | **2人**：<br/>Bob，3579 |

{style="table-layout:auto"}

当标识自定义变量与设备关联时，归因起作用。 在上面的示例中，事件1和10是在重放之后拼接的，因此只有事件8和9处于未拼接状态。 并将人员量度（累积）减少到2。

## 步骤3：隐私请求

当您收到隐私请求时，包含原始用户信息的行会被删除，包含此同一人员信息的任何拼合ID也会被删除。 下表呈现与上表相同的数据，但显示了Bob隐私请求在处理该数据后对数据的影响。 删除了进行Bob身份验证的行（2、3、5、7和11），并删除了Bob作为其他行的临时ID。

*Bob隐私请求后的相同数据：*

| 事件 | 时间戳 | 永久性ID (Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） | 临时ID（登录ID） | 拼合ID（隐私请求后） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 | **2人**：<br/>Bob，3579 |  | **3人**：<br/>246， 3579， 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## 概要

* 拼接会立即拼接已知设备，但不会立即拼接新设备或无法识别的设备。
* 定期重播数据，并根据发现的设备更改连接中的历史数据。
* 在一个数据集上执行实时拼接和重播拼接。 结果产生了一个新的提升数据集，该数据集更适合在与其他数据集（例如呼叫中心数据）结合使用以执行跨渠道分析时使用。
* 隐私请求会删除传播到未经身份验证的行的身份。
