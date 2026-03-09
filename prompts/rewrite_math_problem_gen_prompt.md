# 数学問題作成

## タスク内容
あなたは中学/高校数学の教師です。
数学に関連した話題のテキストが入力として与えられます。
その題材に関連した中学生/高校生向けの数学の問題を1問作成してください。



## 入力出力形式

入力: 数学に関連した話題のテキストが与えられます。

出力: 以下の形式で出力してください
```tex
\section{問題}
ここに問題文を記述

\section{解説}
ここに解説を記述

\section{解答}
$$ここに解答をlatex形式で記述$$
```

出力はtexのコードブロックのみで、それ以外の文章は出力しないでください。


### 入出力例1
入力:
```txt
Question:
Need help finding limit $\lim \limits_{x\to \infty}\left(\frac{x}{x-1}\right)^{2x+1}$ Facing difficulty finding limit
$$\lim \limits_{x\to \infty}\left(\frac{x}{x-1}\right)^{2x+1}$$
For starters I have trouble simplifying it
Which method would help in finding this limit?

Answer:
$$
\begin{eqnarray}
\lim \limits_{x\to \infty}\left(\frac{x}{x-1}\right)^{2x+1}=\lim \limits_{x\to \infty}\left(\frac{x-1+1}{x-1}\right)^{2x+1}
=\lim \limits_{x\to \infty}\left(1+\frac{1}{x-1}\right)^{2x+1}\\= \lim \limits_{x\to \infty}\left(1+\frac{1}{x-1}\right)^{(x-1)\cdot\frac{2x+1}{x-1}}
=\lim \limits_{x\to \infty}\left(1+\frac{1}{x-1}\right)^{(x-1)\cdot\frac{2x+1}{x-1}}=e^{\lim \limits_{x\to \infty}\frac{2x+1}{x-1}}=e^2
\end{eqnarray}
$$
```


出力:
```tex
\section{問題}
次の極限を求めよ。
\[
\lim_{x \to \infty} \left( \frac{x}{x-1} \right)^{2x+1}
\]

\section{解説}
まず、括弧の中を
\[
\frac{x}{x-1} = \frac{(x-1)+1}{x-1} = 1 + \frac{1}{x-1}
\]
と変形すると、
\[
\left( \frac{x}{x-1} \right)^{2x+1}
= \left( 1 + \frac{1}{x-1} \right)^{2x+1}
\]
となる。

ここで、指数部分 $2x+1$ を
\[
2x+1 = (x-1)\cdot \frac{2x+1}{x-1}
\]
と書き直すと、
\[
\left( 1 + \frac{1}{x-1} \right)^{2x+1}
= \left( 1 + \frac{1}{x-1} \right)^{(x-1)\cdot \frac{2x+1}{x-1}}
= \left[ \left( 1 + \frac{1}{x-1} \right)^{x-1} \right]^{\frac{2x+1}{x-1}}
\]
と表せる。

よく知られた極限
\[
\lim_{t \to \infty} \left( 1 + \frac{1}{t} \right)^t = e
\]
を用いると、$t = x-1$ とおくことで
\[
\lim_{x \to \infty} \left( 1 + \frac{1}{x-1} \right)^{x-1} = e
\]
となる。また
\[
\lim_{x \to \infty} \frac{2x+1}{x-1} 
= \lim_{x \to \infty} \frac{2 + \frac{1}{x}}{1 - \frac{1}{x}} = 2
\]
である。

したがって、全体の極限は
\[
\left[ \left( 1 + \frac{1}{x-1} \right)^{x-1} \right]^{\frac{2x+1}{x-1}}
\to e^{2}
\]
となる。

\section{解答}
$\displaystyle \lim_{x \to \infty} \left( \frac{x}{x-1} \right)^{2x+1} = e^{2}$
```


### 入出力例2
入力:
```txt
To find the area enclosed by the given curves, we first need to identify the points of intersection between $x\_1 = (\tan(y))^2$ and $x\_2 = -(\tan(y))^2$. Since both expressions are equal to $x$, their values will be identical at any given value of $y$. By setting them equal to each other, i.e., $(\tan(y))^2 = -(\tan(y))^2$, we see that this equation has no solutions because the square of a real number cannot be negative. However, since $-(\tan(y))^2$ is defined for all $y$ where $(\tan(y))^2$ is defined except when $y = k\pi$ for integer $k$, we can conclude that the region enclosed by the two curves extends from $y = -\pi/4$ to $y = \pi/4$.

Now let's calculate the area using integration. The area function $A(y)$ gives us the signed area between the curve and the $x$-axis up to the vertical line $x = y$:

$$A'(y) = 2(\tan(y))^2.$$

To get the net enclosed area, we want the definite integral of $A'$ from $-\pi/4$ to $\pi/4$:

$$\begin{align*}
A\left(\frac{\pi}{4}\right)- A\left(-\frac{\pi}{4}\right) &= \int\_{-\frac{\pi}{4}}\^{\frac{\pi}{4}} 2(\tan(y))^2 \,dy \\
&= 2\int\_{-\frac{\pi}{4}}\^{\frac{\pi}{4}} \frac{\sin^2(y)}{\cos^2(y)}\,dy\\
&= 2\int\_{-\frac{\pi}{4}}\^{\frac{\pi}{4}} {\sec^2(y)-\csc^2(y)\,dy}\\
&= 2[\tan(y)+\cot(y)]\biggr\rvert\_{\frac{-\pi}{4}}\^{\frac{\pi}{4}},
\end{align*}$$

where we have used the trigonometric identity ${\sin}^2(y)+{\cos}^2(y)=1$ to simplify the integrand. Now evaluating this expression, we obtain

$$\begin{align*}
2[\tan(y)+\cot(y)]\biggr\rvert\_{\frac{-\pi}{4}}\^{\frac{\pi}{4}} &= 2[(\tan({\pi}/{4})+\cot({\pi}/{4})) - (\tan({-\pi}/{4}) + \cot({-\pi}/{4}))]\\
&= 2[(1+1)-(-1-1)]\\
&= 8.
\end{align*}$$

Therefore, the enclosed area between the graphs of $x\_1 = (\tan(y))^2$ and $x\_2=-(\tan(y))^2$ over the interval $[-\pi/4,\pi/4]$ is 8 square units.
```

出力:
```tex
\section{問題}
2つの曲線
\[
y = \tan x,\quad y = -\tan x
\]
および2本の直線
\[
x = -\frac{\pi}{4},\quad x = \frac{\pi}{4}
\]
で囲まれた図形の面積を求めなさい。

\section{解説}
求めたいのは、$x=-\frac{\pi}{4}$ から $x=\frac{\pi}{4}$ の間で、$y=\tan x$ と $y=-\tan x$ の間に挟まれた部分の面積である。

まず、どちらが上側のグラフになるかを考える。  
\begin{itemize}
  \item $0 < x < \frac{\pi}{4}$ のとき、$\tan x > 0$, $-\tan x < 0$ なので、上側が $y=\tan x$、下側が $y=-\tan x$。
  \item $-\frac{\pi}{4} < x < 0$ のとき、$\tan x < 0$, $-\tan x > 0$ なので、上側が $y=-\tan x$、下側が $y=\tan x$。
\end{itemize}

したがって、面積 $S$ は
\[
S = \int_{-\frac{\pi}{4}}^{0} \bigl(-\tan x - \tan x\bigr)\,dx
   + \int_{0}^{\frac{\pi}{4}} \bigl(\tan x - (-\tan x)\bigr)\,dx
   = \int_{-\frac{\pi}{4}}^{0} -2\tan x\,dx + \int_{0}^{\frac{\pi}{4}} 2\tan x\,dx
\]
となる。

ここで、$\tan x$ は奇関数であることから、$-2\tan x$ を $[-\frac{\pi}{4},0]$ で積分した値と、$2\tan x$ を $[0,\frac{\pi}{4}]$ で積分した値は等しくなる。よって
\[
S = 2 \int_{0}^{\frac{\pi}{4}} 2\tan x\,dx = 4\int_{0}^{\frac{\pi}{4}} \tan x\,dx
\]
と計算できる。

$\tan x$ の原始関数は $\displaystyle \int \tan x\,dx = -\ln|\cos x| + C$ なので、
\[
\int_{0}^{\frac{\pi}{4}} \tan x\,dx 
= \bigl[-\ln|\cos x|\bigr]_{0}^{\frac{\pi}{4}}
= -\ln\left|\cos\frac{\pi}{4}\right| + \ln|\cos 0|
= -\ln\left(\frac{\sqrt{2}}{2}\right) + \ln 1
\]
となる。$\ln 1 = 0$、また $\displaystyle \frac{\sqrt{2}}{2} = 2^{-1/2}$ より
\[
-\ln\left(\frac{\sqrt{2}}{2}\right)
= -\ln\left(2^{-1/2}\right)
= -\left(-\frac{1}{2}\ln 2\right)
= \frac{1}{2}\ln 2
\]
となるから、
\[
\int_{0}^{\frac{\pi}{4}} \tan x\,dx = \frac{1}{2}\ln 2
\]
である。

したがって、求める面積 $S$ は
\[
S = 4 \cdot \frac{1}{2}\ln 2 = 2\ln 2
\]
となる。

\section{解答}
$$S = 2\ln 2$$
```


### 留意事項
- 作成する問題は (話題が英語であっても) 数学問題として自然な日本語で記述してください
- 数式や数字は必ずLaTeX形式で記述
- 証明問題は作成しないでください
- それぞれの問題は独立した1つの問題であり、小問は作成しないこと
- 出力は必ず```tex```で囲み、コードブロック以外は出力しないこと

---
それでは、以下の話題を元に問題を1問作成してください：

## 入力
```tex
<<<|TOPIC_TEXT|>>>
```
