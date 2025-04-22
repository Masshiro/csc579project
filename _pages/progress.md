---
layout: page
title: Progress
permalink: /Progress/
---

# Update 4 (Early April)
Building on the completed work, a 6-page, submission-ready manuscript was drafted during this two-week period. Minor issues in the proposed framework were also addressed and resolved.

**Manuscript Drafting**
- Conducted a systematic literature review to investigate the core challenges addressed by the project
- Provided a detailed and rigorous description of the proposed methodology
- Revised and formatted the manuscript to fully comply with the target conference's submission requirements
- Ensured the paper is polished and ready for submission

**Next Step**
- Keep polishing the manuscript until it is submitted.

# Update 3 (Late March)

Since the project ultimately targets a conference submission and a recent publication has already addressed the tier-1 design, the project will now focus solely on the tier-2 design. The proposal has been updated to reflect this shift in focus.

**Proposal Modification**
- Revised the proposal to shift the primary focus to tier-2 design
- Refactored and redefined key components to align with the new direction
- Updated the project webpage to reflect these changes

**Literature Review**
- Conducted a literature review based on the revised proposal scope
- Analyzed the strengths and limitations of existing works, and identified research gaps that this project aims to address

**Algorithm Design and Evaluation**
- Developed a novel peer-to-peer decentralized collaborative learning framework
- Designed and implemented three core algorithms to ensure the framework operates efficiently
- Performed evaluations to demonstrate the effectiveness and robustness of the proposed approach

**Next Step**
- Refine the framework design
- Draft manuscript/final report


# Update 2 (Early March)
Continued working on the tier-1 architecture. 

**Architecture Refactoring**
- Implemented a modular server design with distinct phases for the federated learning process
- Created abstract communication interface supporting both simulation and container deployment
- Enhanced client implementation with better resource management and container compatibility 

**Performance Improvements**
- Added parallel client training capability
- Implemented memory management to prevent unbounded growth during long experiments
- Developed priority-based bandwidth allocation for vehicles with limited connection time, meaning the RSU assigns bandwidth weights inversely proportional to remaining time (vehicles about to leave get higher priority) 

**Containerization Support (under development)**
- Added Docker container-friendly interfaces (without testing yet) for realistic network simulations
- Implemented real network measurement capabilities for latency and bandwidth (without testing yet)

**Issues Addressed**
- Fixed configuration handling for proper vehicle and RL parameter propagation
- Resolved the limitation aroused by fixed pre-defined round time for tier 1 collaboration, and adapt reinforcement learning approach to dynamically tune the round time

**Next Step**
- Implement Tier 2 architecture
- ~~Submit APNet abstract (although based on my current progress, I may not make it)~~


# Update 1 (Late February)

Initialized the goal of the project, which is to design a **two-tier hierarchical federated learning architecture**. Specifically, the two-tier collaborative framework tailored for limited network connectivity scenarios, including Vehicle-RSU and RSU-RSU collaborations.

**Tier-1: Vehicle-RSU Collaboration**

Tier 1 establishes dynamic collaboration between vehicles and Roadside Units (RSUs). RSUs assign tailored models to vehicles within their coverage range, with vehicle arrivals modeled as a Poisson process to reflect real-world mobility patterns. Vehicles participate in federated model training during their limited connection window, with RSUs aggregating these distributed contributions to build robust models despite participant transience. This tier optimizes learning under mobility constraints while minimi zing bandwidth requirements through local computation.

**Tier 2: RSU-RSU Collaboration**

Tier 2 enables decentralized collaboration between RSUs operating as a self-organizing peer-to-peer-like network. Unlike traditional architectures requiring continuous cloud connectivity, RSUs communicate directly to share and refine models focused on bird's-eye surveillance tasks. Each RSU negotiates model updates with peers through a consensus mechanism designed for limited-bandwidth environments like satellite networks. This tier ensures system resilience when cloud access is intermittent, allowing continuous model improvement through background refinement protocols that maximize information exchange under severe network constraints.

**Tools**
- Flower (federated learning framework, version 1.15.1) 
- PyTorch (version 2.6.0) 
- Docker (version 28.0.1)