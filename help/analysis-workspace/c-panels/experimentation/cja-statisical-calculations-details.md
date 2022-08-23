---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# CJA实验面板中的统计计算：详细信息

本页记录了CJA实验面板中使用的详细统计计算。 它面向技术用户。


## 转化率

转化率或 **均值**, *μ<sub>ν</sub>* 对每个变体 *ν* 在实验中，定义为量度总和与分配给该量度的单位数之比， *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="量度均值"></p>
这里，

- *Y<sub>iν</sub>* 是每个单位的量度值 *i*，已分配给给定变体 *ν*.
- 单位总和 *i* 取决于标准化量度的选择。
   - 如果 *人员* 是标准化量度，则每个单位都是一个唯一的人员/用户档案。
   - 如果 *会话* 是标准化量度，则每个单元都是一个唯一的会话。
   - 如果 *事件* 是标准化量度，则每个单位都是一个唯一事件。

通常，应选择此标准化量度以等同于您的独立单位，即如果用户在一个会话中的行为与其在另一个会话中的行为无关，则会话是合理的标准化量度。

根据需要，使用样本标准差，并用表达式


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="量度均值"></p>


## 提升

变体之间的提升度  *ν*、和控制变量  *ν<sub>0</sub>* 是转化率中的相对“增量”，定义为
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="量度均值"></p>
个别兑换率如上文所定义。


## 置信序列

虽然未在CJA实验面板中显示，但单个变体的置信度序列 *ν* 是Adobe使用的统计方法的核心，在此处定义(从 [沃比 — 史密斯等](https://doi.org/10.48550/arXiv.2103.06476))。

> 假设一个人有兴趣估计目标参数 *ψ* （如实验中变体的转化率）。 然后，“固定时间”置信区间(CI)序列与时间一致置信区间(CS)序列之间的二分法可概括如下：
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="量度均值"></p>

换言之，对于常规置信区间，概率可保证目标参数位于值范围内 *A/B<sub>t</sub>* 仅在 *n* (其中 *n* 是示例数)。 相反，对于置信序列，我们保证始终/所有样本量的值 *t*，则目标参数的“true”值位于范围内 *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

这具有一些深层含义，对于在线测试非常重要：
- 当有新数据时，可以选择更新CS。
- 实验可以持续地监控、自适应地停止或持续。
- I类错误在所有停止时间（包括与数据相关的时间）都受到控制。

Adobe使用渐近置信序列，该序列用于具有平均估计的单个变体 *μ* 具有窗体

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="量度均值"></p>

执行:
- *N* 是该变体的单位数
- *σ* 是标准偏差的样本估计值（以前定义）
- *α* 是I类错误的所需级别（或误报概率）
- *ρ*<sup> 2</sup> 是调节CS最紧的样本大小的常量。 Adobe选择了 *ρ*<sup> 2</sup> = 10<sup>-2.8</sup>，适用于在线实验中看到的转化率类型。


## 置信度

Adobe使用的置信度是“任何时候有效”的置信度，该置信度是通过反转平均处理效果的置信度序列来获得的。

确切地说，我们注意到，在两个示例中 *t* 测试两个变体之间的差异，在 *p*&#x200B;值，以及不同值的置信区间。 比如，任何时候都有效 *p*-value可通过反转平均处理效果估算器的（任何有效的）置信序列来获得：
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="量度均值"></p>

我们使用的估计器是逆倾向加权(IPW)估计器。 请考虑 *N = N<sub>0</sub>* + *N<sub>1</sub>* 件数，每个单位$i$的变量分配，标有 *A<sub>i</sub>=0,1* 如果将单位分配给变体ν=0,1。 如果为用户分配了固定概率（倾向） *π<sub>0</sub>,(1-π)<sub>0</sub>)*，其结果量度为 *Y<sub>i</sub>*，则IPW估算器为
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="量度均值"></p>

注意到 *f* 是影响函数，沃比 — 史密斯等 显示此估算器的置信序列为：
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="量度均值"></p>

用经验估计代替分配概率： *π<sub>0</sub> = N<sub>0</sub>/N*，方差项可以用单个样本平均估计表示  *μ<sub>{0,1}</sub>* 及标准差估计，  *σ<sub>{0,1}</sub>* 为：

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="量度均值"></p>


回顾一个带测试统计的常规假设检验 *z =(μ<sub>1</sub> -μ<sub>0</sub>)/ σ<sub>p</sub>*，则$p$值与置信区间之间有对应关系：

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="量度均值"></p>

where *Φ* 是标准正态的累积分布。 适用于任何有效时间 *p*-values，假定上述平均处理效果的置信序列，我们可以反转此关系：
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="量度均值"></p>

最后， **随时有效 *置信度*** is
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="量度均值"></p>


## 宣布实验为结论

对于双臂实验，CJA实验面板会显示一条消息，说明实验是 **结论** 当任何有效置信度超过95%时(即任何有效时间 *p*-value低于5%)。

当存在两个以上变体时，应用邦弗龙尼校正。 为了在 *K* 治疗和单基线（对照）治疗 *K-1* 独立假设检验。 Bonferonni修正意味着，如果在任何有效时，我们拒绝控制与给定变量具有相等手段的零假设 *p*-value低于0.05/(K-1)的阈值。


## 性能最佳的手臂

当宣布实验结果时，显示性能最佳的臂。 这是性能最佳（平均值或转化率最高）的臂，在Set（包括控制）和所有具有 *p* — 值低于Bonferonni阈值。