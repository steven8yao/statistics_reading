# Stage 5 Summary Sheet: Continuous-Time Markov Chains (CTMC)

This stage extends Stage 4 (discrete-time Markov chains) to **continuous time**.
The key shift is: replace “next step” with **rates** and **random waiting times**.

---

## 1. Continuous-Time Stochastic Process (CTSP)

A **continuous-time stochastic process（连续时间随机过程）** is a collection of random variables indexed by a continuous time set.

**{Xₜ : t ∈ T}**, typically **T = [0,∞)**

Each Xₜ is a random variable, but time can vary continuously, so there is no “next step” in the discrete sense.

### Discrete vs continuous time

- Discrete time: t = 0,1,2,…  (step-by-step evolution)
- Continuous time: t ∈ [0,∞)  (changes can occur at any instant)

A time series（时间序列） is usually one observed sample path（样本路径） sampled at discrete times, even if the model time is continuous.

---

## 2. Holding Time (Waiting Time)

In a continuous-time Markov chain（连续时间马尔可夫链）, the process stays in a state i for a random **holding time（停留时间）** Tᵢ, then jumps to a new state.

The Markov idea in continuous time is: the future does not depend on how long the process has already stayed in the current state.

### Exponential holding time

For a CTMC, the holding time in state i is exponential with rate λᵢ:

**P(Tᵢ > t) = e^(−λᵢ t)**  for t ≥ 0

Interpretation:
- P(Tᵢ > t) means “still staying in state i at time t”
- larger λᵢ means faster leaving, so the probability of still staying decays faster

### Mean holding time

**E[Tᵢ] = 1/λᵢ**

This is an average: individual sample paths may stay shorter or longer than 1/λᵢ.

---

## 3. Jump Rates and the Generator Matrix

In discrete time, we used one-step probabilities **P(Xₜ₊₁ = j | Xₜ = i)**.

In continuous time, we use **jump rates（跳跃率）** qᵢⱼ for i ≠ j.

### Jump rates

**qᵢⱼ ≥ 0**  (for i ≠ j)

Meaning:
- qᵢⱼ measures how fast the process jumps from i to j (a rate, not a probability)

### Total leaving rate

The total rate of leaving state i is:

**λᵢ = Σⱼ≠ᵢ qᵢⱼ**

Intuition (“race of clocks”):
- each possible jump i → j has its own exponential “clock” with rate qᵢⱼ
- the first clock to ring determines the jump
- the minimum waiting time is exponential with rate equal to the sum of rates

### Conditional jump probabilities (given that you leave)

If the process leaves i, the probability it jumps to j is:

**P(next state = j | leaving i) = qᵢⱼ / λᵢ**

So CTMC dynamics decompose into:
1) wait Exp(λᵢ) time in i, then
2) jump to j with probability qᵢⱼ/λᵢ

### Generator matrix Q (生成元)

Collect the rates into a matrix Q:

- For i ≠ j: **Qᵢⱼ = qᵢⱼ**
- For i = i: **Qᵢᵢ = −λᵢ**

Key property:
- each row of Q sums to 0

Small example (two states 0 and 1):
- q₀₁ = 2, q₁₀ = 1

Then:

Q =
[ −2   2
   1  −1 ]

---

## 4. Transition Probabilities Over Continuous Time

In continuous time, we define a time-dependent transition matrix P(t):

**Pᵢⱼ(t) = P(Xₜ = j | X₀ = i)**

This replaces the discrete-time object Pⁿ.

### Basic requirements

- Initial condition: **P(0) = I**
  - if no time has passed, the state cannot have changed

- Chapman–Kolmogorov equation（查普曼–科尔莫戈罗夫方程）:
  - **P(s+t) = P(s)P(t)** for s,t ≥ 0

### Generator connection (idea)

Q describes the instantaneous change of P(t) at time 0:

**Q ≈ (P(Δt) − I) / Δt**  for small Δt

In full CTMC theory, the relationship is:

**P(t) = e^(tQ)**

(You do not need to compute matrix exponentials yet; the key idea is that Q determines P(t) for all t ≥ 0.)

---

## 5. Stationary Distribution in Continuous Time

A distribution π over states is **stationary（平稳分布）** if starting with π keeps the distribution unchanged over time.

### Stationarity via P(t)

Stationary means:

**πP(t) = π**  for all t ≥ 0

Interpretation:
- the *distribution* is stable
- sample paths still jump (dynamic equilibrium), but the distribution does not change

### Stationarity via Q

In continuous time, stationarity is equivalently characterized by:

**πQ = 0**

Interpretation (probability flow / 概率流):
- “inflow equals outflow” for each state
- net change of the distribution is zero

---

## Quick Self-Check

1. Explain in words why continuous time has no meaningful “next step.”  
2. If λᵢ increases, what happens to E[Tᵢ] and why?  
3. Why must Qᵢᵢ be negative?  
4. What does P(Tᵢ > t) represent in words?  
5. What is the difference between “stationary distribution” and “state being static”?  
6. Why does πQ = 0 express “inflow equals outflow”?
