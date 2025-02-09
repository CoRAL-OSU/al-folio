---
layout: page
title: Safe Wind-Aware Navigation for Collaborative Autonomous Aircraft in Low Altitude Airspace
organization: NSF National Robotics Initiative
year: 2020 - 2025
importance: 1
---

**(joint work with Drs. Kamalapurkar, Jacob, Kara, Vance and Fala at OSU)**

- Small unmanned aircraft systems (sUAS) technologies found many civil, commercial, and military applications.
- Infrastructure, such as NASA UAS traffic management (UTM) for low-altitude airspace management and monitoring, is being developed.
- Safety and efficiency of sUAS operations are strongly impacted by low-altitude gusts:
  - Negatively affect pilot operations, reduced flight time, damage
  - Airspace management and allocation made conservative and inefficient.

**Our Hypothesis**

‘In-time’ or ‘real-time’ wind field information, communicated effectively to pilots and traffic management, can enhance safety, efficiency, and robustness of future sUAS operations in
low-altitude airspace.

**Proposed Concept of Operation**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/NSF_NRI/CONOP.png" title="CONOP" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Integration diagram**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/NSF_NRI/integration.jpg" title="Integration diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Simulator**
We built a human-in-the-loop simulator based on AirSim to evaluate operators' performance in the presence of wind disturbances. 

[![Simulator](https://img.youtube.com/vi/pj01xTA7kRc/0.jpg)](https://www.youtube.com/watch?v=pj01xTA7kRc)

Our experiments show that in a survey mission for a football stadium, operators' performance improves if wind conditions are presented to them in a user interface. 

{% include figure.html path="assets/img/mission.jpg" title="Surveying 5 locations in a stadium" class="img-fluid rounded z-depth-1" width="200%" height="200%" %}

Figure below compares the traveled distance with a basic user interface and a wind-aware user interface.

{% include figure.html path="assets/img/performance.png" title="Comparison of human operators' performance with and without a wind display" class="img-fluid rounded z-depth-1" width="200%" height="200%" %}

**Experiments**

We conducted outdoor experiments to perform dynamics-based wind velocity estimation (without a wind velocity sensor). 

{% include figure.html path="assets/img/SK8.jpg" title="SK8 in flight" class="img-fluid rounded z-depth-1" width="200%" height="200px" %}

{% include figure.html path="assets/img/horWindEst_test2.png" title="Performance of various methods" class="img-fluid rounded z-depth-1" width="200%" height="200px" %}

**Yearly posters** 

<h2>2022 Poster</h2>

<iframe src="/assets/pdf/BAI_H_PSNSF24_1925147.pdf" width="100%" height="800px"></iframe>

[2023 Poster](/assets/pdf/BAI_H_PSNSF24_1925147.pdf)

[2022 Poster](/assets/pdf/2022NRIPIPosterTemplate_36x24_1925147.pdf)

[2021 Poster](/assets/pdf/2021NRIPIPoster_1925147.pdf)

[2020 Poster](/assets/pdf/NRI_INT_1925147_print.pdf)

**Relevant Publications**

<div class="publications">


{% bibliography --file NRI %}


</div>
