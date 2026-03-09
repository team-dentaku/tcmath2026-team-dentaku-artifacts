# Math Problem Extraction Task

## Task Description
From the following text file, extract **all** pairs of Japanese mathematics problems and their answers in **JSON format**. If an explanation/solution for a problem is also provided, extract that as well.
Also, annotate the topic/unit of each problem (e.g., differentiation / integration / trigonometric functions).

## Output Format

```json
{
	"extracted_math_qa_lists": [
		{
			"problem_statement": str,	     // 問題文
			"explanation": null | str,	 // 解法（ある場合）
			"answer": str,	       // 最終回答
			"unit": str	          // 単元
		},
		{
			"problem_statement": str,	     // 問題文
			"explanation": null | str,	 // 解法（ある場合）
			"answer": str,	       // 最終回答
			"unit": str	          // 単元
		},
	]
}
````

## Output Example

```json
{
	"extracted_math_qa_lists": [
		{
			"question": "次の式を簡単にしなさい。$\\frac{6x+2}{3}\\div\\frac{4}{9}$",
			"explanation": "$\\frac{6x+2}{3}\\div\\frac{4}{9}=\\frac{6x+2}{3}\\times\\frac{9}{4}=\\frac{(6x+2)\\,9}{12}=\\frac{3}{4}\\,(6x+2)=\\frac{18x+6}{4}=\\frac{9x+3}{2}$",
			"answer": "$$\\frac{9x+3}{2}$$",
			"unit": "文字と式"
		},
		{
			"question": "数列$S_n=\\sum_{k=1}^{n}\\frac{k}{3^k}$について、$\\lim_{n\\to\\infty}S_n$の値を求めなさい。",
			"explanation": "無限級数$S=\\sum_{k=1}^{\\infty}\\frac{k}{3^k}$を求める。\\n$|r|<1$のとき、$\\sum_{k=1}^{\\infty}kr^k=\\frac{r}{(1-r)^2}$が成り立つ。\\n$r=\\frac{1}{3}$を代入すると、$S=\\frac{\\frac{1}{3}}{(1-\\frac{1}{3})^2}=\\frac{\\frac{1}{3}}{(\\frac{2}{3})^2}=\\frac{\\frac{1}{3}}{\\frac{4}{9}}=\\frac{1}{3}\\times\\frac{9}{4}=\\frac{3}{4}$",
			"answer": "$$\\frac{3}{4}$$",
			"unit": "数列と極限"
		}
	]
}
```

## Notes

* All mathematical expressions in the output must be written in LaTeX format and must always be enclosed in `$...`.
* The `answer` field must always contain **only** a mathematical expression enclosed in a LaTeX math environment such as `$...$`. Units (e.g., ℃) and other non-numeric / non-mathematical text are unnecessary.
* If the answer cannot be expressed purely as a mathematical expression (e.g., proof problems), that problem should **not** be extracted.
* Extract **all** mathematics problems that appear in the text.
* In the `answer` field, write only the numerical value or formula of the answer.
* If there is no solution/explanation, set the `reasoning` field to `null`.

## Text File

```txt
<<<|wiki_text|>>>
```
