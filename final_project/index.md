---
layout: default
title: 3D Covid-19 Particle and Airflow Simulations
description: Alfredo De Goyeneche - Ke Wang - Catherine Gai - Wenhan Sun
---

[Link to (this) Webpage](https://cal-cs184-student.github.io/sp22-project-webpages-KeWang0622/final_project/index.html)

[//]: # ([Link to Code]&#40;https://github.com/cal-cs184-student/p1-rasterizer-sp22-mr_graphics&#41;)

## Project Summary
Since the first case of COVID-19 was confirmed in 2019, the pandemic has become one of the biggest concerns for the people around the world.
In order to better understanding and visualizing the transmission of COVID-19, in this project, we will be implementing a realistic 3D Covid-19 particle and airflow simulations based on physics modeling.
Furthermore, we aim to simulate how masks/shields can prevent the particles/droplets from spreading out and evaluate our simulations on realistic scenes (e.g., closed space, airplanes).

* Team members
    * Alfredo De Goyeneche `asdegoyeneche@berkeley.edu` CS 284
    * Ke Wang `kewang@berkeley.edu` CS284
    * Catherine Gai `catherine_gai@berkeley.edu` CS184
    * Wenhan Sun `wenhan0112@berkeley.edu` CS184


## Problem Description
COVID-19 disease have posed unprecedented challenges to the entire world. Up to April 2022, around 500 million people were reported to be infected. In order to better understanding and visualizing the transmission of COVID-19, in this project, we will be implementing a realistic 3D COVID-19 particle and airflow simulation based on physics modeling.

It's well understood that COVID-19 is transmitted mainly through close contact and respiratory droplets. Therefore, we aim to investigate how the virus spreads through particles and droplets. We will use the realistic data and parameters (droplet size, ariflow speed, etc.) for our simulations. Specifically, our goals can be summarized as follows:
1) Simulating the transmission of particles/droplets during the phases of inhalation and exhalation using fluid dynamics.
2) Simulating how masks/shields can prevent the particles/droplets from spreading out during the phases of inhalation and exhalation.
3) Simulating and evaluating the COVID particle transmission in realistic scenes (e.g., closed space, airplane with/without active air circulation).

## Goals and Deliverables
The theoretical part of our project will be based mainly on Navier-Stokes equation. We will approach the solutions of this partial differential equation under different boundary conditions, and render the results on the screen. The results will be animations of movement of particles as well as instantaneous distribution of particles around the scene. Concrete breakdowns are as follows:
### First step: particle simulator
The first set of conditions are fairly simple. We will start with a cloud of static particles in space and simulate their movements for a period of time. The particles will have 0 velocity and there will be no constraints in space of their movements.
### Second step: exhalation/ coughing simulator
Next we will impose initial velocity to each particle in the cloud. To simulate exhalation, we plan to sample a direction from a range of solid angles for each particle, while its velocity can be sampled within a small range (The initial velocity of exhaled particles should not vary too much). We then solve the PDE under these initial conditions. Simulating coughing would be similar to exhalation, but with a different solid angle range and higher velocity. We hope to see a significant difference in the propagation distance produced by exhalation and coughing.
### Third step: effect of masks or other facial coverings
Our third step will be imposing more constraints during particle transmission. In particular, we want to explore the effect of masks and other facial coverings on the spread of particles. To simulate a facial covering, we plan to define a surface within a certain distance from the particle source that holds probability <img src="https://render.githubusercontent.com/render/math?math=p"> to let through the particle, and probability <img src="https://render.githubusercontent.com/render/math?math=1-p"> of blocking it. The blocked particles will have velocity 0, and would not be taken into account during simulation in later steps. We will simulate different types of masks with different "passing-parameter" <img src="https://render.githubusercontent.com/render/math?math=p">. In this part, we expect to see that facial coverings can effectively reduce the spread of exhaled particles.
### More to Explore
If time allows, our team hopes to simulate transmission in more realistic settings. For example, we can impose more constraints on the velocity and direction of air flow (boundary conditions) to inspect droplet transmission under different ventilations. Hopefully we can further deduce that proper ventilation can help alleviate the spread of COVID-19-related particles. We can also simulate a more realistic way of interaction between particles and surfaces by retaining a non-zero velocity of the particle as they reach the surface. 
