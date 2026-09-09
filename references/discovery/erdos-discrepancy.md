# Erdős discrepancy：从 Polymath5 的有限探索到 Tao 2015

这里追踪的是路线选择和失败证据，不把时间先后自动解释为因果。问题是：对任意 $\pm1$ 序列，某个齐次算术级数上的部分和是否必然无界。

## 1. 2010：有限计算先改变了“什么值得研究”

2010 年 1 月 6 日，Gowers 回顾早期实验：最长的 discrepancy-2 序列远长于已知乘法序列，因此“完全乘法”是强约束，不能直接当作一般问题的模型；同时乘法结构仍是低差异候选的自然来源（[Gowers, 2010-01-06](https://gowers.wordpress.com/2010/01/06/erdss-discrepancy-problem-as-a-forthcoming-polymath-project/)）。1 月 9 日的新数据给出多个长度 1124 的序列，并显示它们只呈现近似乘法行为；评论中甚至发现强加 $T_2x=-x$ 很快得到长度 584，但解除约束后只到 622，说明“结构有帮助”不等于精确结构是答案（[Gowers, 2010-01-09](https://gowers.wordpress.com/2010/01/09/erds-discrepancy-problem-continued/)）。

1 月 16 日的阶段总结把当时可见证据说得很清楚：长序列“probably”有乘法结构，但这种结构是 approximate 而非 exact；这与 DHJ 中理论、实验彼此分离不同，EDP 可以让实验直接改变猜想的可信度（[Gowers, 2010-01-16](https://gowers.wordpress.com/2010/01/16/the-erds-discrepancy-problem-v/)）。1 月 19 日正式方案因此提出三步：先证明完全乘法序列不能有界差异，再把一般反例“clean up”为准乘法，最后推广到准乘法；Gowers 同时承认这是受 1124 结构启发的方案，早期建议也可能再次被放弃（[EDP1, 2010-01-19](https://gowers.wordpress.com/2010/01/19/edp1-the-official-start-of-polymath5/)）。

这里的决策信号是有限计算提供了模型选择信息：精确完全乘法太窄，准乘法或“近似结构”更值得追踪。它没有证明一般序列可化为准乘法；“接近”是实验观察，clean-up 是待证命题。

## 2. 乘法化简的阶段性成果与停滞

2010 年 2 月 2 日的总结记载：一条把问题化到 $\mathbb F_2$ 多项式空间的变体很快被否定；与此同时，完全乘法序列 discrepancy 大于 2 的人工证明正在形成，作者称还需一点时间（[Gowers, 2010-02-02，2 月存档](https://gowers.wordpress.com/2010/02/)）。这提供了一个局部可发表成果，却没有给出一般 EDP。

2 月 5 日，Gowers 写明 Tao 已把问题“reduction”到乘法函数，Polymath5 因而几乎都在研究乘法函数；但他也记录了分类路线的失败预兆：贪心选素数值的算法表现很差，另一规则却表现较好；实验提示低增长部分和不必都具有明显字符结构，因此“character-like / non-character-like”二分可能不够，或许需要统一证明（[EDP6, 2010-02-05](https://gowers.wordpress.com/2010/02/05/edp6-what-are-the-chances-of-success/)）。2 月 8 日又记载 Gowers 的一个策略因对 $\lambda_3,\mu_3$ 作出错误预测而被放弃；同页同时保留了完全乘法 discrepancy>2 的人工证明继续推进（[2010-02-08](https://gowers.wordpress.com/2010/02/)）。

因此，2010 年已有计算结构、平均化的乘法归约和特例证明尝试，但尚未得到排除所有相关乘法函数的估计。最初设想的直接 clean-up 与后来实际得到的平均化归约并不是同一命题，不能因前者未闭合就说全部归约失败。Gowers 2 月 5 日还说，即使不解决原问题，博客材料也已足以形成关于计算现象的论文；这说明中间工作的独立价值，不表明已接近一般定理。

## 3. 2014：1160/1161 是有限边界，不是无限问题的桥

Konev–Lisitsa 的 v1 论文（2014-02-10）明确给出：存在长度 1160、discrepancy 2 的序列，并用 SAT 不可满足性证明不存在长度 1161 的 discrepancy-2 序列；同时只给出 discrepancy 3 的部分结果，包括长度 13000 的例子（[arXiv v1 摘要与引言](https://arxiv.org/abs/1402.2184v1)，§1）。这解决的是固定常数 $C=2$ 的有限截断；它不等于证明所有无限序列无界，也没有给出一般 $C$ 的手工机制。

Gowers 在 2014 年回访时特别指出，Polymath5 的 1124 数据曾让他相信 1124 是正确上界；SAT 发现 1160 后，他把这称为经验性证据的危险，并转述作者对巨大不可满足性证书可接受性的疑问。但他紧接着明确说自己对这类巨大计算证明“relaxed”，认为常规证明同样可能出错（[EDP 2014 回访](https://gowers.wordpress.com/2014/02/11/recent-news-concerning-the-erdos-discrepancy-problem/)）。改变的是对计算外推的信任边界：1124 没有成为数学上限，1160/1161 也只证明一个有限断点；SAT 证书证明了有限命题，却没有自动提供无限论证。

## 4. 2015：平均相关工具重新激活旧的两段式路线

9 月 11 日的博客结论仍是条件性的：修正版、非渐近的 Elliott 猜想若成立，则推出 EDP；博客明确把相关猜想列为开放问题，并非已经用对数平均工具完成证明（[Tao, 2015-09-11](https://terrytao.wordpress.com/2015/09/11/the-erdos-discrepancy-problem-via-the-elliott-conjecture/)）。随后 9 月 17 日提交的两份 v1 才应分开记载：对数平均 Chowla/Elliott 工具论文为 [arXiv:1509.05422v1](https://arxiv.org/abs/1509.05422v1)，EDP 论文为 [arXiv:1509.05363v1](https://arxiv.org/abs/1509.05363v1)。因此不能把 9 月 11 日的条件定理和 9 月 17 日的平均相关证明混成一个时点。

关于归约，2010 年已经出现随机/平均化桥梁，不能说“从任意序列到乘法函数完全没有完成”。9 月 11 日博客的 Proposition 4（不是 EDP 论文的编号）先表述为：若有界差异反例存在，则可得到随机完全乘法函数的二阶矩控制；在博客 Remark 6 中，Tao 特别说明 Polymath5 原始表述是：对每个 $N$，存在一个可随 $N$ 变化的确定完全乘法 $g$，使 $N^{-1}\sum_{n\le N}|\sum_{j\le n}g(j)|^2\ll1$。这一本来很有用，但 $g$ 随 $N$ 变化，不便接到无限论证。Tao 的改造是改用一个随机 $g$，对全部 $n$ 获得统一的期望二阶矩控制（[博客 Proposition 4、Remark 6](https://terrytao.wordpress.com/2015/09/11/the-erdos-discrepancy-problem-via-the-elliott-conjecture/)）。EDP v1 正文应定位到 §2 的 Fourier reduction，而非把该博客 Proposition 4 当成论文编号（[EDP v1，§2](https://arxiv.org/abs/1509.05363v1)）。未完成的核心是足以排除所有这类（随机）完全乘法函数的增长估计。

这条时间线仍不证明 2010 年参与者预见了 2015 年平均相关定理；可见的因果接合点只是：Polymath5 的归约和末端拟态特征论证后来被纳入 Tao 的框架，而 2015 年新证明的平均工具补上了中间的“拟态”控制。

最应保留的因果边界是：2010 年工作留下可复用的平均化归约；2014 年 SAT 给出有限边界并暴露外推危险；2015 年新平均相关估计把反例约束到拟态特征的情形，再由旧论证的推广排除该情形。新估计与旧末端论证的作用不同。公开记录没有证明哪条失败路线直接导致新工具，也未覆盖线下工作。
