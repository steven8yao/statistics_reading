# Stage 1 Summary Sheet: Probability Basics

A concise but thorough reference for the probability fundamentals used throughout **Random Variables** and **Stochastic Processes**.

---

## 1. Sample Space

**Definition.** The sample space is the set of all possible outcomes of an experiment, denoted by **Ω**.

**Examples.**
- Fair die: **Ω = {1,2,3,4,5,6}**
- Two coin tosses: **Ω = {HH, HT, TH, TT}**

**Why it matters.** All random variables and stochastic processes are defined on an underlying **Ω**, even if it is not written explicitly.

---

## 2. Event

**Definition.** An event **A** is any subset of **Ω** (A ⊂ Ω). It represents a statement about the outcome.

**Common set operations.**
- **Union:** **A ∪ B** = “A or B occurs”
- **Intersection:** **A ∩ B** = “A and B both occur”
- **Complement:** **Aᶜ** = “A does not occur”

---

## 3. Probability P(·)

**Finite, equally likely case.**  **P(A) = |A| / |Ω|**.

**Basic properties.**
- **0 ≤ P(A) ≤ 1**
- **P(Ω) = 1**
- **P(∅) = 0**

**Example.** For **Ω = {1,…,6}** and **A = {2,4,6}**,  
**P(A) = 3/6 = 1/2**.

---

## 4. Complement Rule

**Rule.**  **P(Aᶜ) = 1 − P(A)**.

**Example.** If **A = {1,3,5}**, then **Aᶜ = {2,4,6}**.

**Tip.** Complements often simplify calculations, e.g. **P(A) = 1 − P(Aᶜ)**.

---

## 5. Disjoint Events

**Definition.** Events **A** and **B** are disjoint (mutually exclusive) if **A ∩ B = ∅**.

**Rule.** If **A ∩ B = ∅**, then **P(A ∪ B) = P(A) + P(B)**.

**Warning.** This rule fails if **A** and **B** overlap; then you must subtract **P(A ∩ B)**.

---

## 6. General Addition Rule

**Always true.**  **P(A ∪ B) = P(A) + P(B) − P(A ∩ B)**.

**Intuition.** **P(A) + P(B)** counts outcomes in **A ∩ B** twice, so we subtract that overlap once.

**Example.** **A = {1,3,5}**, **B = {4,5,6}**. Then  
**P(A) = 1/2**, **P(B) = 1/2**, **P(A ∩ B) = 1/6**, so **P(A ∪ B) = 5/6**.

---

## Quick Self-Check

- I can list **Ω** for a simple experiment and count **|Ω|**.
- I can represent events as subsets and compute **A ∪ B**, **A ∩ B**, and **Aᶜ**.
- For equally likely outcomes, I can compute **P(A) = |A| / |Ω|**.
- I know when **P(A ∪ B) = P(A) + P(B)** applies (only if disjoint).
- I can always use **P(A ∪ B) = P(A) + P(B) − P(A ∩ B)**.
