---
title: Agent-Centric Actor-Critic for Asynchronous Multi-Agent Reinforcement Learning
title_zh: 面向异步多智能体强化学习的智能体中心演员评论家算法
authors: "Whiyoung Jung, Sunghoon Hong, Deunsol Yoon, Kanghoon Lee, Woohyung Lim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=323GZNnGqe"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 智能体中心演员评论家用于异步多智能体强化学习
tldr: 针对异步多智能体强化学习中的协调和时域抽象问题，提出ACAC算法。使用智能体中心编码器独立处理轨迹，结合注意力机制汇聚历史信息，构建集中式评论家。在多个异步MARL基准上优于传统方法，有效处理了时间异步性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 771, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 786, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 737, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1785, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 863, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1482, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1751, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1744, \"height\": 1735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1783, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1781, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-323gznngqe/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1784, \"height\": 797, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-323gznngqe/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1290, \"label\": \"Table\"}]"
motivation: 多智能体强化学习在稀疏奖励环境中协调困难，异步性增加学习难度。
method: 提出ACAC算法，使用智能体中心编码器和注意力汇聚机制处理异步性。
result: 在异步MARL基准上优于现有方法，提升了协调性能。
conclusion: ACAC能有效处理异步多智能体学习中的时间抽象问题。
---

## Abstract
Multi-Agent Reinforcement Learning (MARL) struggles with coordination in sparse reward environments. Macro-actions —sequences of actions executed as single decisions— facilitate long-term planning but introduce asynchrony, complicating Centralized Training with Decentralized Execution (CTDE). Existing CTDE methods use padding to handle asynchrony, risking misaligned asynchronous experiences and spurious correlations. We propose the Agent-Centric Actor-Critic (ACAC) algorithm to manage asynchrony without padding. ACAC uses agent-centric encoders for independent trajectory processing, with an attention-based aggregation module integrating these histories into a centralized critic for improved temporal abstractions. The proposed structure is trained via a PPO-based algorithm with a modified Generalized Advantage Estimation for asynchronous environments. Experiments show ACAC accelerates convergence and enhances performance over baselines in complex MARL tasks.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多智能体强化学习（MARL）在稀疏奖励环境中智能体难以协调，传统方法依赖同步执行，但真实场景中智能体的宏动作（macro-action）时长不同，导致决策时间点异步。
- **研究动机**：现有集中式训练分散式执行（CTDE）框架处理异步性时，普遍采用“填充”（padding）来对齐缺失的观测，这会引入冗余信息和虚假相关性，削弱价值函数的学习效果。
- **整体含义**：提出一种无需填充的智能体中心方法（ACAC），通过独立处理每个智能体的轨迹，再利用注意力机制汇聚，实现更准确的时域抽象，提升异步MARL的协调性能。

## 2. 方法论

### 核心思想
- 每个智能体使用**智能体中心编码器**独立编码其宏观测历史，编码器同时接收观测值 `z_i_t` 和对应时间戳 `p_i_t`（通过正弦位置编码嵌入），并经过 MLP + GRU 提取隐状态 `h_i_t`。
- 所有智能体的隐状态通过**基于注意力的汇聚模块**整合为联合历史表示，输入集中式评论家（critic）估计状态价值。
- 演员（actor）以自身历史 `h_i_t` 为输入，输出宏动作概率。

### 关键技术细节
- **异步GAE修改**：传统GAE按微时间步（micro-timestep）折扣，不适合宏动作时长不一的场景。提出**宏级别折扣**：对TD误差的指数折扣基于宏决策步数（macro-timestep）而非实际微时间步，公式为：
  \[
  A^{\lambda, \text{macro}}_{l(0)} = \sum_{k=0}^\infty \lambda^k \gamma^{l(k)-l(0)} \delta_{l(k)}
  \]
  其中 `δ` 为跨步TD误差，`l(k)` 为第k个宏决策点的微时间步。
- **训练算法**：基于PPO的ACAC，使用裁剪的重要性采样比、PPO目标函数（含 `min(surr1, surr2)`），评论家损失为MSE（PopArt归一化）。
- **与填充法的区别**：ACAC仅在智能体获得新观测时更新其编码器；其他智能体保持历史隐状态，不填充重复观测，从而避免误导信息。

## 3. 实验设计

### 场景与Benchmark
- **BoxPushing**：两智能体协作推箱子到目标区，地图尺寸6×6、8×8、10×10。
- **Overcooked**：三智能体合作制作并交付沙拉，地图A/B/C（7×7）。
- **Overcooked-Rand**：随机初始化物体和智能体位置，增加不确定性。
- **Overcooked-Large**：扩大到11×11，六智能体，四把刀/盘，更具挑战性。

### 对比方法
- **宏观动作基线**：Mac-NIACC（单集中评论家+填充），Mac-IAICC（各智能体独立评论家+填充），ACAC-Vanilla（ACAC结构但不用PPO损失）。
- **微观动作基线**：MAPPO micro、ACAC micro（对应微动环境）。
- 所有实验重复**5个随机种子**，报告平均回报和标准误差。

## 4. 资源与算力

- 文中明确提及：使用 **AMD EPYC 7453 28‑Core Processor** 和 **A10 GPU**。
- 训练时长：Overcooked环境约 **24‑150 小时**，BoxPushing约 **30分钟‑2小时**。
- 未明确给出GPU数量，但结合上下文推测为单卡或少量并行。

## 5. 实验数量与充分性

- **主实验**：在BoxPushing（3种尺寸）、Overcooked（3种地图）、Overcooked-Rand（3种地图）共9个标准场景上比较，每个5 seeds。
- **大规模挑战**：Overcooked-Large（6种场景，含随机版）。
- **消融实验三组**：
  1. 移除填充（ACAC vs ACAC-Duplicate）。
  2. 宏级别GAE vs 微级别GAE。
  3. 时间嵌入与自注意力的敏感性。
- **超参数灵敏度**：对裁剪率 `ϵ` 进行了分析。
- **充分性评价**：实验覆盖了不同复杂度、不同随机程度的环境，消融设计直接验证核心改进（无填充、宏GAE、时间嵌入）。多次seeds重复保证了统计可靠性。对比的基线包括填补法变种和PPO变种，公平性较好。

## 6. 主要结论与发现

- ACAC在所有测试环境中均**加速收敛**并**取得更高最终回报**，尤其在Overcooked-Large上，基线性方法几乎失效，而ACAC接近最优回报。
- **无填充**的设计避免冗余信号，使价值函数学习更准确（ACAC vs ACAC-Duplicate）。
- **宏级别GAE** 显著优于微级别GAE，更好地平衡了不同时长宏动作的信用分配。
- 时间嵌入和自注意力模块对性能提升均有贡献（消融实验验证）。

## 7. 优点

- **架构创新**：智能体中心编码器+注意力汇聚，从根本上避免填充引发的偏差。
- **算法通用性**：基于PPO框架，易于集成到现有MARL代码库；提出的宏级别GAE可推广到其他异步设置。
- **实验严谨**：多环境、多尺度、随机种子重复、消融对比层层递进，结果可复现。

## 8. 不足与局限

- **应用限制**：目前仅支持离散宏动作空间，未扩展到连续控制场景。作者指出缺乏连续动作+宏动作的异步基准是主要障碍。
- **实验局限性**：
  - Overcooked-Rand虽引入随机性，但环境结构仍然较小（7×7），更大规模或更复杂物理模拟未测试。
  - 只测试了预设宏动作（非学习得到），未来可结合宏动作发现。
- **资源报告**：未明确GPU数量及总耗时，再现性信息不够完整。
- **可能偏差风险**：基线方法为原始工作中提出的变种，未与其他近期异步MARL方法（如基于transformer的异步模型）对比，可能高估相对优势。

（完）
