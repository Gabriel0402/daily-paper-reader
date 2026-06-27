---
title: Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination
title_zh: 跨环境合作实现零样本多智能体协调
authors: "Kunal Jha, Wilka Carvalho, Yancheng Liang, Simon Shaolei Du, Max Kleiman-Weiner, Natasha Jaques"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zBBYsVGKuB"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 通过强化学习实现零样本多智能体协调
tldr: 现有零样本协调方法局限于单一任务，泛化能力差。本文提出跨环境合作范式（CEC），通过在对环境分布上训练单一智能体来学习通用协作技能，从而支持与多个新伙伴在大量新任务上的零样本协调。实验表明CEC在所有基准测试中均优于现有方法，为多智能体系统的通用协作提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 180, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 726, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 863, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 776, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 849, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1505, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 888, \"height\": 1209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 863, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1782, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 854, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 850, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 847, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 848, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 816, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1772, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 814, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 474, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 473, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 449, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1724, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1730, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 851, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zbbysvgkub/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 853, \"height\": 323, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1709, \"height\": 1404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1578, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zbbysvgkub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1246, \"height\": 911, \"label\": \"Table\"}]"
motivation: 现有零样本协调方法局限于单个任务，无法泛化到新任务。
method: 提出跨环境合作范式，在程序生成的环境分布上训练单一智能体。
result: CEC在多个基准测试中显著优于现有方法。
conclusion: 跨环境训练可学习通用协作技能，实现零样本多任务协调。
---

## Abstract
Zero-shot coordination (ZSC), the ability to adapt to a new partner in a cooperative task, is a critical component of human-compatible AI. While prior work has focused on training agents to cooperate on a single task, these specialized models do not generalize to new tasks, even if they are highly similar. Here, we study how reinforcement learning on a **distribution of environments with a single partner** enables learning general cooperative skills that support ZSC with **many new partners on many new problems**. We introduce *two* Jax-based, procedural generators that create billions of solvable coordination challenges. We develop a new paradigm called **Cross-Environment Cooperation (CEC)**, and show that it outperforms competitive baselines quantitatively and qualitatively when collaborating with real people. Our findings suggest that learning to collaborate across many unique scenarios encourages agents to develop general norms, which prove effective for collaboration with different partners. Together, our results suggest a new route toward designing generalist cooperative agents capable of interacting with humans without requiring human data.

---

## 论文详细总结（自动生成）

好的，这是对给定论文《Cross-environment Cooperation Enables Zero-shot Multi-agent Coordination》的结构化、深入、客观的中文总结。

### 1. 论文的核心问题与整体含义

-   **研究动机**：零样本协调（ZSC）是构建人类兼容AI的关键能力。然而，现有方法（如基于种群训练PBT）通常只训练智能体在**单一任务**上与新伙伴协作。这使得训练出的策略高度专用化，即使面对高度相似的新任务，泛化能力也极差，无法满足现实世界中与多样伙伴在多样场景下协作的需求。
-   **整体含义**：论文的核心假设是，通过让智能体在**大量不同环境**中（而非与大量不同伙伴在单一环境中）进行训练，可以学习到更通用的协作策略、规范或“共识”。这种通用技能不仅能帮助智能体适应新环境，还能使其在与新伙伴（包括人类）协作时表现出更强的适应性和更低的冲突。这项工作为构建通用协作AI提供了一个新范式。

### 2. 论文提出的方法论

-   **核心思想**：提出**跨环境合作（Cross-Environment Cooperation, CEC）** 范式。CEC的核心是**用环境多样性替代伙伴多样性**。它摒弃了维护和训练庞大伙伴群体的复杂流程，转而通过自对弈（Self-Play, SP）方式，在程序化生成的海量多样化环境中训练**单一**策略。
-   **关键技术细节**：
    1.  **程序化环境生成器**：论文构建了两个基于Jax的程序化环境生成器。
        -   **双目的地游戏（Dual Destination Game）**：一个简单的2D网格世界玩具环境，用于隔离变量、验证核心假设。通过随机化智能体初始位置和目标位置来生成多样化任务。
        -   **Overcooked基准**：基于JaxMARL框架和原始Overcooked的5个经典布局，构建了能生成超过 \( 1.16 \times 10^{17} \) 种可解厨房布局的生成器。生成过程通过随机取样墙壁结构、目标、物品（盘子、锅、洋葱）和旋转等操作实现，并严格确保任务可解。
    2.  **优化目标**：
        -   CEC的目标是优化跨环境分布 \( \mathbf{M} \) 下的自对弈期望回报：
            \( J(\pi_C) = \mathbb{E}_{m_i \sim \mathbf{M}} [S(\pi_C, \pi_C, m_i)] \)
        -   其中 \( \pi_C \) 是CEC智能体策略，\( S(.) \) 是协作任务得分。这个公式的核心是**只使用一个策略 \( \pi_C \) 与自己协作，但要在许多不同的环境 \( m_i \) 中进行**。
    3.  **算法流程**：使用多智能体强化学习算法IPPO，在一个训练周期内，算法联合采样一个任务 \( m_i \) 和一个初始状态 \( s_0 \)，然后让两个相同的CEC智能体（由同一个IPPO策略 \( \pi_C \) 控制）在环境中进行协作，并通过PPO目标更新该策略。整个过程不涉及任何其他伙伴策略。

### 3. 实验设计

-   **使用的场景/Benchmark**：
    -   **双目的地游戏**：用于概念验证和机制分析，包含“固定任务”和“程序生成任务”两种设置。
    -   **Overcooked**：作为主基准。包括两个评估集：
        -   **5个原始布局**：Asymmetric Advantages, Coordination Ring, Counter Circuit, Cramped Room, Forced Coordination。这些布局被CEC的训练集**完全剔除**，用于评估跨任务泛化。
        -   **100个程序化生成的新布局**：用于评估跨任务和跨伙伴的真正零样本泛化能力。
-   **对比方法（Baselines）**：
    -   **IPPO**：标准自对弈（SP）基线。
    -   **FCP (Fictitious Co-Play)**：基于种群训练（PBT）的代表性方法。
    -   **E3T (Efficient End-to-End Training)**：单任务场景下的SOTA ZSC方法。
    -   **CEC-Finetune**：论文提出的CEC方法的一种变体，即先在大量环境上预训练，再在单一目标布局上进行少量微调。
    -   **CEC-E3T**：为了对比，将E3T的伙伴多样性方法与CEC的环境多样性方法相结合。

### 4. 资源与算力

-   **论文明确说明**：由于采用了Jax，整个训练流程（从环境模拟到网络更新）在**单个GPU**上可以达到**每分钟1000万步**（10 million steps per minute）的高效训练速度。
-   **训练总量**：**所有算法（包括CEC、IPPO、FCP、E3T）都标准化训练了30亿步（3 billion steps）**，以保证比较的公平性。
-   **模型细节**：CEC网络使用了**循环神经网络（LSTM）** 作为其递归核心，论文实验表明没有LSTM的CEC无法收敛。训练使用了6个随机种子（seeds）以获取统计结果。

### 5. 实验数量与充分性

-   **实验数量**：
    -   **模拟实验**：在双目的地游戏（多个设置变体）和Overcooked（2个评估集）上进行了广泛的跨算法对比和消融实验。
    -   **人类实验**：招募了**80名参与者**，针对最复杂的两个布局（Counter Circuit和Coordination Ring）进行了人机协作实验。每位参与者与多个不同模型（使用随机种子）进行了多轮交互，并填写了包含7个维度（适应力、一致性、拟人性等）的问卷调查。
-   **公平性与客观性**：
    -   **公平**：所有方法训练时间相同；CEC和CEC-FT的训练布局与测试布局完全隔离，这对CEC是不利的，但论文仍将其作为主要基线进行比较。
    -   **客观**：所有比较都基于标准度量，即**交叉游戏得分**，这是评估ZSC的核心指标。此外，还使用**经验博弈论分析**（Meta-game EGT）来评估不同方法策略的稳健性。人类实验的定性评分也提供了额外证据。

### 6. 论文的主要结论与发现

1.  **环境多样性比伙伴多样性更有效**：在交叉游戏性能上，由单一伙伴训练的CEC显著优于使用大量伙伴训练的PBT方法（如FCP）。这表明环境多样性是提升ZSC的一个更强大的维度。
2.  **CEC模型学到了通用的协作规范**：CEC智能体能够与不同算法训练出的伙伴（如IPPO、E3T）以及人类实现良好的协作，这说明它学到的是更高层次的协作原则（如“基于对象”的注意力，避免碰撞的习惯），而非特定于环境的策略。其状态访问分布更均匀地集中在任务相关物体上，策略更灵活。
3.  **CEC模型无法用于小模型**：CEC模型必须使用循环网络（如LSTM）才能收敛并学习到有效的元学习或适应能力。
4.  **泛化性优于SOTA**：在**100个程序化生成的新布局**上，所有单任务方法（IPPO, FCP, E3T）都完全无法适应（得分为0），而CEC展现出很强的泛化能力。在与人类协作的任务中，CEC的协作得分虽略低于单任务SOTA方法E3T，但在**人类主观评价**（适应性、愉悦度、低挫败感、低碰撞率）上全面超越所有基线，包括E3T。
5.  **通用性与专精性的权衡**：CEC-FT通过微调提升了在单个任务上的表现，但损失了CEC对全新任务环境的泛化能力。
6.  **简单结合可能无效**：将CEC与E3T（提供伙伴多样性）简单结合（CEC-E3T）并没有带来进一步的性能提升，甚至在某些场景下表现更差，表明环境多样性与伙伴多样性的结合需要更精细的设计。

### 7. 优点

-   **方法创新**：提出了一个简洁而强大的新范式——用环境多样性替代伙伴多样性，从根本上改变了ZSC问题的研究思路。
-   **基础设施贡献**：构建了基于Jax的高效程序化环境生成器，极大地提升了环境生成和训练的速度，为未来的ZSC研究提供了有力工具。
-   **深入的实验证据**：从**玩具环境**到**复杂基准**再到**人类实验**，系统性地验证了假设。实验结果覆盖了从量化指标（交叉游戏得分）到定性评价（人类问卷调查）的多个层面。
-   **人类实验的洞察**：通过人类实验揭示了CEC在主观协作体验上的显著优势（如更少的碰撞、更高的适应性），这比单纯的得分更能反映实际应用价值。
-   **分析深入**：通过状态访问频率热力图、经验博弈论分析等手段深入解读了CEC成功的内在原因，即学习到更通用的协作规范。

### 8. 不足与局限

-   **训练上限未知**：论文承认，经过30亿步的训练后，CEC的交叉游戏性能尚未收敛或达到平台期。目前无法确定其性能的最终上限。
-   **采样偏差**：人类实验的参与者仅限于能流利说英语的人群，这可能导致文化和语言方面的偏差（WEIRD人群偏差），影响结论的普适性。
-   **方法局限性**：虽然CEC简单有效，但其对循环网络（LSTM）的依赖性增加了一定的模型复杂度。此外，将环境多样性与伙伴多样性有效结合这一开放性问题尚未完全解决。
-   **计算资源不完整**：尽管提到了单个GPU上的训练速度，但未明确说明其使用的具体GPU型号（如A100, V100）以及实际训练一批模型所需的总GPU-小时数，这会使成本评估有些困难。

（完）
