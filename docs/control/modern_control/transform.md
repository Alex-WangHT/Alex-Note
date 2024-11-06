# Laplace变换和z变换

!!! note "本内容参考书目与内容"

    [1]:Alan S Oppenheim:Signal and Systems,Second Edition的Chapter 9和Chapter 10

## 引言

在工程中，所有的物理系统都可以用微分方程或者是差分方程的方式来定量的表达，对系统的分析本质上来说就是求解系统的微分方程或差分方程的过程。而Laplace变换适用于求解微分方程，z变换适用于求解差分方程。

## 一、Laplace变换

### 1.1、Laplace变换与Laplace反变换

拉普拉斯变换的公式如下：
$$
L[x(t)]=F(s)={\int_{0}^{+\infty}}{f(t)}{e^{-st}}{\rm d}t
$$
其中$s={\sigma}+j{\omega}$是一个复数。  
对于双边Laplace变换，有：
$$
F(s)={\int_{-\infty}^{+\infty}}{f(t)}{e^{-st}}{\rm d}t
$$
而Laplace反变换如下：
$$
f(t)={\frac{1}{2{\pi}j}}{\int_{{\sigma}-j{\infty}}^{{\sigma}+j{\infty}}}{f(t)}{e^{st}}{\rm d}t
$$

### 1.2、Laplace变换的收敛域（Region of Convergence）

我们来看以下两个等式：
$$
h_1(t)=e^{-at}u(t)
$$
$$
h_2(t)=-e^{-at}u(-t)
$$
对$h_1(t)$与$h_2(t)$作Laplace变换，结果如下：
$$
H_1(s)=\frac{1}{s+a}\quad{\mathcal{Re}\{s\}>-a}
$$
$$
H_2(s)=\frac{1}{s+a}\quad{\mathcal{Re}\{s\}<-a}
$$
我们能看到对于Laplace变换来说，s域的表达式和……。这被称为收敛域。

#### 1.2.2 收敛域的性质

1、  
2、  
3、  
4、  
5、  
6、  
7、  

### 1.3、Laplace变换的性质

#### 1.3.1、线性性质：  

如果:  
$$
x_1(t)\xleftrightarrow{\mathcal{L}}X_1(s)\quad\{{{\rm ROC}=R_1}\}
$$
并且：
$$
x_2(t)\xleftrightarrow{\mathcal{L}}X_2(s)\quad\{{{\rm ROC}=R_2}\}
$$
则有：
$$
ax_1(t)+bx_2(t)\xleftrightarrow{\mathcal{L}}aX_1(s)+bX_2(s){\quad \{{\rm ROC}=R_3,\{R_1 \cap R_2\} \subseteq R_3\}}
$$

#### 1.3.2、时移性质：

如果：
$$
x(t)\xleftrightarrow{\mathcal{L}}X(s)\quad\{{{\rm ROC}=R}\}
$$
则有：
$$
x(t-t_0)\xleftrightarrow{\mathcal{L}}e^{-st_0}X(s)\quad\{{{\rm ROC}=R}\}
$$

#### 1.3.3、复频域移动：

如果：
$$
x(t)\xleftrightarrow{L}X(s)\quad\{{{\rm ROC}=R}\}
$$
则有：
$$
e^{s_0t}x(t)\xleftrightarrow{\mathcal{L}}X(s-s_0)\quad\{{{\rm ROC}=R+{\rm Re\{s_0\}}}\}
$$
如果$s=j\omega$，则:
$$
e^{j\omega_0t}x(t)\xleftrightarrow[]{\mathcal{L}}X(s-s_0)\quad\{{{\rm ROC}=R}\}
$$

#### 1.3.4、时域缩放性质：

如果：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)\quad\{{{\rm ROC}=R}\}
$$
则有：
$$
x(at)\xleftrightarrow[]{\mathcal{L}}{\frac{1}{{|a|}}}{X({\frac{s}{a}})}\quad\{{{\rm ROC}=|a|R}\}
$$

#### 1.3.5、共轭性质：

如果：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)\quad\{{{\rm ROC}=R}\}
$$
则有：
$$
x^*(t)\xleftrightarrow[]{\mathcal{L}}{X^*({s^*})}\quad\{{{\rm ROC}=R}\}
$$
当$x(t)$为实数域上的函数时，$X(s)=X^*(s^*)$。

#### 1.3.6、卷积性质：

如果:  
$$
x_1(t)\xleftrightarrow[]{\mathcal{L}}X_1(s)\quad\{{{\rm ROC}=R_1}\}
$$
并且：
$$
x_2(t)\xleftrightarrow[]{\mathcal{L}}X_2(s)\quad\{{{\rm ROC}=R_2}\}
$$
则有：
$$
x_1(t)*bx_2(t)\xleftrightarrow[]{\mathcal{L}}X_1(s)X_2(s)\quad\{{\rm ROC}=R_3,\{ R_1 \cap R_2\} \subseteq R_3 \}
$$

#### 1.3.7、时域微分性质：

如果：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)\quad\{{\rm ROC}=R\}
$$
则有：
$$
\frac{{\rm d} x(t)}{{\rm d}t}\xleftrightarrow[]{\mathcal{L}}{sX({s})}\quad\{{\rm ROC}=R_1,\{R\subseteq R_1\}\}
$$

#### 1.3.8、频域微分性质：

如果：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)\quad\{{\rm ROC}=R\}
$$
则有：
$$
-tx(t)\xleftrightarrow[]{\mathcal{L}}\frac{{\rm d} X(s)}{{\rm d}s}\quad\{{\rm ROC}=R\}
$$

#### 1.3.9、时域积分性质：

如果：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)\quad\{{\rm ROC}=R\}
$$
则有：
$$
\int_{-\infty}^{t}x(\tau){\rm d}{\tau}\xleftrightarrow[]{\mathcal{L}}{\frac{X(s)}{s}}\quad\{{\rm ROC}=R_1,\{R \cap \{{\mathcal{Re}\{s\}>0}\}\}\subseteq R_1  \}
$$

#### 1.3.10、初值定理与终值定理：

有：
$$
x(t)\xleftrightarrow[]{\mathcal{L}}X(s)
$$
如果当$t<0$有$x(t)=0$,并且$x(t)$在$t=0$时不包括脉冲分量或更高阶的不连续点，则有：
$$
x(0^+)=\lim_{s \rightarrow {\infty}}{sX(s)}
$$
如果当$t<0$有$x(t)=0$,并且$x(t)$在${t \rightarrow {\infty}}$有一个有限的极限值，则有：
$$
\lim_{t \rightarrow {\infty}}=\lim_{s \rightarrow {0}}{sX(s)}
$$

### 1.4、线性时不变系统的稳定性和因果性与其Laplace变换的关系

#### 1.4.1、因果性

#### 1.4.2、稳定性

## 二、z变换
