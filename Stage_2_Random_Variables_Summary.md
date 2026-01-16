# Stage 2 Summary Sheet: Random Variables & Distributions

A concise but thorough reference for the core objects used in **stochastic processes**: random variables, distributions (PMF/PDF/CDF), expectation/variance, and dependence (covariance/independence).

---

## 1. Random Variable (RV)

**Definition.** A random variable is a function \(X: \Omega \to \mathbb{R}\). The randomness comes from the outcome \(\omega\in\Omega\), not from the function rule.

**Support (possible values).** The **support** is the set of values that \(X\) can take with positive probability (for discrete RVs, it’s a set like \(\{0,1,2\}\), not an interval like \((0,1)\)).

**Example.** If \(\Omega=\{1,2,3,4,5,6\}\) (fair die), one RV is \(X(\omega)=\omega\). Another is \(Y(\omega)=1\{\omega\text{ is odd}\}\in\{0,1\}\).

---

## 2. “Countable” and Discrete Random Variables

**Definition (countably infinite).** A set is **countably infinite** if its elements can be listed in a sequence \(x_1,x_2,x_3,\dots\). The list does *not* need a simple pattern; it only needs a way to label each element with a natural number.

**Definition (discrete RV).** \(X\) is **discrete** if its support is finite or countably infinite.

**Note.** If the support is not countable (e.g., an interval), \(X\) is not discrete (typically continuous or mixed).

---

## 3. PMF (Probability Mass Function)

**Definition.** For a discrete RV \(X\), the **PMF** is
\[
p_X(x)=P(X=x).
\]

**Rules.**
- \(p_X(x)\ge 0\)
- \(\sum_x p_X(x)=1\) (sum over all values in the support)
- If \(x\) is not in the support, then \(p_X(x)=0\)

**Example.** If \(P(Y=0)=0.2\), \(P(Y=1)=0.5\), \(P(Y=2)=0.3\), then \(p_Y(0)=0.2\), \(p_Y(1)=0.5\), \(p_Y(2)=0.3\).

---

## 4. CDF (Cumulative Distribution Function)

**Definition.** For any RV (discrete or continuous),
\[
F_X(x)=P(X\le x).
\]

**Properties.**
- \(0\le F_X(x)\le 1\)
- \(F_X(x)\) is non-decreasing in \(x\)
- \(\lim_{x\to -\infty}F_X(x)=0\), \(\lim_{x\to\infty}F_X(x)=1\)

**Discrete link.**
\[
F_X(x)=\sum_{t\le x} p_X(t),\qquad
p_X(x)=F_X(x)-F_X(x^-).
\]
Here \(F_X(x^-)\) is the left-limit at \(x\) (the CDF’s jump size at \(x\) equals \(p_X(x)\)).

---

## 5. Continuous RVs and PDF (Probability Density Function)

**Key fact.** If \(X\) is continuous, then \(P(X=x)=0\) for every real \(x\). Probabilities come from **intervals**, not points.

**Definition (PDF).** A **PDF** \(f_X\) satisfies
\[
F_X(x)=\int_{-\infty}^{x} f_X(t)\,dt,
\qquad
P(a\le X\le b)=\int_a^b f_X(t)\,dt.
\]

**Rules.**
- \(f_X(x)\ge 0\)
- \(\int_{-\infty}^{\infty} f_X(x)\,dx=1\)
- \(f_X(x)\) is a *density*, not a probability.

**Derivative link (when differentiable).** \(f_X(x)=\frac{d}{dx}F_X(x)\).

---

## 6. Expectation (Mean)

**Definition (discrete).**
\[
\mathbb{E}[X]=\sum_x x\,p_X(x).
\]

**Definition (continuous, when integrable).**
\[
\mathbb{E}[X]=\int_{-\infty}^{\infty} x\,f_X(x)\,dx.
\]

**Linearity (always).** For constants \(a,b\),
\[
\mathbb{E}[aX+bY]=a\mathbb{E}[X]+b\mathbb{E}[Y].
\]
No independence is required.

**Example.** If \(Y\in\{0,1,2\}\) with probabilities \(0.2,0.5,0.3\),
\(\mathbb{E}[Y]=0\cdot0.2+1\cdot0.5+2\cdot0.3=1.1\).

---

## 7. Expectation of a Function (LOTUS)

**Definition (LOTUS).** For a function \(g\),

- Discrete:
  \[
  \mathbb{E}[g(X)] = \sum_x g(x)p_X(x).
  \]
- Continuous:
  \[
  \mathbb{E}[g(X)] = \int g(x)f_X(x)\,dx.
  \]

**Common warning.** In general \(\mathbb{E}[g(X)]\ne g(\mathbb{E}[X])\) unless \(g\) is linear.

**Indicator function.** \(1\{A\}\) (also written \(\mathbf{1}_{\{A\}}\) or \(\chi_A\)) equals 1 if event \(A\) occurs and 0 otherwise. Key identity:
\[
\mathbb{E}[1\{A\}] = P(A).
\]

---

## 8. Variance and Standard Deviation

**Definition.**
\[
\operatorname{Var}(X)=\mathbb{E}[(X-\mathbb{E}[X])^2].
\]

**Computational formula.**
\[
\operatorname{Var}(X)=\mathbb{E}[X^2]-(\mathbb{E}[X])^2.
\]

**Standard deviation.** \(\operatorname{SD}(X)=\sqrt{\operatorname{Var}(X)}\).

**Rules.**
- \(\operatorname{Var}(X+c)=\operatorname{Var}(X)\)
- \(\operatorname{Var}(aX)=a^2\operatorname{Var}(X)\)

---

## 9. Covariance and Correlation

**Covariance definition.**
\[
\operatorname{Cov}(X,Y)=\mathbb{E}[(X-\mathbb{E}[X])(Y-\mathbb{E}[Y])].
\]

**Equivalent formula (derived by expanding).**
\[
\operatorname{Cov}(X,Y)=\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y].
\]

**Variance as covariance.** \(\operatorname{Var}(X)=\operatorname{Cov}(X,X)\).

**Correlation.**
\[
\rho_{X,Y}=\frac{\operatorname{Cov}(X,Y)}{\operatorname{SD}(X)\operatorname{SD}(Y)},\quad -1\le \rho_{X,Y}\le 1.
\]

---

## 10. Independence (Concept 8)

**Events.** Events \(A,B\) are independent if \(P(A\cap B)=P(A)P(B)\).

**Discrete RVs.** \(X\) and \(Y\) are independent if
\[
P(X=x, Y=y)=P(X=x)P(Y=y)\quad\text{for all }x,y.
\]

**General CDF form.** \(X,Y\) are independent if
\[
P(X\le x, Y\le y)=P(X\le x)P(Y\le y)\quad\text{for all }x,y.
\]

**Key facts.**
- Independence \(\Rightarrow\ \operatorname{Cov}(X,Y)=0\).
- \(\operatorname{Cov}(X,Y)=0\) does **not** imply independence in general.

---

## Quick self-check

- I can define an RV as a function \(X: \Omega\to\mathbb{R}\).
- I can compute and interpret PMF, CDF, and (when appropriate) PDF.
- I can compute \(\mathbb{E}[X]\), \(\mathbb{E}[g(X)]\), \(\operatorname{Var}(X)\), \(\operatorname{Cov}(X,Y)\).
- I can distinguish: PDF vs PMF, covariance vs independence.
