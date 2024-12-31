---
title: "Optimality Guarantee for AWR"
excerpt: "This work developed a global optimality guarantee for the advantage-weighted regression (AWR) in the tabular setting. <br/><img src='/images/AWR/AWR_paper.png'>"
collection: portfolio
---

**2024.12**

Based on the concept of reduction to supervised learning, AWR is an iterative RL algorithm in which the policy is updated using standard regression.<br>
Focusing on the expected improvement of successive policy iterates, one can formulate the following constrained policy search problem:<br>
<img src='/images/AWR/constrained_policy_search_problem.png'>
I motivate the AWR algorithm as an *approximate optimization* for this problem, where the approximation can be decomposed into two steps.
## Approximation I
In the first approximation step, I derive a target policy update rule based on the optimal solution to the constrained policy search problem as an intermediate result and show that this intermediate update not only ensures monotonic policy improvements but also enjoys a convergence rate of O(1/K) for near-optimal policies.<br>
<img src='/images/AWR/approx_1.png'>
which has a closed-form solution:<br>
<img src='/images/AWR/target_policy.png'>

