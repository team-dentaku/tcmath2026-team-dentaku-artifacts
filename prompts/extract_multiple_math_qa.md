# 数学問題作成

## タスク内容
あなたは中学/高校数学の教師です。
数学に関連した話題のテキストが入力として与えられます。
その文章に含まれる数学の問題とそれに対する解答を**全て**抽出してください。
答えが書かれていないものについては，新たに解答を導出してください。



## 入力出力形式

入力: 数学に関連した話題のテキストが与えられます。

出力: 以下の形式で出力してください
```tex
\section{問題1}
ここに問題文を記述

\section{解説}
ここに解説を記述

\section{解答}
$$ここに解答をlatex形式で記述$$


\section{問題2}
ここに問題文を記述

\section{解説}
ここに解説を記述

\section{解答}
$$ここに解答をシンプルなlatex形式で記述$$

...

\section{問題N}
ここに問題文を記述

\section{解説}
ここに解説を記述

\section{解答}
$$ここに解答をシンプルなlatex形式で記述$$
```

出力はtexのコードブロックのみで、それ以外の文章は出力しないでください。
また、入力テキストの中に問題が含まれていない場合は

```tex
```

だけを出力してください。


### 入出力例1
入力:
```txt
複素数計算の意味（2）

**注** 複素数とベクトルは全く同じというわけではありません。ベクトルは「向き」と「大きさ」をもつモノでしたが、複素数は単なる「点」です。複素数の実数倍、和や差がベクトルのよう
にはなるというだけのことです。

つまり、点Aに複素数α、点Bに複素数βを対応させると、

\[ \alpha + \beta \leftrightarrow \overrightarrow{OA} + \overrightarrow{OB} \]

\[ \alpha - \beta \leftrightarrow \overrightarrow{OA} - \overrightarrow{OB} = \overrightarrow{BA} \]

みなすことができるのです。このイメージはとても大切です。

**4 積と商**

複素数の和や差は、複素数を「ベクトル」と考えるとイメージしやすかったですが、積や商では
複素数を「変換」と考えることが基本です。ここでは、複素数を全て「極形式」で考えます。

まず、純粋な計算問題をしよう。\( z_1 = r_1(\cos \theta_1 + i \sin \theta_1) \), \( z_2 = r_2(\cos \theta_2 + i \sin \theta_2) \) のとき、積 \( \alpha \beta \) と商 \( \frac{\alpha}{\beta} \) を計算しよう（メンドウですが必ず自力でやってください。加法定理を使うだけです）。

\[ z_1 z_2 = r_1 r_2 (\cos \theta_1 + i \sin \theta_1)(\cos \theta_2 + i \sin \theta_2) \]

\[ = r_1 r_2 \{\cos \theta_1 \cos \theta_2 - \sin \theta_1 \sin \theta_2 + i (\sin \theta_1 \cos \theta_2 + \cos \theta_1 \sin \theta_2)\} \]

\[ = r_1 r_2 \{\cos (\theta_1 + \theta_2) + i \sin (\theta_1 + \theta_2)\} \]
```


出力:
```tex
\section{問題1}
複素数
\[
z_1=r_1(\cos\theta_1+i\sin\theta_1),\quad z_2=r_2(\cos\theta_2+i\sin\theta_2)
\]
が与えられている。ただし \(r_1>0,\,r_2>0\) とする。積 \(z_1z_2\) を極形式で表せ。

\section{解説}
積を展開し，実部と虚部をまとめる。加法定理
\[
\cos(\theta_1+\theta_2)=\cos\theta_1\cos\theta_2-\sin\theta_1\sin\theta_2,\quad
\sin(\theta_1+\theta_2)=\sin\theta_1\cos\theta_2+\cos\theta_1\sin\theta_2
\]
を用いると，極形式に戻せる。

\section{解答}
$$r_1r_2\bigl(\cos(\theta_1+\theta_2)+i\sin(\theta_1+\theta_2)\bigr)$$

\section{問題2}
複素数
\[
z_1=r_1(\cos\theta_1+i\sin\theta_1),\quad z_2=r_2(\cos\theta_2+i\sin\theta_2)
\]
が与えられている。ただし \(r_1>0,\,r_2>0\) とする。商 \(\dfrac{z_1}{z_2}\) を極形式で表せ。

\section{解説}
極形式では
\[
\frac{r_1(\cos\theta_1+i\sin\theta_1)}{r_2(\cos\theta_2+i\sin\theta_2)}
=\frac{r_1}{r_2}\cdot\frac{\cos\theta_1+i\sin\theta_1}{\cos\theta_2+i\sin\theta_2}
\]
であり，\(\cos\theta_2+i\sin\theta_2\) の逆数は
\[
\frac{1}{\cos\theta_2+i\sin\theta_2}=\cos\theta_2-i\sin\theta_2
\]
（なぜなら \((\cos\theta_2+i\sin\theta_2)(\cos\theta_2-i\sin\theta_2)=\cos^2\theta_2+\sin^2\theta_2=1\)）である。
よって
\[
\frac{z_1}{z_2}=\frac{r_1}{r_2}(\cos\theta_1+i\sin\theta_1)(\cos\theta_2-i\sin\theta_2)
\]
を展開し，差の加法定理
\[
\cos(\theta_1-\theta_2)=\cos\theta_1\cos\theta_2+\sin\theta_1\sin\theta_2,\quad
\sin(\theta_1-\theta_2)=\sin\theta_1\cos\theta_2-\cos\theta_1\sin\theta_2
\]
を用いてまとめる。

\section{解答}
$$\frac{z_1}{z_2}=\dfrac{r_1}{r_2}\bigl(\cos(\theta_1-\theta_2)+i\sin(\theta_1-\theta_2)\bigr)$$
```




### 留意事項
- 数学問題として自然な日本語で記述してください
- 数式や数字は必ずLaTeX形式で記述
- 証明問題は含めないでください
- それぞれの問題は独立した1つの問題であり、小問は作成しないこと
- 入力テキストに記載された問題が、小問に分割されていた場合はそれぞれ個別に独立した問題として抽出すること
- 出力は必ず```tex```で囲み、コードブロック以外は出力しないこと

---
それでは、以下のテキストから数学の問題を**全て**抽出してください：

## 入力
```tex
<<<|TEXT|>>>
```
