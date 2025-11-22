---
layout: page
title: Efficient GPT‑2 Inference on FPGA via HLS 
description: "HW/SW Co-Design for Efficient GPT-2 Inference on FPGA via High-Level Synthesis"
img: assets/img/projects/gpt2_profile.png
importance: 1
category: research projects
related_publications: false
---

This project presents an **end-to-end GPT-2 inference accelerator** implemented on an AMD **Alveo U280 FPGA** using **High-Level Synthesis (HLS)**. The goal is to develop a hardware-efficient solution for deploying Transformer-based models, while retaining accuracy comparable to software baselines. Our design integrates **software-level model optimization** with **hardware-level acceleration**, forming a complete **HW/SW co-design** system.

A central part of our work is an optimized **row-wise GEMM scheduling strategy**, enabling linear memory access and reducing BRAM/URAM pressure. We further apply HLS techniques including **loop unrolling, tiling, data packing, memory layout transformation, kernel fusion**, and **bind_storage pragmas** to maximize throughput on FPGA hardware. These optimizations collectively accelerate both the **Multi-Head Attention** and **MLP** modules, which dominate GPT-2 computation.

The accelerator divides responsibilities between the **host** and the **FPGA kernel**: the host manages tokenization, embedding lookup, sampling, and weight orchestration, while the FPGA executes all compute-intensive components, including LayerNorm, tiled linear layers, and fused multi-head attention. This co-design approach delivers a **2.16× speedup over CPU inference** while consuming only **23% of GPU power**, demonstrating the feasibility of FPGA-based Transformer acceleration.

<div class="col-sm-12 text-center">
    {% include figure.liquid loading="eager" path="assets/img/projects/gpt2_workflow.png" title="gpt2 workflow" class="img-fluid rounded z-depth-1 w-75" %}
</div>
<div class="caption">
    Overall model structure of GPT-2 tiny. The yellow blocks indicate modules running on the Alveo U280 FPGA, while the white blocks run on the CPU host. The dotted path is only executed during the prefill stage.
</div>

<div class="col-sm-12 text-center mt-4">
    {% include figure.liquid loading="eager" path="assets/img/projects/gpt2_arch.png" title="gpt2 architecture" class="img-fluid rounded z-depth-1 w-75" %}
</div>
<div class="caption">
    Overall architecture of our GPT-2 accelerator. The host application manages tokenization, embeddings, and weight transfers via PCIe, while the FPGA kernel executes compute-intensive layers using on-chip SRAM and optimized datapaths.
</div>