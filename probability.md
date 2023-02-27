# 確率と確率分布

☆: 覚える必要ないが説明上必要な内容

☆☆: 覚えてほしいが難しいので軽めに流してほしい内容

☆☆☆: 覚えてほしい内容

## 標本空間(☆☆☆)
標本空間とは、起こりうる結果全体の集合の事をいう。

ここでは標本空間は $\Omega$ 、標本空間の元を $\omega$ と表記する。 

## 事象(☆☆)
標本空間の部分集合の内、確率をもつものを事象と呼ぶ。ここでは基本的に事象は $A$ で表記する。すべての事象 $A$ を集めた集合族 $\mathcal{F}$ は完全加法族である必要がある。これ以上分解できない事象を根元事象、複数の根元事象の和集合を複合事象という。つまり $\mathcal{F}$ は、根元事象から生成される最小の完全加法族となっている。

### 完全加法族と可測空間(☆)
集合 $\Omega$ とその上の冪集合 $\mathfrak{P}(\Omega)$ に対し、 $\Omega$ の部分集合族 $\mathcal{F} \subset \mathfrak{P}(\Omega)$ が完全加法族であるとは、以下の性質を持つことである。

1. $\Omega\in\mathcal{F}$
2. $A\in\mathcal{F}$ に対して $A^c\in\mathcal{F}$
3. $(A_n)_{n\in\mathbb{N}}\subset\mathcal{F}$ に対して $\bigcup\limits_{n=1}^{\infty} A_n \in \mathcal{F}$

この時、集合 $\Omega$ とその上の完全加法族 $\mathcal{F}$ との対 $(\Omega, \mathcal{F})$ は可測空間と呼ばれる集合体になる。

## 確率測度と確率空間(☆☆)
可測空間 $(\Omega, \mathcal{F})$ の上の写像 $P$ が以下の性質を持つとき、$P$ を確率測度と呼ぶ。

1. $P:\mathcal{F} \rightarrow [0, 1]$
2. $A_n \in\mathcal{F}, n\in\mathbb{N}$ かつ $A_i \cap A_j = \emptyset \ (\forall i \neq j)$ のとき、
$$
    P \Bigl( \textstyle\bigcup\limits_{n=1}^\infty A_n \Bigr) = \sum\limits_{n=1}^\infty P(A_n)
$$
3.  $P(\Omega)=1$

この時、3つ組 $(\Omega, \mathcal{F}, P)$ を確率空間といい、可測集合$A\in\mathcal{F}$ を事象と呼ぶ。また、 $A$ による $P$ の評価 $P(A)$ を $A$の確率と呼ぶ。


### 確率空間の例(前半☆☆☆後半☆☆)
コインを投げて裏と表が出る確率が、それぞれ $1/2$ であることを確率空間として表したとき、例えば次のようになる。

- $\Omega:=\{裏, 表\}$
- $\mathcal{F} := \mathfrak{P}(\Omega) = \{ \emptyset, \{裏\} , \{表\} , \{裏, 表\} \}$
- $P(\{裏\})=P(\{表\})=\frac{1}{2}$

この定義において、確率空間 $(\Omega, \mathcal{F}, P)$ はコイントスのモデルとなっていることがわかる。

また、 $0$ を裏、 $1$ を表と考えると、以下の確率空間 $(\Omega, \mathcal{F}, P)$ もコイントスのモデルとなっていることがわかる。

- $\Omega:=\{0, 1\}$
- $\mathcal{F} := \mathfrak{P}(\Omega) = \{ \emptyset, \{0\} , \{1\} , \{0, 1\} \}$
- $P(\{0\})=P(\{1\})=\frac{1}{2}$

ここでもう一つ違う表現を考える。(ここから後半)

## 確率変数(☆☆)

## 確率分布(☆☆☆)