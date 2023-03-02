# 測度
可測空間 $(X, \mathcal{F})$ の上の写像 $\mu$ が以下の性質を持つとき、 $\mu$ を測度(可算加法的測度)と呼ぶ。

1. $\mu:\mathcal{F} \rightarrow \mathbb{R}_{\geq 0}$
2. $\mu(\emptyset) = 0$
3. $\lbrace A_n \rbrace_{n\in\mathbb{N}} \subset\mathcal{F}$ かつ $A_i \cap A_j = \emptyset \ (\forall i \neq j)$ のとき、

$$
    \mu \Bigl( \textstyle\bigcup\limits_{n=1}^\infty A_n \Bigr) = \sum\limits_{n=1}^\infty \mu(A_n)
$$

この時、 $\mathcal{F}$ の元は可測集合と呼ばれ、数学的構造 $(X,\mathcal{F}, \mu)$ は測度空間と呼ばれる。

# ルベーグ積分

## ルベーグ外測度
区間 $I=[a_1,b_1]\times [a_2,b_2]\times\dotsb\times [a_n,b_n]\quad (a_i\leq b_i)$ に対し、その体積を $\operatorname{vol}(I) := (b_1-a_1)(b_2-a_2)\dotsb(b_n-a_n)$ と定義する。全体集合 $\mathbb{R}^n$ を区間の可算列によって被覆できるから、 $\mathbb{R}^n$ の任意の部分集合 $E$ が上記の区間の可算合併によって被覆できることは明らかである。そこで $E$ のルベーグ外測度を

$$
    \mu^*(E):= \inf\Big\lbrace \sum_{j=1}^{\infty}\hbox{vol}(I_j): \bigcup_{j=1}^{\infty} I_j \supseteq E \Bigr\rbrace
$$

と定義する。ただし下限 $\inf$ は $E$ を被覆する任意の基本集合列 $I_j$ にわたってとるものとする。

これにより、外測度 $\mu^* : \mathfrak{P}(\mathbb{R}^n) \rightarrow \mathbb{R}_{\geq 0}$ が定まる。

## ルベーグ測度
全体集合 $\mathbb{R}^n$ の部分集合 $A$ がルベーグ可測であるとは、 $\mathbb{R}^n$ の任意の部分集合 $S$ に対して、カラテオドリの条件

$$
    \mu^* = \mu^* (S \cap A) + \mu^* (S \cap A^c)
$$

を満たす事とする。

ルベーグ可測な集合族全体は、 $σ$ 加法族を為す。ルベーグ可測集合 $A$ に対するルベーグ測度 $\mu$ を $\mu(A) := \mu^*(A)$ と定義する。


## 有限加法族
集合 $\Omega$ とその上の冪集合 $\mathfrak{P}(\Omega)$ に対し、 $\Omega$ の部分集合族 $\mathcal{F} \subset \mathfrak{P}(\Omega)$ が 有限加法族であるとは、以下の性質を持つことである。

1. $\Omega\in\mathcal{F}$
2. $A\in\mathcal{F}\Rightarrow A^c(=\Omega\setminus A)\in\mathcal{F}$
3. $ \lbrace A_n \rbrace _{n=1}^k \subset \mathcal{F} \Rightarrow \bigcup\limits_{n=1}^{k} A_n \in \mathcal{F} $

## $\sigma$ 加法族
集合 $\Omega$ とその上の冪集合 $\mathfrak{P}(\Omega)$ に対し、 $\Omega$ の部分集合族 $\mathcal{F} \subset \mathfrak{P}(\Omega)$ が $\sigma$ 加法族であるとは、以下の性質を持つことである。

1. $\Omega\in\mathcal{F}$
2. $A\in\mathcal{F}\Rightarrow A^c(=\Omega\setminus A)\in\mathcal{F}$
3. $ \lbrace A_n \rbrace _{n\in\mathbb{N}} \subset \mathcal{F} \Rightarrow \bigcup\limits_{n=1}^{\infty} A_n \in \mathcal{F} $

この時、集合 $\Omega$ とその上の$\sigma$ 加法族 $\mathcal{F}$ との対 $(\Omega, \mathcal{F})$ は可測空間と呼ばれる集合体になる。

### $\sigma$ 加法族の生成

## 可測関数


## とりあえず

ルベーグ積分は

$$
    \int f d\mu , \int f(x) d\mu(x) , \int f(x)\mu(dx)
$$

という書き方をする。

## 押し出し測度(誘導測度)
可測空間 $(X_1, \Sigma_1),(X_2, \Sigma_2)$ における可測関数 $f: X_1 \rightarrow X_2$ 及び測度 $\mu : \Sigma_1 \rightarrow [0, +\infty]$ 
が与えられたとき、 $\mu$ の押し出し測度 $f_*(\mu):\Sigma_2 \rightarrow [0, +\infty]$ は、 $B\in\Sigma_2$ のとき、

$$
    f_*(\mu)(B) := \mu(f^{-1}(B)) 
$$

とされる。書き方がいろいろある。 $\mu \circ f^{-1}$ など
