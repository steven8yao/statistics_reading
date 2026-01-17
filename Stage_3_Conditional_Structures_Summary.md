# Stage 3 Summary Sheet: Conditional Structures

This sheet introduces conditional concepts that bridge Stage 2 (random variables) and Stage 4 (stochastic processes / Markov chains).
The style matches Stage 2 exactly: readable Markdown, inline symbols, no LaTeX math blocks.

---

## 1. Conditional Probability

Conditional probability answers:

How likely is event A, given that event B has occurred?

If P(B) > 0, conditional probability is defined as:

**P(A | B) = P(A ∩ B) / P(B)**

Interpretation:
- “Given B” restricts the sample space from Ω to B.
- Within B, we recompute probabilities.

Connection to independence:
- Events A and B are independent iff **P(A | B) = P(A)** (and equivalently **P(B | A) = P(B)**).

---

## 2. Conditioning on Random Variables (Events of the form {X = x})

Statements like “X = x” are events:
- **{X = x} = {ω ∈ Ω : X(ω) = x}**

Events can be composite:
- **{X ∈ {x₁,x₂,x₃}} = {X = x₁} ∪ {X = x₂} ∪ {X = x₃}**

This matters because Stage 4 conditions on states like “Xₜ = i”.

---

## 3. Conditional Distribution (Discrete Case)

Conditional distribution applies conditional probability to random variables.

Let X and Y be discrete random variables. If P(Y = y) > 0, define:

**P(X = x | Y = y) = P(X = x , Y = y) / P(Y = y)**

Interpretation:
- “Given Y = y” means we restrict to outcomes where Y takes value y.
- Then we get an updated distribution for X.

Independence:
- If X and Y are independent, then **P(X = x | Y = y) = P(X = x)** for all y (so it does not depend on y).

---

## 4. Conditional Expectation (Discrete Case)

Conditional expectation is the average value of X after conditioning on information about Y.

For discrete random variables:

**E[X | Y = y] = Σ x · P(X = x | Y = y)**

Interpretation:
- First update probabilities using the conditional distribution.
- Then compute the expected value using those updated probabilities.

Special case (independence):
- If X and Y are independent, then **E[X | Y = y] = E[X]** (so it does not depend on y).

---

## Quick Self-Check

- I can interpret “given B” as restricting the sample space to B.
- I can compute P(X = x | Y = y) from a joint distribution table.
- I can compute E[X | Y = y] using the conditional distribution.
- I know how independence shows up as “conditioning does not change anything”.
