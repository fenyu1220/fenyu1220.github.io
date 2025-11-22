---
layout: page
title: CV for Anemia Screening
description: "A Computer Vision-Based Framework for Anemia Screening Using Conjunctiva Photos"
img: assets/img/projects/anemia_profile.png
importance: 1
category: research projects
related_publications: false
---

This project develops a **fully automated computer-vision framework** for hemoglobin (Hb) prediction and anemia screening using conjunctiva photos captured under uncontrolled, real-world conditions. Instead of requiring carefully standardized, eye-only images, our system works directly on unconditioned tablet photos taken in the emergency department, with **variable distance, angle, and lighting**. The goal is to make non-invasive anemia screening practical for **point-of-care (POC) and resource-limited settings**, reducing dependence on blood draws and heavy data curation.

A key contribution of this project is the **mask-aware architecture** built on top of ConvNeXt-tiny, designed to ensure that the network focuses on the conjunctiva rather than irrelevant background features. After UNet3+ generates the conjunctiva mask, we create a two-channel representation consisting of:
1. The original eye image patch.
2. Its corresponding binary mask, where pixels inside the conjunctiva are marked as 1 and all others as 0.

These two channels are concatenated at the input stage and passed into a specially designed mask attention module. The mask is first processed through a 1×1 convolutional projection, which transforms it into a spatial attention map matching the feature resolution. This attention map is then element-wise multiplied with the intermediate feature maps of ConvNeXt, suppressing responses outside the conjunctival area.

The entire inference pipeline, including eye detection, filtering, segmentation, and Hb prediction, runs in under one second per image on a CPU-only machine, demonstrating the feasibility of deploying our workflow on edge devices and lightweight clinical systems.

<div class="col-sm-12 text-center">
    
        {% include figure.liquid loading="eager" path="assets/img/projects/anemia_workflow.png" title="anemia workflow" class="img-fluid rounded z-depth-1" %}
    
</div>
<div class="caption">
    This figure illustrates the complete workflow of our method. The green section represents the process of extracting the conjunctiva from the original input image. The blue section corresponds to our regression model. The purple section depicts our ROI-Aware ConvNeXt model. Finally, the predictions from the regression model and the ROI-Aware ConvNeXt model are combined to produce the final output.
</div>