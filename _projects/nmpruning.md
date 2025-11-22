---
layout: page
title: FPGA Co-Design for N:M Sparse and Quantized
description: "Optimizing AI Model with Compression and Accelerator Design"
img: assets/img/projects/nmpruning_profile.png
importance: 1
category: research projects
related_publications: false
---
This project explores how **model compression and hardware co-design** can jointly improve the scalability, throughput, and energy efficiency of modern AI models. Our work centers on combining **N:M structured sparsity**, **low-bit quantization**, and **FPGA accelerator design** to create a unified framework for efficient inference.

We begin by applying **N:M pruning** along the inner GEMM dimension (e.g., 2:4, 2:8, 4:16), retaining the highest-magnitude weights within each group. The surviving weights are then quantized to **INT4 or INT8**, producing compact, hardware-friendly tensors with reduced memory footprint and bandwidth demand. To preserve accuracy after aggressive compression, we incorporate a **LoRA-based fine-tuning strategy**, allowing the model to recover performance with minimal parameter updates.

On the hardware side, we design **FPGA accelerators capable of executing multiple N:M sparsity patterns and integer precisions**, enabling fair comparisons across CPU, dense GPU, NVIDIA 2:4 sparse GPU kernels, and our FPGA prototype. Using a shared dequantization-plus-matmul benchmark, we evaluate **throughput, latency, and energy consumption** across backends and extrapolate these results to **LLaMA-scale linear layers** to estimate full-model performance impact. Preliminary findings show that our FPGA design achieves **higher throughput and better energy efficiency** than CPU/GPU baselines under comparable sparsity and precision settings, highlighting the potential of compression-aware accelerator co-design.

<div class="col-sm-12 text-center">

<div class="col-sm-12 text-center">
    {% include figure.liquid loading="eager" path="assets/img/projects/nmpruning_workflow.png" title="N:M pruning and quantization pipeline" class="img-fluid rounded z-depth-1" %}
</div>
<div class="caption">
    Overview of the proposed pipeline. The green section shows offline preparation (N:M pruning, INT4 quantization, and packing). The red section shows benchmark execution (loading, dequantization, and matrix multiplication) across CPU, dense GPU, NVIDIA 2:4 sparse GPU kernels, and our FPGA prototype. Purple cells denote FP16 values, blue cells denote INT4 nonzeros, and white cells denote zeros.
</div>