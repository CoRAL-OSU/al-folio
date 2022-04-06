---
layout: page
title: Detect-and-Avoid with delayed pilot commands
organization: Navy
year: 2020
---

**Dynamic control allocation between onboard DAA and Delayed Pilot Command**

Control authority allocation between an autonomous system and a remote human pilot in Unmanned Aircraft System (UAS) Platform has added complexity as it requires  guaranteed operability in dynamic environment. Since human pilot is not the primary analyzer of the dynamic environment,  latency in the communication channel may significantly compromise situational awareness and results in outdated control command.  In this context we present our work on command optimization onboard UAS during an encounter. The objectives of this work:

- Generate offline guidance waiting time map
- Develop real-time control-switching algorithm
- Develop command blending algorithm 

We consider a Detect-and-Avoid (DAA) problem, where the UAS is in an active encounter with a dynamic intruder. The UAS is remotely controlled by a pilot at the Ground Control Station ( GCS) . We assume that the communication between the GCS and the UAS is subject to a constant delay. We approach the problem without redesigning the onboard DAA algorithm. Instead, we employ a dynamic control allocation approach between the pilot and the DAA system to effectively increase pilot’s contribution within safe operational conditions and enhance human-machine user experience.


**Generate offline guidance waiting time map**

We propose a Markov Decision Process (MDP) to develop an optimal waiting strategy to determine how long the UAS can wait for the pilot command at each state. We consider that a UAS (ownship) encounters a dynamic intruder in the three dimensional space. The state space of the relative kinematics has six states:

- Relative distance in x dimension, 
- Relative distance in y dimension, 
- Relative altitude, 
- Intruder horizontal speed ,
- Relative vertical velocity, and
- Intruder heading.

The action space has two actions:
- Wait, and
- Maneuver. 

The reward function is designed such that it will get positive reward for waiting at the same time will receive high negative reward if the encounter get closer than the well clear threshold. We propagated 1.5 million trajectories and using value iteration algorithm estimated the optimal action at each state.

As we have transition matrix and the optimal action, we propagate every possible path to the threshold violation state and obtain the corresponding collision probability. Assuming that the path is acyclic, the expected waiting time for that state is calculated as the average of the waiting times of all the paths leading to collision weighted by their probabilities.  Examples of wait map can be seen in below, the figure in the left  illustrates a front view of 3-D wait map, the red zone depicts the collision zone, where the figure in the right side illustrates top view of the map and how intruder heading affect the wait time.

<!-- Side by side images -->
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_front_wait_map.png" title="Front View: 3-D wait map" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
        Parameters: Intruder velocity = 110 m/s ; intruder heading =0
        </div>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_top_wait_map.png" title="Top View: 3-D wait map" class="img-fluid rounded z-depth-1" %}
        <div class="caption">
        Parameters: Intruder velocity = 255 m/s ; intruder heading =+5
        </div>
    </div>
    
</div>


**Develop real-time control-switching algorithm and command blending algorithm**

To incorporate the waiting time map, a wait time manager is developed and integrated in the simulator. The wait time manager incorporates the waiting time map during an encounter and initializes a timer to wait for the pilot command. It is activated by default when the operation mode is DAA-Pilot with the provision of manually turning it off. The command blending is coupled with wait manager and can only be utilized when the wait manager is turned on. The wait time manager loads the waiting time maps and matches the current state with a state in the wait map. If the pilot command is delayed and the wait time at the current state is greater than the anticipated communication latency, the UAS waits. Otherwise the DAA overrides the delayed pilot command to resolve the encounter. However, if a delayed pilot command is received, the command blending algorithm discussed in [1, Section III.C ] is invoked to decide the maneuver options and to execute a more pilot-like maneuver. We compare two different setup:

- Baseline setup with the DAA-Pilot mode and the wait manager turned off

- Integrated setup with the DAA-Pilot mode and the wait manager turned on.

To examine the performance of our proposed algorithms, we consider the following questions:

- First, does the UAS wait without jeopardizing safety? 
    - We find that no loss of well clear (LoWC) occurred during any of the encounters in the 1000 simulations. This shows that waiting for pilot command does not lead to well clear violation for the simulated encounters.
- Second, if the UAS waits, is it able to receive and execute the delayed pilot command instead of overriding it?
    - Yes, the wait manager allows the UAS to receive more pilot commands and reduce instances of DAA overrides. The pilot command reception is increased by 21.12% with the integrated setup compared to the baseline setup.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_pilot_command_graph.png" title="Number of commands vs Command status" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <div class="caption">

        <strong>Command type with control-switching algorithm</strong>

        The plot at left side shows the status of Pilot Command in Encounters. Blue bar represents the baseline setup and orange bar represents the integrated setup. The number of pilot command reception is increased with the integrated setup.

        </div>
    </div>
    
</div>


- Third, how much does the UAS deviate from the desired trajectory with the wait manager compared to without the wait manager?

    - Table below shows the average deviation from the actual trajectory in the two setup. The results in Table 4 show that the mean trajectory deviation is almost the same for both setups. In the integrated setup, the UAS waits for the pilot command to arrive, which may induce more aggressive maneuvers, causing the UAS to deviate more from the original trajectory. However, the difference is minimal.  


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_deviation_table.png" title="Mean horizontal and vertical deviation" class="img-fluid rounded z-depth-0 mx-auto" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_trajectory_3d_isometric.png" title="Isometric trajectory view" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/daa_delayed/daa_trajectory_xy.png" title="X-Y trajectory view" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
The trajectory deviations from the two setup for the same scenario.  In this scenario, the DAA override trajectory is 4.36 times more deviated than the delayed piloted trajectory. However, alternate example is also plausible.
</div>



We are currently working on large scale simulation with constant and irregular delay as well as extending command-blending algorithm.


**Publication**

[1] Tabassum, Asma, He Bai, and Craig Kleski. "Optimizing Unmanned Aircraft System Decision Making for Detect-and-Avoid with Delayed Pilot Commands." AIAA AVIATION 2020 FORUM. 2020.