# Classification task for Japanese math problems by field

## Task
Read the given problem written in Japanese and determine which type (field category) it mainly belongs to. Choose **exactly one** label from the classification labels defined below.

Note: The input may sometimes be a problem from a subject other than mathematics (for example, physics).

## Classification labels (types)

<<<|LIST_OF_FIELDS|>>>



## Output format
Your output must consist of **exactly one line**, and must strictly follow this format:
```txt
<ONE_LABEL_FROM_TAXONOMY>
```

* For `<ONE_LABEL_FROM_TAXONOMY>`, write **exactly one** of the labels from the taxonomy above, verbatim.
* Output only the label. Do **not** output any explanations, reasoning, or additional text.

## Input/output example

Input:

```tex
$S_n$は次の式で与えられる。$S_n = \frac{1}{3^1} + \frac{2}{3^2} + \frac{3}{3^3} + \frac{4}{3^4} + \cdots + \frac{n}{3^n} = \sum_{k=1}^{n}\frac{k}{3^k}.$ このとき$\lim_{n \to \infty} S_n$の値を求めよ。
```

Output:

```txt
極限
```

---

## Problem statement to classify (Input)
Now, please classify the fields of the following problems.
**You do not need to solve the problems.**

```txt
<<<|PROBLEM_STATEMENT|>>>
```
