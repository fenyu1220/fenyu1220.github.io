---
layout: page
title: Coin Bank
description: "Course project of CS 312000: Introduction of Integrated Circuit Design"
img: assets/img/projects/coinbank_profile.png
importance: 1
category: course projects
related_publications: false
---

This project focuses on the **full custom design of a digital coin bank**, leveraging fundamental principles of **integrated circuit (IC) design** to develop an efficient and scalable savings management system. The coin bank circuit is designed to store, update, and display monetary values using **flip-flops (DFFs), multiplexers (MUXs), and finite state machines (FSMs)**. The system operates on a 1.8V power supply, with state transitions dictated by clock signals, power control, and store commands.

The circuit consists of a 4-bit input for storing money, a 4-bit monitor output, and a dual-state encoding system, supporting both binary and one-hot encoding to represent FSM states. The FSM transitions through four key states—Sleep, Idle, Store Money, and Show Money—where the deposited amount is accumulated and displayed dynamically. Notably, due to the absence of a reset signal, the initial stored value is retrieved from flip-flop registers (Init3 to Init0) to ensure accurate tracking.

The project employs **pre-simulation and post-simulation analysis**, validating the system's functional correctness, latency, and area efficiency. Performance evaluation includes waveform analysis, state transition validation, and design rule checks (DRC) and layout versus schematic (LVS) verification. The project also explores different FSM encoding methods, analyzing their impact on circuit complexity and performance.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/coinbank_wave1.png" title="waveform 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/coinbank_wave2.png" title="waveform 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    These two figures are part of the waveform of my project.
</div>

Challenges encountered include **ensuring timing synchronization**, optimizing **logic gate arrangements**, and maintaining **low power consumption**. The study highlights the critical role of **circuit architecture, state encoding, and memory elements** in IC design, providing a foundational understanding of digital system integration.

Here is my project report: [Report]({{ "/assets/pdf/coin_bank_report.pdf" | relative_url }})

<div class="col-sm-12 text-center">
    
        {% include figure.liquid loading="eager" path="assets/img/projects/coinbank_layout.png" title="the whole layout of my coin bank design" class="img-fluid rounded z-depth-1" %}
    
</div>
<div class="caption">
    This figure shows the whole layout of my coin bank design.
</div>
