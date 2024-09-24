---
title: "複素数と複素平面"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# 複素数と複素平面


複素解析では定義域と値域が複素数であるような関数について調べる。
特に微分可能な関数を正則関数といい、正則関数の性質を調べるのが目的である。

複素数と複素平面．複素微分
複素数と複素平面について復習した後，複素関数の連続性と微分を解説する．

## 複素数と四則

複素数とは、実数の組\\(x, y\\)を用いて定まる数
{{< katex >}}z=x+yi{{< /katex >}}
\\(x\\)を\\(z\\)の実部といい\\(Re(z)\\)で表す。
\\(y\\)を\\(z\\)の虚部といい\\(Im(z)\\)で表す。
また、\\(i\\)を虚数単位という。

複素数全体の集合を\\(\mathbb{C}\\)と表す。
\\(z\in\mathbb{C}\\)であれば、一意的に実数\\(x, y\\)を用いて\\(z=x+yi\\)と表すことができる。
二つの複素数が一致することは、実部と虚部が共に等しいこととして定義する。
つまり、\\(z=x+yi, z\'=x\'+y\'i\\)について、\\(z=z\'\\)であることと\\(x=x\'\\)かつ\\(y=y\'\\)であることが同値である。

複素数全体の集合は、集合としては実数の対全体の集合\\(\mathbb{R}^2=\mathbb{R}\times \mathbb{R}\\)と思うことができる。
この集合に四則演算を、特に\\(i^2=-1\\)となるように複素数の積を定める。

## 複素数の四則演算

足し算と引き算はベクトル空間\\(\mathbb{R}^2\\)のものと同じである。
つまり実部同士と虚部同士をそれぞれ足し引きすればいい。
$$
	(a+bi)+(c+di)=(a+c)+(b+d)i\\\\
	(a+bi)-(c+di)=(a-c)+(b-d)i
$$

この定義のもとで、\\(a+bi=(a+0i)+(0+bi)\\)である。

掛け算は次のように定める。
$$
	(a+bi)(c+di)=(ac-bd)+(ad+bc)i
$$
これは、\\(i^2=-1\\)かつ実双線形（分配法則を満たす）という条件で特徴づけられる。

この定義のもとで、\\(bi=(b+0i)(0+1i)\\)である。

割り算をどう定義するかを考えよう。
$$
	(a+bi)/(c+di)=(a+bi)\times\frac{1}{c+di}
$$
とすることで、逆数を定めればよいことになる。

では逆数はどう定めるかというと、
$$
	(a+bi)(x+yi)=(ax-by)+(ay+bx)i=1
$$
となる複素数\\(x+yi\\)が\\(a+bi\\)の逆数であるから、この方程式を解けばよい。

すなわち
$$
	\begin{cases}
	ax-by=1\\\\
	ay+bx=0
	\end{cases}
$$
あるいは行列とベクトルを用いて
$$
	\begin{pmatrix}
	a&-b\\\\
	b&a
	\end{pmatrix}
	\begin{pmatrix}
	x\\\\
	y
	\end{pmatrix}
	=
	\begin{pmatrix}
	1\\\\
	0
	\end{pmatrix}
$$
を解くことで、\\(x=\dfrac{a}{a^2+b^2}, y=\dfrac{-b}{a^2+b^2}\\)となり、
$$
	\frac{1}{a+bi}=\dfrac{a}{a^2+b^2}+\dfrac{-b}{a^2+b^2}i
$$
とわかる。

あるいは、\\((a+bi)(a-bi)=a^2+b^2\\)となることを利用して、分子分母に\\(a-bi\\)をかけると考えることもできる。

この四則演算について、通常の実数の和や積と同様に結合法則や交換法則、分配法則が成り立つことが証明できる。

## 複素共役

\\(z\in\mathbb{C}\\)に対し、\\(z=a+bi\\)であるとき\\(\bar{z}\in\mathbb{C}\\)を\\(\bar{z}=a-bi\\)により定める。
これを\\(z\\)の複素共役という。

複素共役は2回行うと元に戻る。
つまり、\\(\bar{\bar{z}}=z\\)である。

複素共役をとる操作と四則演算は順序を入れ替えることができる。
すなわち以下が成り立つ。

$$
	\overline{\alpha\pm\beta}=\overline{\alpha}\pm\overline{\beta}\\\\
	\overline{\alpha\beta}=\overline{\alpha}\overline{\beta}\\\\
	\overline{\left(\dfrac{\alpha}{\beta}\right)}=\dfrac{\overline{\alpha}}{\overline{\beta}}
$$


\\(z\\)が実数であることは、\\(z=\bar{z}\\)と同値である。

\\(z\\)と\\(\bar{z}\\)から\\(z\\)の実部虚部を復元できる。
$$
	Re(z)=\frac{z+\overline{z}}{2}\\\\
	Im(z)=\frac{z-\overline{z}}{2i}
$$

## 複素数の絶対値
複素数\\(z=x+yi\\)に対し、
$$
\lvert z\rvert=\sqrt{z\overline{z}}=\sqrt{x^2+y^2}
$$
と定義し、これを\\(z\\)の絶対値と呼ぶ。

\\(\lvert z\rvert=1\\)のとき、\\(\bar{z}=\dfrac{1}{z}\\)である。

## 複素平面

複素数\\(z=x+yi\\)に対して\\((x,y)\\)という点を対応させることで、複素数を\\(xy\\)座標平面にプロットできる。
\\(x\\)軸と\\(y\\)軸の代わりに実軸と虚軸と呼ぶ。

複素数の和は平面ベクトルの和と同じで、平行四辺形により定まる。
また、複素共役は\\(x\\)軸に関する鏡映変換である。
複素数\\(z\\)の絶対値\\(\lvert z\rvert\\)は線分\\(0z\\)の長さである。

複素数の和と絶対値に関しては、三角不等式が成り立つ。
距離、位相に関連して、収束などを議論する上で重要な性質である。
$$
\lvert z\rvert-\lvert w\rvert\leq\lvert z+w\rvert\leq\lvert z\rvert+\lvert w\rvert
$$

\\(0\\)でない複素数\\(z\\)に対し、その偏角とは、線分\\(0z\\)と実軸のなす角のこと。
角の範囲を\\(0\\)から\\(2\pi\\)とすれば一意に定まるが、一般角としては一意ではないことに注意しよう。


## 極形式

複素数の積と複素平面の関係については極形式の方が見やすい。
積の絶対値が積、積の偏角が和に対応する。
積と和を結びつけるものとして、指数関数と対数関数があるが、後で見るように偏角は対数関数と関係する。

\\(0\\)でない複素数\\(z\\)の極形式とは、
$$
z=r(\cos\theta+i\sin\theta)
$$
のことをいう。
単位円を用いた三角関数の定義を思いだそう。

ここで、\\(z=x+yi\\)に対し、\\(r=\lvert z\rvert=\sqrt{x^2+y^2}\\)は\\(z\\)の絶対値で
\\(\theta\\)は\\(z\\)の偏角である。

つまり、\\(\theta=\arctan\dfrac{x}{y}\\)であり、\\(r\cos\theta=x, r\sin\theta=y\\)で定まるもの。
\\(\theta\\)は\\(2\pi\\)の不定性がある。

積と回転。
複素数の積に対し、絶対値は積、偏角は和になる。
\\(z_1=r_1(\cos\theta_1+i\sin\theta_1), z_2=r_2(\cos\theta_2+i\sin\theta_2)\\)とすると、
$$
z_1z_2=r_1r_2(\cos(\theta_1+\theta_2)+i\sin(\theta_1+\theta_2))
$$
となる。
これは加法定理から証明できる。

{{< hint >}}

\\(\alpha=1+i=\sqrt{2}(\cos\dfrac{\pi}{4}+i\sin\dfrac{\pi}{4}),
\beta=\sqrt{3}+i=2(\cos\dfrac{\pi}{6}+i\sin\dfrac{\pi}{6})\\)に対し、
\\(\alpha\beta=2\sqrt{2}(\cos\dfrac{5}{12}\pi+i\sin\dfrac{5}{12}\pi)\\)となることを用いて
\\(\cos\dfrac{5}{12}\pi, \sin\dfrac{5}{12}\pi\\)を求めることができる。
{{< /hint >}}

## 複素平面における直線
\\(xy\\)座標平面における直線は\\(x, y\\)の一次式で表すことができた。
複素平面において、\\(z\\)と\\(\bar{z}\\)の一次式でも表すことができる。
例えば\\(z-\bar{z}=0\\)が実軸、\\(z+\bar{z}=0\\)が虚軸である。
\\(\alpha z-\bar{\alpha z}=0\\)が原点と\\(z=\bar{\alpha}\\)を通る直線。
\\(\alpha(z-\beta)-\bar{\alpha}(\bar{z}-\bar{\beta})=0\\)が\\(z=\beta\\)を通る直線である。

## 複素平面における円

平面における円は、ある点（これを中心という）から等しい距離（これを半径という）にある点の集まり。

\\(\lvert z\rvert=r\\)は原点中心で半径\\(r\\)の円の方程式である。

また、\\(\lvert z-\alpha\rvert=r\\)が\\(z=\alpha\\)が中心で半径\\(r\\)の円の方程式である。

## 一次分数変換と円
一次分数変換\\(w=\dfrac{az+b}{cz+d}\\)により、円\\(\lvert w\rvert = k\\)にうつる\\(z\\)の条件を求めよう。

\\(\lvert\dfrac{az+b}{cz+d}\rvert=k\\)を整理する。
$$
	\lvert az+b\rvert=k\lvert cz+d\rvert\\\\
	\lvert a\rvert\lvert z+\dfrac{b}{a}\rvert=k\lvert c\rvert\lvert z+\dfrac{d}{c}\rvert\\\\
	\lvert z+\dfrac{b}{a}\rvert:\lvert z+\dfrac{d}{c}\rvert=\lvert a\rvert:k\lvert c\rvert
$$
となる。
\\(-\dfrac{b}{a}\\)からの距離と\\(-\dfrac{d}{c}\\)からの距離の比が\\(\lvert a\rvert : k\lvert c\rvert\\)になる点の集まりが求める集まり。
これはアポロニウスの円である。

一次分数変換により円と円が対応する。

## ドモアブルの公式
\\(z=r(\cos\theta+i\sin\theta)\\)に対し、
\\(z^n=r^n(\cos n\theta+i\sin n\theta)\\)となる。

\\(z=r(\cos\theta+i\sin\theta)\\)に対し、\\(z\\)の\\(n\\)乗根は
$$
	r^{1/n}(\cos(\dfrac{\theta}{n}+\dfrac{2\pi}{n}k)+i\sin(\dfrac{\theta}{n}+\dfrac{2\pi}{n}k))
$$
である。
\\(z\\)の偏角が一通りではなかったことに注意しよう。

特に\\(1\\)の\\(n\\)乗根は、整数\\(k\\)を用いて
$$
\cos\frac{2\pi}{n}k+i\sin\frac{2\pi}{n}k
$$
と表すことができる。

また、一般の\\(\alpha\\)の\\(n\\)乗根は、\\(r\\)の\\(n\\)乗根に\\(1\\)の\\(n\\)乗根をかけることで全て得られる。