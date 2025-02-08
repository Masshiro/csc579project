---
layout: page
title: Proposal
permalink: /proposal/
---

# Introduction

With the increasing deployment of edge devices for real-time video analytics, applications such as smart surveillance, intelligent transportation, and autonomous driving demand highly efficient, low-latency, and bandwidth-aware computing. However, existing edge-based video analytics systems suffer from the following critical issues:

- **Task Overload and Imbalance**: Edge nodes operate independently and may become bottlenecks, leading to inefficiencies.

- **Redundant Frame Processing**: Most approaches process all video frames uniformly, wasting bandwidth and computation.

- **Lack of Adaptability to Multi-Task Scenarios**: Different edge nodes may specialize in different tasks (e.g., object detection, license plate recognition), but existing approaches do not effectively optimize for such heterogeneity.

These limitations hinder the scalability and efficiency of edge-based video analytics, especially in large-scale, dynamic environments.

# Related Work and Limitations

Several approaches have been adopted to address these challenges:

1. EdgeVision <sup><a href="#ref1">[1]</a></sup> proposes a multi-agent reinforcement learning (MARL)-based collaborative video analytics framework, where edge nodes autonomously manage workload distribution. However:
   - Each node operates independently, leading to suboptimal global performance.
   - Task allocation is not dynamic, making it inefficient in high-load conditions.
   - Video frames are processed uniformly, leading to redundant computation.
2. Federated Learning (FL) in Edge Computing <sup><a href="#ref2">[2]</a></sup> has been used to optimize model updates across distributed nodes, but:
   - Standard FL assumes homogeneous tasks, making it unsuitable for multi-task edge nodes.
   - Existing FL methods do not optimize inference-time resource allocation, limiting real-time adaptability.
3. BiSwift (2024) <sup><a href="#ref3">[3]</a></sup> introduced adaptive frame selection for efficient video analytics by dynamically selecting keyframes, but:
   - It was designed for single-node inference and does not account for collaborative edge environments.
   - It lacks integration with task-aware scheduling in edge networks.

# Proposed Approach

>  **NOTE** that this part may be subject to change.

To overcome these limitations, we propose a collaborative edge video analytics framework that integrates:

1. Federated Learning with Task-Aware Personalization: We introduce a shared backbone network for feature extraction while allowing edge nodes to maintain task-specific model heads. Unlike traditional FL, which assumes homogeneous tasks, this Personalized FL (PFL) approach allows each node to specialize while benefiting from shared knowledge.
2. Adaptive Multi-Node Task Allocation: A centralized scheduler dynamically assigns tasks to edge nodes based on: 1) task type (e.g., pedestrian detection vs. license plate recognition), 2) resource load (e.g., GPU utilization, bandwidth availability). Unlike EdgeVision’s independent decision-making, this approach ensures globally optimized workload balancing.
3. BiSwift-Inspired Adaptive Frame Selection: We integrate a keyframe selection strategy to reduce redundant frame processing. The model uses Variational Autoencoders (VAE) plus Optical Flow to compute frame importance. It also applies Reinforcement Learning (RL) to dynamically select frames based on importance and network conditions.

# Expectation of Project

- Website for the project: [link](https://masshiro.github.io/csc579project/)

- Coding-based contributions: By addressing EdgeVision’s shortcomings, our framework will enhance edge collaboration, reduce latency, and improve overall efficiency in real-world edge video analytics systems.

- Expected publication output: If everything goes well, [APNet'25](https://conferences.sigcomm.org/events/apnet2025/index.php) and [MobiHoc'25](https://www.sigmobile.org/mobihoc/2025/) will be targets.

- Project timetable

  | Date                       | Tasks                                                        |
  | -------------------------- | ------------------------------------------------------------ |
  | Feb. 1 - Feb. 7 (Week 1)   | Literature review and proposal drafting                      |
  | Feb. 8 - Feb 15 (Week 2)   | Confirmation of code tools and deployment of the experimental environment.<br />Prototype implementation |
  | Feb. 15 - Feb 21 (Week 3)  | Prototype implementation<br />Initial analysis of experimental results |
  | Feb. 22 - Feb 28 (Week 4)  | Prototype refinement <br />Midterm preparation (on Feb. 25)  |
  | Mar. 1 - Mar 7 (Week 5)    | Prototype refinement<br />Abstract drafting (if APNet is possible, due on Mar. 6 AoE) |
  | Mar. 8 - Mar.14 (Week 6)   | Prototype refinement<br />Manuscript drafting (if APNet is possible, due on Mar. 13 AoE) |
  | Mar. 15 - Mar.21 (Week 7)  | Prototype refinement<br />Abstract drafting (if MobiHoc is possible, due on Mar. 23 DET) |
  | Mar. 22 - Mar. 28 (Week 8) | Prototype refinement<br />Manuscript drafting (if MobiHoc is possible, due on Mar. 30 DET) |
  | Mar. 29 - (onwards)        | Report drafting (if none of the target conferences are met)<br />Presentation preparation (slides, video recording, etc.) |

# Reference

<p id="ref1">[1] Gao, Guanyu, et al. "EdgeVision: Towards Collaborative Video Analytics on Distributed Edges for Performance Maximization." IEEE Transactions on Multimedia, 2024.

<p id="ref2">[2] Abreha, Haftay Gebreslasie, et al. "Federated learning in edge computing: a systematic survey." Sensors, 2022.

<p id="ref3">[3] Sun, Lin, et al. "BiSwift: Bandwidth orchestrator for multi-stream video analytics on edge." IEEE INFOCOM, 2024.