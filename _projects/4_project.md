---
layout: page
title: Robust Dynamic Average Consensus (RoDAC)
organization:
year: 2017
---

**Internal model average consensus estimator (IMACE)**

*(joint work with Dr. Kevin Lynch and Dr. Randy Freeman at Northwestern University)*

Consider a connected and bidirectional network of agents (e.g., sensors), where each agent in a network has access to its own local input signal, but it must compute and track the average of all such inputs. Each agent communicates only with neighbors in the network, and local computation and memory requirements should be independent of the number of the agents in the network.  The RoDAC is defined as the local output of each agent tracking the exact average of the inputs regardless of the initial values of the internal states and the estimates. This robustness feature becomes important when there are agents joining/leaving the network,  changes in the network topology, computation faults, and communication faults (i.e., dropped packets), all of which introduce new nonzero initial conditions into the estimator dynamics. While each such event introduces a transient, if the network is constant and connected after these events, robust dynamic average consensus implies convergence to the correct average value. Examples of such inputs are distance measurements between a static sensor and a moving target, or sensor measurements of a time-varying environment.

We developed a class of average consensus estimators to achieve robust dynamic average consensus of time-varying inputs, given partial linear model information of the inputs. These estimators make use of the celebrated internal model principle (IMP), and thus called the internal model average consensus estimator (IMACE). The block diagram form of the estimator is shown below, where L is the graph Laplacian matrix that represents the communication topology of the network, h(s) and g(s) are transfer functions that represent the internal filtering at each agent, \phi(s) is the Laplace transform of the time-varying inputs, and \xi^1(s) and \xi^2(s) are the initial conditions of the h(s) and g(s). 


**Extension to Nonlinear systems**

This framework also applies to synchronization of nonlinear systems under disturbance, that is the input  is considered disturbance to the system. In this case, the h(s) in the above diagram will be replaced by a nonlinear operator H. We require H to satisfy an incremental-passivity property. If this property is verified, we develop similar conditions as in [C10](https://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=5717485) to guarantee the synchronization of the outputs of the H's under the time-varying input disturbances.  The recent paper [C15] discusses this extension using an example of Goodwin oscillator model. 


**Extension to PDE systems**

This framework has also been extended to achieve spatial homogenization of nonlinear reaction-diffusion PDEs subject to a class of spatially and temporally-varying heterogeneities. The recent paper [C17] discusses this extension.


**Publications**

[C28] J. George and H. Bai. An Output Feedback Approach to Robust Dynamic Average Consensus. In the Proceedings of the IEEE Conference on Decision and Control, 2017.

[C24] H. Bai. A two-time-scale dynamic average consensus estimator. In the Proceedings of the 54th IEEE Conference on Decision and Control, 2016.

[[J7](https://docs.google.com/viewer?a=v&pid=sites&srcid=ZGVmYXVsdGRvbWFpbnxoZWJhaXJlc2VhcmNofGd4OjFhYzYwNmQ3OTgzNDBiYjk)] S. Yusef Shafi and H. Bai. Synchronization under space and time-dependent heterogeneities. Automatica, 2015.

[C17] S. Yusef Shafi and H. Bai. Homogenization in reaction diffusion PDEs under space and time-dependent heterogeneities. In the proceedings of the 53rd IEEE Conference on Decision and Control, 2014.

[C15]. H. Bai and S. Yusef Shaﬁ. Output Synchronization of Nonlinear Systems under Input Disturbances. In the Proceedings of the 21st International Symposium on Mathematical Theory of Networks and Systems, Groningen, Netherlands, 2014.

[[C10](https://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=5717485)]. H. Bai, R. A. Freeman, and K. M. Lynch. Robust dynamic average consensus of time-varying inputs. In the Proceedings of the 49th IEEE Conference on Decision and Control, Atlanta, GA, 2010. pp. 3104-3109.