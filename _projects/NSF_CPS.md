---
layout: page
title: Cooperative Driving in Heterogeneous Traffic of Manned and Unmanned Vehicles
organization: NSF Cyber Physical Systems Medium
year: 2022
importance: 1
---

**(joint work with Dr. Weihua Sheng at OSU)**

The development of vehicles with advanced features of driving automation is expected to have a profound impact on transportation safety, efficiency, and cost. As a result, the traffic will inevitably become more heterogeneous. This mixed traffic of human-driven vehicles and automated vehicles creates both challenges and opportunities for transportation safety. Recent years have witnessed significant growth of research on cooperative driving in mixed traffic. Most existing research is from the perspective of autonomous vehicles, which accommodates nearby human-driven vehicles, but does not actively involve them in cooperation.  If a human-driven vehicle can actively participate in cooperative driving, safety and efficiency of the mixed traffic can be potentially improved. 

Motivated by such potential, we are investigating cooperative driving in mixed traffic consisting of three types of vehicles: CHV (Conventional Human-driven Vehicle), IHV (Intelligent Human-driven Vehicle), and EAV (Enhanced Autonomous Vehicle with V2V communication). Compared to the CHV, the IHV is equipped with a copilot that offers driving advice based on driver monitoring and V2V communication, enabling active involvement of human drivers in cooperative driving scenarios. Technological advances and advanced driver assistance systems make it possible to convert a CHV to an IHV. 

Our current research is focused on the coordination of IHVs and EAVs to generate suggestive actions for human drivers and control commands for EAVs. The key challenge is to incorporate uncertain human decision models into an online coordination framework. In our recent work below, we employed discrete hybrid stochastic automata (DHSA) to model stochastic transitions in human driving behaviors and delays in human responses to advising commands. Together with scenario-based stochastic model predictive control (sMPC), we generate advising commands for human drivers in lane merging scenarios. We performed validation experiments on our cooperative driving testbed.

**Testbed**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/NSF_CPS/simulator.jpg" title="Driving simulator" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Relevant Publications**

<div class="publications">


{% bibliography --file CPS %}


</div>
