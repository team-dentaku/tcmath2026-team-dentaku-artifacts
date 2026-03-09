# Detecting Whether Computation Occurs in Python Comments
You are an information processing expert responsible for evaluating **comment text** extracted from Python code.
Your task is to determine whether the given comments contain evidence that **some computation (an operation or simplification) was actually carried out**.

In this task, **“computation occurs”** means there is a trace that an operation/simplification has been **applied**, not merely mentioned.

Specifically, output `computed` **only if** the comments include an explicit **input → output** relationship such as:
- **A written result of a calculation** (e.g., `3*4=12`, “the total is 42”, `log(1)=0`)
- **Before/after of an algebraic transformation or simplification** (e.g., `2/4 -> 1/2`, “expand to (n^2+n)/2”, `a(b+c)=ab+ac`)
- **A substitution/rearrangement where the expression changes and the outcome is shown** (e.g., “substitute x=2 and get 3x+1=7”)

Important:
- **Merely writing a formula** (a definition, reference note, or stating an identity without indicating it was applied) is `N/A`.
- **Stating intent only** (e.g., “we compute…”, “we will find…”) is `N/A` if no result or post-transformation expression appears in the comments.
- **Describing an operation without showing the result** (e.g., “divide numerator and denominator by 2 to reduce”) is also `N/A` unless the reduced form / before-after mapping is present.

In other words, output `computed` only when it is clear from the comments that **something was computed and the computed outcome is shown**.

The following do **not** count as computation:
- Only explaining purpose/background
- Explaining variable names, generic notes, TODOs, warnings, spec memos
- Listing values without any shown result or transformation


## Task Definition

### Input / Output Specification
- **Input**: All comments extracted from Python code (may contain multiple lines)
- **Output**: Output **only one word**:
  - `computed` if the comments show that some computation was actually applied (with an explicit outcome)
  - `N/A` otherwise

Do not output anything other than `computed` or `N/A`.


### Examples (Computation occurs)

Input:
```text
# Reduce 2/4 to 1/2
```

Output:
```txt
computed
```

Input:
```text
# a(b+c) = ab+ac
```

Output:
```txt
computed
```

Input:
```text
# Substitute x=2: 3x+1 = 7
```

Output:
```txt
computed
```

Input:
```text
# Divide numerator and denominator by 2: 2/4 -> 1/2
```

Output:
```txt
computed
```


### Examples (No computation)

Input:
```text
# Divide numerator and denominator by 2 to simplify the expression
```

Output:
```txt
N/A
```

Input:
```text
# Here we compute n*(n+1)/2 to get the sum from 1 to n
```

Output:
```txt
N/A
```

Input:
```text
# Bernoulli distribution B(p): X∈{0,1}, P(X=1)=p, P(X=0)=1-p
```

Output:
```txt
N/A
```

Input:
```text
# Area is πr^2
```

Output:
```txt
N/A
```

---

## Evaluation

Input:

```text
<<<|COMMENTS|>>>
```
