# Stage 2 Summary Sheet: Random Variables & Distributions

This sheet continues Stage 1 and introduces **random variables**, their **distributions**, and basic notions of **dependence**.
The style matches Stage 1 exactly: readable Markdown, inline symbols, no LaTeX math blocks.

---

## 1. Random Variable (RV)

A **random variable** is a function from the sample space to the real numbers.

**X : Ω → ℝ**

The word *random* refers to the randomness of the outcome ω ∈ Ω, not the function rule.

### Support
The **support** of X is the set of values that X can take with positive probability.

Example:
- If X takes values 0 or 1, then the support is **{0,1}**, not (0,1).

---

## 2. Countable Sets and Discrete Random Variables

A set is **countable** if its elements can be listed as a sequence:
x₁, x₂, x₃, …

The list does not need a simple pattern — it only needs a way to label each element with a natural number.

A random variable is **discrete** if its support is:
- finite, or
- countably infinite

---

## 3. PMF (Probability Mass Function)

For a discrete random variable X, the **PMF** is defined by:

**pₓ(x) = P(X = x)**

Properties:
- pₓ(x) ≥ 0
- Σ pₓ(x) = 1  (sum over all values in the support)
- If x is not in the support, then pₓ(x) = 0

Example:
- P(Y = 0) = 0.2
- P(Y = 1) = 0.5
- P(Y = 2) = 0.3

---

## 4. CDF (Cumulative Distribution Function)

For any random variable (discrete or continuous), the **CDF** is:

**Fₓ(x) = P(X ≤ x)**

Properties:
- 0 ≤ Fₓ(x) ≤ 1
- Fₓ(x) is non-decreasing
- limₓ→−∞ Fₓ(x) = 0
- limₓ→∞ Fₓ(x) = 1

Discrete case:
- Fₓ(x) = Σ pₓ(t) for all t ≤ x
- pₓ(x) = Fₓ(x) − Fₓ(x⁻)

The PMF corresponds to the jump sizes of the CDF.

---

## 5. Continuous Random Variables and PDF

If X is **continuous**, then:

**P(X = x) = 0** for every real x.

Probabilities come from intervals, not points.

The **PDF (probability density function)** fₓ(x) satisfies:
- Fₓ(x) = ∫ from −∞ to x of fₓ(t) dt
- P(a ≤ X ≤ b) = ∫ from a to b of fₓ(t) dt

Properties:
- fₓ(x) ≥ 0
- ∫ from −∞ to ∞ of fₓ(x) dx = 1

The PDF is a **density**, not a probability.

---

## 6. Expectation (Mean)

Expectation is a weighted average.

Discrete case:
- **E[X] = Σ x · pₓ(x)**

Continuous case:
- **E[X] = ∫ x · fₓ(x) dx**

### Linearity of Expectation

For constants a, b:

**E[aX + bY] = aE[X] + bE[Y]**

No independence is required.

Example:
- If Y ∈ {0,1,2} with probabilities 0.2, 0.5, 0.3
- Then E[Y] = 1.1

---

## 7. Expectation of a Function (LOTUS)

For a function g:

Discrete:
- **E[g(X)] = Σ g(x) · pₓ(x)**

Continuous:
- **E[g(X)] = ∫ g(x) · fₓ(x) dx**

In general:
- **E[g(X)] ≠ g(E[X])**, unless g is linear

### Indicator Function

The indicator of an event A is written as **1{A}**.

- 1{A} = 1 if A occurs
- 1{A} = 0 otherwise

Key identity:
- **E[1{A}] = P(A)**

---

## 8. Variance and Standard Deviation

Variance measures spread around the mean.

Definition:
- **Var(X) = E[(X − E[X])²]**

Equivalent formula:
- **Var(X) = E[X²] − (E[X])²**

Standard deviation:
- **SD(X) = √Var(X)**

Rules:
- Var(X + c) = Var(X)
- Var(aX) = a² Var(X)

---

## 9. Covariance and Correlation

Covariance measures linear dependence between X and Y.

Definition:
- **Cov(X,Y) = E[(X − E[X])(Y − E[Y])]**

Equivalent formula:
- **Cov(X,Y) = E[XY] − E[X]E[Y]**

Variance is a special case:
- **Var(X) = Cov(X,X)**

Correlation:
- **ρ = Cov(X,Y) / (SD(X) · SD(Y))**
- −1 ≤ ρ ≤ 1

---

## 10. Independence (Concept 8)

Events A and B are **independent** if:
- **P(A ∩ B) = P(A)P(B)**

Discrete random variables X and Y are independent if:
- **P(X = x, Y = y) = P(X = x)P(Y = y)** for all x, y

Equivalent CDF form:
- **P(X ≤ x, Y ≤ y) = P(X ≤ x)P(Y ≤ y)**

Key facts:
- Independence ⇒ Cov(X,Y) = 0
- Cov(X,Y) = 0 does not imply independence

---

## Quick Self-Check

- I can define a random variable as a function X : Ω → ℝ.
- I can compute PMF, CDF, and PDF.
- I can compute E[X], Var(X), and Cov(X,Y).
- I understand the difference between covariance and independence.
