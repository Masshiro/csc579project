---
layout: page
title: Proposal
permalink: /proposal/
---

# Introduction

Connected and automated vehicles (CAVs) are essential to the future of intelligent transportation systems (ITS), which encompass both ground and air transportation <sup><a href="#ref1">[1]</a></sup>. The vast amount of data needed to train machine learning models has raised significant concerns about data security, including the legitimacy of data collection, potential misuse, and privacy breaches. To address these concerns, federated learning has gained considerable attention in the ITS field, as it eliminates the need to share users' raw data. However, when deployed in ITS scenarios, existing federated learning approaches may still face several challenges:

- **Centralized Bottleneck and Single Point of Failure**: Federated learning relies on a central aggregation server to coordinate model updates from distributed clients. This creates a bottleneck in communication and computation, limiting scalability. Additionally, if the central server fails or is compromised, the entire learning process is disrupted.
- **High Communication Overhead**: Even though federated learning reduces raw data transmission by keeping data on local devices, it still requires frequent communication between clients and the server to exchange model updates. This can be costly in terms of bandwidth and latency, especially in environments with unstable or low-bandwidth network connections.

# Related Work and Limitations

### **Related Work**

Federated learning (FL) has gained significant attention in the field of intelligent transportation systems (ITS) due to its ability to enable collaborative model training while preserving data privacy. However, existing FL approaches still face several challenges, particularly in RSU-side learning, handling heterogeneous data distributions, and overcoming centralized bottlenecks.

One major limitation of current FL frameworks is the **limited focus on RSU-side learning**. Most FL-based vehicular applications primarily emphasize model training on the vehicle side, where individual cars contribute local updates to a centralized or peer-to-peer system <sup><a href="#ref2">[2]</a></sup>. While vehicles are highly dynamic and frequently disconnect from the network, RSUs have more stable connectivity and computational resources, making them well-suited for learning tasks. However, existing work has not fully leveraged RSUs as key participants in collaborative learning, limiting the potential efficiency of FL in vehicular networks <sup><a href="#ref3">[3]</a></sup>.

Another challenge in federated learning for ITS is **data heterogeneity due to non-IID distributions**. In traditional FL, clients are often assumed to have data that follows a similar distribution, allowing for straightforward aggregation via methods like FedAvg. However, in vehicular networks, different RSUs collect traffic data from varying environments, leading to highly diverse and non-IID datasets. For example, RSUs positioned along the same road segment may have similar data distributions, while those located at intersections experience vastly different traffic patterns. This heterogeneity can significantly impact model convergence and performance, yet current FL solutions do not adequately address this issue <sup><a href="#ref4">[4]</a></sup>.

Furthermore, **many existing FL frameworks still rely on centralized aggregation**, creating bottlenecks in communication and computation. Traditional FL approaches, such as client-server architectures, require a central aggregator to collect and update global models, which introduces a single point of failure and limits scalability in large-scale ITS deployments <sup><a href="#ref5">[5]</a></sup>. Even decentralized FL variants, such as peer-to-peer FL, often require some level of coordination, making them less resilient in highly dynamic vehicular networks. Addressing these challenges requires a more decentralized and adaptive learning approach that can effectively utilize the unique characteristics of RSUs while ensuring efficient model training across diverse ITS environments.

# Proposed Approach

>  **NOTE** that this part may be subject to change.

To address these limitations, this research proposes a **decentralized federated learning framework focusing on RSU-side learning**, leveraging **gossip learning** for model propagation and aggregation. The key contributions of this method include:

1. **Hierarchical RSU Categorization for Efficient Learning**
   - RSUs are categorized into two groups based on their data characteristics:
     - **Corridor RSUs (C-RSUs)**: These RSUs are located along the same road segment, experiencing relatively **IID** data as they observe similar traffic patterns.
     - **Crossroad RSUs (X-RSUs)**: These RSUs are positioned at intersections or highway exits, where the data distribution is **non-IID** due to varying traffic patterns from multiple directions.
   - By identifying these two RSU types, different federated learning strategies can be applied:
     - **C-RSUs** can use traditional federated averaging (FedAvg) since their data is IID.
     - **X-RSUs** require techniques such as personalized FL or meta-learning to handle non-IID distributions effectively.
2. **Decentralized Federated Learning via Gossip Learning**
   - Instead of relying on a central server for model aggregation, this method employs **gossip learning**, where RSUs exchange model updates directly with their neighbors in a peer-to-peer manner.
   - This decentralized approach reduces reliance on a single point of failure and improves scalability, making it more robust for large-scale ITS deployments.
3. **Dynamic Model Adaptation Based on Data Characteristics**
   - Each RSU dynamically selects an appropriate learning strategy based on its category:
     - C-RSUs participate in a stable, structured federated learning approach.
     - X-RSUs employ a flexible, adaptive strategy that accommodates non-IID data, improving generalization.
   - This adaptive mechanism ensures that both local and global models can improve without compromising efficiency.

By **shifting the focus to RSU-side learning** and **removing reliance on a central aggregation server**, this approach improves communication efficiency, robustness, and adaptability in intelligent transportation systems.

# Expectation of Project

- Website for the project: [link](https://masshiro.github.io/csc579project/)

- Coding-based contributions: A simple while functional simulation repo will be implemented.

- Expected publication output: If everything goes well, [GLOBECOM'25](https://globecom2025.ieee-globecom.org/) or other conferences open for submission in late April or May will be targeted.

- **Project timetable**

  | Date                       | Tasks                                                        |
  | -------------------------- | ------------------------------------------------------------ |
  | Feb. 1 - Feb. 7 (Week 1)   | Literature review and proposal drafting                      |
  | Feb. 8 - Feb 15 (Week 2)   | Confirmation of code tools and deployment of the experimental environment.<br />Prototype implementation |
  | Feb. 15 - Feb 21 (Week 3)  | Prototype implementation<br />Initial analysis of experimental results |
  | Feb. 22 - Feb 28 (Week 4)  | Prototype refinement <br />Midterm preparation (on Feb. 25)  |
  | Mar. 1 - Mar 7 (Week 5)    | Prototype refinement                                         |
  | Mar. 8 - Mar.14 (Week 6)   | Prototype refinement                                         |
  | Mar. 15 - Mar.21 (Week 7)  | Prototype refinement                                         |
  | Mar. 22 - Mar. 28 (Week 8) | Prototype refinement                                         |
  | Mar. 29 - (onwards)        | Report drafting                                              |

# Reference

<p id="ref1">[1] Chellapandi, Vishnu Pandi, et al. "Federated learning for connected and automated vehicles: A survey of existing approaches and challenges." IEEE Transactions on Intelligent Vehicles 9.1 (2023): 119-137.

<p id="ref2">[2] Nguyen, Anh, et al. "Deep federated learning for autonomous driving." 2022 IEEE Intelligent Vehicles Symposium (IV). IEEE, 2022.

<p id="ref3">[3] Lu, Yunlong, et al. "Federated learning for data privacy preservation in vehicular cyber-physical systems." IEEE Network 34.3 (2020): 50-56.

<p id="ref4">[4] Yuan, Liangqi, et al. "Peer-to-peer federated continual learning for naturalistic driving action recognition." Proceedings of the IEEE/CVF conference on computer vision and pattern recognition. 2023.

<p id="ref5">[5] Hegedűs, István, et al. "Gossip learning as a decentralized alternative to federated learning." Distributed Applications and Interoperable Systems, 2019.