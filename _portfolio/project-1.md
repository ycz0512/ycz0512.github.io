---
title: "Optimality Guarantee for AWR"
excerpt: "This work developed a global optimality guarantee for the advantage-weighted regression (AWR) in the tabular setting. <br/><img src='/images/AWR/AWR_paper.png'>"
collection: portfolio
---

**2024.12** / [PDF](https://ycz0512.github.io/assets/AWR_Guarantees.pdf)

Based on the concept of reduction to supervised learning, AWR is an iterative RL algorithm in which the policy is updated using standard regression.<br>
Maximizing the expected improvement of successive policy iterates, one can formulate the following constrained policy search problem:
<img src='/images/AWR/constrained_policy_search_problem.png'>
I motivate the AWR algorithm as an *approximate optimization* for this problem, where the approximation can be decomposed into two steps.

### Approximation I
In the first approximation step, I derive a target policy update rule as an intermediate result 
and show that this intermediate update not only ensures monotonic policy improvements 
but also enjoys a convergence rate of O(1/K) for near-optimal policies.
<img src='/images/AWR/approx_1.png'>
<img src='/images/AWR/target_policy.png'>
<img src='/images/AWR/thm_1.png'>
This sub-optimality upper bound has no dependence on the size of the state space and the distribution mismatch coefficient, 
even though the target policy is updated under a different measure µ.

### Approximation II
I motivate AWR as the projection of the target policy onto the policy class in each iteration
and derive an upper bound on the sub-optimality of the policy output by AWR upon termination, 
which has no dependence on the size of the state and action space.
