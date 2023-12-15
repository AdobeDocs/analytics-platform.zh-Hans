---
title: 拼合的工作原理
description: 了解拼接的概念
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
source-git-commit: 2c650cf688112be1e6bf16c0863e743d61f9c35c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 20%

---

# 拼合的工作原理

拼合过程对给定数据集中的数据至少进行两次传递：

* **实时拼合**：尝试在每次点击（事件）进入时拼合点击。 来自对数据集“最新”的设备（从未经过身份验证）的点击通常不会在此级别拼合。 来自已识别设备的点击将立即拼合。

* **重播拼合**：根据已学到的唯一标识符（临时ID）“重播”数据。 在此阶段，来自先前未知设备（永久ID）的点击将被拼合（到临时ID）。 Adobe 提供以下两个重播时间间隔：
   * **每日**：数据每天重播，回顾时间范围为24小时。 此选项的优势在于重播更频繁，但未经身份验证的访客必须在访问您网站的同一天进行身份验证。
   * **每周**：数据每周重播一次，回顾时间范围为7天。 此选项的优势在于允许未经身份验证的会话在更加宽松充裕的时间范围内进行身份验证。但是，只有到下一次每周重放时，才会重新处理不到一周的未拼合数据。

* **隐私（可选）**：在收到与隐私相关的请求时，除了删除所请求的身份之外，还必须撤消该身份在未验证事件之间的任何拼合。

不会重放回看窗口以外的数据。访客必须在给定的回看窗口内进行身份验证，才能同时识别未经验证及已验证的访问。一旦识别出设备，就会从该时间点开始对其进行实时拼合。

## 步骤1：实时拼合

实时拼接会尝试在收集时将每个事件拼接到已知设备和渠道。 请考虑以下示例，其中Bob将不同的事件记录为事件数据集的一部分。

*收集数据当天显示的数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **鲍勃** |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **鲍勃** | |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **鲍勃** |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 |

新设备上未经身份验证和经过身份验证的事件都将计为单独的人员（临时）。已识别设备上的未经身份验证的事件将进行实时拼合。

当标识的自定义变量与设备关联时，归因有效。 在以上示例中，除事件1、8、9和10之外的所有其他事件都将进行实时拼合(它们都使用 `Bob` 标识符)。 实时拼接“解析”事件4、6和12的拼接ID。

延迟的数据（时间戳超过24小时之前的数据）会尽最大努力处理，同时会优先拼合当前数据以获得最高质量。

## 步骤 2：重播拼接

重播拼合会定期（每周一次或每天一次，具体取决于选择的回顾时间范围）根据其当前识别的设备重新计算历史数据。 如果设备最初在未经身份验证的情况下发送数据，然后登录，则重播拼接会将那些未经身份验证的事件与正确的人员关联起来。 下表与上表所示的数据相同，但根据重播数据显示了不同的数字。

*重播后的相同数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **鲍勃** |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 |
| 4 | 2023-05-12 12:04 | 246 | - | **鲍勃** | 鲍勃 |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 |
| 6 | 2023-05-12 12:06 | 246 | - | **鲍勃** | 鲍勃 |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 | 鲍勃 |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **鲍勃** |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **鲍勃** | 鲍勃 |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 | **2人**：<br/>鲍勃，3579 |

{style="table-layout:auto"}

当标识的自定义变量与设备关联时，归因有效。 在以上示例中，事件1和10是在重放之后拼接的，仅留下事件8和9未拼接。 并将“人员”量度（累积）减少到2。

## 步骤3：隐私请求

当您收到隐私请求时，包含原始用户信息的行会被删除，包含此同一人员信息的任何拼合ID也会被删除。 下表显示与上表相同的数据，但显示了Bob隐私请求在处理该数据后对数据的影响。 删除了Bob进行身份验证的行（2、3、5、7和11），同时还删除了Bob作为其他行的临时ID。

*向Bob发出隐私请求后的相同数据：*

| 事件 | 时间戳 | 永久性ID(Cookie ID) | 临时ID（登录ID） | 拼合ID（实时拼合后） | 拼合ID（重播后） | 临时ID（登录ID） | 拼合ID（隐私请求后） |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **鲍勃** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **鲍勃** | 鲍勃 | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **鲍勃** | 鲍勃 | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 | 鲍勃 | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **鲍勃** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | 鲍勃 ![向右箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | 鲍勃 ![向下箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 鲍勃 ![向上箭头](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **鲍勃** | 鲍勃 | - | 81911 |
| | | **3台设备** | | **4人**：<br/>246，鲍勃， 3579， 81911 | **2人**：<br/>鲍勃，3579 |  | **3人**：<br/>246， 3579， 81911 |


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

* 拼接会立即拼接来自已知设备的事件，但不会立即拼接来自新设备或无法识别的设备的事件。
* 定期重播数据，并根据发现的设备更改连接中的历史数据。
* 在一个数据集中执行实时拼接和重播拼接。 结果是产生一个新的提升数据集，该数据集更适合在与其他数据集（例如呼叫中心数据）结合使用时执行跨渠道分析。
* 隐私请求会删除传播到未经身份验证的行的身份。
