---
layout: page
title: Passivity-based cooperative control of multi-agent systems
organization:
year: 2016
---

**A Passivity-based Cooperative Control Framework**

*(Joint work with Dr. Murat Arcak at UC Berkeley and Dr. John T. Wen at Rensselaer Polytechnic Institute)*

Multiple robots or sensors have a number of advantages over a single agent, including robustness to failures of individual agents, reconfigurability, and the ability to perform challenging tasks such as environmental monitoring, target localization, interferometry sensing, that cannot be achieved by a single agent. 

Under a passivity-based framework, we developed robust, adaptive, and scalable design techniques that address a broad class of cooperative control problems, including the formation control, consensus, and synchronization of nonlinear systems. This framework makes explicit the passivity properties used implicitly in the Lyapunov analysis of several earlier results, and simplifies the design and analysis of a complex network of agents by exploiting the network structure and inherent passivity properties of agent dynamics. With this simplification, the passivity approach further overcomes the simplifying assumptions of existing designs and offers numerous advantages, including:

1. Admissibility of complex and heterogenous nonlinear agent dynamics;

2. Design flexibility, robustness and adaptivity;

3. Modularity and scalability.

We have applied the passivity-based framework to a number of cooperative control problems. A brief description of each problem is presented below. Detailed results can be found in [B1](https://link.springer.com/book/10.1007/978-1-4614-0014-1).

**a) Adaptive formation control**

Formation control finds natural applications in coverage control, drag force reduction, and space interferometry. We developed a decentralized control law which ensures that a group of agents maintain a desired formation meanwhile adaptively estimating and tracking a leader's motion profile. The desired group motion can be either pure translation (e.g., flocking) or both translation and rotation (e.g., rigid motion). One experimental validation can be found [here](http://youtu.be/7-CLlWl90eE).

**b) Attitude coordination of multiple rigid bodies without inertial frame information**

The objective is to achieve the agreement of attitudes (orientations) of multiple rigid bodies without relying on inertial frame information, which is practically limited by its low bandwidth. We used the unit quarternion as the representation of the attitude matrix in SO(3) and exploited the passivity of the rigid body dynamics. The resulting decentralized attitude control law achieves attitude coordination with an undirected communication topology. In the controller, other representations of SO(3) can be employed similarly to the unit quarternion.

**c) Synchronization of Euler-Lagrange systems**

The Euler-Lagrange model is prevalently used to model multi-link robots and encompasses the double integrator dynamics as a special case. We considered the case where the dynamics of each agent are subject to a class of parameterized uncertainty. Such uncertainty may come from unknown parameters in agent dynamics or external disturbances, such as wind and friction. We developed two approaches to achieve synchronization in the presence of the uncertainty. The first approach employs the "adding cross term" technique while the second approach makes use of the relative velocity information for control implementation.

**d) Cooperative load transport**

For the previous problems, the relative information between agents, such as relative distances/positions, relative path variables, is obtained through explicit information flow, including sensor measurements and direct communication. In this problem, we considered a group of agents handling a flexible payload, where the contact forces between the agents and the payload serve as implicit communication between the agents with the payload acting as the “medium”. With this idea, we developed decentralized controllers that guarantee the force regulation on the payload and the velocity convergence of the agents and the payload. One experimental validation using PUMA 560 arms can be found [here](http://youtu.be/x0x2zJN8JwY).

**e) Caveats for Robustness**

We examined the robustness of a cooperative control system with respect to time-varying communication topology, parametric resonance, and unmodeled dynamics. 

**Publications**

[J8] H. Bai. Two-time-scale adaptive internal model designs for motion coordination. Automatica, 2016.

[[B1](https://link.springer.com/book/10.1007/978-1-4614-0014-1)]. H. Bai, M. Arcak and J. T. Wen. Cooperative Control Design: A Systematic, Passivity-based Approach. Springer-Verlag: Series of Communication and Control Engineering. 1st Edition, 209 p., 78 illus., ISBN 978-1-4614-0013-4, 2011.

[J5] H. Bai and J. T. Wen. Cooperative load transport: a formation control perspective. IEEE Transactions on Robotics, vol. 26, no. 4, pp. 742-750, Aug. 2010.

[J4] H. Bai and M. Arcak. Instability mechanisms in cooperative control. IEEE Transactions on Automatic Control, vol. 55, no. 1, 2010, pp. 258-263.

[J3] H. Bai, M. Arcak, and J. T. Wen. Adaptive motion coordination: using relative velocity information to track a reference velocity. Automatica 45 (2009), pp.1020-1025.

[J2] H. Bai, M. Arcak, and J. T. Wen. Rigid body attitude coordination without inertial frame information. Automatica 44 (2008), pp. 3170-3175.

[J1] H. Bai, M. Arcak, and J. T. Wen. Adaptive design for reference velocity recovery in motion coordination. Systems & Control Letters 57 (2008), pp. 602-610.