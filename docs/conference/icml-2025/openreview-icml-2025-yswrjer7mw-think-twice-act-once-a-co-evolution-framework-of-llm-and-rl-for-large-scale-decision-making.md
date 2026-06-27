---
title: "Think Twice, Act Once: A Co-Evolution Framework of LLM and RL for Large-Scale Decision Making"
title_zh: 三思而行：面向大规模决策的大语言模型与强化学习协同进化框架
authors: "Xu Wan, Wenyue Xu, Chao Yang, Mingyang Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ySWrJer7mW"
tags: ["query:vlm-rl"]
score: 7.0
evidence: LLM与RL协同进化用于大规模决策
tldr: 针对大语言模型缺乏实时决策能力、强化学习样本效率低的问题，提出ACE协同进化框架。LLM在RL训练中扮演策略演员和值评论家，通过多步推理优化次优动作。在大规模工业决策问题上显著提升了样本效率和决策质量，展示了LLM与RL协同的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1698, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1756, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 871, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1829, \"height\": 957, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 891, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1170, \"height\": 719, \"label\": \"Table\"}]"
motivation: 大语言模型缺乏实时决策能力，强化学习面临样本效率问题。
method: 提出ACE框架，让LLM在强化学习训练中同时扮演策略演员和值评论家。
result: 在大规模工业决策问题上显著提升了样本效率和决策质量。
conclusion: LLM与RL协同进化能有效解决大规模决策难题。
---

## Abstract
Recent advancements in Large Language Models (LLMs) and Reinforcement Learning (RL) have shown significant promise in decision-making tasks. Nevertheless, for large-scale industrial decision problems, both approaches face distinct challenges: LLMs lack real-time long-sequence decision-making capabilities, while RL struggles with sample efficiency in vast action spaces. To bridge this gap, we propose **A**gents **C**o-**E**volution (ACE), a synergistic framework between LLMs and RL agent for large-scale decision-making scenarios. ACE introduces a dual-role trajectory refinement mechanism where LLMs act as both Policy Actor and Value Critic during RL's training: the Actor refines suboptimal actions via multi-step reasoning and environment validation, while the Critic performs temporal credit assignment through trajectory-level reward shaping. Concurrently, RL agent enhance LLMs' task-specific decision-making via prioritized experience replay.

Through extensive experiments across multiple power grid operation challenges with action spaces exceeding 60K discrete actions, ACE demonstrates superior performance over existing RL methods and LLM-based methods.

---

## 论文详细总结（自动生成）

# 论文总结：Think Twice, Act Once: A Co-Evolution Framework of LLM and RL for Large-Scale Decision Making

## 1. 核心问题与整体含义（研究动机和背景）

大规模工业决策（如电网调度、交通控制、多机器人协调）面临两个核心瓶颈：
- **大语言模型（LLM）**：具备丰富的世界知识和推理能力，但缺乏实时、长序列的细粒度决策能力，推理延迟高，不适合工业实时控制（响应需低于1000ms）。
- **强化学习（RL）**：能够学习最优策略，但在巨大动作空间下样本效率低下，且收敛解与最优解存在差距。

现有方法（如模仿学习、逆强化学习、人类反馈）依赖高质量专家数据或持续人类介入，难以推广。本文提出 **ACE（Agents Co-Evolution）框架**，将LLM与RL协同进化：LLM在RL训练阶段离线充当策略演员（Policy Actor）和值评论家（Value Critic），RL则通过优先经验回放生成高质量数据微调LLM，实现“三思而行（Think Twice, Act Once）”的范式。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- **“Think Twice”**：在RL训练阶段，LLM在两个角色上离线指导策略更新：
  1. **Actor**：识别并修正RL的次优动作（通过多步推理和仿真验证）。
  2. **Critic**：对整条轨迹进行反事实推理，重新分配长期奖励（类似多步TD(λ)但用LLM的非参数因果归因）。
- **“Act Once”**：RL agent与环境交互产生轨迹，与LLM修正后的轨迹混合形成经验缓冲，用于训练RL和微调LLM。

### 关键技术细节
- **RL基础**：采用SAC（Soft Actor-Critic）作为RL模块（离线策略，熵正则化）。
- **LLM作为Actor**：从RL缓冲采样低奖励转换（r < r̄），将状态/动作转为自然语言，LLM推理得到修正动作ˆa_t，并通过环境仿真验证后存入LLM缓冲D_LLM。
- **LLM作为Critic**：对整条轨迹τ中关键决策点（|r| > r̄）进行反事实奖励修正，离散化为四个级别{−2K, −K, +K, +2K}，修改后替换原奖励。
- **混合经验缓冲**：RL缓冲D_RL与LLM缓冲D_LLM按比例β混合，采用基于奖励的重要性权重w_r(τ)优先采样高质量经验。
- **奖励加权策略学习**：RL策略更新时使用重要性权重加权，使得高奖励的LLM修正经验被更重视。
- **LLM微调**：使用混合缓冲D_mix对LLM进行低秩适配（LoRA）微调，以奖励信号作为标签提升任务能力。

### 算法流程
1. **Act Once**：RL agent与环境交互，存储转换到D_RL。
2. **Think Twice**：定期从D_RL采样，LLM作为Actor修正低奖励动作，作为Critic修正关键轨迹奖励，结果存入D_LLM。
3. 从D_mix（D_RL + D_LLM）采样，用重要性权重更新RL的Q函数和策略；定期用D_mix微调LLM。

## 3. 实验设计

### 数据集/场景
- **L2RPN WCCI 2020**：模拟美国中西部电网（36个变电站，59条线路，22个发电机，动作空间 >60,000）。测试：10个3天场景（864步）。
- **L2RPN NeurIPS 2020**：在上述基础上增加对手（随机断开重载线路），测试：24个周场景（2016步）。
- **L2RPN WCCI 2022**：IEEE-118标准电网（118个变电站，186条线路，动作空间 >70,000），包含可再生能源，训练数据32年约1.7GB。

### Benchmark与对比方法
三类基线：
1. **专家引导RL**：WCCI 2020冠军方案（基于SAC+层次策略）。
2. **纯LLM**：GPT-4o-0806, Qwen2-7B-Instruct（直接决策）。
3. **LLM引导RL**：修改版LLM4Teach（KL散度正则化，同阶段离线）。
- ACE有两个变体：ACE (Qwen2-7B+SFT)，ACE (GPT-4，无微调)。

## 4. 资源与算力

论文未明确说明GPU型号、数量等硬件细节。但在计算开销分析中（NeurIPS 2020）给出了训练时长：
- 专家引导RL（100K步）：6h 4m 14s
- ACE总训练（40K步）：6h 18m 3s
- 其中ACE-LLM推理（508次，264个样本）：1h 48m 0s
- ACE-LLM采样：59m 12s
- ACE-LLM微调（2次，200个样本）：26m 10s
- ACE-RL（40K步）：3h 4m 41s

粗估：总训练时间与基线RL相近（40K vs 100K步），LLM额外开销约3.2h。未提及GPU型号，推测为单卡或多卡（A100或类似）。

## 5. 实验数量与充分性

- **主要实验**：在3个L2RPN任务上比较ACE与基线的性能（表1），每个任务报告均值±标准差（5次运行）。
- **消融实验**：
  - 去除Actor (f_LLM)或Critic (g_LLM)（表2）
  - 去除bad-case推理或多轮推理（图4）
  - 超参数分析：f_LLM激活频率、坏阈值、SFT频次；g_LLM激活频率、轨迹选择标准、调整尺度K（表3）
- **额外分析**：计算开销分解（表4）、单步奖励 vs 回合性能（图5）、可视化案例（附录C）。
- 实验覆盖了不同规模（WCCI较小，NeurIPS中等，WCCI 2022大规模）和不同难度（有无对手、可再生能源），基线方法涵盖RL、LLM、LLM+RL三种范式。
- **充分性**：较为充分，消融和超参数分析较全面，但缺少对LLM微调数据量、推理模型其他架构（如更大模型）的对比。实验客观（多次运行、标准差报告）。

## 6. 主要结论与发现

1. **性能优势**：ACE在所有三个挑战中优于所有基线。在WCCI 2022上，ACE比专家引导RL提升约145%的回合奖励，同时维持实时响应（测试时间38.7s vs 纯LLM的数千秒）。
2. **样本效率**：仅需287~700次LLM修正即可显著加速RL收敛（对比传统100K~200K步训练）。
3. **模块必要性**：Actor和Critic均不可或缺；bad-case推理和多轮推理对性能贡献显著。
4. **LLM作为离线指导优于在线对齐**：LLM直接用于序贯决策效果差（长序列耦合），但离线修正轨迹效果更好；策略正则化（LLM4Teach）导致过度保守，不如选择性修正。
5. **微调效果**：多次SFT（3次）优于单次或无SFT，LLM性能可随RL数据联合提升。

## 7. 优点

- **创新性**：提出LLM在RL训练中扮演双角色（Actor+Critic）的离线修正范式，避免在线推理延迟，适合工业实时需求。
- **实用性**：在大规模电网（>60K动作空间）上验证，显著提升样本效率和最终性能，且测试时间与纯RL相当（38.7s），远优于纯LLM（>1000s）。
- **可解释性**：prompt设计清晰，bad-case推理、多轮推理等技巧直观有效。
- **消融深入**：超参数分析（阈值、频率、SFT次数等）提供了实用指导。
- **通用性**：框架不依赖于特定LLM（支持Qwen2-7B和GPT-4），微调用LoRA低资源。

## 8. 不足与局限

- **实验场景单一**：仅限电网调度（L2RPN），未在机器人、自动驾驶等其它大规模决策任务上验证，泛化性存疑。
- **评估指标有限**：主要报告回合奖励和存活率，缺乏对安全性、鲁棒性（如对抗扰动）的专门评估。
- **LLM开销**：虽然离线校正，但LLM推理和微调仍需额外计算（约3h），且LLM调用次数受限于模拟器速度（Grid2Op仿真瓶颈）。
- **超参数敏感性**：阈值r̄, K, 激活频率等需要调参，在实践中可能影响性能。
- **LLM能力依赖**：ACE性能受基础LLM推理能力限制（如Qwen2-7B在复杂场景下修正效果不如GPT-4），且微调数据集规模有限。
- **未考虑部署难题**：LLM修改需要环境仿真验证，若环境模型不可用或成本高则无法直接应用。

（完）
