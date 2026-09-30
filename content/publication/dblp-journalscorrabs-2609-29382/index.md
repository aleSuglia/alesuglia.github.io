---
title: 'Decoupled Early Exits for Task-Dependent Compute Allocation in Flow-Matching VLAs'

authors:
- Riccardo Andrea Izzo
- Rimvydas Rubavicius
- Gianluca Bardaro
- Subramanian Ramamoorthy
- Matteo Matteucci
- Alessandro Suglia

author_notes: []

date: '2026-09-29'

publishDate: '2026-09-30T20:07:05.818828Z'

publication_types:
- article-journal

publication: '*CoRR*'
publication_short: ''

doi: 10.48550/ARXIV.2609.29382

abstract: 'Flow-matching Vision-Language-Action (VLA) models have emerged as a potential solution for generalist robot control, designed by combining a pretrained Vision-Language Model (VLM) backbone with an action expert that generates continuous robot actions. While these models exhibit impressive capabilities, due to their very high number of parameters, their computational requirements are often prohibitive for robotics control. To mitigate these inefficiencies, existing methods predominantly skip VLM backbone layers with early exits or reduce denoising steps, while leaving action expert depth untouched. We propose a framework that exposes backbone depth $V$, action expert depth $A$, and denoising steps $D$ as three jointly configurable compute axes in a VLA. Starting from a pretrained VLA, we attach lightweight Exit Transformers (ET) at intermediate depths in both the backbone and the action expert, trained to distil the last layer of the policy into each exit. Furthermore, we introduce a KV Cache synthesis mechanism that manages the missing keys and values of the skipped backbone layers, allowing the action expert to exit deeper than the backbone. Finally, we show that the optimal compute budget is task-dependent, with different tasks benefiting from different axes and depths. Notably, our method does not require training the original policy from scratch, and for each exit, it increases the number of parameters by only $2.1\%$ for SmolVLA and $4.1\%$ for $π_{0.5}$. We validate our approach across two flow-matching VLAs (SmolVLA, $π_{0.5}$) and two benchmarks (LIBERO, Meta-World), revealing complementary effects: $V$ and $A$ respectively reduce FLOPs and latency, while $D$ improves both. Our joint configurations $(V,A,D)$ reduce latency by $79.2\%$ and computation (FLOPs) by $31.8\%$, while improving mean success rate by $5.6\%$.'

summary: ''

tags: []

featured: true

url_pdf: 'https://arxiv.org/pdf/2609.29382'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

image:
  caption: ''
  focal_point: ''
  preview_only: false

projects: []
links:
- name: URL
  url: https://arxiv.org/abs/2609.29382
---

Decoupled early exits across backbone depth, action-expert depth and denoising steps for task-dependent compute allocation in flow-matching VLAs.
