---
title: "The Synergy of LLMs & RL Unlocks Offline Learning of Generalizable Language-Conditioned Policies with Low-fidelity Data"
title_zh: 大语言模型与强化学习的协同：从低保真数据离线学习可泛化语言条件策略
authors: "Thomas Pouplin, Kasia Kobalczyk, Hao Sun, Mihaela van der Schaar"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5hyfZ2jYfI"
tags: ["query:vlm-rl"]
score: 5.0
evidence: 大语言模型与强化学习协同实现语言条件策略
tldr: TEDUO提出了一种离线语言条件策略学习流水线，利用大语言模型与强化学习的协同，从低保真无标签数据中学习可泛化的语言条件策略，在符号环境中实现了对未见目标的成功泛化。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1647, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 802, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 975, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 492, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1339, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 886, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 717, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1689, \"height\": 1767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1757, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1672, \"height\": 833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5hyfz2jyfi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1736, \"height\": 1007, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1724, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 810, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1465, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1781, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1780, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1752, \"height\": 820, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1780, \"height\": 704, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 935, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1775, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1078, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5hyfz2jyfi/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 900, \"height\": 381, \"label\": \"Table\"}]"
motivation: 在真实场景中，标注数据稀缺且实时实验不可行，现有强化学习方法难以泛化到未见目标和状态。
method: 提出TEDUO流水线，结合大语言模型和离线强化学习，从无标签数据中学习语言条件策略。
result: 在符号环境中成功泛化到未见目标。
conclusion: LLM与RL的协同为低数据场景下的语言条件决策提供了有效方案。
---

## Abstract
Developing autonomous agents capable of performing complex, multi-step decision-making tasks specified in natural language remains a significant challenge, particularly in realistic settings where labeled data is scarce and real-time experimentation is impractical. Existing reinforcement learning (RL) approaches often struggle to generalize to unseen goals and states, limiting their applicability. In this paper, we introduce $\textit{TEDUO}$, a novel training pipeline for offline language-conditioned policy learning in symbolic environments. Unlike conventional methods, $\textit{TEDUO}$ operates on readily available, unlabeled datasets and addresses the challenge of generalization to previously unseen goals and states. Our approach harnesses large language models (LLMs) in a dual capacity: first, as automatization tools augmenting offline datasets with richer annotations, and second, as generalizable instruction-following agents. Empirical results demonstrate that $\textit{TEDUO}$ achieves data-efficient learning of robust language-conditioned policies, accomplishing tasks beyond the reach of conventional RL frameworks or out-of-the-box LLMs alone.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

论文旨在解决离线语言条件策略学习问题：在真实场景中，标注数据稀缺且实时交互不可行，现有强化学习方法难以泛化到未见目标和状态。作者提出一种新的流水线TEDUO，利用大语言模型与强化学习的协同，从仅有的无标签状态-动作转移数据集和未配对的自然语言目标集合中，学习可泛化的语言条件策略。核心动机是构建能够在动态环境中遵循自然语言指令完成复杂多步任务的自主智能体。

## 2. 方法论

**核心思想**：结合大语言模型的先验知识与强化学习的策略优化能力，通过三阶段流水线实现零样本泛化。

**关键步骤**：
- **Step 1：构建可解马尔可夫决策过程**  
  - 可选状态抽象：利用LLM按目标g去除无关特征，降低状态空间维度。  
  - 事后标注：用LLM近似判断状态是否达成目标g，再训练轻量代理奖励网络R_θ(·; g)以降低计算成本。
- **Step 2：离线策略学习**  
  - 对每个训练目标g，用离线强化学习（如表格Q学习或Deep Q-Learning）从抽象数据集D_g中学习最优策略π_g。
- **Step 3：LLM监督微调**  
  - 将步骤2学到的策略蒸馏到预训练LLM中：构建监督数据集D_SFT（包含目标命令、初始抽象状态、最优动作序列），采用标准下一词预测目标对LLM进行LoRA微调，使其能够作为可泛化的语言条件策略。

## 3. 实验设计

**数据集/场景**：
- **BabyAI**（主要基准）：符号网格世界，22×22格子，9个房间，任务包括“去某颜色物体”、“拾取某颜色物体”、“将某物放在某物旁边”等。训练目标500个，测试目标100个（语义不同）。
- **Webshop**（额外环境）：模拟电商网站，动态动作空间，需要生成搜索词等语言输入。

**基准方法**：
- Vanilla LLM（Llama-3-8B/70B）
- In-context + Chain-of-Thought 提示
- DeepSeek-R1（蒸馏到Llama-8B）
- BabyAI-IL-bot（GRU+CNN+FILM+ LSTM，基于TEDUO步骤2的策略进行模仿学习）

**评估指标**：成功率、回合长度、无效动作比例。

**泛化设置**：
- 新环境：训练时未见的不同网格布局。
- 新目标：语义上与训练目标不同的自然语言指令。
- 更大网格：从较小网格训练后测试到更大的网格尺寸。

## 4. 资源与算力

论文明确提及使用 **4块A100 GPU（80GB VRAM）** 进行LoRA微调。训练时长未直接给出，但提供了TFlops估算（见表4）：例如，使用5.2e7 TFlops对应266个训练目标时成功率33%；1.4e8 TFlops对应534个目标时成功率45%。论文指出计算能力成为新瓶颈。

## 5. 实验数量与充分性

**实验组数**：
- 主泛化实验（表1）：4种环境×4种目标/环境组合，共400个测试对。
- 消融实验（表2）：对比仅步骤1+GCBC、步骤1+2（GCRL）与完整TEDUO。
- 技能迁移与组合实验（表3）：在三种环境类型上训练并测试组合任务。
- 数据效率实验（图5）：不同数据集大小下有无状态抽象的对比。
- 计算缩放实验（表4）：不同目标数量下的性能。
- 附加实验：Webshop结果（附录B.1）、DQN替代表格Q学习（附录B.4）、网格大小泛化（附录B.7）、线性探针（图4）。

**充分性**：实验覆盖了多个环境、多种基线、消融、可解释性分析，结果客观公平。对比基线包括纯LLM、纯RL、混合方法等。消融验证了每一步的必要性。泛化测试包括新环境、新目标、更大网格，证明方法有效。

## 6. 主要结论与发现

- 纯LLM（不论参数量或提示技术）在简单BabyAI任务中表现极差（成功率<20%），表明缺乏环境动态知识。
- TEDUO将成功率提升至65%（训练集）和45%（测试新目标），远超纯LLM和BabyAI-IL-bot。
- 状态抽象显著提高数据效率（图5），将状态空间大小平均减少10%，目标标识空间减少至20%左右。
- 微调后的LLM学会了可迁移的核心技能（如避障、开门、拾取物体），并能组合这些技能解决未见过的任务（表3）。
- 线性探针实验表明，微调后的模型内部表示编码了“是否面对障碍物”等信息，而基础模型虽有先验知识但无法转化为正确行动。
- 计算能力成为新瓶颈：增大训练目标数量持续提升性能，未见饱和（表4）。

## 7. 优点

- **首次**在完全离线、无标签、非专家数据上学习可泛化语言条件策略，消除昂贵标注需求。
- **LLM与RL协同**：LLM提供数据增强（标注、抽象）和泛化能力，RL提供策略优化和动态建模，两者优势互补。
- **数据高效**：状态抽象和代理奖励网络大幅降低所需数据量和LLM调用次数。
- **强泛化**：零样本泛化到新环境、新目标、更大网格，且性能下降幅度远低于传统RL基线。
- **可解释性分析**：通过线性探针揭示模型内部学到了环境动态相关的表示，验证了微调的有效性。
- **框架灵活**：步骤2可替换为不同离线RL算法（如DQN），步骤3可选不同LLM底座。

## 8. 不足与局限

- **环境假设**：需要环境状态可文本化表示，且动作空间离散，限制了在连续控制或视觉基任务的直接应用。
- **LLM分布外**：某些场景（如罕见任务或极复杂逻辑）可能超出LLM先验知识范围。
- **先验依赖**：需要实践者了解环境并手动提供目标列表G，无法完全自动生成。
- **计算成本高**：尽管数据需求低，但微调LLM（尤其大模型）仍需要大量GPU算力，且性能随计算量增长未见饱和。
- **单环境评估**：主要结果仅基于BabyAI，Webshop实验在附录中且规模有限，缺乏对更多复杂符号环境的测试。
- **目标可达性**：若训练目标对应的状态未在数据集中出现，步骤2无法生成有效策略，可能导致微调数据缺失。

（完）
