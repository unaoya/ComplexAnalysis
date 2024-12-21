---
title: "リュービルの定理"
weight: 11
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# リュービルの定理

{{< katex >}}{{< /katex >}}

コーシーの積分公式の応用として，リューヴィルの定理，代数学の基本定理，最大値の原理などについて解説する．    

まずはコーシーの積分公式を用いて次のリュービルの定理を証明し、
その応用として任意の多項式は必ず複素数の範囲で解を持つという事実を証明しよう。

リューヴィルの定理とは\\(\mathbb{C}\\)上正則で有界な関数は定数のみであることを主張する定義である。
対偶をとると、\\(\mathbb{C})\\上正則で定数でない関数\\(f)\\は\\(z\to\infty)\\で\\(\lvert f(z)\rvert\to\infty)\\となる。


{{< hint >}}
複素平面\\(\mathbb{C}\\)全体で正則な関数\\(f\\)に対し、
ある定数\\(M\\)が存在して任意の\\(z\in\mathbb{C}\\)に対して\\(\lvert f(z) \rvert&lt;M\\)であるとする。
このとき、\\(f\\)は定数関数である。
{{< /hint >}}

{{< hint >}}
\\(\mathbb{C})\\全体で正則な関数\\(f(z)\\)に対し、\\(\lvert f(z)\rvert)\\の上界を一つとり\\(M\\)とする。
つまり、任意の\\(z\in\mathbb{C}\\)に対し\\(\lvert f(z) \rvert&lt;M\\)であるような正の実数\\(M)\\をを一つとる。

以下ではまず任意の\\(a\in\mathbb{C})\\に対し\\(f\'(a)=0)\\であることを証明する。
\\(a\in\mathbb{C})\\を一つとり、正の実数\\(r)\\を一つとる。
\\(C\\)を半径\\(r\\)で中心\\(z=a\\)の円周とすると、導関数に対するコーシーの積分公式から、
$$
    \'(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-a)^2}d\zeta
$$
となる。
よって、積分の三角不等式により、
$$
    \lvert f\'(a) \rvert\leq\frac{1}{2\pi}\int_C\frac{\lvert f(\zeta) \rvert}{\lvert\zeta-a\rvert^2}\lvert d\zeta \rvert\\\\
    \leq\frac{1}{2\pi}\int_C\frac{M}{r^2}\lvert d\zeta\rvert
    \leq \frac{M}{r}
$$
となる。
\\(f)\\が\\(\mathbb{C})\\全体で正則であるため、これが任意の\\(r)\\で成り立つ。
よって、\\(\lvert f'(a)\rvert=0)\\であり、\\(f\'(a)=0)\\である。

よって任意の\\(z\in\mathbb{C}\\)で\\(f'(z)=0\\)となることがわかり、\\(f(z)\\)は定数関数であることが示された。
{{< /hint >}}

リュービルの定理を用いると、任意の\\(1)\\次以上の多項式は複素数の範囲で根を持つという代数学の基本定理を証明することができる。

{{< hint >}}
\\(1\\)次以上の複素数係数多項式は複素数の範囲に解を持つ。
{{< /hint >}}

{{< hint >}}
\\(P(z)\\)を\\(1\\)次以上の多項式とし、解を持たないと仮定する。
\\(z\to\infty\\)で\\(\lvert P(z) \rvert\to\infty\\)であることから、
\\(\dfrac{1}{P(z)}\\)は\\(\mathbb{C}\\)上で有界になる。
リュービルの定理より\\(P(z)\\)は定数となり、これは矛盾。  
{{< /hint >}}


# 最大値の原理

次の定理は、正則関数の定義域を開集合に取ったとき、その絶対値は最大値を持たないというものである。
正則関数の定義域を閉集合に制限したとき、絶対値の最大値は境界上でとる、という形で述べることもある。

リュービルの定理と似ているが、最大値の存在と有界であることには差があることに注意する。
また、こちらは一般の定義域に対して述べていることも違いである。

{{< hint >}}
\\(f:D\to\mathbb{C}\\)が正則で定数でないなら、\\(f\\)の絶対値は最大値を持たない。
{{< /hint >}}

対偶を取れば、\\(f:D\to\mathbb{C})\\が正則で、\\(\lvert f(z)\rvert)\\が最大値を持つならば\\(f)\\は定数である、という主張になる。

{{< hint >}}
\\(\alpha\in D\\)で\\(f)\\の絶対値\\(\lvert f(z)\rvert)\\が最大値を持つとする。
このとき、任意の\\(z \in D\\)について\\(\lvert f(z)\rvert\leq\lvert f(\alpha)\rvert\\)である。

\\(C)\\を\\(\alpha)\\中心半径\\(f)\\の円で、その内部も含めて\\(D)\\に含まれるものとする。
これに対し、コーシーの積分公式から、
$$
\lvert f(\alpha)\rvert=\lvert\frac{1}{2\pi i}\int_C\frac{f(z)}{z-\alpha}dz\rvert\\\\
\leq\frac{1}{2\pi}\frac{\lvert f(\alpha)\rvert}{r}2\pi r=\lvert f(\alpha)\rvert
$$
となる。
よって、途中の不統合においては等号が成り立ち、曲線\\(C\\)上で\\(\lvert f(z)\rvert=\lvert f(\alpha)\\)となる。
\\(C\\)の半径\\(r)\\を動かすことで、\\(\alpha)\\を中心とするある円板内部\\(B)\\において\\(\lvert f(z)\rvert\\)は一定である。

\\(f(z)=u(x,y)+iv(x,y)\\)と実部虚部に分ける。
\\(\lvert f(z)\rvert=u(x,y)^2+v(x,y)^2\\)であり、上でとった\\(B)\\の内部においてはこれが定数になる。
したがって、\\(u(x,y)^2+v(x,y)^2=c)\\を\\(x, y\\)でそれぞれ偏微分すると、
\\(2u_x(x,y)u(x,y)+2v_x(x,y)v(x,y)=0, 2u_y(x,y)u(x,y)+2v_y(x,y)v(x,y)=0\\)となる。
コーシーリーマン方程式を用いると、第二式は\\(-2v_x(x,y)u(x,y)+2u_x(x,y)v(x,y)=0\\)となるから、
\\(B)\\内部において、\\(u_x(x,y)=v_x(x,y)=u_y(x,y)=v_y(x,y)=0\\)となる。
よって\\(B)\\内部において\\(f(z)\\)は定数である。
したがって、一致の定理より\\(D)\\内部で\\(f(z))\\は定数である。
{{< /hint >}}


# 平均値の性質

コーシーの積分公式から、正則関数のある点での値はその周りの円周上での値の「平均」であると解釈できる。

{{< hint >}}
\\(f\\)が円\\(C=C(\alpha,r)\\)とその内部で正則であるとき、
$$
f(\alpha)=\frac{1}{2\pi}\int^{2\pi}_0f(\alpha+re^{i\theta})d\theta
$$
である。
{{< /hint >}}

{{< hint >}}
コーシーの積分公式より、
$$
f(\alpha)=\frac{1}{2\pi i}\int_C\frac{f(z)}{z-\alpha}dz
$$
である。

この右辺の積分を、\\(\gamma(\theta)=\alpha+re^{i\theta}\\)とパラメータづけて計算すると、
$$
\frac{1}{2\pi i}\int_C\frac{f(z)}{z-\alpha}dz
=\frac{1}{2\pi i}\int^{2\pi}_0\frac{f(\alpha+re^{i\theta})}{re^{i\theta}}ire^{i\theta}d\theta\\\\
=\frac{1}{2\pi}\int^{2\pi}_0f(\alpha+re^{i\theta})d\theta\\\\
$$
となる。
{{< /hint >}}
