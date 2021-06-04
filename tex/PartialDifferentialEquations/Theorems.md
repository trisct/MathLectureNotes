$\newcommand{\derv}[2]{\frac{\ud #1}{\ud #2}}\newcommand{\parf}[2]{\frac{\partial #1}{\partial #2}}\newcommand{\secpf}[2]{\frac{\partial^2 #1}{\partial #2^2}}\newcommand{\RR}{\mathbb{R}}\newcommand{\x}{\times}\newcommand{\ud}{{\rm d}}\newcommand{sqb}[1]{\left[#1\right]}$

# PDE 中的相关定理

## 第二章

### 能量不等式

- 出现位置：44、83、106页。

__能量不等式__是对波传播过程中能量模的估计。

> **定理（一维Cauchy问题（44页）的能量不等式）** 记$Q=\RR\x(0,\infty)$，并设$u\in C^1(\bar Q)\cap C^2(Q)$是一维Cauchy问题的解，则能量不等式给出
> $$
> \int_{\Omega_\tau}[u_t^2(x,\tau)+a^2u_x^2(x,\tau)]\ud x\leq e^{t_0}\sqb{\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\ud x+\iint_{K_\tau}f^2(x,t)\ud x\ud t}\\
> \iint_{K_\tau}[u_t^2(x,\tau)+a^2u_x^2(x,\tau)]\ud x\ud t\leq e^{t_0}\sqb{\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\ud x+\iint_{K_\tau}f^2(x,t)\ud x\ud t}
> $$
> 其中积分区域与$(x_0,t_0)$的特征锥相关，$\Omega_\tau$是特征锥与$t=\tau$的截面，$K_\tau$则是特征锥在$t=0$与$t=\tau$之间的所有区域。
>
> _证明_ 首先考虑把波动方程乘上$u_t$后在$K_\tau$上积分
> $$
> \iint_{K_\tau}u_t(u_{tt}-a^2u_{xx})\ud x\ud t=\iint_{K_\tau}u_tf\ud x\ud t
> $$
> 式左可通过Green公式转为$K_\tau$边界上积分，去掉其中非负项之后（对应特征锥侧面），可得
> $$
> \frac{1}{2}\int_{\Omega_\tau}\sqb{u_t^2+a^2u_x^2}\ud x-\frac{1}{2}\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\leq\iint_{K_\tau}u_tf\ud x\ud t
> $$
> 式右则由代数不等式放缩：
> $$
> \iint_{K_\tau}u_tf\ud x\ud t\leq\frac{1}{2}\iint_{K_\tau}u_t^2\ud x\ud t+\frac{1}{2}\iint_{K_\tau}f^2\ud x\ud t
> $$
> 可得
> $$
> \int_{\Omega_\tau}\sqb{u_t^2+a^2u_x^2}\ud x-\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)\leq\iint_{K_\tau}u_t^2\ud x\ud t+\iint_{K_\tau}f^2\ud x\ud t
> $$
> 继续往后则需要借助Gronwall不等式，令
> $$
> G(\tau)=\iint_{K_\tau}\sqb{u_t^2+a^2u_x^2}\ud x\ud t=\int_0^\tau\int_{\Omega_t}\sqb{u_t^2+a^2u_x^2}\ud x\ud t
> $$
> 则它满足
> $$
> \derv{G(\tau)}{\tau}=\int_{\Omega_\tau}\sqb{u_t^2+a^2u_x^2}\ud x\\
> \leq\iint_{K_\tau}u_t^2\ud x\ud t+\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)+\iint_{K_\tau}f^2\ud x\ud t\\
> \leq\iint_{K_\tau}(u_t^2+a^2u_x^2)\ud x\ud t+\int_{\Omega_0}(\psi^2+a^2\varphi_x^2)+\iint_{K_\tau}f^2\ud x\ud t\\
> =G(\tau)+F(\tau)
> $$
> 由Gronwall不等式（需要$G(\tau)$非负连续可微，$G(0)=0$，以及$F(\tau)$非负且关于$\tau$是非降的可积函数），有
> $$
> \derv{G(\tau)}{\tau}\leq e^\tau F(\tau),\quad G(\tau)\leq(e^\tau-1)F(\tau)
> $$
> 即得能量不等式。

