---
title: "From Debate to Equilibrium: Belief‑Driven Multi‑Agent LLM Reasoning via Bayesian Nash Equilibrium"
title_zh: 从辩论到均衡：基于贝叶斯纳什均衡的信念驱动多智能体LLM推理
authors: "Xie Yi, Zhanke Zhou, Chentao Cao, Qiyu Niu, Tongliang Liu, Bo Han"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=RQwexjUCxm"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 多智能体LLM推理结合博弈论与强化学习
tldr: 针对多智能体LLM推理计算成本高且缺乏收敛保证的问题，本文将多LLM协调建模为不完全信息博弈，寻求贝叶斯纳什均衡，并引入层次化强化学习范式ECON，使每个智能体根据对其他智能体的信念独立选择最大化期望奖励的响应。实验证明该方法在保证收敛的同时显著降低了计算开销。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1731, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 884, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1036, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 964, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1381, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1384, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1381, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-rqwexjucxm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1494, \"height\": 937, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1631, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 2165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 2247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 687, \"height\": 1770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 689, \"height\": 1773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 686, \"height\": 1775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 689, \"height\": 1778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 686, \"height\": 1774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-rqwexjucxm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 688, \"height\": 1778, \"label\": \"Table\"}]"
motivation: 多智能体LLM推理计算成本高且缺乏收敛保证。
method: 将多LLM协调建模为不完全信息博弈，利用层次化RL求解贝叶斯纳什均衡。
result: 在多个推理任务上取得了与全连接通信方法相当甚至更优的性能，且计算成本更低。
conclusion: ECON为多智能体LLM推理提供了高效且可收敛的解决方案。
---

## Abstract
Multi-agent frameworks can substantially boost the reasoning power of large language models (LLMs), but they typically incur heavy computational costs and lack convergence guarantees. To overcome these challenges, we recast multi-LLM coordination as an incomplete-information game and seek a Bayesian Nash equilibrium (BNE), in which each agent optimally responds to its probabilistic beliefs about the strategies of others. We introduce Efficient Coordination via Nash Equilibrium (ECON), a hierarchical reinforcement-learning paradigm that marries distributed reasoning with centralized final output. Under ECON, each LLM independently selects responses that maximize its expected reward, conditioned on its beliefs about co-agents, without requiring costly inter-agent exchanges.
We mathematically prove that ECON attains a markedly tighter regret bound than non-equilibrium multi-agent schemes. Empirically, ECON outperforms existing multi-LLM approaches by 11.2% on average across six benchmarks spanning complex reasoning and planning tasks. Further experiments demonstrate ECON’s ability to flexibly incorporate additional models, confirming its scalability and paving the way toward larger, more powerful multi-LLM ensembles. The code is publicly available at: https://github.com/tmlr-group/ECON.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究背景
- **问题**：多智能体LLM框架（如多智能体辩论MAD）虽然能显著提升推理能力，但存在三大障碍：高昂的计算开销（大量token交换）、上下文窗口限制（多轮信息易超长）、缺乏收敛保证（协调协议不明，可能无预期效果）。
- **动机**：需要一种**原则性强、可扩展**的多智能体协调框架，既能保持协作推理优势，又能降低通信成本并保证收敛。

## 2. 方法论：ECON框架
### 核心思想
- 将多LLM协调建模为**不完全信息博弈**，目标是使全体智能体达到**贝叶斯纳什均衡（BNE）**——每个智能体基于对其他智能体策略的概率信念选择最优反应，无需直接交换消息。
- 采用**层次化强化学习**架构：多个执行LLM（Execution LLM）独立推理，一个协调器LLM（Coordinator LLM）输出最终结果，并通过信念网络和集中混合网络促进协调。

### 关键技术细节
- **形式化**：建模为**DEC-POMDP**（分散部分可观测马尔可夫决策过程），每个智能体维护局部历史，策略映射到动作分布。
- **信念网络（Belief Network）**：将智能体的局部轨迹和观测映射为信念状态，进而生成提示嵌入（temperature, repetition penalty），并输出本地Q值。
- **信念编码器（Belief Encoder）**：使用多头注意力聚合所有信念状态，生成组级表示。
- **集中混合网络（Centralized Mixing Network）**：结合组级表示和本地动作嵌入，产生全局Q值，优化全局目标，同时保证单调性（确保本地改进促进全局改进）。
- **奖励设计**：包含动作似然奖励、任务特定奖励和协作贡献奖励，动态调整权重。
- **早期停止机制**：基于最终输出稳定度、平均奖励阈值和损失收敛。

### 理论保证
- 证明BNE存在（基于Glicksberg不动点定理）。
- 遗憾界：ECON达到 **O(N√T/(1-γ))**（亚线性），而现有非均衡多智能体方法为**线性遗憾 O(δ_max T/(1-γ))**，表明ECON能高效学习近优策略。

## 3. 实验设计
### 数据集与场景
- 5个推理任务：**GSM8K、GSM-Hard、MATH、SVAMP、StrategyQA**（数学和常识推理）。
- 1个规划任务：**TravelPlanner**（复杂工具使用与约束满足）。
- 使用6个开源LLM（LLaMA3.1 8B/70B/405B, Mistral-7B, Mixtral-8x22B, Qwen1.5 110B）和GPT-4 Turbo。

### 对比方法
- 单智能体：零样本CoT、少样本CoT。
- 多轮/自一致性：Self-Consistency（64次采样）。
- 价值引导搜索：TS-LLM、PPO-MCTS。
- 多轮自改进：ToT、RAP、ReAct。
- 多LLM框架：rStar、多智能体辩论（MAD）。

## 4. 资源与算力
- **论文未明确说明**使用的GPU型号、数量及训练时长。仅给出了不同模型配置下的超参数（如学习率、批次大小等），但未透露硬件详细信息。
- 训练参数规模约为1.7M（8B/70B）到2.5M（405B）可学习参数，说明计算开销相对较低。

## 5. 实验充分性与公平性
- **实验数量充分**：包括主结果（图3）、每个数据集单独结果（附录E）、模型配置对比（表2）、可扩展性实验（图4-5）、消融研究（表5-6）、token效率对比（表3）、与完全信息变体对比（表4）。
- **客观性与公平性**：
  - 使用了多种规模的开源模型和闭源模型（GPT-4）。
  - 所有对比方法均在零样本或少样本设置下运行，ECON也使用零样本。
  - 消融研究验证了信念网络、混合网络、奖励组件等核心模块的必要性。
  - 异构模型实验表明性能略降，但作者客观分析了原因（达到BNE难度增加）。
- **潜在偏差**：主要在数学和规划任务上评估，未覆盖开放式推理或创意生成任务。此外，协调器LLM的输出长度限制（50 token软限制，70 token硬限制）可能影响策略质量。

## 6. 主要结论与发现
- **性能**：ECON在6个基准上平均超越现有多LLM方法**11.2%**，超越单智能体方法**10.9%**。
- **效率**：相比3轮MAD，token消耗平均减少**21.4%**。
- **扩展性**：从3个执行LLM增加到9个（配合多协调器），性能提升**18.1%**，验证了层次化全局-局部Nash协调的有效性。
- **收敛性**：通过奖励和损失监控，ECON能稳定到达BNE状态，遗憾界为亚线性，优于非均衡方法。

## 7. 优点
- **理论严谨**：首次将BNE引入多LLM协调，并给出存在性证明和亚线性遗憾界，为方法提供坚实保证。
- **通信节约**：用信念更新替代直接消息传递，大幅降低token开销，同时保持或提升推理质量。
- **可扩展架构**：层次化设计（局部协调器+全局协调器）使得增加LLM代价可控，实验验证了扩展性。
- **模块化设计**：信念网络、混合网络、动态奖励可独立优化或替换，便于集成更强模型或新任务。
- **消融充分**：全面验证了各组件贡献，包括是否包含信念编码器、不同奖励组合等，增强了结果可信度。

## 8. 不足与局限
- **硬件信息缺失**：未报告具体GPU型号、数量、训练时长，难以复现资源需求。
- **任务覆盖有限**：仅涉及数学推理和规划，未在更开放的问答、代码生成或创意任务上验证。
- **异构模型表现逊色**：混合不同规模和架构的LLM时性能低于同质组合，说明框架对异构协作仍需改进。
- **策略生成长度限制**：协调器策略被强制限制在70 token内，可能丢失复杂推理所需的细节。
- **仍需少量通信**：协调器必须聚合所有执行LLM的输出并下发策略，并非完全零通信；增加代理数时，协调器可能成为瓶颈。
- **未与最新基线对比**：论文截止于2025年，未包含此后可能出现的更强多智能体方法（如基于图推理或进化算法的框架）。
- **理论假设强度**：准凹性、连续性和紧凑策略空间等假设在实际LLM场景中可能不完全成立，需谨慎看待理论保证的严格适用性。

（完）
