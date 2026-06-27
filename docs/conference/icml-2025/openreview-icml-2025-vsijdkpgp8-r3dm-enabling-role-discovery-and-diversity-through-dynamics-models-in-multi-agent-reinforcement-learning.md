---
title: "R3DM: Enabling Role Discovery and Diversity Through Dynamics Models in Multi-agent Reinforcement Learning"
title_zh: R3DM：通过动力学模型实现多智能体强化学习中的角色发现与多样性
authors: "Harsh Goel, Mohammad Omama, Behdad Chalaki, Vaishnav Tadiparthi, Ehsan Moradi Pari, Sandeep P. Chinchali"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VSIjdKPGp8"
tags: ["query:vlm-rl"]
score: 5.0
evidence: 多智能体强化学习中的角色发现
tldr: R3DM提出基于动力学模型的角色发现与多样性机制，使智能体角色能够影响未来轨迹，从而在复杂多智能体任务中提升协调效率。实验显示该方法在多个合作场景中优于现有角色基MARL方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1660, \"height\": 1411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vsijdkpgp8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 386, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1115, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 929, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vsijdkpgp8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1867, \"height\": 662, \"label\": \"Table\"}]"
motivation: 现有角色基多智能体强化学习方法仅从历史经验中提取角色，忽视了角色对未来行为的引导作用。
method: 提出R3DM框架，通过动力学模型学习影响未来轨迹的角色表示，增强智能体间的协调。
result: 在多个合作任务中取得更优的协作性能。
conclusion: 考虑角色对未来行为的影响能有效提升多智能体协调能力。
---

## Abstract
Multi-agent reinforcement learning (MARL) has achieved significant progress in large-scale traffic control, autonomous vehicles, and robotics. Drawing inspiration from biological systems where roles naturally emerge to enable coordination, role-based MARL methods have been proposed to enhance cooperation learning for complex tasks. However, existing methods exclusively derive roles from an agent's past experience during training, neglecting their influence on its future trajectories. This paper introduces a key insight: an agent’s role should shape its future behavior to enable effective coordination. Hence, we propose Role Discovery and Diversity through Dynamics Models (R3DM), a novel role-based MARL framework that learns emergent roles by maximizing the mutual information between agents' roles, observed trajectories, and expected future behaviors. R3DM optimizes the proposed objective through contrastive learning on past trajectories to first derive intermediate roles that shape intrinsic rewards to promote diversity in future behaviors across different roles through a learned dynamics model. Benchmarking on SMAC and SMACv2 environments demonstrates that R3DM outperforms state-of-the-art MARL approaches, improving multi-agent coordination to increase win rates by up to 20%. The code is available at https://github.com/UTAustin-SwarmLab/R3DM.

---

## 论文详细总结（自动生成）

# R3DM：通过动力学模型实现多智能体强化学习中的角色发现与多样性 —— 详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在多智能体强化学习（MARL）中，角色是促进智能体协调的关键。然而现有角色基方法（如 ROMA、ACORM、CIA 等）仅从智能体的**历史经验**（已观察到的轨迹）中提取角色，忽略了角色对**未来行为**的塑造作用。这导致智能体无法根据角色有效分化行为，容易陷入冗余策略（例如所有智能体涌向同一目标），削弱了协调效率。
- **核心问题**：如何让智能体在学习角色时不仅考虑过去，还能引导角色影响未来的差异化行为，从而实现更有效的协调。
- **整体含义**：论文提出 R3DM 框架，通过最大化角色、历史轨迹与未来期望轨迹之间的互信息，让角色直接关联未来行为，从而在参数共享的 CTDE 框架下学习真正互补的角色，提升复杂多智能体任务（如星际争霸微操）的胜率。

## 2. 论文提出的方法论

### 核心思想
- 通过信息论推导，将互信息 \(I(\tau_i^{t+k}; m_i^t)\) 分解为两个可优化项：
  1. **角色嵌入学习**：从历史轨迹中通过对比学习得到紧凑的角色表示（类似 ACORM）。
  2. **角色与未来轨迹的互信息**：通过内在奖励鼓励角色引导多样且专属的未来行为。
- 最终目标：平衡任务奖励与内在奖励，使智能体在协调的同时探索不同角色路径。

### 关键技术细节
- **对比学习（角色嵌入）**：采用 ACORM 框架，使用 K-means 聚类将智能体嵌入分组，通过正负样本对比优化角色表示（式 14）。
- **内在奖励设计**：
  - **策略内在奖励**：鼓励角色条件策略与平均策略的 KL 散度（式 7），使不同角色产生不同行动选择。
  - **动力学内在奖励**：学习一个角色条件的世界模型（DreamerV3 的 RSSM）和一个角色无关的世界模型，计算两者对数似然之差（式 9），促使角色影响未来观测预测。
- **最终目标**：总奖励 = 任务奖励 + α × 内在奖励，其中内在奖励结合了策略和动力学项（式 10）。

### 算法流程简述
1. 每个智能体通过轨迹编码器得到嵌入 \(e_i^t\)，再由角色编码器采样角色表示 \(z_i^t\)。
2. 定期进行对比学习更新角色表示。
3. 训练两个 RSSM 模型（角色条件与角色无关），用于计算动力学内在奖励。
4. 在每个时间步，为每个智能体计算策略内在奖励和动力学内在奖励，求和后与任务奖励结合，更新 QMIX 的 Q 网络。

## 3. 实验设计

- **Benchmark 与场景**：
  - **SMAC**（SC 2.4.10）：6 个硬/超硬地图，包括 5m_vs_6m, MMM2, 3s5z_vs_3s6z, 27m_vs_30m, 6h_vs_8z, Corridor。
  - **SMACv2**：6 个地图（pro 5vs5, terran 5vs5, zerg 5vs5, pro 10vs11, terran 10vs11, zerg 10vs11），引入随机初始化和不对称配置。
- **对比方法**：QMIX、ACORM（同为角色基）、CIA、GoMARL、CDS、EMC，共计 6 个 SOTA baseline。
- **评价指标**：测试胜率（Test Win Rate）和测试累积奖励（Test Cumulative Reward），报告 5 个随机种子的均值和标准差。

## 4. 资源与算力

- **论文未明确说明**使用的 GPU 型号、数量或训练总时长。仅提及训练超参数（如 batch size、学习率等），但未涉及硬件资源。因此无法总结具体算力消耗。

## 5. 实验数量与充分性

- **实验数量**：共 12 个地图（SMAC 6 + SMACv2 6），每个方法 5 种子，加上 3 类消融实验（想象视野、角色数量、有无对比学习）以及定性可视化，实验总组数较多。
- **充分性**：
  - 对比了多种类型 baseline（无角色、角色基、分组基、多样性基），覆盖全面。
  - 消融实验单独分析了关键超参数和组件影响，结果合理。
  - 难点场景（如 SMACv2 的 10vs11）虽所有方法均表现一般，但 R3DM 仍有边际提升，未出现不公平比较。
  - 定性分析（TSNE 可视化 + 策略轨迹）展示了角色分化与协调差异，增强了说服力。
- **客观性**：所有方法均在同一框架下实现，使用相同随机种子，报告均值与标准差，结论可信。

## 6. 论文的主要结论与发现

- R3DM 在 SMAC 的多个困难场景（如 3s5z_vs_3s6z、Corridor）中胜率比最优 baseline 提升最高达 20%。
- 在 SMACv2 的 5v5 和 10v11 场景中，R3DM 在胜率和累积奖励上普遍优于或持平于现有方法，尤其在 protoss / zerg 环境中表现更优。
- 消融实验表明：
  - 较短的想象视野（k=1 或 2）优于更长视野（累积预测误差导致不稳定）。
  - 适中的角色数量（3 个）比过多或过少更有利于样本效率。
  - 同时使用对比学习和内在奖励才能取得最佳性能，缺少任一部分都会下降。
- 定性分析显示 R3DM 能引导智能体产生差异化策略（例如引诱敌人、分兵包抄），而 ACORM 则倾向于聚集行动。

## 7. 优点

- **理论创新**：首次明确将角色与未来轨迹的互信息作为优化目标，并通过 infoNCE 下界和 RSSM 进行可计算分解。
- **方法整合巧妙**：将对比学习（角色嵌入）与模型基内在奖励（多样性）有机结合，既保证了角色分离又促进了探索。
- **实验全面**：涵盖两种主流 MARL 基准、多种困难程度，消融实验和定性分析均到位。
- **性能显著**：在多个场景中一致超过 SOTA，说明方法鲁棒性强。
- **代码开源**：提高可复现性。

## 8. 不足与局限

- **角色数量需先验设定**：|M| 是一个超参数，在动态变化的任务中可能不是最优，论文未提供自动确定方法。
- **动力学模型局限**：RSSM 仅基于局部观测和自身动作，忽略了其他智能体的行动或角色对自身观测的影响，可能导致内在奖励偏差。
- **实验范围有限**：仅在 StarCraft 微操任务上验证，未涉及其他实际多智能体应用（如交通信号控制、机器人协作），泛化性存疑。
- **超参数较多**：α, β1, β2, β3 以及想象视野 k 等均需仔细调节，论文仅给出具体数值，缺乏系统敏感性分析。
- **未报告算力消耗**：无法评估训练效率或可扩展性。
- **未与最新模型基 MARL 方法（如 MBPO 扩展）对比**：基线仅包括无模型方法，可能未能充分体现动力学模型的优势。

（完）
