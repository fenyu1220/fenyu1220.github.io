---
layout: page
title: BertEncoder Accelerator Engine
description: "Course project of CS 512000: VLSI System Design"
img: assets/img/projects/bert_profile.png
importance: 1
category: course projects
related_publications: false
---

This project focuses on the **hardware acceleration of a BERT Encoder layer**, leveraging **VLSI system design** principles to optimize performance for natural language processing tasks. The accelerator is implemented in **Verilog**, targeting the **quantized BERT-Tiny model**, and is designed to efficiently process the **multi-head attention** and **feedforward layers**. The architecture integrates **SRAM-based memory management, clock handling, and hardware-specific optimizations** to ensure low-latency execution.  

The accelerator handles **8-bit quantized** input data, weights, and activations, enabling reduced memory footprint while maintaining accuracy. The **multi-head attention module** employs two attention heads, with each head operating on 64-dimensional feature vectors. The **attention mechanism** involves query, key, and value computations, followed by matrix multiplications and softmax operations, efficiently implemented using **custom hardware modules**. The **feedforward network** further processes the data through fully connected layers with GELU activation functions, enhancing the model’s ability to capture complex language patterns. 

<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/bert_dataflow.png" title="bert dataflow" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/bert_detail.png" title="bert detail" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left, the overall data flow within one BertEncoder. Right, the ineternal components and their connections within one BertEncoder.
</div> 

The project is validated through **RTL and gate-level simulations**, **Design Compiler-based area and power analysis**, and **latency measurements**. The results demonstrate the efficiency of the hardware accelerator in executing BERT inference tasks, with optimized **power consumption and silicon area**.  

Here is our project report: [Report]({{ "/assets/pdf/bert_report.pdf" | relative_url }})

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/bert_blockdiagram.png" title="bert block diagram" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/bert_blockdiagram2.png" title="bert block diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    On the left is the block diagram of the part I designed. On the right is the part designed by my partner.
</div>