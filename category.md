# 圏論
前提知識:

集合論

## 資料
http://alg-d.com/math/kan_extension/

# 圏論をやる意義について
https://zenn.dev/lotz/articles/14458f024674e14f4134

# 定義
## 圏(Category)

次の様な2つ組 $C = \langle \mathrm{Ob}(C), \mathrm{Mor}(C) \rangle$ を考える。 

- クラス $\mathrm{Ob}(C)$ その要素を対象(object)と呼ぶ。
- クラス $\mathrm{Mor}(C)$ その要素を射(morphism)と呼ぶ。

圏 $C$ とは以下の条件を満たすものをいう。

1. 各 $f\in \mathrm{Mor}(C)$ に対して、ドメイン(domain)と呼ばれる対象 $\mathrm{dom}(f)\in \mathrm{Ob}(C)$ とコドメイン(codomain)と呼ばれる対象 $\mathrm{cod}(f)\in \mathrm{Ob}(C)$ が定められている $\mathrm{dom}(f)=a,\mathrm{cod}(f)=b$ であることを $f:a\rightarrow b$ や $a\overset{f}\rightarrow b$ と書いて表す。また対象 $a,b \in \mathrm{Ob}(C)$ に対して $\mathrm{Hom}_C(a,b) := \lbrace f\in \mathrm{Mor}(C)| f:a\rightarrow b\rbrace$ と書く。

2. 2つの射 $f,g \in \mathrm{Mor}(C)$ が $\mathrm{cod}(f) = \mathrm{dom}(g)$ を満たすとき、 $f$ と $g$ の合成射と呼ばれる射  $g \circ f$ が定められていて、 $\mathrm{dom}(g \circ f) = \mathrm{dom}(f), \mathrm{cod}(g \circ f) = \mathrm{cod}(g)$ を満たす。(つまり $f:a\rightarrow b, g:b\rightarrow c$ のとき、 $g \circ f: a \rightarrow c$)

3. 射の合成は結合律を満たす。即ち、 $f:a\rightarrow b, g:b\rightarrow c, h:c\rightarrow d$ に対して $(h \circ g) \circ f = h \circ (g \circ f)$ が成り立つ。

4. 各 $a \in \mathrm{Ob}(C)$ に対して、恒等射と呼ばれる射 $\mathrm{id}_a :a\rightarrow a$ が存在し、射の合成に関する単位元となる。即ち $f: a\rightarrow b$ に対して $f\circ \mathrm{id}_a = f, \mathrm{id}_b \circ f = f$ である。

### 圏の例

- 集合の圏 $\mathbf{Set}$: 対象は集合、射は写像
- 群の圏 $\mathbf{Grp}$: 対象は群、射は群の準同型
- 位相空間の圏 $\mathbf{Top}$: 対象は位相空間、射は連続写像
- 環の圏 $\mathbf{Ring}$: 対象は環、射は環の準同型
- 体の圏 $\mathbf{Field}$: 対象は体、射は体の準同型
- 圏の圏 $\mathbf{Cat}$: 対象は圏、射は圏の間の関手

### 反転圏(Opposite category)

反転圏 $C^{\mathrm{op}}$ は次の様に定義される。

1. $\mathrm{Ob}(C^{\mathrm{op}}) := \{a^{\mathrm{op}}|a\in \mathrm{Ob}(C)\}$
2. $\mathrm{Mor}(C^{\mathrm{op}}) := \{f^{\mathrm{op}}|f\in \mathrm{Mor}(C)\}$
3. $\mathrm{dom}(f^{\mathrm{op}}) := \mathrm{cod}(f)^{\mathrm{op}} , \mathrm{cod}(f^{\mathrm{op}}) = \mathrm{dom}(f)^{\mathrm{op}}$
4. $g^{\mathrm{op}} \circ f^{\mathrm{op}} := (f \circ g)^{\mathrm{op}}$
5. $\mathrm{id}_{a}^{\mathrm{op}}$ := $\mathrm{id}_{a^{\mathrm{op}}}$

### 圏の同型

$C$ を圏、 $a,b$ を $C$ の対象とする。

1. 射 $f:a\rightarrow b$ が同型射(isomorphism)であるとは、ある射 $g:b\rightarrow a$ が存在して $g \circ f = \mathrm{id}_a, f \circ g = \mathrm{id}_b$ を満たすことをいう。
2. 対象 $a$ と $b$ が同型(isomorphic)であるとは、ある射 $f:a\rightarrow b$ が存在して $f$ が同型射であることをいう。同型は $a \cong b$ と書く。

### 圏の直積

$C, D$ を圏とする。 $C$ と $D$ の直積圏 $C \times D$ は次の様に定義される。

1. $\mathrm{Ob}(C \times D) := \mathrm{Ob}(C) \times \mathrm{Ob}(D) = \{(a,b)|a\in \mathrm{Ob}(C), b\in \mathrm{Ob}(D)\}$
2. $\mathrm{Hom}_{C \times D}(\langle a,b \rangle, \langle a',b' \rangle) := \mathrm{Hom}_C(a,a') \times \mathrm{Hom}_D(b,b')$
3. 合成射は各成分で合成する。 即ち、 $\langle f,g \rangle \circ \langle f',g' \rangle := \langle f \circ f', g \circ g' \rangle$
4. $\langle a,b \rangle$ に対する恒等射は $\mathrm{id}_{\langle a,b \rangle} := \langle \mathrm{id}_a, \mathrm{id}_b \rangle$ である。

### 圏の直和

$C, D$ を圏とする。 $C$ と $D$ の直和 $C \amalg D$ は次の様に定義される。

1. $\mathrm{Ob}(C \amalg D) := \mathrm{Ob}(C) \sqcup \mathrm{Ob}(D)$ (非交和) である。
2. $a$ から $b$ への射は 以下のように定義される。
    - $a,b \in \mathrm{Ob}(C)$ のとき、 $\mathrm{Hom}_{C \amalg D}(a,b) := \mathrm{Hom}_C(a,b)$
    - $a,b \in \mathrm{Ob}(D)$ のとき、 $\mathrm{Hom}_{C \amalg D}(a,b) := \mathrm{Hom}_D(a,b)$
    - $a \in \mathrm{Ob}(C), b \in \mathrm{Ob}(D)$ のとき、 $\mathrm{Hom}_{C \amalg D}(a,b) := \emptyset$
3. 射の合成は $C$ または $D$ の合成と同様に定義される。
4. 恒等射は $C$ または $D$ の恒等射と同様に定義される。

### slice圏

$C$ を圏, $x \in \mathrm{Ob}(C)$ とする。 $C$ の $x$ に関するslice圏 $C/x$ は次の様に定義される。

1. $\mathrm{Ob}(C/x) := \{f\in \mathrm{Mor}(C)|\mathrm{cod}(f) = x\}$
2. $f:a\rightarrow x$ から $g:b\rightarrow x$ への射は $h:a\rightarrow b$ であって $g \circ h = f$ を満たすものである。
3. 射の合成は $C$ の合成と同様に定義される。
4. 恒等射は $C$ の恒等射と同様に定義される。

### coslice圏

$C$ を圏, $x \in \mathrm{Ob}(C)$ とする。 $C$ の $x$ に関するcoslice圏 $x/C$ は次の様に定義される。

1. $\mathrm{Ob}(x/C) := \{f\in \mathrm{Mor}(C)|\mathrm{dom}(f) = x\}$
2. $f:x\rightarrow a$ から $g:x\rightarrow b$ への射は $h:a\rightarrow b$ であって $g = h \circ f$ を満たすものである。
3. 射の合成は $C$ の合成と同様に定義される。
4. 恒等射は $C$ の恒等射と同様に定義される。

### 部分圏

$C,D$ を圏とする。 $D$ が $C$ の部分圏(subcategory) であるとは、 $\mathrm{Ob}(D) \subset \mathrm{Ob}(C), \mathrm{Mor}(D) \subset \mathrm{Mor}(C)$ であって、 $C$ におけるドメイン、コドメイン、合成、恒等射の構造を引き継いでいるものをいう。

部分圏 $D \subset C$ が充満部分圏(full subcategory) であるとは、 $\mathrm{Hom}_D(a,b) = \mathrm{Hom}_C(a,b)$ であるものをいう。

## 関手(Functor)

関手は、写像とは異なり、対象と射の両方を写す対応になっている。

$C,D$ を圏、 $a,b$ を $C$ の対象とする。 

$C$ から $D$ への共変関手(converiant functor) または単に関手(functor) $F:C\rightarrow D$ とは次のものの組である。

1. 写像 $F: \mathrm{Ob}(C) \rightarrow \mathrm{Ob}(D); a \mapsto F(a)$
2. 写像 $F: \mathrm{Hom}_C(a,b) \rightarrow \mathrm{Hom}_D(F(a),F(b)); f \mapsto F(f)$ であり次を満たす。
    - 恒等射の保存: $F(\mathrm{id}_a) = \mathrm{id}_{F(a)}$
    - 合成射の保存: $F(f \circ g) = F(f) \circ F(g)$

$C$ から $D$ への反変関手(contrafunctor) $F:C\rightarrow D$ とは次のものの組である。

1. 写像 $F: \mathrm{Ob}(C) \rightarrow \mathrm{Ob}(D); a \mapsto F(a)$
2. 写像 $F: \mathrm{Hom}_C(a,b) \rightarrow \mathrm{Hom}_D(F(b),F(a)); f \mapsto F(f)$ であり次を満たす。
    - 恒等射の保存: $F(\mathrm{id}_a) = \mathrm{id}_{F(a)}$
    - 合成射の保存: $F(f \circ g) = F(g) \circ F(f)$

なお、反転圏 $C^{\mathrm{op}}$ を使用すれば、反変関手 $F:C\rightarrow D$ は共変関手 $F:C^{\mathrm{op}}\rightarrow D$ として表すことができる。