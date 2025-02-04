---
layout: page
title: Mass Detection in Mammogram Images 
description: "Course project of CS 460200: Introduction to Machine Learning"
img: assets/img/projects/mass_profile.png
importance: 1
category: course projects
related_publications: false
---

**Mass detection** in mammogram images is a critical aspect of early breast cancer diagnosis. This project aims to develop an efficient model for **accurately identifying and marking masses in mammograms**. The proposed approach involves **preprocessing DICOM** (Digital Imaging and Communications in Medicine) images and utilizing **YOLO** (You Only Look Once) for initial mass region identification. Subsequently, a **CNN** (Convolutional Neural Network) is employed to refine and evaluate the likelihood of each identified region being a mass. Additionally, a **user-friendly web** interface is designed for medical personnel to upload DICOM images directly.

Here is our project report: [Report]({{ "/assets/pdf/mass_report.pdf" | relative_url }})

<div class="col-sm-12 text-center">
    
        {% include figure.liquid loading="eager" path="assets/img/projects/mass_web.png" title="mass detection web" class="img-fluid rounded z-depth-1" %}
    
</div>
<div class="caption">
    This figure shows the website we designed, where you can upload a DICOM image and receive a prediction.
</div>