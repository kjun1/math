# 圏論
前提知識:

集合論

## 資料
http://alg-d.com/math/kan_extension/

# 圏論をやる意義について
https://zenn.dev/lotz/articles/14458f024674e14f4134

# 定義
## 圏(Category)

次の様な6つ組 $C = \langle \mathrm{Ob}(C), \mathrm{Mor}(C), \mathrm{dom}, \mathrm{cod}, \mathrm{id}, \circ \rangle$ を考える。 

- クラス $\mathrm{Ob}(C)$ その要素を対象(object)と呼ぶ。
- クラス $\mathrm{Mor}(C)$ その要素を射(morphism)と呼ぶ。


1. 各 $f\in \mathrm{Mor}(C)$ に対して、ドメイン(domain)と呼ばれる対象 $\mathrm{dom}(f)\in \mathrm{Ob}(C)$ とコドメイン(codomain)と呼ばれる対象 $\mathrm{cod}(f)\in \mathrm{Ob}(C)$ が定められている $\mathrm{dom}(f)=a,\mathrm{cod}(f)=b$ であることを $f:a\rightarrow b$ や $a\overset{f}\rightarrow b$ と書いて表す。また対象 $a,b \in \mathrm{Ob}(C)$ に対して $\mathrm{Hom}_C(a,b) := \lbrace f\in \mathrm{Mor}(C)| f:a\rightarrow b\rbrace$ と書く。

2. 2つの射 $f,g \in \mathrm{Mor}(C)$ が $\mathrm{cod}(f) = \mathrm{dom}(g)$ を満たすとき、$f$ と $g$ の合成射と呼ばれる射  $g \circ f$ が定められていて、 $\mathrm{dom}(g \circ f) = \mathrm{dom}(f), \mathrm{cod}(g \circ f) = \mathrm{cod}(g \circ f) = \mathrm{cod}(g)$ を満たす。(つまり $f:a\rightarrow b, g:b\rightarrow c$ のとき、 $g \circ f: a \rightarrow c$)


圏 $C$ とは以下の条件を満たすものをいう。

3. 射の合成は結合律を満たす。即ち、 $f:a\rightarrow b, g:b\rightarrow c, h:c\rightarrow d$ に対して $(h \circ g) \circ f = h \circ (g \circ f)$ が成り立つ。

4. 各 $a \in \mathrm{Ob}(C)$ に対して、恒等射と呼ばれる射 $\mathrm{id}_a :a\rightarrow a$ が存在し、射の合成に関する単位元となる。即ち $f: a\rightarrow b$ に対して $f\circ \mathrm{id}_a = f, \mathrm{id}_b \circ f = f$ である。

## 関手(Functor)

$C,D$ を圏とする。

$C$ から $D$ への共変関手(converiant functor) $F:C\rightarrow D$ とは 

$F:\mathrm{Ob}(C) \rightarrow \mathrm{Ob}(D); a \rightarrow F(a), \mathrm{Hom}_C(a, b) \rightarrow \mathrm{Hom}_D(F(a), F(b)); f \mapsto F(f)$

であって、次の条件を満たすものである。

1. $F(f \circ g) = F(f) \circ F(g)$
2. $F(\mathrm{id}_a) = \mathrm{id}_{F(a)}$

$C$ から $D$ への反変関手(contravariant functor) $F:C\rightarrow D$ とは 

$F:\mathrm{Ob}(C) \rightarrow \mathrm{Ob}(D); a \rightarrow F(a), \mathrm{Hom}_C(a, b) \rightarrow \mathrm{Hom}_D(F(b), F(a)); f \mapsto F(f)$

であって、次の条件を満たすものである。

1. $F(f \circ g) = F(g) \circ F(f)$
2. $F(\mathrm{id}_a) = \mathrm{id}_{F(a)}$