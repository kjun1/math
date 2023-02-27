# 確率と確率分布

☆: 覚える必要ないが説明上必要な内容

☆☆: 覚えてほしいが難しいので軽めに流してほしい内容

☆☆☆: 覚えてほしい内容

## 集合の復習(☆☆☆)
集合は「ものの集まり」である。集合の元(要素)として集められる対象となる、「もの」は、数、文字、記号をはじめ、どんなものでも構わない。

「集まり」が集合呼ばれるためには、対象が「その集まりの源であるかどうかが不確定要素なしに一意に決定できる」ように定義されなければならない。

**note**「集まり」を「関東圏の都道府県」とした時に「山梨」はどうなるんかわからんよね〜

「 $\omega$ が集合(個体変数) $\Omega$ の元である」という文は

$$
    \omega \in \Omega
$$

という式で示される。

## 標本空間(☆☆☆)
標本空間とは、起こりうる結果全体の集合の事をいう。

ここでは標本空間は $\Omega$ 、標本空間の元を $\omega$ と表記する。 

## 事象(☆☆)
標本空間の部分集合の内、確率をもつものを事象と呼ぶ。ここでは基本的に事象は $A$ で表記する。すべての事象 $A$ を集めた集合族 $\mathcal{F}$ は完全加法族である必要がある。これ以上分解できない事象を根元事象、複数の根元事象の和集合を複合事象という。つまり $\mathcal{F}$ は、根元事象から生成される最小の完全加法族となっている。

### 完全加法族と可測空間(☆)
集合 $\Omega$ とその上の冪集合 $\mathfrak{P}(\Omega)$ に対し、 $\Omega$ の部分集合族 $\mathcal{F} \subset \mathfrak{P}(\Omega)$ が完全加法族であるとは、以下の性質を持つことである。

1. $\Omega\in\mathcal{F}$
2. $A\in\mathcal{F}$ に対して $A^c\in\mathcal{F}$
3. $(A_n)_{n\in\mathbb{N}} \subset \mathcal{F}$ に対して 

$$
    \bigcup\limits_{n=1}^{\infty} A_n \in \mathcal{F}
$$

この時、集合 $\Omega$ とその上の完全加法族 $\mathcal{F}$ との対 $(\Omega, \mathcal{F})$ は可測空間と呼ばれる集合体になる。

## 確率測度と確率空間(☆☆)
可測空間 $(\Omega, \mathcal{F})$ の上の写像 $P$ が以下の性質を持つとき、 $P$ を確率測度と呼ぶ。

1. $P:\mathcal{F} \rightarrow [0, 1]$
2. $A_n \in\mathcal{F}, n\in\mathbb{N}$ かつ $A_i \cap A_j = \emptyset \ (\forall i \neq j)$ のとき、

$$
    P \Bigl( \textstyle\bigcup\limits_{n=1}^\infty A_n \Bigr) = \sum\limits_{n=1}^\infty P(A_n)
$$

3. $P(\Omega)=1$

この時、3つ組 $(\Omega, \mathcal{F}, P)$ を確率空間といい、可測集合 $A\in\mathcal{F}$ を事象と呼ぶ。また、 $A$ による $P$ の評価 $P(A)$ を $A$の確率と呼ぶ。


### 確率空間の例前半(☆☆☆)
コインを投げて裏と表が出る確率が、それぞれ $1/2$ であることを確率空間として表したとき、例えば次のようになる。

- $\Omega:=\lbrace裏, 表\rbrace$
- $\mathcal{F} := \mathfrak{P}(\Omega) = \lbrace \emptyset, \lbrace裏\rbrace , \lbrace表\rbrace , \lbrace裏, 表\rbrace \rbrace$
- $P(\lbrace裏\rbrace)=P(\lbrace表\rbrace)=\frac{1}{2}$

この定義において、確率空間 $(\Omega, \mathcal{F}, P)$ はコイントスのモデルとなっていることがわかる。

また、 $0$ を裏、 $1$ を表と考えると、以下の確率空間 $(\Omega, \mathcal{F}, P)$ もコイントスのモデルとなっていることがわかる。

- $\Omega:=\lbrace0, 1\rbrace$
- $\mathcal{F} := \mathfrak{P}(\Omega) = \lbrace \emptyset, \lbrace0\rbrace , \lbrace1\rbrace , \lbrace0, 1\rbrace \rbrace$
- $P(\lbrace0\rbrace)=P(\lbrace1\rbrace)=\frac{1}{2}$

## 確率変数(☆☆)
確率空間 $(\Omega, \mathcal{F}, P)$ 上の確率変数とは、ある可測空間 $(E, \mathcal{E})$ に対して、写像 $X: \Omega \rightarrow E$ であって、任意の $A\in\mathcal{E}$ に対して $X^{-1}(A):=\lbrace \omega\in\Omega | X(\omega) \in A \rbrace \in \mathcal{F}$ を満たすものをいう。

多くの場合 $E$ は位相空間であって、その時完全加法族 $\mathcal{E}$ としてはボレル集合族 $\mathcal{B}(E)$ を採用する。 $E=\mathbb{R}^d$ のとき、 $X$ を $d$ 次元確率変数といい、特に $d=1$ のときは単に確率変数と呼ぶことが多い。

## 確率分布(☆☆)



### 確率空間の例後半(☆☆)