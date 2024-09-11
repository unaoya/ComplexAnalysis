---
title: "Complex Function"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

{{< hint info >}}
ヒント．
{{< /hint >}}

{{< hint danger >}}
ヒント．
{{< /hint >}}

{{< katex >}}\int_{-\infty}^{\infty}e^{-t^2}dt=0{{< /katex >}}

{{< katex display >}}
  \int_{-\infty}^{\infty}e^{-t^2}dt=0
{{< /katex >}}

{{< hint info >}}

以下の式が成り立つ．

{{< katex display >}}
  \int_{-\infty}^{\infty}e^{-t^2}dt=\pi.
{{< /katex >}}
{{< /hint >}}

{{< hint info >}}
次の式が成り立つ．\\(\int_{-\infty}^{\infty}e^{-t^2}dt=0\\).
{{< /hint >}}

# 複素関数

複素関数。
\\(f:\mathbb{C}\to \mathbb{C}\\)とか、\\(U\subset\mathbb{C}\\)に対して\\(f:U\to\mathbb{C}\\)を考える。

ここでは複素関数について説明する。
このノートにおいて、**複素関数**とは複素平面のある部分集合で定義された複素数値関数をいう。
\\(f\\)が\\(U\subset \mathbb{C}\\)で定義された複素関数であることを\\(f:U\to \mathbb{C}\\)と表す。

## 複素関数の図示

二つの複素平面を書いて考える。

## 複素関数の連続性
複素関数の連続性は、単に二変数関数\\(f(x,y)\\)の連続性と同じ。
\\(\mathbb{C}\\)の位相は\\(\mathbb{R}^2\\)の位相と同じで、距離を絶対値で測る。
\\(z=x+iy, w=u+vi\\)としたとき、\\(z, w\\)の距離と\\((x,y), (u,v)\\)の距離は同じ。
連続であることは
$$
  \lim_{z\to a}f(z)=f(a)
$$
で定義する。
\\(\epsilon\delta\\)でかくと、任意の\\(\epsilon>0\\)に対し、ある\\(\delta>0\\)が存在して、
\\(\lvert z-a\rvert&lt;\delta\\)ならば\\(\lvert f(z)-f(a)\rvert&lt;\epsilon\\)である。

## ベクトル値実関数との対比

\\(\mathbb{R}^2\\)と\\(\mathbb{C}\\)を同一視する

集合として、また連続性についてはどちらでも同じ。

## 一次関数

一次関数は\\(f(z)=\alpha z+\beta\\)で、
これは\\(\alpha\\)倍で回転拡大、\\(+\beta\\)で平行移動を表す。
図示する。


## 多項式函数

多項式関数。
\\(z\\)の多項式で定まる関数\\(f(z)=z^n+\cdots+a_n\\)を考える。

## 有理関数

多項式函数の比で定まる関数を有理関数という。

{{< hint >}}
  \\(f(z)=\dfrac{az+b}{cz+d}\\)を一次分数変換という。
  これは\\(\mathbb{C}\setminus\left\\{\dfrac{-d}{c}\right\\}\\)で正則な関数である。

  \\(\mathbb{C}\\)に無限遠点\\(\{\infty\}\\)を付け加えてリーマン球面を考える。
  すると、一次分数変換はリーマン球面からリーマン球面への「正則関数」となる。
  この関数により、リーマン球面の「円」は「円」にうつる。

  リーマン球面における「円」は通常の複素平面における円または直線である。
{{< /hint >}}

## 指数関数

指数関数。\\(e^z, \exp(z)\\)をどう定義するか。
いくつかのやり方がある。
冪級数、オイラーの公式、微分方程式など。
等角な拡張として特徴づけられる。
例えば、天下りに\\(f(z)=e^{x+iy}=e^x(\cos y+i\sin y)\\)と定義してみる。
（ここでは実数の範囲での指数関数と三角関数しか用いていないことに注意する。）
すると、これについて\\(u, v\\)は全微分可能であり、コーシーリーマン方程式を満たすことも直接計算できる。
さらに導関数は\\(f\'(z)=f(z)\\)となることもわかる。
上で与えた天下りな式は、指数法則の等角性から導出することもできる。
この関数について、周期\\(2\pi i\\)をもつ。
特に単車ではないため、全域で逆関数を持たない。

指数関数。
\\(\exp z\\)は正則関数である。
そもそも複素関数としての\\(\exp z\\)はどう定義されるか。
オイラーの公式を用いて定義するのが一つのやり方。

{{< hint >}}
  \\(z\in\mathbb{C}\\)を\\(z=x+yi\\)と表したとき、
  $$
    \exp(z)=e^x(\cos y+i\sin y)
  $$
  と定める。
{{< /hint >}}

指数関数の様子を把握するために、\\(x\\)一定の曲線や\\(y\\)一定の曲線がどのようにうつるかをみておこう。

次のような冪級数を定義とする方法もある。
$$
  \exp(z)=1+z+\frac{1}{2}z^2+\frac{1}{3!}z^3+\cdots
$$

この二つの定義の同値性は証明が必要だが、今回は省略する。

等角性を用いて拡張する。

## 三角関数

複素関数としての三角関数を定義しよう。

上の指数関数の定義において、実数\\(\theta\\)にたいし、\\(e^{i\theta}=\cos\theta+i\sin\theta\\)となることから、
$$
  \dfrac{e^{i\theta}+e^{-i\theta}}{2}=\cos\theta
$$
$$
  \dfrac{e^{i\theta}-e^{-i\theta}}{2i}=\sin\theta
$$
が成り立つ。

そこで、同じ式用いてそのまま複素数に拡張する。
$$
  \cos z = \dfrac{e^{iz}+e^{-iz}}{2}
$$
$$
  \sin z = \dfrac{e^{iz}-e^{-iz}}{2i}
$$

すると、これは実数に対する三角関数と同様に、周期\\(2\pi\\)をもち、加法定理が成り立つことが、指数関数の周期性と指数法則からわかる。
$$
  \cos (z + 2\pi) = \cos z
$$
$$
  \sin (z + 2\pi) = \cos z
$$

$$
  \cos (z + w) = \cos z \cos w - \sin z \sin w
$$
$$
  \sin (z + w) = \sin z \cos w + \sin w \cos z
$$

## 対数関数

複素数に対する対数関数を定義しよう。
実数の範囲では、指数関数の逆関数として定義できた。
これは、異なる実数\\(x, y\\)に対しては\\(e^x\\)と\\(e^y\\)が異なるためである。

一方で複素数の範囲では、指数関数が複数の複素数で同じ値をとる。
なので、逆関数が直ちには定義できない。

しかし、多価関数としては以下のように定義することができる。

指数関数は、\\(z=x+yi\\)に対して
$$
  \exp(z)=e^x(\cos y+i\sin y)=e^x\cos y +i e^x\sin y
$$
と定義された。

\\(w=\exp(z)\\)を\\(z\\)について解くことで\\(z=\log w\\)を定める。
\\(z=x+yi\\)とし、\\(w=u+vi\\)として、\\(x, y\\)について解けばよい。
$$
  u+iv = e^x\cos y +i e^x\sin y
$$
であるので、
$$
  u=e^x\cos y, v = e^x\sin y
$$
である。
$$
  u^2+v^2=e^{2x}(\cos^2y+\sin^2y)=e^{2x}
$$
であるので、
$$
  x=\log\sqrt{u^2+v^2}
$$
である。ただし、ここの\\(\log\\)は実関数としての対数関数である。

また、
$$
  \frac{v}{u}=\frac{\sin y}{\cos y}
$$
なので、
$$
  \arctan\frac{v}{u}=y
$$
である。
\\(\dfrac{v}{u}\\)は複素平面で言えば原点と\\(z\\)を結ぶ線分の傾きであり、偏角\\(\theta\\)とすればこの傾きは\\(\tan\theta\\)であったから、
$$
  y=\arg(z)
$$
である。
ただし、これは一位的に決まらないことに注意する。

つまり、
$$
\log(w)=\log\lvert w\rvert+i\arg w
$$
であることが\\(w=\exp(z)\\)であることと同値である。

そこで、改めて文字を置き直して\\(z=r(\cos\theta+i\sin\theta)\\)に対して、
$$
  \log(z)=\log r+i\theta
$$
とする。
ただし、偏角\\(\theta\\)は一意には定まらないことに注意しよう。

## 冪乗函数

複素数の複素数乗を定義しよう。
対数関数を用いて次のように定義する。

一般の\\(\alpha\\)に対し、
$$
  z^\alpha=\exp(\alpha\log z)
$$
と定義する。

対数関数が多価関数であったことから、\\(f(z)=z^\alpha\\)も一般には多価関数となることに注意せよ。
ただし、\\(\exp\\)が周期関数であることにより、\\(\alpha\\)の値によっては\\(\alpha\log z\\)の多価性が消える場合がある。
\\(\alpha\\)が整数であれば一価正則に定まる。
有理数であれば有限通りの不定性がある。

べき関数の定義を与えよう。
例えば\\(f(z)=\sqrt{z}=z^{1/2}\\)でも上の対数関数と同様に\\(\mathbb{C}\\)上で一価正則な関数として定義することはできない。

指数が複素数の冪乗は注意して計算する必要がある。
次の計算がどこがおかしいか考えよ。
$$
  -1 = (\sqrt{-1})^2 = \sqrt{-1} \times \sqrt{-1} = \sqrt{(-1)^2} = \sqrt{1} = 1
$$

実数\\(x\\)に対する\\(\sqrt{x}\\)は二つある平方根のうち正の方をとる、ということで全ての実数に対して一斉に\\(\sqrt{x}\\)を定めることができ、
これが連続関数となっていた。

複素数に対しては、二つある平方根のうち、例えば偏角が\\(0\\)以上\\(\pi\\)未満の方をとることにすると、一斉に\\(\sqrt{z}\\)を定めることができるが、
これは連続関数とはならない。
単位円周に沿って一周連続的に\\(\sqrt{z}\\)の値を変化させるとどうなるかを考えよう。