---
layout: page
title: Coin Bank
description: 'Course project of CS 312000: Introduction of Integrated Circuit Design'
img: assets/img/projects/layout_profile.png
importance: 1
category: course projects
related_publications: true
---

This project explores the application of reinforcement learning (RL) to autonomous drone racing, addressing the challenges of policy training and the design of action spaces, reward structures, and training strategies. The Proximal Policy Optimization (PPO) algorithm, a model-free RL approach, was employed due to its stability and performance. Simulations utilizing a six-degree-of-freedom drone dynamics model evaluated the impact of rotor speed and body rate control inputs on policy effectiveness. The study highlighted the importance of designing coherent action-observation mappings for robust performance, favoring body rate control for its simplicity. Reward structures were tailored to incentivize progress, path following, and safety, with distinct modes tested to balance risk and efficiency. A custom simulator incorporated collision detection and dynamic initialization strategies, enabling efficient exploration of diverse racecourse configurations. Experiments revealed that the initialization buffer strategy yielded inconsistent results, emphasizing the need for refinement. Performance metrics such as completion rates, trajectory lengths, and generalization across unseen courses were analyzed. While the trained policies performed well on simpler racecourses, challenges persisted on complex layouts like figure-of-eight courses, partly due to policy forgetting during prolonged training. Generalization evaluations indicated that policies designed for specific courses struggled to adapt to simpler or structurally different environments. Despite these limitations, the findings underscore the critical role of design decisions in RL applications for dynamic and safety-critical tasks. Future work could explore alternative algorithms, reward tuning, and programming optimizations to enhance scalability and efficiency in training.

 
 Here is our project report: [Report]({{ site.url }}/assets/pdf/coin_bank_report.pdf)


<div class="col-sm-12 text-center">
    
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    
</div>
<div class="caption">
    This figure shows a quadrotor completing half of a figure-of-eight racecourse using a policy trained with RL.
</div>
