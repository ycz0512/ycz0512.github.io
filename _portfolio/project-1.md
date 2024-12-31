---
title: "Optimality Guarantee for AWR"
excerpt: "This work developed a global optimality guarantee for the advantage-weighted regression (AWR) in the tabular setting. <br/><img src='/images/AWR_paper.png'>"
collection: portfolio
---


Based on the concept of reduction to supervised learning, AWR is an iterative RL algorithm in which the policy is updated using standard regression.

Focusing on the expected performance improvement of successive policy iterates, one can formulate the following constrained policy search problem:  
<img src='/images/constrained_policy_search_problem.png'>
I motivate the AWR algorithm as an *approximate optimization* for this problem, where the approximation can be decomposed into two steps.
