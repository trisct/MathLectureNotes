$\newcommand{\parf}[2]{\frac{\partial #1}{\partial #2}}\newcommand{\secpf}[2]{\frac{\partial^2 #1}{\partial #2^2}}\newcommand{\RR}{\mathbb{R}}\newcommand{\x}{\times}$

# PDE复习笔记

格式：按作业题中出现的概念整理

[TOC]

## 概念
### 第二章（正文）

1. __第二边界条件__ 出现在69页最下方 <span style="color:red">what</span>

2. __Sturm-Liouville 问题__ 定义在67页，指齐次边值特征值问题，具体形式为：
   $$
   \begin{aligned}
   X''+\lambda X=0 &,& 0<x<l\\
   -\alpha_1X'(0)+\beta_1X(0)=0 &&\\
   \alpha_2X'(l)+\beta_2X(l)=0 &&
   \end{aligned}
   $$
   
3. __相容性条件__ 出现在73页 <span style="color:red">what</span>

### 第二章（习题）

1. __Cauchy 问题、混合问题、定解问题__ 出现在100页2、3等多题中。定义在第8页，指__空间区域无界的初值问题__，具体形式为
   $$
   \begin{aligned}
   u_{tt}-a^2\Delta u=f&,& (x,t)\in\RR^n\x(0,\infty)\\\
   u|_{t=0}=\varphi(x)&,& x\in\RR^n\\
   u_t|_{t=0}=\psi(x)&,& x\in\RR^n
   \end{aligned}
   $$
   其中 $x$ 可以是高维变量。若空间求解区域有界（记为$\Omega$），则还需再给出边界条件，一般有以下几种：
   
   - 边界值已知：$u|_{x\in\partial\Omega}$
   - 边界流量已知：$\parf{u}{\mathbf{n}}|_{x\in\partial\Omega}$
   - 边界流量与边界值相关：$\left.\left(\parf{u}{\mathbf{n}}+\alpha u\right)\right|_{x\in\partial\Omega}$
   
   以上三个边界条件一般只给出其中一个，称为__边界条件__。同时给出初值条件和边界条件的问题称为__混合问题__，而Cauchy问题和混合问题统称为__定解问题__。
   
1. __半无界问题、延拓法__ 出现在100页10、11、16题等题中。定义在49页。其中__半无界问题__指求解区域只考虑 $x\geq0$ 且给定 $x=0$ 时边界条件，具体形式如下：
   $$
   \begin{align}
   u_{tt}-a^2u_{xx}=f&,& (x,t)\in[0,\infty)^2\\
   u|_{t=0}=\varphi(x)&,& x\in[0,\infty)\\
   u_t|_{t=0}=\psi(x)&,& x\in[0,\infty)\\
   u|_{x=0}=g(t)&,& t\in(0,\infty)
   \end{align}
   $$
   __延拓法__是指将上述初值条件进行延拓成为全空间定义的方程，从而可用原本的解法。有以下情形：
   
   - $g(t)\equiv0$：一个充分条件是：使得 $u$ 一定是关于 $x$ 的奇函数。即只要解出了一个奇函数解则它一定满足 $u|{x_0}=0$。方法为先把 $\varphi,\ \psi,\ f$ 都关于 $x$ 做奇延拓，如此可保证所得解也是奇函数，从而确保边值条件的满足。
   - $g(t)$ 不恒为 $0$：把 $g(t)$ 这部分去掉即可，即令 $v(x,t)=u(x,t)-g(t)$.
   
3. __边界条件齐次化__ 出现在105页24、25题中，定义在54页。<span style="color:red">[注：可能在别的地方也出现过，定义暂不明确，它可能是指空间导数在边界处为 $0$]</span> 边界条件齐次化是针对空间导数边界条件而言的。在半无界问题中，若将边界条件 $u|_{x=0}=g(t)$ 改成 $u_x|_{x=0}=g(t)$，则在 $g(t)\equiv0$ 时可以采用__偶延拓__来得到自然满足此边界条件的解。

4. __能量不等式__ 出现在106页28题中，定义在44、83页，主要指对波传播过程中能量模的估计，在不同具体问题中，能量不等式形式不同。

## 技巧

### 第二章

#### 混合问题的齐次化（74页、36页）

__边界条件齐次化__ 若边界条件为 $u(0,t)=g_1(t),\ u(l,y)=g_2(t)$，则可做
$$
v=u-\frac{l-x}{l}g_1-\frac{x}{l}g_2
$$
__方程齐次化__ 若方程本身非齐次 $u_{tt}-a^2u_{xx}=f(x,t)$，则可想办法求一个特解 <span style="color:red">(不知道咋整）</span>。

#### 非齐次方程的展开解法（75页）

若求解非齐次方程，可如下做：

1. 求齐次方程的Sturm-Liouville问题的解，得特征函数系
2. 把 $f(x,t)$，$u(x,t)$，$\varphi(x)$， $\psi(x)$ 都按照该特征函数系展开（系数要么是常数，要么是$t$的函数，称为Fourier系数）。
3. 其中，设$u(x,t)$的Fourier系数为$T_n(t)$，则它满足对应的（非齐次）微分方程。

