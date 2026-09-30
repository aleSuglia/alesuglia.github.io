---
title: 'GPTNT: Benchmarking Real-Time Collaboration Between Multimodal Agents on Keep Talking And Nobody Explodes'

authors:
- Amit Parekh
- Sabrina McCallum
- Kareem Al-Hasan
- Malvina Nikandrou
- Alessandro Suglia
- Ioannis Konstas

author_notes: []

date: '2026-09-04'

publishDate: '2026-09-30T20:07:05.818828Z'

publication_types:
- article-journal

publication: '*Transactions on Machine Learning Research 2026*'
publication_short: 'TMLR 2026'

doi: 10.48550/ARXIV.2606.28514

abstract: 'Multimodal models are increasingly deployed to solve tasks collaboratively with humans or other artificial agents. While existing benchmarks show that they possess the fundamental capabilities, the various conditions that coincide when collaborating---time pressure, information asymmetry, and imperfect communication---have traditionally been studied in isolation. To address this gap, we introduce GPTNT, a benchmark built on the cooperative video game Keep Talking and Nobody Explodes, in which two agents must coordinate to defuse procedurally generated bomb puzzles against a live countdown. One agent has access to the bomb but not the instructions for defusing it; the other holds the instructions but cannot see or manipulate the bomb. Neither agent can succeed alone: the task requires contributions from both, and is solvable only through effective, efficient communication. We remove turn-taking proxies or simplifications, instead requiring agents to act asynchronously and communicate in real time. GPTNT is designed to expose how models collaborate versus how they perform alone: the instruction manual, the partner, or both, can optionally be withheld to surface what a model has memorised versus what it derives in the moment. We demonstrate that GPTNT poses a considerable challenge to the state-of-the-art: not one of the closed- and open-source models we test defuses a single bomb in real time, a bar that human players clear. In a range of controlled experiments, we explore where capabilities break down, identifying critical weaknesses in state tracking, efficient acting within the time budget, handling ambiguity, and error recovery. Since it runs on the real game, GPTNT benefits from procedural generation and inherits a living modding community: as models improve, the benchmark can be evolved to remain challenging, rather than being solved once and retired.'

summary: ''

tags: []

featured: true

url_pdf: 'https://arxiv.org/pdf/2606.28514'
url_code: ''
url_dataset: ''
url_poster: ''
url_project: 'https://gptnt.github.io/'
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
  url: https://arxiv.org/abs/2606.28514
---

A benchmark for real-time collaboration between multimodal agents on Keep Talking and Nobody Explodes.
