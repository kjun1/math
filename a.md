# ZFC集合論

集合は「ものの集まり」である。集合の元(要素)として集められる対象となる、「もの」は、数、文字、記号をはじめ、どんなものでも構わない。

「集まり」が集合呼ばれるためには、対象が「その集まりの源であるかどうかが不確定要素なしに一意に決定できる」ように定義されなければならない。

**note**「集まり」を「関東圏の都道府県」とした時に「山梨」はどうなるんかわからんよね〜


## 公理系

### 表記
$x,y,z,\cdots,A,B,C$は個体変数。

$P,Q,R$は論理式。

$P(x)$は「$P$の中に現れる変数$x$に注目する」の意味で $P$ と $P(x)$は同じ文字列。

**warning**小さい文字$x,y$などが集合などを含む要素であることに注意。勝手に集合ではないと思い込まない

### 外延性公理(等しさの定義)
同じ元を持つ場合、2つの集合は等しい。
$$
    \forall A \forall B(\forall x(x \in A \leftrightarrow x \in B)\rightarrow A = B)
$$

### 空集合公理

$$
    \exist \empty(\forall x (x \notin \empty))
$$

このような$\empty$を空集合と呼ぶ。

###  対の公理($\{x,y\}$の存在)
$$
    \forall x \forall y\exist A \forall z(z \in A \leftrightarrow (z=x \lor z=y))
$$
外延性の公理から$x,y$に対して対の公理が存在を主張する集合はただ1つであることが言えるので、これを$\{x,y\}$で表す。$\{x,x\}$ を $\{x\}$で表す。


### 置換公理図式($\mathrm{map}(X,Y)$の存在)
$Y$は$P$の自由変数ではない。

$$
    \forall w_0 \cdots \forall w_{i-1}\forall X[(\forall x(x\in X\land \exists!	yP)) \rightarrow \exist X\forall y(y\in Y\rightarrow \exist x(x \in X\land P))]
$$


### 和集合の公理($\bigcup X$の存在)
$$
    \forall X \exist A \forall x(x\in A \leftrightarrow \exist B(x\in B \land B \in X))
$$

外延性の公理から$X$に対して対の公理が存在を主張する集合はただ1つであることが言えるので、これを$X$の和集合とよび $\bigcup X$ で表す。$\bigcup\{x,y\}$ を $x\cup y$で表す。

$$
    \bigcup X = \{x\in A| \exist B(x\in B \land B \in X)\}
$$


### 無限公理(無限集合の存在)
$$
    \exist A(\empty\in A \land \forall a(a\in A \rightarrow a \cup \{a\}\in A))
$$

### 冪集合公理($\mathcal{P}(X)$の存在)
先に部分集合について定義しておく
$$
    A\subseteq B \leftrightarrow \forall x(x\in A\rightarrow x\in B)
$$
以下から公理
$$
    \forall X \exist A \forall x(x\in A \leftrightarrow x \subseteq X)
$$

外延性の公理から$X$に対して対の公理が存在を主張する集合はただ1つであることが言えるので、これを$X$の冪集合とよび$\mathcal{P}(X)$で表す。

$$
    \mathcal{P}(X) = \{x\in A| x \subseteq X \}
$$

### 正則性公理
$$
    \forall A(A\neq \empty \rightarrow \exist a (a \in A \land a\cap A = \empty))
$$

### 選択公理

$$
    \forall\lambda(\lambda\in \Lambda \rightarrow A_\lambda \neq \empty)\rightarrow \prod_{\lambda\in\Lambda}A_\lambda\neq\empty
$$

## 公理系の説明中に出てくる不届きもの

### 分出公理図式
実質的に公理系に含まれない

$A$は$P$の自由変数でない。

$$
    \forall w_0 \cdots \forall w_{i-1}\forall X\exist A\forall x[x\in A \leftrightarrow (x\in X\land P)]
$$

この時
$$
    \{x\in A|x\in X\land P(x)\}
$$
と表され、これを内包表記と呼ぶ。

### 共通部分
$$
    \forall X \exist A \forall x(x\in A \leftrightarrow\forall B(B \in X \rightarrow x \in B))
$$

外延性の公理から$X$に対して対の公理が存在を主張する集合はただ1つであることが言えるので、これを$X$の共通部分とよび$\bigcap X$で表す。$\bigcap\{x,y\}$ を $x\cap y$で表す。

$$
    \bigcap X = \{x\in A|\forall B(B \in X \rightarrow x \in B)\}
$$

### 集合族

$$
    \{A_\lambda\}_{\lambda\in\Lambda}\leftrightarrow\{A_\lambda\in \mathfrak{A}|\lambda\in\Lambda\}
$$

### 順序組
クラトフスキーの順序対の定義
$$
    \langle a,b\rangle = \{a,\{a,b\}\}
$$

これを用いて、入れ子構造として順序組($n$-組)を定義できる。

### 直積集合
$$
a\times b = \{u\in \mathcal{P}(\mathcal{P}(a\cup b))|\exist x\exist y(x\in a \land y\in b\land u=\langle x,y\rangle)\}
$$

### 2項関係
$R=\langle X,Y,G\rangle \leftrightarrow G\subseteq X\times Y$

この時、3-組$R$ を二項関係、集合$G$を二項関係$R$のグラフと呼ぶ

### 写像
二項関係$G_f$が
- 左全域性: 
- 右一意性:

つまり置換公理を満たす時、3-組 $f = \langle X, Y, G_f \rangle$をこの関数関係 $G_f$から定まる$X$から$Y$への写像と呼び、$f: X → Y$で表す。またこのとき、$(x, y) ∈ Gf $であることを f(x) = y と書き、Gf = {(x, y) | y = f(x)} を写像 f のグラフと呼ぶ。