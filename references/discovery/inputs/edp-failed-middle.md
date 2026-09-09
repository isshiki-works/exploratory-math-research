# Polymath5 的一条未闭合分支：正半定二次型与对偶权重

这里追踪 2010 年 2 月 27 日至 3 月 1 日 Gowers 博客 EDP9 的同一条评论串。为避免把检索工具编号当成评论号，以下使用作者、日期时间和可核查的 WordPress anchor：父评论 [comment-6339](https://gowers.wordpress.com/2010/02/24/edp9-a-change-of-focus/#comment-6339)，后续为 [comment-6358](https://gowers.wordpress.com/2010/02/24/edp9-a-change-of-focus/#comment-6358)、[comment-6363](https://gowers.wordpress.com/2010/02/24/edp9-a-change-of-focus/#comment-6363)、[comment-6364](https://gowers.wordpress.com/2010/02/24/edp9-a-change-of-focus/#comment-6364)。

## 1. 从“可能一行证明”到可计算命题

2 月 27 日 comment-6339 把目标具体化为：对足够大的 $n$，找 $c_{k,d}\ge0$ 与 $b_m\ge0$，使

```math
Q(x)=\sum_{kd\le n}c_{k,d}(x_d+x_{2d}+\cdots+x_{kd})^2-\sum_{m\le n}b_mx_m^2\succeq0,
```

且 $\sum c_{k,d}=1,\ \sum b_m=\omega(n)\to\infty$。在 $x_i=\pm1$ 时第二项恒为 $\sum b_m$，对第一项按 $c_{k,d}$ 平均即可推出某个 HAP 平方和至少为 $\omega(n)$。Gowers 当时的理由是：SDP 能算到较大 $n$，可观察系数形状；正半定性可由平方和分解证明；他因此说，若继续工作，似乎“只是时间问题”。这是公开的希望条件，不是已得证明。

2 月 27 日 2:41 pm 的回复先试验

```math
(a+b)^2+(b+c)^2+(a+c)^2=a^2+b^2+c^2+(a+b+c)^2.
```

同日 4:44 pm 又研究

```math
ax_1^2+a^2(x_1+x_2)^2+a^3(x_1+x_2+x_3)^2+\cdots .
```

配方 $x^2+a(x+y)^2=(1-a)x^2+a(2(x+y/2)^2+y^2/2)$ 确实允许扣掉 $\frac12(a^2x_2^2+a^4x_4^2+\cdots)$，但作者马上指出：对所有公差 $d$ 求和后，扣出的对角总量至多与全部系数同阶，仍然有界；HAP 必须更深地混合。这是局部可行、全局不够的第一次失败。

## 2. 数值 SDP 给出方向，却没有证书

同一页的 2 月 27 日讨论公开了 $n=512,1024,1500$ 的 SDP 对偶解；$n=1500$ 的最佳界仍小于 1，若要超过 1 可能需极大的 $n$。另一个八变量二次型可写成三个平方，使 $n=8$ 的 SDP 界从 $1/4$ 跳到 $1/3$，但没有随 $n$ 增长的模式。

2 月 28 日 comment-6358（1:23 pm）把门槛明确为：$\sum c_{k,d}=1$，并写成 $\sum_iL_i^2+\Delta$，$\Delta=\sum_i d_ix_i^2$，要求 $\sum_i d_i>4$；“4”来自最后取平方根。随后给出 $x_mx_n$ 系数

```math
2\sum_{d\mid(m,n)}\sum_{kd\ge m\vee n}c_{k,d}.
```

同日作者尝试指数衰减的尾权重，并讨论带 $\gcd(m,n)$、$m\vee n$ 的核与平滑截断；无限尾部的控制仍未解决。3 月 1 日 7:47 am，Charikar 还修正了参数依赖：取 $\tau_{k,d}=C_de^{-\alpha kd}$ 才会得到 $2e^{-\alpha(m\vee n)}\sum_{d\mid(m,n)}C_d$ 的非对角系数。不能漏掉指数中的 $d$。

## 3. 反例限制了一个权重选择

Gowers 在 comment-6328（2010-02-26 3:35 pm）已经先取 $C_d=\varphi(d)$，得到 $(m,n)e^{-\alpha(m\vee n)}$ 核；2 月 28 日才提出 $C_d=\Lambda(d)$ 的替代。后一选择的数值动机很弱：$n=2^9$ 到 $2^{10}$ 的界只增加约 0.014，按该速度增加 1 需约乘 $2^{70}$。因此 $\varphi(d)$ 早于 $\Lambda(d)$，不能把 3 月 1 日的改回说成首次发明 $\varphi$ 核。

真正的结构性失败在 comment-6363（2010-03-01 12:28 am）：取 $z_n=e^{2\pi i n/6}$。若 $d$ 是素数幂，则 $d\bmod6\in\{1,2,3,4,5\}$，所以 $r=z_d\ne1$，阶为 6、3 或 2，且

```math
\left|\sum_{j=1}^{k}z_{jd}\right|
=\left|r\frac{1-r^k}{1-r}\right|
\le\frac{2}{|1-r|}\le2.
```

故每个 HAP 平方至多为 4。若实对称矩阵 $M\succeq0$，分解 $M=\sum_j\lambda_ju_ju_j^T$（$\lambda_j\ge0$）后，对复向量仍有 $z^*Mz=\sum_j\lambda_j|u_j\cdot z|^2\ge0$。代入上述 $z$ 到二次型，且 $\sum c_{k,d}=1$，得到 $\sum_m b_m\le4$。所以这类证书不能产生发散的 $\sum b_m$，也不能证明超过 4；它并未排除有限正下界。Gowers 的原话因此应理解为“该方法无法给出所需的无界下界”，不是“不能给出任何正下界”。

comment-6364（2010-03-01 12:31 am）承认忘了 $\sum_{d\mid n}\varphi(d)=n$，随后回到 $C_d=\varphi(d)$，对应核 $\sum_{m,n\le N}(m,n)e^{-\alpha(m\vee n)}x_mx_n$。这只是撤回一个被结构反例击穿的权重，留下新的 gcd 核；原始评论没有给出其正半定分解、无限截断控制或 $\sum b_m\to\infty$ 证书。

来源：Gowers, “EDP9 — a change of focus”, 2010-02-24，以上 anchor 均在：https://gowers.wordpress.com/2010/02/24/edp9-a-change-of-focus/ 。
