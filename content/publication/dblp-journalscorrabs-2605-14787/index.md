---
title: 'Do Composed Image Retrieval Benchmarks Require Multimodal Composition?'

authors:
- Matteo Attimonelli
- Alessandro De Bellis
- Aryo Pradipta Gema
- Rohit Saxena
- Monica Sekoyan
- Wai-Chung Kwan
- Claudio Pomo
- Alessandro Suglia
- Dietmar Jannach
- Tommaso Di Noia
- Pasquale Minervini

author_notes: []

date: '2026-05-15'

publishDate: '2026-09-30T20:07:05.818828Z'

publication_types:
- paper-conference

publication: '*Advances in Neural Information Processing Systems 2026*'
publication_short: 'NeurIPS 2026'

doi: 10.48550/ARXIV.2605.14787

abstract: 'Composed Image Retrieval (CIR) is a multimodal retrieval task where a query consists of a reference image and a textual modification, and the goal is to retrieve a target image satisfying both. In principle, strong performance on CIR benchmarks is assumed to require multimodal composition, i.e., combining complementary information from reference image and textual modification. In this work, we show that this assumption does not always hold. Across four widely used CIR benchmarks and eleven Generalist Multimodal Embedding models, a large fraction of queries can be solved using a single modality (from 32.2% to 83.6%), revealing pervasive unimodal shortcuts. Thus, high CIR performance can arise from unimodal signals rather than true multimodal composition. To better understand this issue, we perform a two-stage audit. First, we identify shortcut-solvable queries through cross-model analysis. Second, we conduct human validation on 4,741 shortcut-free queries, of which only 1,689 are well-formed, with common issues including ambiguous edits and mismatched targets. Re-evaluating models on this validated subset reveals qualitatively different behaviour: queries can no longer be solved with a single modality, and successful retrieval requires combining both inputs. While accuracy decreases, reliance on multimodal information increases. Overall, current CIR benchmarks conflate shortcut-solvable, noisy, and genuinely compositional queries, leading to an overestimation of model capability in multimodal composition.'

summary: ''

tags: []

featured: true

url_pdf: 'https://arxiv.org/pdf/2605.14787'
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
  url: https://arxiv.org/abs/2605.14787
---

An audit of composed image retrieval benchmarks revealing pervasive unimodal shortcuts.
