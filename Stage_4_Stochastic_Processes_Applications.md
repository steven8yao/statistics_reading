# Stage 4 — Discrete-Time Markov Chains (Applications)

This document contains the **Applications** for Stage 4.  
It follows exactly the same structure, tone, and explanation rhythm as the
**Stage 4 Stochastic Processes (Concepts)** document, but with **expanded detail**.

---

## Application 1 — Transition Matrices

### Definition

A **transition matrix** is a matrix that stores all one-step transition probabilities of a Markov chain.

For a finite state space S = {1,2,…,n}, the transition matrix P is defined by:

**Pᵢⱼ = P(Xₜ₊₁ = j | Xₜ = i)**

---

### Interpretation

Each row corresponds to a **fixed current state**.

Row i answers the question:

> If the process is currently in state i at time t, what is the probability distribution of the state at time t+1?

Because the process must move to *some* state next, every row of P must sum to 1.

This organization by rows reflects the **conditional structure** of the Markov property.

---

### Why columns are not used

Columns correspond to fixing the *next* state instead of the current state.

Column sums have no probabilistic meaning and are not constrained to equal 1.

---

### Small example

Suppose the state space is:

S = {0,1}

Assume:
- P(Xₜ₊₁ = 1 | Xₜ = 0) = 0.3
- P(Xₜ₊₁ = 1 | Xₜ = 1) = 0.8

Then the remaining probabilities are determined automatically:

- P(Xₜ₊₁ = 0 | Xₜ = 0) = 0.7
- P(Xₜ₊₁ = 0 | Xₜ = 1) = 0.2

The transition matrix is:

P =
[ 0.7  0.3  
  0.2  0.8 ]

---

## Application 2 — n-step Transition Probabilities

### Definition

The **n-step transition probability** is:

**P(Xₜ₊ₙ = j | Xₜ = i)**

It describes the probability that the process is in state j after n steps, given that it is currently in state i.

---

### Interpretation

For n = 1, this probability is given directly by the transition matrix.

For n ≥ 2, the process must pass through one or more **intermediate states**.

Because these intermediate states are unknown, we must sum over all possible paths connecting i to j.

---

### Two-step case

For two steps:

P(Xₜ₊₂ = j | Xₜ = i)
= Σₖ P(Xₜ₊₂ = j | Xₜ₊₁ = k) P(Xₜ₊₁ = k | Xₜ = i)

The summation index k runs over all states in the state space.

Each term represents one possible intermediate path i → k → j.

---

### General pattern

- One step: no summation
- Two steps: one summation
- n steps: n−1 nested summations

This combinatorial explosion explains why matrix notation is essential.

---

### Matrix interpretation

Matrix multiplication performs exactly these summations automatically.

The matrix power Pⁿ satisfies:

**(Pⁿ)ᵢⱼ = P(Xₜ₊ₙ = j | Xₜ = i)**

This identity holds **only** because of the Markov property.

---

## Application 3 — Long-run Behavior and Stationary Distributions

### Definition

A **stationary distribution** π is a probability distribution over the state space such that:

**πP = π**

---

### Interpretation

If the chain starts with distribution π, then after one step it still has distribution π.

The probability flow into each state balances the flow out.

---

### Stationarity vs convergence

Stationarity is a **static property** of a distribution.

Convergence is a **dynamic property** of the chain.

A stationary distribution may exist even when convergence fails.

---

### Long-run meaning

When convergence occurs, π describes:

- the long-run proportion of time spent in each state
- the equilibrium behavior of the chain

---

## Application 4 — State Classification

### Communication

States i and j **communicate** if each can reach the other with positive probability in some number of steps.

Communication is an equivalence relation and partitions the state space into **communicating classes**.

---

### Recurrent vs Transient states

A **recurrent state** is returned to with probability 1.

A **transient state** has a positive probability of never being revisited.

Transient states do not contribute to long-run behavior.

---

### Absorbing states

A state i is **absorbing** if:

P(Xₜ₊₁ = i | Xₜ = i) = 1

Once entered, the process remains in that state forever.

---

### Why classification matters

Long-run behavior depends only on **recurrent communicating classes**.

Chains with a single recurrent class exhibit stable long-run structure.

---

## Key Takeaways

- Transition matrices encode local one-step dynamics
- Matrix powers encode multi-step evolution
- Stationary distributions describe equilibrium behavior
- Long-run behavior is governed by recurrent state structure
