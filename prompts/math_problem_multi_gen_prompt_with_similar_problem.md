# Math Problem Creation Task

## Instructions
You are a skilled educator tasked with creating mathematics problems for university entrance examinations.
Please create 6 math problems according to the conditions below.

## Creation Conditions
### Target Level
- Japanese high school students

### Input Format
- Field: Choose one mathematical area within the learning scope of Japanese high school students.
- Level: Create one problem for each of the following six levels:
  - Level 1: 教科書レベル
  - Level 2: センター試験レベル
  - Level 3: 二次試験レベル
  - Level 4: 旧帝大レベル
  - Level 5: 東大レベル
  - Level 6: 数学オリンピックレベル
- Point to be assessed: The mathematical ability or perspective you want to evaluate with the problem you create
- Example problem: A problem that has been asked in the past.

### Problem Requirements
2. **No sub-questions**: Do not divide the problem into sub-questions like (1)(2)(3); make it a single, self-contained problem.
3. **Problem structure**:
   - Problem statement: Describe concretely and clearly.
   - Explanation: Explain in detail the process leading to the answer.
   - Answer: Concisely state only the numbers or expressions of the answer in LaTeX format.

### Output Format
Output in the following format:
```tex
\section{Level 1: 教科書レベル}
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]

\section{Level 2: センター試験レベル}
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]

\section{Level 3: 二次試験レベル}
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]

\section{Level 4: 旧帝大レベル}
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]

\section{Level 5: 東大レベル}o
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]

\section{Level 6: 数学オリンピックレベル}
\subsection{問題}
ここに問題文を記述

\subsection{解説}
ここに解説を記述

\subsection{解答}
\[ここに解答をlatex形式で記述\]
```

## Notes

* Always write formulas and numbers in LaTeX format.
* Make sure the problem statements are clear and unambiguous.
* The output must be enclosed in ```tex``` and nothing should be output outside the code block.
* Each subsequent level’s problem must be more difficult than the previous level’s problem.
* Create problems that are different in type from the given example problem.
 * Instead of only changing the numbers, make problems that ask about related but different aspects.

---

Now, please create 6 problems under the following conditions:

## Conditions

Field: <<<|CATEGORY|>>>

Point to be assessed:
<<<|EVALUATION_POINT|>>>

Example problem (Create problems whose format/complexity is completely different from this problem):
<<<|SIMILAR_PROBLEM|>>>
