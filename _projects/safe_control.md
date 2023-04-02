---
layout: page
title: Safe Control Under Uncertainty
description: Designing provably correct controllers for dynamical control systems under uncertainty.
img: assets/img/projects/uav_conceptual.jpg
importance: 2
category: work
---

In today’s world, more and more autonomous systems operate in safety-critical settings. These systems must accomplish their task safely without the intervention of a human operator. For example, consider a unmanned aerial vehicle (UAV) whose task is to deliver a package to a designated target area. The UAV should not crash into obstacles, nor should it run out of battery. In other words, the drone must behave safely.

<div class="row" style="justify-content: center;">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/uav_gif.gif" title="Drone Motion Planning" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

However, turbulence or wind gusts may cause uncertainty in the position and velocity of the UAV. Such factors, also referred to as noise, render the behavior of the UAV uncertain. Consequently, the ambitious aim is to compute a controller for the UAV, such that it progresses safely to its target, despite the uncertainty. The focus of our research group is such dependable and safe decision-making under uncertainty. AI systems, such as the UAV, need to account for the inherent uncertainty in the real world autonomously. We combine state-of-the-art techniques from machine learning, artificial intelligence, control theory, and rigorous formal verification to provide strong guarantees on the safe decision-making of AI systems.


<h2>Abstraction-based planning</h2>
Given a continuous-state, continuous-action dynamical system with uncertainty, the general problem that we face is to compute a feedback controller that maximizes the probability to satisfy a complex specification, such as reaching a desired goal state while avoiding unsafe states. This problem is very hard to solve in general, because the state and control inputs are continuous, and because the outcomes of control inputs are uncertain due to disturbances in the form of noise.

The key step in our approach is to compute a discrete-state abstraction of the continuous system. Loosely speaking, we partition the infinitely many states into a set of abstract, discrete regions. We then define abstract actions that correspond to control inputs that cause transitions between these regions. Depending on the type of uncertainty about the system dynamics, the outcome of every action is either stochastic or even nondeterministic. Our abstraction procedure ensures that we obtain a faithful, yet abstract representation of the dynamical system as a type of Markov decision process.

<h2>Solving the UAV delivery problem</h2>
Now consider the specific UAV delivery problem in Figure 2, with the target area in green, and the obstacles that we must avoid in red. With our method, we can compute a controller, for which the probability to safely reach the target area is above a predefined safety threshold. The effect of turbulence causes a non-Gaussian stochastic disturbance that affects the 6-dimensional state of the UAV. The wind strength may vary from day to day, so the optimal path to take may differ as well. With our method, we can take this effect into account, because we reason over the effect of the turbulence explicitly. As shown in the figure, under weak turbulence, the UAV takes the short but narrow path, while under high noise, it is safer to take the longer path around the obstacles. Thus, accounting for noise is important to obtain controllers that are safe.

<div class="row" style="justify-content: center;">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/uav_trajectories_highnoise.gif" title="Weak Turbulence" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/uav_trajectories_lownoise.gif" title="Strong Turbulence" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulated trajectories for the UAV under different turbulence conditions. Left: weak turbulence. Right: strong turbulence.
</div>

<div class="publications">
<h2>Related publications</h2>
{% bibliography -f papers -q @*[safecontrol=true]* %}
</div>