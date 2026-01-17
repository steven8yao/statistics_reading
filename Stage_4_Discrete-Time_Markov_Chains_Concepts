# # Stage 4 Summary Sheet: Discrete-Time Markov Chains (Concepts)

This stage introduces **stochastic processes** and the conceptual foundation of discrete-time Markov chains.
The writing style matches Stage 2: short definitions + interpretation + small examples.

---

## 1. Stochastic Process

A **stochastic process** is a collection of random variables indexed by time.

**{Xₜ : t ∈ T}**

Each Xₜ is a random variable, and the whole collection describes randomness evolving over time.

### What is “random” here?
“Random” comes from ω ∈ Ω. The mapping ω ↦ Xₜ(ω) is random because ω is random.
For a fixed time t, Xₜ is just a random variable (Stage 2 object).

### Snapshot vs whole process
- Xₜ: one random variable at time t (a snapshot).
- {Xₜ : t ∈ T}: the entire process across time (a movie).

---

## 2. Index Set T

The **index set** T specifies *when* the process is defined (which time points exist).

Common cases:
- Discrete time: **T = {0,1,2,…}**
- Continuous time: **T ⊂ ℝ** (often T = [0,∞) or T = ℝ)

Example:
- Daily measurements: T = {0,1,2,…}
- Continuous monitoring: T = [0,∞)

---

## 3. Sample Paths

Fix an outcome ω ∈ Ω. The function

**t ↦ Xₜ(ω)**

is called a **sample path** (trajectory).

Key point:
- The process {Xₜ} is random (because ω is random).
- A sample path is deterministic once ω is fixed.

Example (discrete time):
- If T = {0,1,2} and one ω gives X₀(ω)=0, X₁(ω)=1, X₂(ω)=1, then the sample path is 0 → 1 → 1.

---

## 4. State Space S

The **state space** S is the set of all possible values the process can take.

For all t and ω:
**Xₜ(ω) ∈ S**

Interpretation:
- T answers *when*.
- S answers *where*.

Examples:
- Simple random walk: S = ℤ
- Coin-state process: S = {0,1}
- Real-valued process: S = ℝ

---

## 5. Transition Probabilities

For a discrete-time process, **transition probabilities** describe one-step evolution:

**P(Xₜ₊₁ = j | Xₜ = i)**

Interpretation:
- “Given the current state is i, what is the chance the next state is j?”
- This is a conditional probability / conditional distribution idea from Stage 3.

Example (two states S={0,1}):
- If P(Xₜ₊₁=1 | Xₜ=0)=0.3 and P(Xₜ₊₁=1 | Xₜ=1)=0.8, then the process tends to stay at 1 more than it tends to move 0→1.

---

## 6. Markov Property

A process has the **Markov property** if the future depends only on the present, not the full past.

Formally, for all t and states i,j:

**P(Xₜ₊₁ = j | Xₜ = i, Xₜ₋₁,…,X₀) = P(Xₜ₊₁ = j | Xₜ = i)**

Interpretation:
- The current state Xₜ is a sufficient summary of the past for predicting Xₜ₊₁.
- This is a “memoryless” property with respect to the state Xₜ (not necessarily memoryless in time intervals).

---

## Key Takeaways

- A stochastic process is a time-indexed family of random variables.
- Xₜ is a snapshot; {Xₜ} is the full object.
- Sample paths are deterministic realizations after fixing ω.
- Transition probabilities describe one-step movement.
- The Markov property says: given Xₜ, earlier history provides no extra predictive power.
