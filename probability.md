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
標本空間の部分集合の内、確率をもつものを事象と呼ぶ。ここでは基本的に事象は $A$ で表記する。すべての事象 $A$ を集めた集合族 $\mathcal{F}$ は $\sigma$ 加法族である必要がある。これ以上分解できない事象を根元事象、複数の根元事象の和集合を複合事象という。つまり $\mathcal{F}$ は、根元事象から生成される最小の $\sigma$ 加法族となっている。

### $\sigma$ 加法族と可測空間(☆)
集合 $\Omega$ とその上の冪集合 $\mathfrak{P}(\Omega)$ に対し、 $\Omega$ の部分集合族 $\mathcal{F} \subset \mathfrak{P}(\Omega)$ が $\sigma$ 加法族であるとは、以下の性質を持つことである。

1. $\Omega\in\mathcal{F}$
2. $A\in\mathcal{F}\Rightarrow A^c(=X\setminus A)\in\mathcal{F}$
3. $ \lbrace A_n \rbrace _{n\in\mathbb{N}} \subset \mathcal{F} \Rightarrow \bigcup\limits_{n=1}^{\infty} A_n \in \mathcal{F} $

この時、集合 $\Omega$ とその上の $\sigma$ 加法族 $\mathcal{F}$ との対 $(\Omega, \mathcal{F})$ は可測空間と呼ばれる集合体になる。

## 確率測度と確率空間(☆☆)
可測空間 $(\Omega, \mathcal{F})$ の上の写像 $P$ が以下の性質を持つとき、 $P$ を確率測度と呼ぶ。

1. $P:\mathcal{F} \rightarrow \mathbb{R}_{\geq 0}$
2. $P(\Omega)=1$
3. $A_n \in\mathcal{F}, n\in\mathbb{N}$ かつ $A_i \cap A_j = \emptyset \ (\forall i \neq j)$ のとき、

$$
    P \Bigl( \textstyle\bigcup\limits_{n=1}^\infty A_n \Bigr) = \sum\limits_{n=1}^\infty P(A_n)
$$


この時、3つ組 $(\Omega, \mathcal{F}, P)$ を確率空間といい、可測集合 $A\in\mathcal{F}$ を事象と呼ぶ。また、 $A$ による $P$ の評価 $P(A)$ を 可測集合 $A$ の確率と呼ぶ。

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

多くの場合 $E$ は位相空間であって、その時 $\sigma$ 加法族 $\mathcal{E}$ としてはボレル集合族 $\mathcal{B}(E)$ を採用する。 $E=\mathbb{R}^d$ のとき、 $X$ を $d$ 次元確率変数といい、特に $d=1$ のときは単に確率変数と呼ぶことが多い。

$X$ の像(値域)が高々可算個である時、 $X$ は離散型確率変数と呼ばれ、その分布(離散確率分布)は確率変数値の確率の全てを表したものとして確率質量関数で記述できる。

像が非可算個である時、 $X$ は連続型確率変数と呼ばれ、確率分布 $P_X$ が絶対連続ならば確率密度関数が存在し、確率変数が  $E\in \mathcal{E}$ (例えば区間)に属する確率が確率密度関数の $E$ 上のルベーグ積分で表される。

### 実数値確率変数(☆☆)
確率空間 $(\Omega, \mathcal{F}, P)$ 上の実数値確率変数とは、ある可測空間 $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ に対して、関数 $X:\Omega \rightarrow \mathbb{R}$ であって、任意の $r\in\mathcal{B}(\mathbb{R})$ に対して $X^{-1}(A):=\lbrace \omega\in\Omega | X(\omega) \leq r \rbrace \in \mathcal{F}$ を満たすものをいう。

## 期待値 (☆☆☆)



### 不注意な統計学者の法則(☆☆)

## 確率分布(☆☆)
確率変数 $X: \Omega \rightarrow E$ の確率分布とは、 $P_X(A) := P(X^{-1}(A)), A \in \mathcal{E}$ によって定まる、可測空間 $(E, \mathcal{E})$ 上の確率測度 $P_X$ のことである。すなわち、 $P_X$ は確率変数 $X$ による確率測度 $P$ の押し出し測度のことである。しばしば $P(X \in A)$ と略記される。

一般的に確率分布は、可測空間 $(\mathbb{R}^d, \mathcal{B}(\mathbb{R}^d))$ の上で定義された確率測度の事をいう。(正確には $d$ 次元確率分布と呼ばれる)


### 確率空間の例後半(☆☆)
コイントスを確率変数を使って表現してみよう。

- $\tilde{\Omega}:=[0, 1]$
- $\tilde{\mathcal{F}} := \mathcal{B}([0,1])$
- $\tilde{P}: ルベーグ測度$

とする。さらに確率変数 $X: \tilde{\Omega}\rightarrow\lbrace 0, 1 \rbrace$ を

$$
    X( \omega )= \begin{cases} 0 &\text{if } \omega \in [0,1/2] \\ 1 &\text{if } \omega \in (1/2,1] \end{cases}
$$

と定義する。 すると $\tilde{P}_X = P$ であり、 $X$ は $( \tilde{\Omega} , \tilde{\mathcal{F}} , \tilde{P} )$ 上に定義されたコイントスを表す確率変数であるといえる。

続きは後で



## あんまり書かれてない事実(☆☆)

積事象の確率と同時確率は同じ

$$
    P(X,Y) = P(X\cap Y)
$$

**warning** $(X,Y) \neq X\cap Y$ です。上記事実は証明なしに使われることが多いですが、それぞれ違う事象からの確率なので、本来はちゃんと証明されるべき。