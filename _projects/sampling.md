---
layout: page
title: Sampling-Based Verification for Markov Models
description: Designing provably correct controllers for dynamical control systems under uncertainty.
img: assets/img/projects/sampling_curves.png
importance: 2
category: work
---

Markov models are widely used to model complex probabilistic systems in reliability engineering, network processes, systems biology, and autonomous systems. However, traditional analysis methods from formal verification require that the parameters of these Markov models are precisely known. This assumption is often unrealistic in practice.

Instead, certain parameters in the transition probabilities, initial conditions, and reward function of Markov models are not exactly known. In this line of research, we consider Markov models with a prior probability distribution over the parameters. This distribution encodes prior knowledge about the possible values for the parameters. We have developed principled methods to that allow for probably approximately correct (PAC) verification of these Markov models. Our methods are based on a technique called scenario optimization and can be applied to Markov decision processes (STTT, 2022) as well as continuous-time Markov chains (CAV, 2023) with uncertain parameters.

<h2>Robust Analysis of Fault Trees</h2>
One practical application of our methods is for fault trees with uncertain fialure rates. Fault trees are widely used to predict how component faults lead to system failure in safety and economically critical assets. However, how can and should these predictions be made if there is uncertainty about the failure rates of the components? With our methods, we can analyze fault trees while being robust against uncertainty in the failure rates of components.

As a concrete example, consider the fault tree shown below, which models high-voltage and relay cabinets along a railway. However, two railway cabinets produced in the same factory may show different failure rates. To capture this uncertainty, we assume that the failure rates are stochastic and are sampled from a probability distribution. With our methods, we can answer the question: What can we expect for the failure probability over time of the railway cabinet?

<div class="row" style="justify-content: center;">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/sampling_faulttree.png" title="Railway cabinets fault tree" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fault tree for a railway cabinet presented in  Ruijters et al. (2019, Reliab. Eng. Syst. Saf.).
</div>

With our methods, we can analyze the fault tree while being robust against the uncertainty in the failure rates. Concretely, we find prediction regions as in the figures below, which contain the failure probabilities over time with at least a specific (high) probability. Based on these regions, we can determine time-based maintenance policies that are robust against deviations in the failure rates.

<div class="row" style="justify-content: center;">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/sampling_curves.png" title="Prediction regions" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: the prediction regions for the case with no inspections; right: the prediction regions with inspections. With our approach, maintenance planners can make decisions about maintenance policies, while taking into account the uncertainty about failure rates of components.
</div>


<div class="publications">
<h2>Related publications</h2>
{% bibliography -f papers -q @*[sampling=true]* %}
</div>