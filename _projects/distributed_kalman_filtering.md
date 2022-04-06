---
layout: page
title: Distributed Kalman Filtering
organization:
year: 2011
---

**Distributed Kalman Filtering using the internal model average consensus estimator [IMACE](https://sites.google.com/view/he-bai/research/consensus-estimation-and-dkf)**

*(joint work with Dr. Kevin Lynch and Dr. Randy Freeman at Northwestern University)*

One of the major applications of average consensus lies in the distributed estimation of the state of dynamical systems, such as distributed Kalman filtering, distributed Kriged Kalman filtering, distributed H_inf filtering, etc. Distributed filtering finds its applications in target tracking and localization, environmental modeling, etc. 

One common approach in distributed Kalman filtering is to represent the centralized Kalman filter in the information form, where the correction step of the filter simply sums information from individual agents. With a decentralized average consensus estimator, the needed sum can be estimated to implement the Kalman filter. 

When an average consensus estimator is updated sufficiently fast, the estimates of the necessary sums converge to their true values before the next Kalman filter update. Although this approach can recover the optimality of the centralized Kalman filter at each agent, it requires high communication bandwidth and energy consumption for each agent, which may not be feasible for some applications.

In [C11](https://ieeexplore.ieee.org/document/5991484?tp=&arnumber=5991484), we developed a distributed implementation of the centralized Kalman filter with a *single time-scale*, that is, the average consensus estimator and the Kalman filter are updated at the same frequency. The key observation is that *if the agent already has information of the model dynamics for its Kalman filter, it should also employ this information in its average consensus estimator*. We then make use of the [IMACE](https://sites.google.com/view/osu-coral/home/research/average-consensus)  to match the dynamics of each agent's consensus estimator to the dynamics of its Kalman filter.This ensures that the estimation error between each agent's estimate of the state and the true state of the dynamical system has bounded covariance even when the dynamical system is *neutrally stable or unstable*.

Our assumption on the dynamical system to be estimated is that it is *observable only in a centralized sense*, that is, the state of the dynamical system may not be observable to individual agents but is observable when the measurements from the agents are fused. The embedded IMACE allows each agent to estimate the entire state of the dynamical system.

**Publication**

[[C11](https://ieeexplore.ieee.org/document/5991484?tp=&arnumber=5991484)]. H. Bai, R. A. Freeman, and K. M. Lynch. Distributed Kalman filtering using the internal model average consensus estimator. In the Proceedings of the 2011 American Control Conference, San Francisco, CA, 2011, pp. 1500-1505.

