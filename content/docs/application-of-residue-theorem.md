---
title: "留数定理の応用"
weight: 10
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---
# 留数定理の積分計算への応用

{{< katex >}}{{< /katex >}}

## 三角関数を含む定積分

三角関数の有理式の積分を留数定理を用いて計算しよう。
\\(F(X,Y)\\)を\\(X, Y\\)についての有理式としたとき、
$$
\int^{2\pi}_0F(\cos\theta, \sin\theta)d\theta
$$
を考える。

単位円周\\(\lvert z \rvert=1\\)正の向き\\(C\\)での線積分を\\(\gamma(\theta)=e^{i\theta}\\)とパラメータづけすることで、
\\(\theta\\)の\\(0\leq\theta\leq2\pi\\)での積分に書き換えることができる。
この書き換えの逆によって、数直線上の積分を単位円周での線積分に書き換えることにより、留数定理を用いて積分が計算できる。
$$
\cos\theta=\frac{z+z^{-1}}{2}, \sin\theta=\frac{z-z^{-1}}{2i}, dz=ie^{i\theta}d\theta=izd\theta
$$
となるので、
$$
\int^{2\pi}_0F(\cos\theta, \sin\theta)d\theta=\int_CF\left(\frac{z+z^{-1}}{2}, \frac{z-z^{-1}}{2i}\right)\frac{dz}{iz}
$$
である。
この単位円周での線積分を留数定理を用いて計算する。

いくつか例題を見てみよう。
{{< hint >}}
  $$
    \int^{2\pi}_0\frac{d\theta}{3+\sin\theta} 
  $$
  を計算する。

  まず上の通り単位円周での線積分に書き換えると、
  $$
    \int^{2\pi}_0\frac{d\theta}{3+\sin\theta}=\int_C\frac{1}{3+(z-z^{-1})/2i}\frac{dz}{iz}
    =\int_C\frac{2}{6iz+z^2-1}dz
    =2\int_C\frac{dz}{6iz+z^2-1}
  $$
  となる。

  ここで、\\(\dfrac{1}{6iz+z^2-1}\\)の正則でない孤立特異点は、\\(z^2+6iz-1=0\\)の解\\(z=-3i\pm2\sqrt{2}i\\)であり、これらはいずれも\\(1\\)位の極である。
  このうち\\(\lvert z\rvert&lt;1\\)なのは、\\(z=-3i+2\sqrt{2}i\\)のみである。

  \\(z=-3i+2\sqrt{2}i\\)での留数は、
  $$
    \lim_{z\to-3i+2\sqrt{2}i}\frac{1}{(z-(-3i+2\sqrt{2}i))(z-(-3i-2\sqrt{2}i))}(z-(-3i+2\sqrt{2}i))=\frac{1}{4\sqrt{2}i}
  $$
  である。
  
  よって、留数定理により
  $$
    2\int_C\frac{dz}{6iz+z^2-1} = \frac{4\pi i}{4\sqrt{2}i} = \frac{\pi}{\sqrt{2}}
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  $$
  \int^{2\pi}_0\frac{1}{5+3\cos\theta}d\theta=\frac{\pi}{2}
  $$
{{< /hint >}}

## 有理関数の無限区間上の定積分

{{< hint >}}
  $$
    \int^\infty_{-\infty}\frac{1}{1+x^4}dx=\frac{\pi}{\sqrt{2}}
  $$
  を示す。

  実数\\(R>0\\)に対して、\\(A_R\\)を原点中心半径\\(R\\)の上半円の正の向き、\\(I_R\\)を閉区間\\([-R, R]\\)負から正への向きとする。
  十分大きな\\(R\\)に対する閉曲線\\(C_R=H_R+I_R\\)での線積分
  $$
    \int_{C_R}\frac{1}{1+z^4}dz
  $$
  を留数定理を用いて計算する。

  \\(f(z)=\dfrac{1}{1+z^4}\\)は\\(1+z^4=0\\)の解\\(z=e^{\pi i/4}, e^{3\pi i/4}, e^{5\pi i/4}, e^{7\pi i/4}\\)でそれぞれ\\(1\\)の極を持つ。
  これらのうち\\(C_R\\)の内部にあるのは\\(z=e^{\pi i/4}, e^{3\pi i/4}\\)の二つである。
  それぞれにおける\\(f\\)の留数を求めよう。
  ロピタルの定理を使って計算すると、
  $$
    \lim_{z\to e^{\pi i/4}}\frac{z-e^{\pi i/4}}{1+z^4}=\frac{1}{4e^{3\pi i/4}}\\\\
    \lim_{z\to e^{3\pi i/4}}\frac{z-e^{3\pi i/4}}{1+z^4}=\frac{1}{4e^{\pi i/4}}
  $$
  である。
  よって、留数定理により
  $$
    \int_{C_R}\frac{1}{1+z^4}dz=2\pi i\left(\frac{e^{-3\pi i/4}+e^{-\pi i/4}}{4}\right)=\frac{\pi i}{2}(-2i\frac{1}{\sqrt{2}})=\frac{\pi}{\sqrt{2}}
  $$
  となる。
  これは\\(R\\)には依存しない。

  次に、\\(I_R\\)における線積分を計算する。
  \\(I_R\\)を\\(\gamma(t)=t\\)でパラメータづけると
  $$
    \int_{I_R}\frac{1}{1+z^4}dz=\int^R_{-R}\frac{1}{1+t^4}dt
  $$
  である。
  これの\\(R\to\infty\\)の極限が（広義積分の存在は別に証明が必要だが、）求める積分である。

  最後に\\(A_R\\)における線積分を計算する。
  実際には、これが\\(R\to\infty\\)で\\(0\\)に収束することを証明する。
  そのため、絶対値を評価する。
  まず積分の三角不等式により
  $$
    \left\lvert\int_{A_R}\frac{1}{1+z^4}dz\right\rvert
    \leq\int_{H_R}\left\lvert\frac{1}{1+z^4}\right\rvert\lvert dz\rvert
  $$
  である。
  ここでさらに\\(\lvert z\rvert=R\\)のとき、\\(R\\)が十分大きければ、三角不等式より\\(R^4-1\leq \lvert1+z^4\rvert\\)となる。
  よって、
  $$
    \int_{H_R}\left\lvert\frac{1}{1+z^4}\right\rvert\lvert dz\rvert
    \leq\int_{H_R}\frac{1}{R^4-1}\lvert dz\rvert=\frac{\pi R}{R^4-1}
  $$
  となる。
  これは\\(R\to\infty\\)で\\(0\\)に収束するので、
  $$
    \lim_{R\to\infty}\int_{A_R}\frac{1}{1+z^4}dz=0
  $$
  である。

  以上より
  $$
    \frac{\pi}{\sqrt{2}}=\int_{I_R}\frac{1}{1+z^4}dz+\int_{H_R}\frac{1}{1+z^4}dz
  $$
  で、\\(R\to\infty\\)の極限をとることで、
  $$
    \frac{\pi}{\sqrt{2}}=\int_{-\infty}^\infty\frac{1}{1+x^4}dx
  $$
  が得られる。
{{< /hint >}}

{{< hint >}}
  $$
    \int^\infty_0\frac{1}{x^3+1}dx=\frac{ 2\pi}{3\sqrt{3}}
  $$
  を示す。

  \\(f(z)=\dfrac{1}{z^3+1}\\)とおく。
  \\(R\\)を正の実数とし、\\(I_R\\)を実軸の\\(0\\)から\\(R\\)に向かう線分、\\(A_R\\)を半径\\(R\\)の円弧のうち偏角が\\(0\\)から\\(\dfrac{2\pi}{3}\\)の部分、
  \\(J_R\\)を\\(z=R\exp(\frac{2\pi}{3}i)\\)から\\(z=0\\)を結ぶ線分とし、\\(C_R=I_R+A_R+J_R\\)とする。

  \\(C_R\\)内部にある\\(f\\)の極は\\(z^3+1=0\\)の解のうち\\(z=e^{\pi i/3}\\)のみである。
  ここでの\\(f\\)の留数は、ロピタルの定理を用いて
  $$
    \lim_{z\to e^{\pi i/3}}\frac{z-e^{\pi i/3}}{z^3+1}=\frac{1}{3e^{2\pi i/3}}
  $$
  と計算できる。
  よって、留数定理により
  $$
    \int_{C_R}f(z)dz=2\pi i\frac{1}{3e^{2\pi i/3}}
  $$
  である。

  この左辺の積分を三つの曲線に分けて計算する。

  まず\\(I_R\\)での積分は
  $$
    \int_{I_R}f(z)dz=\int^R_0\frac{1}{x^3+1}dx
  $$
  であり、\\(R\to\infty\\)としたものが求めるべき積分である。

  次に\\(J_R\\)での積分は
  また、
  $$
    \int_{J_R}f(z)dz=\int^0_R\frac{1}{(x\exp(\frac{2\pi}{3}i))^3+1}e^{2\pi i/3}dx=-e^{2\pi i/3}\int^R_0\frac{1}{x^3+1}dx
  $$
  である。

  最後に\\(A_R\\)での積分は、、三角不等式を用いると、
  $$
    \left\lvert\int_{A_R}f(z)dz\right\rvert
    \leq
    \int_0^{2\pi/3}\left\lvert\frac{Rie^{i\theta}}{R^3e^{3 i\theta}+1}\right\rvert d\theta \\\\
    \leq\int_0^{2\pi/3}\frac{R}{R^3-1}d\theta
    =\frac{R}{R^3-1}\frac{2\pi}{3}
  $$
  となる。
  これは\\(R\to\infty\\)で\\(0\\)に収束するため、
  $$
    \lim_{R\to\infty}\int_{A_R}f(z)dz=0
  $$
  である。

  以上をまとめると、
  $$
    \frac{2\pi i}{3e^{2\pi i/3}} = (1-e^{2\pi i/3})\int^R_0\frac{1}{x^3+1}dx+\int_{A_R}\frac{1}{z^3+1}dz
  $$
  である。

  この式で\\(R\to\infty\\)とすることで、
  $$
    \frac{2\pi i}{3e^{2\pi i/3}} = (1-e^{2\pi i/3})\int^\infty_0\frac{1}{x^3+1}dx
  $$
  となる。
  よって、
  $$
    \int^\infty_0\frac{1}{x^3+1}dx=\frac{2\pi i}{3}e^{-2\pi i/3}(1-e^{2\pi i/3})^{-1}
    =\frac{2\pi}{3\sqrt{3}}
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  自然数\\(n\\)に対し
  $$
    \int^\infty_0\frac{1}{x^n+1}dx=\frac{\pi}{n\sin(\pi/n)}
  $$
  を示す。
{{< /hint >}}

## フーリエ変換の計算例

{{< hint >}}
  \\(\xi>0\\)とし、
  $$
    \int^\infty_{-\infty}\frac{e^{i\xi x}}{x^2+1}dx
  $$
  を計算する。

  積分経路として、\\(C=C_1+C_2\\)とし、\\(C_1\\)は実軸上\\(-R\\)から\\(R\\)まで、\\(C_2\\)を原点中心半径\\(R\\)の上半円周とする。
  \\(f(z)=\dfrac{e^{i\xi z}}{z^2+1}\\)は\\(C\\)の内部に\\(z=i\\)に\\(1\\)の極をもち、留数は
  $$
    \lim_{z\to i}\frac{e^{i\xi x}}{z^2+1}(z-i)=\frac{e^{-\xi}}{2i}
  $$
  である。
  よって、
  $$
    \int_C\frac{e^{i\xi z}}{z^2+1}dz=\pi e^{-\xi}
  $$
  となる。

  $$
    \int_{C_1}\frac{e^{i\xi z}}{z^2+1}dz=\int^R_{-R}\frac{e^{i\xi z}}{z^2+1}dz
  $$
  であり、（収束を示した上では）\\(R\to\infty\\)とすることで、
  $$
    \int^\infty_{-\infty}\frac{e^{i\xi x}}{x^2+1}dx
  $$
  に収束する。

  $$
    \left\lvert\int_{C_2}\frac{e^{i\xi z}}{z^2+1}dz\right\rvert
    \leq\int_0^\pi\left\lvert\dfrac{e^{i\xi Re^{i\theta}}}{R^2e^{2i\theta}+1}iRe^{i\theta}\right\rvert d\theta
    \leq\int_0^\pi\dfrac{e^{-\xi R\sin\theta}}{R^2-1}Rd\theta
  $$
  で、\\(R\\)が十分大きいとき\\(\xi>0\\)であることから、
  $$
    \leq\int_0^\pi\dfrac{R}{R^2-1}d\theta=\dfrac{\pi R}{R^2-1}
  $$
  で、\\(R\to\infty\\)で\\(0\\)に収束する。
{{< /hint >}}

## 半周の留数

{{< hint >}}
  \\(g\\)が正則であるとき、\\(H_r\\)を原点中心半径\\(r\\)の上半円に反時計まわりに向きをつけたものとすると、
  $$
  \lim_{r\to+0}\int_{H_r}\frac{g(z)}{z}dz=\pi ig(0)=\pi iRes_{z=0}\frac{g(z)}{z}
  $$
  となる。
{{< /hint >}}

{{< hint >}}
  コーシーの積分公式と同様に証明できる。
  $$
  \int_{H_r}\frac{g(z)}{z}dz=\int_{H_r}\frac{g(0)}{z}dz+\int_{H_r}\frac{g(z)-g(0)}{z}dz\\\\
  =g(0)\int_{H_r}\frac{1}{z}dz+\int_{H_r}\frac{g(z)-g(0)}{z}dz\\\\
  =\pi ig(0)+\int_{H_r}\frac{g(z)-g(0)}{z}dz
  $$
  であり、
  $$
  \lvert\int_{H_r}\frac{g(z)-g(0)}{z}dz\rvert\leq(\lvert g'(0)\rvert+\epsilon)\pi r
  $$
  で、\\(r\to0\\)で\\(0\\)に収束する。
{{< /hint >}}

これを利用して、以下の積分を計算しよう。

{{< hint >}}
  $$
  I=\int^\infty_0\frac{\sin x}{x}dx=\frac{\pi}{2}
  $$
  を示す。

  積分経路\\(C=H_1+H_2+J_1+J_2\\)を以下のように定める。
  \\(H_1\\)は原点中心半径\\(R\\)の上半円で反時計回りに向きをつけたもの、\\(H_2\\)は原点中心半径\\(r\\)の上半円で時計回りに向きをつけたもの。
  \\(J_1\\)は実軸の\\(-R\\)から\\(-r\\)で\\(J_2\\)は実軸の\\(r\\)から\\(R\\)の区間。
  
  \\(f(z)=\frac{e^{iz}}{z}\\)とおくと、これは\\(z=0\\)のみで\\(1\\)の極を持つ。
  よって、
  $$
  \int_Cf(z)dz=0
  $$
  である。

  $$
  \int_{J_1}\frac{e^{iz}}{z}dz+\int_{J_2}\frac{e^{iz}}{z}dz=\int^{-r}_{-R}\frac{e^{it}}{t}dt+\int^R_r\frac{e^{it}}{t}dt\\\\
  =2i\int^R_r\frac{\sin t}{t}dt
  $$
  である。

  \\(H_1\\)を\\(z=Re^{i\theta}\\)とパラメータつけて積分を評価する。
  $$
  \lvert\int_{H_1}\frac{e^{iz}}{z}dz\rvert\leq\int_{H_1}\lvert\frac{e^{iz}}{z}\rvert \lvert dz\rvert\\\\
  =\int^\pi_0\frac{1}{R}\lvert e^{iRe^{i\theta}}\rvert \lvert Rie^{i\theta}\rvert d\theta\\\\
  =\int^\pi_0e^{-R\sin\theta}d\theta\\\\
  =2\int^{\pi/2}e^{-R\sin\theta}d\theta\\\\
  \leq 2\int^{\pi/2}e^{-2R\theta/\pi}d\theta\\\\
  =\frac{\pi}{R}(1-e^{-R})\to0(R\to\infty)
  $$
  となる。
  
  次に\\(r\to+0\\)で
  $$
  \int_{H_2}\to -\pi i
  $$
  となることを示す。
  これは以下に述べる半周の留数で、\\(g(z)=e^{iz}\\)として向きに注意して用いればよい。

  以上をまとめると、\\(R\to\infty, r\to+0\\)の極限を取ることで、（あらかじめ広義積分の収束は示した上で？）
  $$
  0=2i\int^\infty_0\frac{\sin x}{x}dx-\pi i
  $$
  となり、
  $$
  \int^\infty_0\frac{\sin x}{x}dx=\frac{\pi}{2}
  $$
  となる。
{{< /hint >}}


## 多価関数を含む定積分

複素数\\(s\\)に対し、\\(z^s\\)を単位円周で積分することを考えよう。
全体で一価正則には定義できないので、\\(z=1\\)を除いた広義積分と解釈してもよいし、半円に分けてそれぞれの積分の和と考えてもよい。
\\(z\\)の偏角を\\(0\leq \arg z\leq 2\pi\\)ととることにする。
単位円周のパラメータづけを\\(\gamma(t)=\exp(2\pi it)\\)とすると、
$$
  z^s=\gamma(t)^s=\exp(s\log\gamma(t))=\exp(s2\pi t i)
$$
となる。
よって、\\(s\neq 1\\)のとき、
$$
  \int_Cz^sdz = \int_0^1\exp(2\pi tis)2\pi i\exp(2\pi it)dt \\\\
  = 2\pi i\left[\frac{1}{2\pi i(s+1)}\exp(2\pi i(s+1)t)\right]^1_0
  = 2\pi i(\exp(2\pi i(s+1))-1)
$$
となる。\\(s\\)が整数ならこれは\\(0\\)だが、そうでない場合には\\(0\\)とならない。

円周の半径を\\(r\\)として同様の計算を行う。
円周\\(C_r\\)のパラメータづけを\\(\gamma(t)=r\exp(2\pi it)\\)とすると、
$$
  z^s=\gamma(t)^s=\exp(s\log\gamma(t))=\exp(s(r+2\pi t i))=\exp(rs)\exp(2\pi ist)
$$
となる。
よって、\\(s\neq 1\\)のとき、
$$
  \int_Cz^sdz = \int_0^1\exp(2\pi tis)2\pi i\exp(2\pi it)dt \\\\
  = 2\pi i\left[\frac{1}{2\pi i(s+1)}\exp(2\pi i(s+1)t)\right]^1_0
  = 2\pi i(\exp(2\pi i(s+1))-1)
$$
となる。こちらもやはり\\(s\\)が整数ならこれは\\(0\\)だが、そうでない場合には\\(0\\)とならない。
また、\\(r\\)に依存することにも注意しよう。
\\(z^s\\)が一価正則な原始関数を持つならば線積分の値は\\(r\\)には依存しない。

留数定理による積分計算の例題を見てみよう。
ここでは特に関数の多価性を利用する例を紹介する。  

{{< hint >}}
\\(s\\)を複素数で、その実部が\\(0&lt;Re(s)&lt;1\\)なるものとする。
$$
    \int^\infty_0\frac{x^{s-1}}{x+1}=\frac{\pi}{\sin\pi s}
$$
を示そう。

$$
    f(z)=\frac{z^{s-1}}{z+1}
$$
とすると、\\(z^{s-1}\\)に多価性があるので、実軸の正の部分を除いた領域を定義域とし、
\\(z\\)の偏角を\\(0&lt;\arg z&lt;2\pi\\)とすることで定まる分枝をとって一価正則な関数を定める。
$$
    z^{s-1}=\exp((s-1)\log z)
$$
と定義していたことを思い出そう。
このとき、\\(z=-1\\)のみが孤立特異点でそこでの留数は\\((-1)^{s-1}=\exp((s-1)\pi i)=-\exp(s\pi i)\\)である。

さて、積分経路\\(C\\)を次の四つの曲線を繋いでできるものとする。
\\(C_1\\)を実軸の\\(0&lt;\epsilon\\)から\\(R\\)まで。
パラメータづけを\\(z=x, x\in[\epsilon,R]\\)で与える。
\\(z^{s-1}\\)はha\\(\arg z=0\\)で考える。
ここでの積分は
$$
    \int_{C_1}f(z)dz=
    \int_\epsilon^R\frac{x^{s-1}}{x+1}dx
$$
となり、\\(R\to\infty, \epsilon\to0\\)の極限を取ることで
$$
    \int^\infty_0\frac{x^{s-1}}{x+1}dx
$$
に収束する。

\\(C_2\\)を半径\\(R\\)の円を偏角\\(0\\)から\\(2\pi\\)での円周とする。

パラメータづけを\\(\gamma(t)=R\exp(2\pi it)\\)とすると、
\\(\gamma\'(t)=R2\pi i\exp(2\pi it)\\)であり、\\(\lvert\gamma\'(t)\rvert=2\pi R\\)である。

また、
$$
  \gamma(t)^{s-1}=\exp((s-1)\log(R\exp(2\pi it)))=\exp((s-1)(\log R+ 2\pi it))
$$
であり、
$$
  \lvert\gamma(t)^{s-1}\rvert=\exp(Re((s-1)(\log R+ 2\pi it)))=\exp((Re(s)-1)\log R - Im(s)2\pi t)
$$
である。

積分の絶対値は
$$
    \int_{C_2}f(z)dz
    =
    \int_0^1\frac{R^{s-1}\exp(2\pi i(s-1)t)}{R\exp(2\pi it)+1}2\pi iR\exp(2\pi it)dt
$$
となる。
これの絶対値は
$$
    \left\lvert \int_{C_2} f(z)dz\right\rvert 
    \leq
    2\pi R\int_0^1\left\lvert\frac{\gamma(t)^{s-1}}{\gamma(t)+1}\right\rvert dt
$$
となり、これは\\(s\\)の実部が\\(1\\)より小さいから\\(R\to\infty\\)で\\(0\\)に収束する。

\\(C_3\\)を実軸の\\(R\\)から\\(\epsilon\\)までの線分とする。
ここでは\\(\arg z=2\pi\\)となることに注意すると、積分は
$$
    \int_{C_3}f(z)dz
    =
    \exp(2\pi i(s-1))\int_R^\epsilon\frac{x^{s-1}}{\exp(2\pi i)x+1}\exp(2\pi i)dx
$$
となり、\\(R\to\infty, \epsilon\to0\\)の極限を取ることで
$$
    -\exp(2\pi i(s-1))\int^\infty_0\frac{x^{s-1}}{x+1}dx
$$
に収束する。

\\(C_4\\)を半径\\(\epsilon\\)の円を偏角\\(2\pi\\)から\\(0\\)までの円周とすると、
\\(C_2\\)と同様に\\(s\\)の実部が\\(0\\)より大きいから、これは\\(\epsilon\to0\\)で\\(0\\)に収束する。

全て合わせて\\(R\to\infty, \epsilon\to0\\)の極限を考えると
$$
    (1-\exp(2\pi i(s-1)))\int^\infty_0\frac{x^{s-1}}{x+1}dx
    =-2\pi i\exp(\pi is)\\\\
    \int^\infty_0\frac{x^{s-1}}{x+1}dx
    =2\pi i\frac{-\exp(\pi is)}{1-\exp(2\pi is)}\\\\
    =
    \frac{-2\pi i}{\exp(-\pi is)-\exp(\pi is)}\\\\
    =
    \frac{\pi}{\sin \pi\alpha}
$$
となる。
{{< /hint >}}

上の積分は\\(f(x)=\dfrac{1}{x+1}\\)のメリン変換
$$
\int^\infty_0f(x)x^{s-1}dx
$$
を計算したことになる。

この積分

$$
\int^\infty_0\frac{x^{s-1}}{x+1}dx=\frac{\pi}{\sin \pi s}
$$

において\\(\dfrac{1}{x+1}=t\\)とすると、\\(x=\dfrac{1-t}{t}, dx=-\dfrac{dt}{t^2}\\)となるので

$$
\int^\infty_0\frac{x^{s-1}}{x+1}dx
=\int^1_0t^{-s}(1-t)^{s-1}dt\\\
=B(1-s,s)\\\\
=\Gamma(s)\Gamma(1-s)
$$
となる。

結果として、例で与えた計算により、\\(\Gamma\\)関数の相補公式
$$
\Gamma(s)\Gamma(1-s)=\frac{\pi}{\sin(\pi s)}
$$
が\\(0&lt;Re(s)&lt;1\\)で証明された。
この両辺は\\(\mathbb{C}\\)全体で有理形関数として定義されるので、一致の定理から\\(\mathbb{C}\\)全体で上の等式が示される。

{{< hint >}}
\\(a,b\in\mathbb{R}, a&lt;b\\)として
$$
    \int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}
$$
を計算する。
これは三角関数による置換積分で初等的にも計算可能である。

まず
$$
    f(z)=((z-a)(b-z))^{-1/2}
$$
とする。
ただしこれは多価関数なので、分枝を\\(x\\)軸の\\(b\\)より大きな部分で\\(\sqrt{z-b}, \sqrt{z-a}\\)がともに正になるように選ぶ。
するとこれは\\(\mathbb{C}\\)から線分\\([a,b]\\)を除いた領域で一価正則関数を定める。
ここで、\\(a,b\\)をともに囲むような円周に沿って一周回ったときに何が起こるか気になるが、
二つの平方根が両方符号が変わることによってトータルでは符号が変わらないという現象が起きていることに注意しよう。

さて、このような\\(a,b\\)をともに囲む円周\\(C\\)に沿った線積分
$$
    \int_Cf(z)dz
$$
を考える。
この線積分を留数定理を用いて計算したいが、このままではうまくいかない。
というのも、この円周の内部において\\(f\\)は「有限個の孤立特異点を除いて正則」という条件を満たさないためである。

ではどうするかというと、\\(w=\dfrac{1}{z}\\)と置換する。
すると、
$$
    f(z)=((z-a)(b-z))^{-1/2}\\\\
    =(z^2(1-\frac{a}{z})(\frac{b}{z}-1))^{-1/2}\\\\
    =\frac{1}{z}((1-\frac{a}{z})(\frac{b}{z}-1))^{-1/2}
$$
となる。

したがって\\(\dfrac{dz}{z}=\dfrac{dw}{w}\\)であり、また回る向きが逆になることに注意して
$$
    \int_C f(z)dz=-\int_C\frac{1}{w}((1-aw)(bw-1))^{-1/2}dw
$$
となる。

この形にすると\\(w\\)についての関数は\\(\dfrac{1}{w}\notin[a,b]\\)において\\(w=0\\)で孤立点を持つ以外は一価正則関数となる。
したがって留数定理を用いることができて、\\(w=0\\)での留数は上の関数をローラン級数展開することにより\\(1\\)とわかる。
よって、\\(w\\)についての積分と
$$
    \int_C f(z)dz=-\int_C\frac{1}{w}((1-aw)(bw-1))^{-1/2}dw\\\\
    =-2\pi i
$$
である。


一方で元の\\(z\\)についての積分を積分経路を次のように取り替える。
\\(C_1\\)を\\(O\\)の周りを反時計回りに偏角\\(0\\)から\\(2\pi\\)まで回る半径\\(r\\)の円周、
\\(C_3\\)を\\(O\\)の周りを反時計回りに偏角\\(-\pi\\)から\\(\pi\\)まで回る半径\\(r\\)の円周、
\\(C_2\\)を\\(C_1\\)の終点から\\(C_3\\)の始点を結ぶ線分、
\\(C_4\\)を\\(C_3\\)の終点から\\(C_1\\)の始点を結ぶ線分とすると、\\(C\\)についての線積分と\\(C_1, C_2, C_3, C_4\\)についての線積分の和が一致することはコーシーの積分定理よりわかる。
この\\(4\\)つの曲線に沿った線積分を計算しよう。



\\(C_1\\)に沿った線積分をパラメータ\\(\gamma(t)=r\exp(2\pi it)+a\\)として計算する。
$$
    \int_{C_1}f(z)dz
    =
    \int_0^1(r\exp(2\pi it)(b-a-r\exp(2\pi it)))^{-1/2}r2\pi i\exp(2\pi it)dt\\\\
    =
    2\pi ir\int_0^1(r\exp(2\pi it)(b-a)-r^2\exp(4\pi it))^{-1/2}\exp(2\pi it)dt
$$
となる。
\\(r\to0\\)の極限を計算することに注意して、\\(r\\)を十分小さいとすれば
$$
    \lvert \int_{C_1} \rvert f(z)dz
    \leq
    2\pi r\int_0^1(r(b-a))^{-1/2}dt
$$
となるから\\(r\to0\\)で上の積分は\\(0\\)に収束する。
\\(C_3\\)に沿った線積分についても同様。



\\(C_2\\)に沿った線積分は実軸上の積分だが、分枝の取り方に注意する。
\\(z-a=\exp(2\pi i)(x-a), b-z=\exp(-\pi i)(b-x)\\)となるので、\\(r\to0\\)とすると
$$
    \int_{C_2}f(z)dz
    =
    \int_a^b\exp(-\frac{\pi i}{2})\frac{dx}{\sqrt{(x-a)(b-x)}}\\\\
    =
    -i\int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}
$$
となる。



\\(C_4\\)に沿った積分も同様で、\\(z-a=\exp(2\pi i)(x-a), b-z=\exp(\pi i)(b-x)\\)となるので、\\(r\to0\\)とすると
$$
    \int_{C_2}f(z)dz
    =
    \int_b^a\exp(-\frac{3\pi i}{2})\frac{dx}{\sqrt{(x-a)(b-x)}}\\\\
    =
    -i\int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}
$$
となる。



以上をまとめると
$$
    -2i\int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}=-2\pi i\\\\
    \int_a^b\frac{dx}{\sqrt{(x-a)(b-x)}}=\pi
$$
と計算できる。

{{< /hint >}}

{{< hint >}}
  $$
    \int_a^b\sqrt{(x-a)(b-x)}dx
  $$
  を計算せよ。

  $$
    \int_a^b\sqrt{(x-a)(b-x)}dx =\frac{\pi}{8}(a-b)^2
  $$
  となる。
  これは半円の面積。
{{< /hint >}}
