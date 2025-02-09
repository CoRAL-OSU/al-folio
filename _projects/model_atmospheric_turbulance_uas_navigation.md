---
layout: page
title: Modeling atmospheric turbulence and its impact on small UAS navigation
organization: NASA-EPSCoR
year: 2018 - 2019
---

**(joint work with Dr. Balaji Jayaraman at OSU and supported by NASA EPSCoR)**

The greatest challenge for widespread use of small UAS (sUAS) is integrating their operations seamlessly with manned aircraft. For sUAS, NASA has been developing UAS Traffic Management (UTM) systems that can provide infrastructure for low-altitude airspace management and monitoring. UTM systems have the potential to enable safe, efficient operations of sUAS and integration with manned aircraft at low altitudes. However, navigation performance of sUAS is still not well understood. In particular, flight dynamics of sUAS operating in low altitudes are subject to spatially and temporally varying turbulent gusts in the Atmospheric Boundary Layer (ABL). 

The objectives of this research are

- Modeling turbulence structures in ABL 
- Modeling sUAS navigation performance in the presence of turbulence

**Modeling turbulence structures in the ABL**

The turbulent flow dynamics is an extremely complex dynamical system characterized by the combined influences of the weather, topography, solar heating and diurnal variations, cloud processes, scalar transport and the prevalent state of the atmosphere at the location and time of interest. This interplay produces highly coherent gust pattern that are not faithfully reproduced in standard wind models. The figure below shows a complex transition in 3D ABL turbulence structure with systematic variation of stability parameter by changing the surface heat flux while the mesoscale wind vector remains constant. Because surface heating drives thermal activity in the mixed layer while shear deformation of turbulence dominates the surface layer, coherent turbulence structure in the horizontal fluctuations is closely correlated with vertical fluctuations driven by buoyancy forces. The implications of such unique coherent structures tied to particular values of atmospheric stability state on sUAS flight performance have not been systematically explored. We are exploring the interplay between realistic atmospheric turbulence structure and sUAS, both qualitatively and quantitatively.

**Quadcopter trajectory modeling in turbulence**

We investigate the feasibility of modeling the trajectory of a quadcopter under wind disturbances using input-output modeling approaches. Our preliminary work [C30] shows that it is possible to model a quadcopter's trajectory response to a cross wind using a difference equation model. This model takes wind magnitude as input and predicts the trajectory deviation of the quadcopter due to the wind. The left figure below shows a time history of an east cross wind generated from the Dryden wind model and the right figure compares the predicted trajectory with the true trajectory in the east direction given the wind.  The prediction is fairly close to the true east trajectory.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/atmospheric_turbulence_uas_navigation/atmoturb_wind_velocity_plot.png" title="Wind Velocity" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/atmospheric_turbulence_uas_navigation/atmoturb_predict_vs_true.png" title="Predicted East Position vs True" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Our current work** is investigating nonlinear modelling approaches and comparing the quadcopter trajectories in the presence of ABL turbulence with the Dryden wind model. Although the linear difference equation approach works well for a pure crosswind, it is not effective at modeling trajectory deviations in multidimensional wind, due partly to a nonlinear coupling in the drag. Thus, the nonlinear approach is required in order to capture the dynamics in multidimensional wind.

**Publications**

Jayaraman, Balaji, Sam Allison, and He Bai. "On the Trajectory Dependence of Atmospheric Boundary Layer Turbulence Sensing using Small Unmanned Vehicles." arXiv preprint arXiv:1807.04304 (2018). 

[C30] S. Allison, H. Bai and B. Jayaraman. Modeling Trajectory Performance of Quadrotors Under Wind Disturbances. In 2018 AIAA Information Systems-AIAA Infotech@ Aerospace.
