---
title: "コーシーの積分公式"
weight: 6
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# コーシーの積分公式

{{< katex >}}{{< /katex >}}

コーシーの積分定理から次のコーシーの積分公式を導くことができる。
これは正則関数の性質を調べる上で非常に重要な定理である。

コーシーの積分公式は\\(\delta\\)関数のようなものと思うこともできる。

## コーシーの積分公式

{{< hint >}}
  正則関数\\(f:D\to\mathbb{C}\\)と\\(a\in D\\)に対し、\\(C_r\\)を中心\\(a\\)で半径\\(r\\)の円周に反時計回りに向きをつけたものとする。
  \\(C_r\\)およびその内部が\\(D\\)に含まれるならば、

  $$
    f(a)=\frac{1}{2\pi i}\int_{C_r}\frac{f(z)}{z-a}dz
  $$
  が成り立つ。
{{< /hint >}}

つまり、正則関数\\(f(z)\\)の\\(z=a\\)での値は、その点を中心とする円周上の\\(f\\)の値の平均であると理解できる。

まず証明の方針を説明しよう。
被積分関数\\(\dfrac{f(z)}{z-a}\\)は\\(D\setminus\\{a\\}\\)で正則なので、\\(r\\)を小さくしても積分値は変化しない。
（ここは連続変形と考えることもできるし、星形領域において経路を取り替えると考えてもよい。二つの同心円を半分に区切って、それぞれは星形領域内で取り替えられる。）

\\(r\to0\\)の極限を考えると、\\(C_r\\)は一点に近づくが、\\(\dfrac{f(z)}{z-a}\\)は無限大に発散するのである種の不定形の極限のようになっている。
ここを処理するために、\\(\dfrac{f(z)-f(a)}{z-a}+\dfrac{f(a)}{z-a}\\)と変形する。

1つ目の項は\\(a\\)での微分可能性から、\\(r\to0\\)で有限の値に収束し、線積分は\\(0\\)に収束する。
2つ目の項は極限を取らずとも直接計算できる。

この議論を整理したのが以下の証明である。

{{< hint >}}
  $$
  \frac{f(z)}{z-a}=\frac{f(z)-f(a)}{z-a}+\frac{f(a)}{z-a}
  $$
  であるので、
  $$
  \int_{C_r}\frac{f(z)}{z-a}dz=\int_{C_r}\frac{f(z)-f(a)}{z-a}dz+\int_{C_r}\frac{f(a)}{z-a}dz
  $$
  である。
  $$
  \int_{C_r}\frac{f(a)}{z-a}dz=2\pi if(a)
  $$
  であるので、残った積分が\\(0\\)であることを証明する。

  \\(f\\)が\\(a\\)で正則であることから、
  $$
  \lim_{z\to a}\frac{f(z)-f(a)}{z-a}=f\'(a)
  $$
  であり、ある\\(M\\)を用いて任意の十分小さな\\(r\\)に対し\\(z\in C_r\\)ならば、
  $$
  \left\lvert\frac{f(z)-f(a)}{z-a}\right\rvert &lt; M
  $$
  とできる。

  そのような十分小さな\\(r\\)に対し、
  $$
  \lvert\int_{C_r}\frac{f(z)-f(a)}{z-a}dz\rvert
  \leq
  \int_{C_r}\lvert\frac{f(z)-f(a)}{z-a}\rvert\lvert dz\rvert
  =\int_{C_r}M\lvert dz\rvert
  \leq
  2\pi rM
  $$
  である。
  ここで、コーシーの積分定理により左辺の積分は\\(r\\)に依存しない。
  一方で\\(2\pi rM\\)は\\(r\to 0\\)で\\(0\\)に収束するため、
  $$
  \lvert\int_{C_r}\frac{f(z)-f(a)}{z-a}dz\rvert=0
  $$
  である。
{{< /hint >}}

コーシーの積分定理を用いた経路の連続変形により、閉曲線の形を取り替えることもできる。

{{< hint >}}
  正則関数\\(f:D\to \mathbb{C}\\)と\\(a\in D\\)とする。
  閉曲線\\(C\\)が\\(D\setminus\\{a\\}\\)において、\\(a\\)中心の十分小さな半径\\(r\\)の円周反時計回りに連続変形できるとする。

  このとき、
  $$
    f(a)=\frac{1}{2\pi i}\int_C\frac{f(z)}{z-a}dz
  $$
  が成り立つ。
{{< /hint >}}

例題。

{{< hint >}}
  \\(C=B_2(0)\\)とする。
  $$
    \int_C\frac{e^z}{z-1}dz= 2\pi ie\\\\
    \int_C\frac{e^z}{z^2-1}dz=\int_C\frac{e^z}{2}(\frac{1}{z-1}-\frac{1}{z+1})dz
  $$
{{< /hint >}}

## 微分係数の積分表示と正則関数の解析性

コーシーの積分公式を用いることで、正則関数の非常に重要な性質である解析性、
つまり何回でも微分できまた冪級数展開可能であるという性質を導くことができる。

{{< hint >}}
  領域\\(D\\)で正則な関数\\(f\\)は任意の自然数\\(n\\)に対して\\(n\\)階微分可能で、\\(f\\)の\\(n\\)階導関数は
  $$
    f^{(n)}(z)=\frac{n!}{2\pi i}\int_C\frac{f(\zeta)}{(\zeta-z)^{n+1}}d\zeta
  $$
  を満たす。
  ここで、\\(C\\)はその内部まで含めて\\(D\\)に含まれる円で、\\(z\\)は円の内部の点。
{{< /hint >}}

さらに正則関数はテイラー展開できることもわかる。

{{< hint >}}
  領域\\(D\\)で正則な関数\\(f\\)は\\(a\in D\\)の周りで冪級数展開可能である。
  つまり、ある\\(a\\)の周りで収束する冪級数が存在して、\\(a\\)の近傍の\\(z\\)に対して
  $$
    f(z) = \sum_{n=0}^\infty a_nz^n
  $$
  となる。
{{< /hint >}}

コーシーの積分公式を用いて\\(f\\)の冪級数展開を計算する。
\\(a\in D\\)とし、\\(a\\)を中心とする半径の小さな円周\\(C\\)と\\(C\\)の内部の点\\(z\\)に対し
$$
  f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta
$$
である。

まずは被積分関数\\(\dfrac{1}{\zeta-z}\\)の\\(z=a\\)を中心とする冪級数展開を計算する。
その上で、無限和と積分の順序が交換できることを用いれば、\\(f\\)の冪級数展開を求めることができる。

$$
\frac{1}{\zeta-z}
=\frac{1}{(\zeta-a)-(z-a)}
=\frac{1}{(\zeta-a)(1-(z-a/(\zeta-a)))}
=\frac{1}{\zeta-a}\times\frac{1}{1-(z-a/(\zeta-a))}
$$
となる。

ここで、等比級数の和の公式を用いると、
\\(\left\lvert\dfrac{z-a}{\zeta-a}\right\rvert&lt;1\\)が成り立つため、
$$
\frac{1}{1-((z-a)/(\zeta-a))}
=\left(1+\frac{z-a}{\zeta-a}+\left(\frac{z-a}{\zeta-a}\right)^2+\cdots\right)
=\sum_{n=0}^\infty\frac{(z-a)^n}{(\zeta-a)^{n}}
$$
となる。

よって、
$$
\frac{1}{\zeta-z}=\sum_{n=0}^\infty\frac{(z-a)^n}{(\zeta-a)^{n+1}}
$$
である。

$$
  f(z)=\frac{1}{2\pi i}\int_C\frac{f(\zeta)}{\zeta-z}d\zeta=\frac{1}{2\pi i}\int_C\sum_{n=0}^\infty\frac{f(\zeta)}{(\zeta-a)^{n+1}}(z-a)^nd\zeta
$$

一様収束すれば順序交換できる。
$$
  \frac{1}{2\pi i}\int_C\sum_{n=0}^\infty\frac{f(\zeta)}{(\zeta-a)^{n+1}}(z-a)^nd\zeta
  =\frac{1}{2\pi i}\sum_{n=0}^\infty\left(\int_C\frac{f(\zeta)}{(\zeta-a)^{n+1}}d\zeta\right)(z-a)^n
$$

よって、
$$
  f(z)
  =\frac{1}{2\pi i}\sum_{n=0}^\infty\left(\int_C\frac{f(\zeta)}{(\zeta-a)^{n+1}}d\zeta\right)(z-a)^n
$$
である。

冪級数展開できる関数は何回でも微分可能であり、その微分係数も冪級数の係数から計算できる。


{{< hint >}}
  $$
    \int_{C_i}\frac{1}{z^2(z-1)(z-2)}dz
  $$
  を計算する。
  ここで、\\(C_1\\)は\\(z=0\\)中心で小さな半径を持つ円、\\(C_2\\)は\\(z=1\\)中心で小さな半径を持つ円、\\(C_3\\)は\\(z=2\\)中心で小さな半径を持つ円、
  \\(C_4\\)は\\(z=0,1,2\\)全てを囲む大きな半径をもつ円である。
  
  \\(C_1\\)での積分は、\\(f(z)=\dfrac{1}{(z-1)(z-2)}\\)とみて、微分係数の積分表示を使うと
  $$
  \int_{C_1}\frac{f(z)}{z^2}dz=2\pi if\'(0)=
  $$
  となる。
    
  \\(C_2\\)での積分は、\\(f(z)=\dfrac{1}{z^2(z-2)}\\)とみて、コーシーの積分公式により
  $$
  \int_{C_2}\frac{f(z)}{z-1}dz=2\pi if(1)=-2\pi i
  $$
  となる。
  
  \\(C_3\\)での積分は、\\(f(z)=\dfrac{1}{z^2(z-1)}\\)とみて、コーシーの積分公式により
  $$
  \int_{C_3}\frac{f(z)}{z-2}dz=2\pi if(2)=\frac{\pi i}{2}
  $$
  となる。
    
  \\(C_4\\)での積分は、\\(C_1+C_2+C_3\\)が\\(C_4\\)に\\(f\\)がが正則な領域内で連続変形できることから、
  $$
  \int_{C_4}=\int_{C_1}+\int_{C_2}+\int_{C_3}=
  $$
  となる。  
{{< /hint >}}

## 積分計算への応用

積分定理を使うことで、
初等的には計算の難しい積分を計算できる。

{{< hint >}}
  
  フレネル積分
  $$
    \int^\infty_{0}\cos(x^2)dx=\int^\infty_{0}\sin(x^2)dx=\frac{\sqrt{\pi}}{2\sqrt{2}}
  $$
  を計算しよう。
{{< /hint >}}

正の実数\\(R\\)に対し、曲線\\(C_R\\)を原点中心で半径\\(R\\)の扇型で弧が偏角が\\(0\\)から\\(\dfrac{\pi}{4}\\)の部分に反時計回りに向きをつけたものとする。
この曲線に沿って\\(f(z)=e^{-z^2}\\)を積分する。

曲線のパラメータづけを
$$
  \gamma_1(t)=t, t\in[{0},R]\\\\
  \gamma_2(t)=R\exp(i\dfrac{\pi}{4}t), t\in[{0},1]\\\\
  \gamma_3(t)=(R-t)\exp(i\dfrac{\pi}{4}), t\in[{0},R]
$$
とする。
  
これらでの積分は
$$
  \int_{0}^R\exp(-t^2)dt+\int_{0}^1\exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)dt+\int_{0}^R\exp(-(R-t)^2i)(-\exp(i\frac{\pi}{4}))dt
$$
となる。

第二項は
$$
  \left\lvert \int_{0}^1\exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)dt\right\rvert
  \leq\int_{0}^1\lvert \exp(-R^2\exp(i\frac{\pi}{2}t))iR\frac{\pi}{4}\exp(i\frac{\pi}{4}t)\rvert dt\\\\
  \leq\int_{0}^1R\exp(-R^2\cos(\frac{\pi}{2}t))\frac{\pi}{4}dt
$$
となる。
  
さらに、\\(t\in[0,1]\\)において\\(\cos\dfrac{\pi}{2}t\geq1-t\\)であることから、
$$
  \int_{0}^1R\exp(-R^2\cos(\frac{\pi}{2}t))\frac{\pi}{4}dt
  \leq\frac{\pi}{4}R\int_{0}^1\exp(-R^2(1-t))dt\\\\
  =\frac{\pi}{4}R\int_1^{0}\exp(-R^2s)d(1-s)\\\\
  =\frac{\pi}{4}R\int_{0}^1\exp(-R^2s)ds\\\\
  =\frac{\pi}{4}R\frac{-1}{R^2}[\exp(-R^2s)]^1_{0}\\\\
  =\frac{\pi}{4R}(1-\exp(-R^2))
$$
となり、\\(R\to0\\)で\\(0\\)に収束することがわかる。
  
第一項の計算には
$$
  \int^\infty_{-\infty}\exp(-x^2)dx=\sqrt{\pi}
$$
を用いる。
第一項について\\(R\to\infty\\)での極限は
$$
  \int^\infty_{0}\exp(-t^2)dt=\frac{\sqrt{\pi}}{2}
$$
となる。
  
次に第三項について、
$$
  \int_{0}^R\exp(-(R-t)^2i)(-\exp(i\frac{\pi}{4}))dt
  =\int_R^{0}\exp(-s^2i)(-\exp(i\frac{\pi}{4}))d(R-s)\\\\
  =-\exp(i\frac{\pi}{4})\int_{0}^R\exp(-s^2i)ds\\\\
  =-\exp(i\frac{\pi}{4})\int_{0}^R\cos(-s^2)+i\sin(-s^2)ds
$$
となる。
  
\\(f(z)=\exp(-z^2)\\)は扇型の内部で正則だから、
一周積分すると\\(0\\)になる。
  
最後に\\(R\to\infty\\)の極限をとってをまとめると、
$$
  \frac{\sqrt{\pi}}{2}-\exp(i\frac{\pi}{4})\int_{0}^\infty\cos(-s^2)+i\sin(-s^2)ds=0
$$
となるので、実部と虚部をそれぞれ比較することで
$$
  \int_{0}^\infty\cos(-x^2)ds=\int_{0}^\infty\sin(-x^2)ds=\sqrt{\frac{\pi}{2}}
$$
となる。  

{{< hint >}}
  
  $$
    \int^\infty_{0}\frac{\sin x}{x}dx=\frac{\pi}{2}
  $$
  を証明する。
{{< /hint >}}
  
\\(R, T, \epsilon\\)をそれぞれ適当な大きさの実数とし、
\\(C_1\\)を\\(から\\)R+Ti\\(を結ぶ線分、\\)C_2\\(を+Ti\\)から\\(-R+Ti\\)を結ぶ線分、
\\(C_3\\)を\\(-R+Ti\\)から\\(-R\\)を結ぶ線分、\\(C_4\\)を\\(-R\\)から\\(-\epsilon\\)を結ぶ線分、
\\(C_5\\)を原点中心で半径\\(\epsilon\\)の上半円周を時計回りに向きをつけたもの、
\\(C_6\\)を\\(\epsilon\\)から\\(R\\)を結ぶ線分とする。
  
この曲線に沿って\\(f(z)=\dfrac{e^{iz}}{z}\\)を積分する。
上の曲線で囲まれた領域の内部で\\(f(z)\\)は正則だから、一周積分した値は\\(0\\)である。

まず\\(C_1\\)ではパラメータを\\(R+ti\\)とつけることで、
$$
  \lvert \int_{0}^T\frac{\exp(iR-t) \rvert{R+ti}idt}\rvert
  \leq\int_{0}^T\lvert \frac{\exp(iR-t) \rvert{R+ti}}dt\rvert
  \leq\int_{0}^T\frac{\exp(-t)}{R}dt
  \leq\int_{0}^\infty\frac{\exp(-t)}{R}dt
  \leq\frac{1}{R}
$$
となり、これは任意の\\(T\\)について\\(R\to\infty\\)で\\(0\\)に収束する。
\\(C_3\\)についても同様。

\\(C_2\\)ではパラメータを\\(t+Ti\\)とつけることで
$$
  \lvert \int_R^{-R} \rvert\frac{\exp(it-T)}{t+Ti}dt
  \leq\frac{1}{T}\int^{-R}_R\exp(-T)dt
  =\frac{2Re^{-T}}{T}
$$
となり、これは任意の\\(R\\)について\\(T\to\infty\\)で\\(0\\)に収束する。

\\(C_4, C_6\\)での積分については
$$
  \int_{-R}^{-\epsilon}\frac{\exp(iz)}{z}dz+\int_\epsilon^R\frac{\exp(iz)}{z}dz=
  \int_\epsilon^R\frac{\exp(-iz)}{-z}dz+\int_\epsilon^R\frac{\exp(iz)}{z}dz=
  2i\int^R_\epsilon\frac{\sin z}{z}dz
$$
となる。
\\(\epsilon\to0, R\to\infty\\)の極限を取ることで求めるべき積分値に収束する。

最後に\\(C_5\\)での積分について見てみよう。
\\(\exp(iz)\\)は全複素平面で正則函数であり、\\(z=0\\)の周りのテイラー展開を考えることで
$$
  \frac{\exp(iz)}{z}=z^{-1}+g(z)
$$
と収束半径\\(\infty\\)の冪級数\\(g(z)\\)を用いて表すことができ、
この\\(g(z)\\)は\\(\lvert z \rvert\leq1\\)に対し\\(\lvert g(z) \rvert\leq M\\)なる\\(M\\)が存在する。
このことにより、
$$
  \lvert \int_{C_5}g(z)dz\rvert\leq\pi\epsilon M
$$
となり、\\(\epsilon\to0\\)で\\(0\\)に収束する。
一方、直接計算により
$$
  \int_{C_5}z^{-1}dz=-\pi i
$$
となるから、\\(\epsilon\to0\\)の極限で
$$
  \int_{C_5}\frac{\exp(iz)}{z}dz\to-\pi i
$$
である。
  
これらを全てまとめ、\\(T\to\infty, R\to\infty, \epsilon\to0\\)の順に極限を取ることで
$$
  2i\int^\infty_{0}\frac{\sin x}{x}dx-\pi i=0
$$
が得られる。

{{< hint >}}
$$
	\frac{1}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2-itx)dx
$$
を計算しよう。
{{< /hint >}}

\\(z=b, b+\dfrac{it}{2}, -a+\dfrac{it}{2}, -a\\)を頂点にもつ長方形の周に反時計回りに向きをつけた曲線を\\(C\\)とする。
このとき、虚軸と平行な辺での積分は
$$
\left\lvert \int^{b+it/2}_b f(z)dz\right\rvert
$$

$$
\leq e^{-b^2}\int_{0}^{t/2} e^{y^2}dy
\leq \frac{t}{2}e^{-b^2}e^{t^2/4}
$$
となり、これは\\(b\to\infty\\)で\\(0\\)に収束する。
もう一つの辺についても同様。

したがって、\\(C\\)での積分が\\(0\\)であることから、さらに\\(a,b\to\infty\\)での極限を考えると、
長方形の残りの辺での積分値は一致する。

よって
$$
	\frac{1}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2-itx)dx=
	\frac{e^{-t^2/4}}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-(x+it/2)^2)dx=
	\frac{e^{-t^2/4}}{\sqrt{2\pi}}\int^\infty_{-\infty}\exp(-x^2)dx=
	\frac{1}{\sqrt{2}}e^{-t^2/4}
$$
と計算できる。
