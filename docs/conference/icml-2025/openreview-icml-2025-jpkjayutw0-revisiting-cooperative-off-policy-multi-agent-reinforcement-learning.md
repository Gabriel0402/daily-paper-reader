---
title: Revisiting Cooperative Off-Policy Multi-Agent Reinforcement Learning
title_zh: 重新审视合作离策略多智能体强化学习
authors: "Yueheng Li, Guangming Xie, Zongqing Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JPkJAyutW0"
tags: ["query:gt-mai"]
score: 6.0
evidence: 合作多智能体强化学习的离策略改进
tldr: 本文针对合作多智能体强化学习中离策略方法因联合Q函数导致的外推误差问题，提出一系列技术包括退火多步自举、目标表示等。实验证明这些方法能有效缓解随智能体数量增长的误差，提升离策略MARL的扩展性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1548, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1644, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1731, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1744, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 823, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1714, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1729, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1712, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jpkjayutw0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1727, \"height\": 359, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jpkjayutw0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1247, \"height\": 878, \"label\": \"Table\"}]"
motivation: 离策略MARL方法面临联合动作空间指数增长导致的Q目标估计错误。
method: 提出退火多步自举等系列技术，减少外推误差并适应多智能体设置。
result: 有效缓解随智能体数量增长的误差，提升离策略MARL性能。
conclusion: 针对外推误差的优化可显著改善离策略MARL的扩展性。
---

## Abstract
Cooperative Multi-Agent Reinforcement Learning (MARL) has become a critical tool for addressing complex real-world problems. 
However, off-policy MARL methods, which rely on joint Q-functions, face significant scalability challenges due to the exponentially growing joint action space.
In this work, we highlight a critical yet often overlooked issue: erroneous Q-target estimation, primarily caused by extrapolation error.
Our analysis reveals that this error becomes increasingly severe as the number of agents grows, leading to unique challenges in MARL due to its expansive joint action space and the decentralized execution paradigm.
To address these challenges, we propose a suite of techniques tailored for off-policy MARL, including annealed multi-step bootstrapping, averaged Q-targets, and restricted action representation. Experimental results demonstrate that these methods effectively mitigate erroneous estimations, yielding substantial performance improvements in challenging benchmarks such as SMAC, SMACv2, and Google Research Football.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：合作多智能体强化学习（MARL）在自动驾驶、交通管理、机器人集群等复杂现实场景中具有重要应用。离策略（off-policy）MARL方法依赖联合Q函数，但面临联合动作空间随智能体数量指数增长的严峻挑战，导致可扩展性差。

- **核心问题**：本文指出了一个被忽视的关键问题——Q目标估计错误，主要由**外推误差（extrapolation error）** 引起。随着智能体数量增加，联合动作空间巨大，使得TD目标中下一状态的Q值估计严重依赖未见过的状态-动作对，导致误差累积。此外，现有价值分解方法虽然缓解了部分可扩展性问题，但未能根本解决外推误差，且在复杂任务中性能随智能体数量增加而显著下降。

- **整体意义**：作者旨在揭示离策略MARL方法性能瓶颈的根源，并提出一套通用技术来缓解外推误差，从而提升离策略MARL方法的可扩展性和实际效果。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 核心思想
本文从误差分解出发，指出目标估计误差（TEE）是主要问题，源于外推误差在联合动作空间中的放大。为此提出三项技术，分别从**减少对Q函数的依赖、降低估计方差、限制联合动作影响**三个角度缓解TEE。

### 关键技术细节

1. **退火多步自举（Annealed Multi-Step Bootstrapping）**  
   - 采用Peng's Q(λ)（PQL）算子，用多步蒙特卡洛回报替代单步TD目标，减少对未训练Q值的依赖。PQL定义：  
     \( N^{\mu,\pi}_{\lambda} Q = (1-\lambda) \sum_{n=1}^\infty (\lambda T^\mu)^{(n-1)} T^\pi Q \)  
   - 但固定大λ会引入策略偏差。作者提出**λ退火策略**：从1开始逐渐退火到较小的λ*，使得训练初期利用多步回报降低误差，后期减少偏差。

2. **平均Q目标（Averaged TD Target）**  
   - 使用M个独立估计的Q函数（或个体效用函数）进行集成，在TD目标中取平均，从而将方差降低至原来的1/M。  
   - 对价值分解方法，平均个体效用而非混合网络，因为误差主要来自动作空间，混合网络仅依赖状态。

3. **受限动作表示（Restricted Action Representation, RAR）**  
   - 针对直接使用联合Q函数的方法（如MADDPG），设计映射函数g(a)将联合动作空间压缩为更小的离散向量（例如用straight-through梯度训练神经网络），减少外推点。  
   - 针对类似QPLEX的方法，将权重λ_i约束在[0,1]区间（使用Sigmoid函数），防止异常值导致误差累积。

### 算法流程（以AEQMIX为例）
- 初始化M个个体Q网络和一个混合网络，对应目标网络；
- 与环境交互收集轨迹存入回放缓冲区；
- 每隔固定步数更新目标网络并退火λ；
- 采样批量数据，对每条轨迹计算多步PQL目标，其中下一动作由平均个体Q函数贪婪选择，目标Q值用平均后的Q函数计算；
- 采用均方误差损失函数联合训练所有Q网络和混合网络。

## 3. 实验设计

- **数据集/场景**：
  - **SMAC**（StarCraft Multi-Agent Challenge）：包含Easy、Hard、Super Hard难度地图，如2s3z、2c_vs_64zg、MMM2、27m_vs_30m等。
  - **SMACv2**：引入随机单位和初始位置，更具随机性和挑战性，测试了15张地图（如zerg5_vs_5、protoss10_vs_11等）。
  - **Google Research Football (GRF)**：多智能体足球场景。

- **对比方法**：
  - 值函数分解方法：QMIX、VDN、QPLEX（作为基线）。
  - 策略梯度方法：MADDPG、FACMAC（作为基线）。
  - 本文改进版本：AEQMIX、AEFACMAC、AEMADDPG-RAR、AEVDN、AEQPLEX-RAR。

- **评估指标**：主要使用平均测试胜率（Mean Test Win Rate）或平均得分，报告学习曲线。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量及训练时长等具体算力信息。仅在代码开源部分提及基于pymarl2和FACMAC代码库。通常此类研究使用单块或少量GPU（如NVIDIA V100/RTX 3090），但本文未披露。

## 5. 实验数量与充分性

- **实验数量**：
  - SMAC：使用4张地图（1 Easy, 1 Hard, 2 Super Hard），评估AEFACMAC和AEMADDPG-RAR。
  - SMACv2：在15张地图上评估AEQMIX vs QMIX（含不同种族和智能体数量5/10/20），以及AEVDN、AEQPLEX-RAR vs 基线。
  - GRF：在5张场景（如3_vs_1_with_keeper、counterattack_easy等）上比较AEQMIX和QMIX。
  - 消融实验：探讨λ、集成大小M、网络隐层大小、RAR效果、TEE/Variance分析等（共约6组消融图）。

- **充分性与公平性**：实验覆盖多种难度和智能体规模，对比了多种主流方法（包括值分解和策略梯度），并且进行了详细的消融分析。报告了多次运行的平均曲线（误差条未显示但通常有多个随机种子）。但缺乏与最新在线策略方法（如MAPPO）的直接对比，不过本文重点在于改进离策略方法本身。整体实验设计较为充分且客观。

## 6. 主要结论与发现

1. **外推误差**是离策略MARL性能瓶颈的关键，随智能体数量增加急剧恶化，且现有价值分解方法无法彻底解决。
2. 提出的三项技术（退火多步自举、平均Q目标、受限动作表示）均能有效降低TEE，提升算法稳定性和最终性能。
3. **集成与退火结合**比单独使用更好：大λ早期效率高，退火避免后期偏差；集成降低方差。
4. 单纯增大网络容量（如增加隐层尺寸）反而会加剧外推误差，导致性能下降，说明性能提升来自更准确的目标估计而非模型参数增多。
5. 悲观性约束（如取最小Q值）在在线MARL中并非必要，反而损害性能，与离线RL不同。
6. 在SMAC、SMACv2、GRF等多个基准上，改进算法相比基线获得显著提升，尤其在智能体数量多的困难任务上优势明显。

## 7. 优点

- **问题洞察深刻**：将外推误差明确引入MARL分析，并揭示了其在联合动作空间中的放大效应及误差传播一致性（EPC）条件。
- **方法通用且实用**：提出的三项技术可即插即用于多种现有离策略方法（值分解、策略梯度），无需修改基础框架。
- **理论支撑**：对PQL误差传播给出了上界分析，并形式化证明了单调性对EPC的充分必要性，为技术选择提供理论依据。
- **实验全面**：在多个基准、多种算法、不同智能体规模下进行了系统比较和消融，结果一致。
- **消融设计清晰**：单独分析了λ退火、集成大小、网络容量等对性能和TEE的影响，并揭示了过大会反而有害的反直觉现象。

## 8. 不足与局限

- **算力资源未报告**：缺乏训练时间、GPU型号等具体信息，不利于可重复性和实际部署评估。
- **对随机种子的处理不明确**：虽然通常报告多次运行均值，但文中未明确说明种子数和误差条细节（仅图中可看到可能存在）。
- **实验范围局限**：仅在合作型离散动作空间场景验证（SMAC、GRF），未测试连续动作或混合合作竞争场景；也未与最新的在线策略方法（如MAPPO）进行全面对比。
- **理论深度有限**：虽然对PQL和EPC有分析，但未提供整体收敛保证；集成方法的误差i.i.d假设在实际中未必严格成立。
- **RAR方法的设计**：依赖于人为选择映射维度（如5个二分类），缺乏自动化或理论指导，可能需针对不同任务调整。
- **超参数敏感性**：λ退火速率、集成大小M、RAR设计等需要调参，文中仅给出默认值，未研究敏感性。

（完）
