---
layout: page
title: Reinforcement learning for multi-agent systems
organization: Army Research Lab
year: 2023 - 2025
importance: 1
---
RL is a data-driven approach to determining optimal policies in the presence of unknown stochastic dynamics. 	RL has recently seen a resurgence in optimal control and decision making for dynamical systems based on adaptive dynamic programming, Q-learning, and actor-critic methods. However, when applied to a MAS, RL faces challenges on the  curse of dimensionality and learning efficiency. Targeting these challenges, we have investigated strategies that learn coordination policies effectively and efficiently by exploiting structures in a MAS, including 

a) time-scale separation in clustered networks, such as power networks,

b) a hierarchical structure driven by global and local reward functions, such as multi-group target tracking application.

[![drone swarm multi-target tracking](https://img.youtube.com/vi/CEz4tTX1CIU/0.jpg)](https://www.youtube.com/watch?v=CEz4tTX1CIU)


Currently, we are investigating a graph-based multi-agent reinforcement learning (MARL) problem that specify topological connections between the agents. Specifically, a **state graph**, an **observation graph**, and a **reward graph** characterize the coupling between the agent dynamics, the constraints in the agents' observations, and the dependency of the agents' rewards on others, respectively. We exploit the graph structures to decompose the learning process *without approximation* and find that the variance in the policy gradient estimates can be greatly reduced, leading to faster convergence and better sample complexity and scalability. The figure below shows the comparison of our algorithms "MAStAC" (multi-agent structured actor-critic) compared with other baseline algorithms for a 40-zone temperature control problem. 
{% include figure.html path="assets/img/multizone_baseline.jpg" title="Driving simulator" class="img-fluid rounded z-depth-1" %}

**Relevant Publications**

<div class="publications">


{% bibliography --file MARL %}


</div>
