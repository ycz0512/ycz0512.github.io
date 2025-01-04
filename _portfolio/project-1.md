---
title: "Optimality Guarantee for AWR"
excerpt: "This work developed a global optimality guarantee for the advantage-weighted regression (AWR) in the tabular setting. <br/><img src='/images/AWR/AWR_paper.png'>"
collection: portfolio
---

**2024.12**  \|  [PDF](https://ycz0512.github.io/assets/AWR_Guarantees.pdf)

Based on incremental policy updates, the AWR algorithm is derived from maximizing the expected improvement of successive policy iterates.
Borrowing ideas from TRPO, one can formulate the following constrained policy search problem:
<img src='/images/AWR/constrained_PS.png'>
I motivate AWR as an *approximate optimization* of this problem, where the approximation can be decomposed into two steps.

### Step 1
In the first approximation step, I develop a target policy update rule as an intermediate result
and show that this target policy update not only ensures monotonic policy improvement
but also enjoys a convergence rate of O(1/K) for near-optimal policies.
<img src='/images/AWR/approx_1.png'>

<img src='/images/AWR/lemma_1.png'>

<img src='/images/AWR/thm_1.png'>
The sub-optimality upper bound has no dependence on the size of the state space and the distribution mismatch coefficient,
even though the target policy is updated under a different measure \\(\mu\\).

### Step 2
In the second step, I develop a variant algorithm of AWR as the projection of the target policy onto the policy class.
The variant algorithm guarantees near optimality while the original AWR doesn't.
Also, I derive an upper bound on the sub-optimality of the policy output by the (variant) AWR algorithm upon termination.
<img src='/images/AWR/approx_2.png'>
<img src='/images/AWR/AWR_update.png'>

<img src='/images/AWR/lemma_4.png'>
<img src='/images/AWR/delta_plus.png'>

<img src='/images/AWR/termination_criterion.png'>

<img src='/images/AWR/thm_2.png'>
<img src='/images/AWR/conditions.png'>
The sub-optimality upper bound has no dependence on the size of the state and action space.
Note that there is no convergence guarantee for the (variant) AWR algorithm since in each iteration 
the output policy doesn’t guarantee to achieve improvement (lemma 4) due to the incorporation of the approximation II.
