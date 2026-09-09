# 电路下界：受限模型、Natural Proofs 与算法路线

## 受限模型为何值得投入

1980 年代可见的理由是受限模型给出了可检验的结构性问题：固定深度、门型或单调性，目标函数仍可显式写出。Furst–Saxe–Sipser、Ajtai、Yao、Håstad 对 AC⁰ 的 PARITY 下界，以及 Razborov 1985 对 CLIQUE 的单调下界，证明这条路线确能产出强定理。关于“逐步解除限制、最终触及一般下界”的表述来自 Williams 2011 的事后回顾，不能当作当时研究者的同期决策记录；该回顾同时说 Razborov 的单调技术后来“probably would not extend”到一般电路（[Williams 2011, pp.1–2](https://www.cs.cmu.edu/~ryanw/acc-lbs-ccc.pdf)）。

Razborov 的原论文是 1985 年（[原论文及全文入口](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&option_lang=eng&paperid=9192&wshow=paper)）：图 CLIQUE 函数具有超多项式单调复杂度。Alon–Boppana 1987 将其改进为指数下界：团大小约为 $\frac14(m/\log m)^{2/3}$ 时，规模至少 $\exp(\Omega((m/\log m)^{1/3}))$；对显式 NP 函数的最好界为 $\exp(\Omega(n^{1/4}(\log n)^{1/2}))$（[原文 PDF，pp.1–2](https://web.math.princeton.edu/~nalon/PDFS/Publications/The%20monotone%20circuit%20complexity%20of%20Boolean%20functions.pdf)）。成果真正增加了近似方法、偏序/图结构和单调复杂度工具；没有给出一般电路下界，因为 NOT 门超出了模型。

代数方法也在受限常深度模型中成功。Smolensky 1987 给出固定模数门类上的指数型下界（[STOC 1987 原论文](https://doi.org/10.1145/28395.28404)）。Razborov 1989 对“近似方法”作了同期边界分析：总变量数为 $n$、函数实际依赖 $n_0$ 个变量时，定义中的近似距离满足 $\rho(f,M)\le O(n_0n)$（定理 2.1，印刷页168）；指定的概率估计版本至多给出 $O(n_0)$（定理 2.4，印刷页169）。因此，没有辅助变量时，前一种方法至多产生二次规模的界；单调模型中的指数成功不能直接推广。他也研究了引入大量辅助变量的通用模型，但其巨大规模和非规范构造不构成便宜的通用下界工具（[原文](https://people.cs.uchicago.edu/~razborov/files/approx.pdf)，引言、定理2.6–2.7）。这些是当时可见的数学限制，不是“没人愿意继续”的证据。ACC 的强下界后来仍长期停滞，Williams 在2011年对此作了回顾（[2011, p.2](https://www.cs.cmu.edu/~ryanw/acc-lbs-ccc.pdf)）。

## Natural Proofs 究竟排除了什么

Razborov–Rudich 1997 对真值表集合 $F_n$ 要求性质含有 $C_n^*$：(i) **constructivity**：从长度 $2^n$ 的真值表判定成员，时间对真值表长度为多项式（默认 $2^{O(n)}$）；(ii) **largeness**：$|C_n^*|\ge 2^{-O(n)}|F_n|$；(iii) **usefulness**：落入该性质的函数序列不在目标小电路类。定义见 [RR97, pp.3–4](https://www1.karlin.mff.cuni.cz/~krajicek/rr.pdf)。

核心结论是条件性的：若存在硬度为 $2^{n^\varepsilon}$ 的伪随机生成器，则不存在满足这些条件、能证明一般电路超多项式下界的自然性质；论文另无条件指出，自然证明不能给离散对数函数一般电路指数下界（[RR97 摘要 pp.1–2](https://www1.karlin.mff.cuni.cz/~krajicek/rr.pdf)）。对 AC⁰-natural 证明，论文无密码学假设地说明：足以证明 PARITY 的这类性质不能证明 Razborov–Smolensky 的 AC⁰[q] 下界（[RR97, pp.1–2、7–8](https://www1.karlin.mff.cuni.cz/~krajicek/rr.pdf)）。所以不能说 Natural Proofs 说明“一般下界不可得”：它针对一大类三条件方法，密码学部分依赖 PRG 假设；作者还明确说对计数/对角化能否解决障碍“nothing to say”（[RR97, pp.4–5](https://www1.karlin.mff.cuni.cz/~krajicek/rr.pdf)）。单调证明也缺少“随机单调函数”的可用定义，不能机械套 largeness。

这提供了研究决策工具：先检查新性质是否会 naturalize，而非把失败归因于难题本身。RR 所谓“当前技术倾向自然”来自既有证明分析，不是多数研究者调查；他们没有证明未来证明必须自然。密码学条件也不能升级为无条件不可能性。

## 算法到下界的有限转向

Williams 2010 的作者版本给出的精确范围是：若对某些自然 NP/BPP 问题存在相对朴素穷举的“小幅”算法改进，则蕴含 NEXP ∉ P/poly、LOGSPACE ≠ NP；这是条件蕴含，不是已获得一般电路下界。其原始稿还明确区分：对所有问题的普遍改进尚未知，且把改进落实到一般 CIRCUIT-SAT 仍是挑战（[Williams 2010, 摘要及 pp.4–5](https://people.csail.mit.edu/rrw/improved-algs-lbs2.pdf)）。2011 年他把方案落实到 ACC：先给 ACC-SAT 次指数改进，再转移为下界。定理是 NTIME[2^n] 不具有多项式大小非一致 ACC 电路；并且对每个深度 $d$、模数 $m$，存在 $\delta>0$，使 E^NP 中某语言没有深度 $d$、规模 $2^{n^\delta}$ 的 ACC 电路（[2011, Theorems 1.1–1.2, pp.1–2](https://www.cs.cmu.edu/~ryanw/acc-lbs-ccc.pdf)）。

这是工具增加而非 P vs NP 解决：目标在 NEXP/E^NP，模型仍是 ACC；证明组合 SAT 算法、时间层级、压缩和局部可检验性。若一般电路可被次指数 ACC 模拟，或 SAT 再快一点，才可能触及另一前沿（p.2）；不能外推为一般电路突破。

## 最能改变判断的五点

1. 单调 CLIQUE 的精确指数界说明受限模型能产生可复用工具，也同时暴露 NOT 门这个边界。
2. AC⁰ 到 AC⁰[MOD] 的分层表明，加一个门类可能需要全新数学；ACC 停滞是局部失败，不是所有下界的已证障碍。
3. Natural Proofs 在 PRG 假设下排除“构造性+大+有用”方法类；不排除不自然方法，也不评价计数/对角化。
4. Williams 路线的可检验承诺是“更快 SAT ⇒ 同类下界”，2011 年在 ACC 上兑现，范围有限但反馈真实。
5. 可支持的量词始终是特定模型、特定参数或特定假设；没有证据声称多数研究者已放弃某路线，或 P vs NP 客观不可推进。
