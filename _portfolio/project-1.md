---
title: "Optimality Guarantee for AWR"
excerpt: "This work developed a global optimality guarantee for the advantage-weighted regression (AWR) in the tabular setting. <br/><img src='/images/AWR/AWR_paper.png'>"
collection: portfolio
---

**2024.12**  \|  [PDF](https://ycz0512.github.io/assets/AWR_Guarantees.pdf)

Based on incremental policy updates, the AWR algorithm is derived from maximizing the expected improvement of successive policy iterates.<br>
Borrowing ideas from TRPO, one can formulate the following constrained policy search problem:
<img src='/images/AWR/constrained_PS.png'>
I motivate AWR as an *approximate optimization* of this problem, where the approximation can be decomposed into two steps.

### Step 1
In the first approximation step, I develop a target policy update rule as an intermediate result
and show that this intermediate update not only ensures monotonic policy improvements
but also enjoys a convergence rate of O(1/K) for near-optimal policies.
<img src='/images/AWR/approx_1.png'>

<img src='/images/AWR/lemma_1.png'>

<img src='/images/AWR/thm_1.png'>
The sub-optimality upper bound has no dependence on the size of the state space and the distribution mismatch coefficient,
even though the target policy is updated under a different measure \\(\mu\\).

### Step 2
I motivate AWR as the projection of the target policy onto the policy class in each iteration
and derive an upper bound on the sub-optimality of the policy output by AWR upon termination,
which has no dependence on the size of the state and action space.
Under certain conditions, the near optimality can be guaranteed.
<img src='/images/AWR/approx_2.png'>
<img src='/images/AWR/AWR_update.png'>
<img src='/images/AWR/lemma_4.png'>
<img src='/images/AWR/delta_plus.png'>
<img src='/images/AWR/thm_2.png'>
<img src='/images/AWR/conditions.png'>
The first condition is about the function class with only the realizability concern.
The second condition is about the data distribution which requires exploratory initial state distribution.<br>
Note that there is no convergence guarantee for the AWR algorithm since in each iteration the output policy doesn’t guarantee to achieve improvement (lemma 4) due to the incorporation of the approximation II.
