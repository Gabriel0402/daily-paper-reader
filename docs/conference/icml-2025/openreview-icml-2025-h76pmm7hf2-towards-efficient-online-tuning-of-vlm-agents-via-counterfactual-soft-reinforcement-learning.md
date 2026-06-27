---
title: Towards Efficient Online Tuning of VLM Agents via Counterfactual Soft Reinforcement Learning
title_zh: 基于反事实软强化学习的VLM智能体高效在线调优
authors: "Lang Feng, Weihao Tan, Zhiyi Lyu, Longtao Zheng, Haiyang Xu, Ming Yan, Fei Huang, Bo An"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=H76PMm7hf2"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 使用反事实软强化学习在线调优VLM智能体
tldr: VLM智能体在线强化学习面临动作空间爆炸问题。本文提出反事实软强化学习（CoSo），通过反事实推理动态评估每个token的因果影响，从而指导高效探索。在多个动态环境任务中，CoSo显著提升了VLM智能体的在线学习效率，为VLM在多智能体场景下的部署提供了实用方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1664, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1711, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 833, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1592, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1592, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 894, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 543, \"height\": 83, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 293, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 294, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-h76pmm7hf2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 293, \"height\": 290, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 782, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 584, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1726, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1236, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-h76pmm7hf2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1560, \"height\": 275, \"label\": \"Table\"}]"
motivation: VLM智能体在线RL因文本动作空间过大而难以探索。
method: 提出CoSo，利用反事实推理评估token重要性以指导探索。
result: 在多个动态环境中显著提升在线调优效率。
conclusion: 反事实推理可有效解决VLM智能体在线RL的探索问题。
---

## Abstract
Online fine-tuning vision-language model (VLM) agents with reinforcement learning (RL) has shown promise for equipping agents with multi-step, goal-oriented capabilities in dynamic environments. However, their open-ended textual action space and non-end-to-end nature of action generation present significant challenges to effective online exploration in RL, e.g., explosion of the exploration space. We propose a novel online fine-tuning method, Counterfactual Soft Reinforcement Learning (CoSo), better suited to the textual output space of VLM agents. Compared to prior methods that assign uniform uncertainty to all tokens, CoSo leverages counterfactual reasoning to dynamically assess the causal influence of individual tokens on post-processed actions. By prioritizing the exploration of action-critical tokens while reducing the impact of semantically redundant or low-impact tokens, CoSo enables a more targeted and efficient online rollout process. We provide theoretical analysis proving CoSo's convergence and policy improvement guarantees, and extensive empirical evaluations supporting CoSo's effectiveness. Our results across a diverse set of agent tasks, including Android device control, card gaming, and embodied AI, highlight its remarkable ability to enhance exploration efficiency and deliver consistent performance gains. The code is available at https://github.com/langfengQ/CoSo.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：视觉语言模型（VLM）智能体被广泛用于动态环境中的多步决策任务（如移动设备控制、游戏、具身AI）。使用强化学习（RL）对VLM进行在线微调能够提升其多步、目标导向的能力，具有很大潜力。
- **核心问题**：VLM智能体的文本动作空间是开放式的（非端到端），生成的文本（包括思维链、行动）需经解析函数转换为可执行动作。这导致RL在线探索面临两大挑战：一是文本采样空间随词汇量和序列长度呈指数级增长（例如词汇量32,100、长度100时空间达32,100^100）；二是许多token（如固定格式或语义冗余部分）对最终动作几乎无影响，均匀探索这些token效率极低。传统RL方法将所有token视为同等重要，造成大量无效探索。
- **整体含义**：提出一种更高效的在线调优方法，通过识别并优先探索对动作至关重要的token，大幅降低探索空间，提升学习效率。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- **因果加权探索**：利用反事实推理评估每个生成token对最终解析动作的因果影响力（causal weight），然后基于这些权重对策略熵进行加权，使RL在探索时更关注高影响token，减少对低影响token的扰动。
- **公式化**：将传统软RL目标中的熵项 `H(π(·|s))` 替换为因果加权熵 `H_B(π(·|s)) = Σ_i B_i^{y→a} · H(y_i|y_{1:i-1})`，其中 `B_i^{y→a}` 是token y_i 的因果权重。

### 关键技术细节
- **结构因果模型（SCM）**：假设 token 与动作的关系可由 SCM `a = f_SCM(y, ε)` 描述，其中 ε 是外生噪声。
- **反事实推理计算因果权重**：对于每个 token y_i，构造反事实序列（将 y_i 替换为 null 值），比较原动作概率与反事实动作概率之差：
  `B_i^{y→a} = P(a|y, ε) - P(a|y_{-i} ∪ y_i^{null}, ε)`
  实践中使用轻量级 BERT 网络（0.01B 参数）作为 SCM 来近似 `P(a|y, ε)`。
- **因果加权软RL目标**：
  `max_π Σ_t E_{(s_t,a_t)~ρ_π}[γ^t (r(s_t,a_t) + α H_B(π(·|s_t)))]`
- **理论保证**：提供了策略评估、策略改进和策略迭代的收敛性证明（Lemma 4.2, 4.3, Proposition 4.4），证明因果加权熵能保持标准软RL的稳定性和收敛性。

### 算法流程（两阶段）
- **离线阶段**：先用 SFT 在任务数据上初始化 VLM，使其掌握基本输出格式和有效 utterance。
- **在线阶段**（Algorithm 1）：
  1. **Rollout**：VLM 与环境交互，采样数据（状态、动作、奖励、utterance）。
  2. **反事实推理**：为每个 token 生成 nullified 序列，通过 SCM 计算因果权重 `B_y→a`，进而计算因果加权熵 `H_B`。
  3. **模型更新**：用交叉熵损失更新 SCM（分类目标），并用 CoSo 目标更新 VLM 策略（可适配 AWR 或 PPO）。
- **灵活性**：CoSo 的目标是一般化的，可集成到现有 RL 算法中（如 DigiRL 的 AWR 和 RL4VLM 的 PPO）。

## 3. 实验设计：数据集/场景、基准、对比方法

### 场景与数据集
- **Android-in-the-Wild (AitW)**：移动控制任务，含 **General**（545 个训练任务，96 个测试任务）和 **WebShopping**（438 个训练任务，96 个测试任务）。动作空间包括 DUAL_POINT, TYPE, HOME, BACK, ENTER 等。
- **Gym Cards**：纸牌推理环境，含 **NumberLine**、**EZPoints**、**Points24**、**Blackjack** 四个任务，需要数字识别与算术操作。
- **ALFWorld**：具身AI环境，含 **Pick&Place**, **ExamineInLight**, **Clean&Place**, **Heat&Place**, **Cool&Place**, **PickTwo&Place** 六种子任务（共4639个游戏）。

### 基准方法
- **Prompting 方法**：Gemini 1.5 Pro、GPT-4V、AppAgent + Gemini/GPT-4V。
- **学习 / 微调方法**：CogAgent、AutoUI + SFT、Online Filtered BC、DigiRL（AWR-based）、CNN + RL、LLaVA-1.6 + SFT、RL4VLM（PPO-based）。
- **CoSo 变体**：基于 DigiRL 实现（移动设备控制）和基于 RL4VLM 实现（卡片游戏、具身AI）。

### 对比设置
- 主要实验报告了平均成功率（3个随机种子平均）。
- 消融实验：在 WebShopping 和 NumberLine 上对比标准 RL、RL + 均匀熵、CoSo（RL + 因果加权熵）。
- 探索效率分析：通过可视化因果权重分布和重复动作采样比较不同方法的探索行为。
- 额外实验：附录C中在 AlfredTWEnv（纯文本环境）上用 LLM 智能体验证了 CoSo 的扩展性。

## 4. 资源与算力

- **论文中明确提及**：计算预算在附录D中给出。
- **硬件**：所有实验在 **NVIDIA H100 GPU** 上完成。
- **模型规模**：VLM 参数量 7.96B（如 LLaVA-1.6），SCM 参数量 0.01B（BERT-based），总计 7.97B。
- **GPU内存**：VLM 37.0 GB，SCM 0.7 GB，总计 37.7 GB。
- **训练时间**（单次实验，NumberLine 示例）：
  - RL 基线：13.9 H100 GPU 小时
  - RL + 均匀熵：14.0 小时
  - CoSo：14.5 小时（rollout 10.4h，update 3.6h，HB 因果权重计算 0.5h）
- **总结**：CoSo 仅引入约 0.5 小时的额外开销，参数和内存增加极小（<2%），计算成本可控。

## 5. 实验数量与充分性

- **实验数量**：
  - 三大场景共 3 个独立实验（AitW, Gym Cards, ALFWorld），每个场景含多个子任务，共约 13 个任务变体。
  - 消融实验 1 组（2 个任务，对比 3 种方法）。
  - 额外 LLM agent 实验 1 组（AlfredTWEnv, 2 种方法）。
  - 探索效率可视化与分析（因果权重分布、重复采样对比）。
- **重复性与统计**：所有主要结果平均 3 个随机种子，并报告标准差（如 AitW 表格中 `±` 值）。
- **公平性**：与多种 SOTA 方法对比，包括 prompting 和学习方法；在相同基础模型上比较 RL 变体；消融实验控制变量；附录展示了实验超参数一致性。
- **结论**：实验覆盖了多种动态环境，任务类型丰富（移动控制、数值推理、具身交互），对比充分，结果具有可信度。

## 6. 主要结论与发现

1. **性能提升显著**：CoSo 在三个场景中均优于所有基线：
   - AitW：平均成功率 72.9%，比 DigiRL (64.9%) 提升 12.3%。
   - Gym Cards：平均成功率 49.3%，比 RL4VLM (45.1%) 提升 9.3%。
   - ALFWorld：平均成功率 26.5%，比 RL4VLM (22.7%) 提升 16.7%。
2. **探索效率更高**：因果权重可视化显示，仅不到10%的 token 具有高影响力（>0.8），超过80%的 token 权重低于0.2。CoSo 通过聚焦高权重 token，在重复采样中能更快速地生成正确恢复动作（如“Home”），而均匀熵容易产生格式错误或无效输出。
3. **因果加权熵优于均匀熵**：消融实验证明，RL + 均匀熵仅带来微小改进，而因果加权熵（CoSo）显著加速收敛并提升最终成功率。
4. **理论支持**：收敛性和策略改进保证确保了算法的稳定性。

## 7. 优点

- **方法创新**：将反事实推理引入 VLM 智能体的 RL 探索，有效解决文本动作空间爆炸问题，思路新颖且有理论支撑。
- **通用性强**：CoSo 的目标是一般化的最大熵形式，可以灵活适配多种 RL 算法（如 AWR、PPO），易于集成进现有框架。
- **实验充分且严谨**：覆盖三大类任务，对比多种基线（包括闭源模型和最新 SOTA RL 方法），消融实验清晰，可视化直观，随机种子重复保证统计可靠性。
- **计算开销小**：SCM 仅 0.01B 参数，引入的额外训练时间不足 4%，内存消耗增加 <2%，实用性强。
- **理论分析完整**：证明了策略评估、改进和迭代的收敛性，为方法稳定性提供了保证。

## 8. 不足与局限

- **序列长度限制**：实验中最长 utterance 少于 300 个 token，超长思维链（CoT）场景未被验证，可能因 token 数量激增导致因果权重计算成本上升或失效。
- **依赖解析函数**：因果权重的计算基于确定性解析函数 `f_parse`，若解析函数复杂或非确定性，可能影响反事实推理的准确性。
- **SCM 近似误差**：SCM 是轻量级 BERT 模型，其对 `P(a|y)` 的近似可能不完美，尤其是在动作空间复杂或 token 与动作关系模糊时，可能导致权重估计偏差。
- **未探讨分层推理**：对于超长输出，论文指出未来可通过分层推理扩展 CoSo，但当前未提出具体方案。
- **实验环境多样性**：虽然覆盖了三个场景，但均为模拟或虚拟环境，真实世界应用（如物理机器人、自动驾驶）尚未测试。
- **基线覆盖**：部分基线（如 Gemini、GPT-4V）的结果可能受限于报告自原始论文，未在同一实验条件下完全复现，存在对比误差风险（但论文注明来源，并尽量保持一致超参数）。

（完）
