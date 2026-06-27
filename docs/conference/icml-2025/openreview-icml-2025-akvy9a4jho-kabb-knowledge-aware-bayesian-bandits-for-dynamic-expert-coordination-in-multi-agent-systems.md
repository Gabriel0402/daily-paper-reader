---
title: "KABB: Knowledge-Aware Bayesian Bandits for Dynamic Expert Coordination in Multi-Agent Systems"
title_zh: KABB：面向多智能体系统动态专家协调的知识感知贝叶斯强盗
authors: "Jusheng Zhang, Zimeng Huang, Yijia Fan, Ningyuan Liu, Mingyan Li, Zhuojie Yang, Jiawei Yao, Jian Wang, Keze Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AKvy9a4jho"
tags: ["query:gt-mai"]
score: 7.0
evidence: 提出知识感知贝叶斯强盗框架用于多智能体系统中的动态专家协调，直接针对多智能体协调问题，与博弈论决策相关。
tldr: 该工作针对多智能体系统中静态知识假设和协调效率低下的问题，提出知识感知贝叶斯强盗（KABB）框架。框架包含定制知识距离模型、双重适应机制和知识感知汤普森采样，实现高效的专家动态协调。实验表明KABB在保持高性能的同时达到最优成本-性能平衡。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 786, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 978, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-akvy9a4jho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 727, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1764, \"height\": 955, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1531, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1532, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 610, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 725, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1279, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 1813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1782, \"height\": 2086, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1783, \"height\": 1694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-akvy9a4jho/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1785, \"height\": 1796, \"label\": \"Table\"}]"
motivation: 多智能体系统面临静态知识假设和协调效率问题，现有方法难以平衡成本与性能。
method: 引入知识距离模型和双重适应机制，结合知识感知汤普森采样选择最优专家。
result: 在多个多智能体协调任务上实现最优成本-性能平衡，性能优于基线。
conclusion: KABB提供了一种可扩展的多智能体协调方案，具有语义理解和动态适应能力。
---

## Abstract
As scaling large language models faces prohibitive costs, multi-agent systems emerge as a promising alternative, though challenged by static knowledge assumptions and coordination inefficiencies. We introduce Knowledge-Aware Bayesian Bandits (KABB), a novel framework that enhances multi-agent system coordination through semantic understanding and dynamic adaptation. The framework features three key innovations: a customized knowledge distance model for deep semantic understanding, a dual-adaptation mechanism for continuous expert optimization, and a knowledge-aware Thompson Sampling strategy for efficient expert selection. Extensive evaluation demonstrates KABB achieves an optimal cost-performance balance, maintaining high performance while keeping computational demands relatively low in multi-agent coordination.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：大型语言模型（LLM）在复杂任务中表现出色，但进一步扩展模型规模成本高昂。多智能体系统（MAS）通过协调多个专用智能体，提供了一种成本效益更高的替代方案。然而，现有MAS框架（如Mixture-of-Agents MoA、Mixture-of-Experts MoE）存在静态知识假设和协调效率低下的问题：它们无法动态适应专家能力的变化或新概念的出现，且存在冗余和噪声。
- **核心问题**：如何在多智能体系统中实现动态、语义感知的专家协调，以平衡性能与计算成本。
- **整体含义**：本文提出知识感知贝叶斯强盗（KABB）框架，通过结合知识图谱和贝叶斯强盗算法，实现专家选择的动态优化和语义理解，为可扩展、自适应的MAS协调提供了新范式。

## 2. 方法论：核心思想、技术细节与算法流程

### 2.1 核心思想
- 将专家能力与任务需求表示为知识图谱中的向量，通过**知识距离度量**评估专家团队与任务的匹配度。
- 利用**双重适应机制**（Bayesian参数更新与知识图谱演化）持续优化专家能力表征。
- 采用**知识感知Thompson采样**（Knowledge-Aware TS）动态选择最优专家子集，平衡探索与利用。

### 2.2 关键技术细节
1. **知识距离模型**（公式4）：
   - 整合五个维度：任务难度缩放、语义不匹配（Jaccard相似度）、依赖复杂度、历史有效性、团队协同性（Synergy）。
   - 定义：`Dist(S,t) = log(1+d_t) * [ω₁(1-ρ_overlap) + ω₂|R_dep|/K + ω₃(1-Ḣ_S) + ω₄(1-Synergy(S))]`，权重ω经深度学习优化。
   - 该度量满足伪度量性质（非负性、条件对称性、近似三角不等式）。

2. **双重适应机制**：
   - 动态Beta分布参数更新：`α^{(t+1)} = γ^{Δt}α^{(t)} + r + δ·KM(S,t)`，其中γ为指数时间衰减因子，δ为知识匹配奖励强度。
   - 综合置信函数`θ̃^{(t)}_S`（公式6）融合历史期望、知识距离惩罚、时间衰减和协同增益。

3. **知识感知Thompson采样**：
   - 从Beta分布中采样，并乘以知识距离衰减和协同增益，选择期望最高的专家子集。
   - 收敛性证明（定理3.3）：累计遗憾满足`R(T) ≤ εT + O(√T log T)`。

### 2.3 算法流程
1. **任务接收与概念提取**：解析用户输入为概念需求向量d_t。
2. **专家能力映射**：每个LLM被表示为能力向量v_e，形成专家集合E。
3. **专家子集选择**：通过知识感知Thompson采样选择最优子集S_t，各专家独立处理任务。
4. **响应聚合**：利用知识图谱引导的融合过程（语义冲突检测、加权融合）生成最终输出。
5. **反馈更新**：收集成功/失败信号，更新Beta分布参数和知识图谱。

## 3. 实验设计

### 3.1 使用的数据集/基准
- **AlpacaEval 2.0**：805条指令，GPT-4评估偏好，主要指标为长度控制（LC）胜率。
- **MT-Bench**：多轮对话评估。
- **FLASK-Hard**：89个最困难实例，12个技能维度细粒度评估。
- 附加推理任务：**BBH**（Big-Bench Hard）、**MATH**、**Arena-Hard**（见附录D）。

### 3.2 对比方法
- **基线模型**：Qwen2-72B-Instruct、LLaMa-3-70B-Instruct、WizardLM-2-8x22B、Gemma-2-27B、Deepseek-V3、Deepseek-R1，以及GPT-4系列。
- **框架对比**：MoA（相同6个提议者+1个聚合器），以及KABB的消融变体（KABB w/o Deepseek、KABB-Single-LLaMa3）。
- **路由策略对比**：Classifier-based (CL) 路由、PPO、MCTS、A2C。

### 3.3 默认配置
- 6个开源模型，12个知识概念，24个专家（模型均匀分配），动态路由至top-3专家（来自top-2概念），聚合器为Qwen2-72B-Instruct。

## 4. 资源与算力

- **文中明确说明**：所有实验在单张 NVIDIA GeForce RTX 3090 服务器上进行（附录F）。
- 未提供具体训练时长或GPU数量细节，仅提及推理通过Together API进行。

## 5. 实验数量与充分性

### 实验数量
- **主要基准**：AlpacaEval 2.0、MT-Bench、FLASK-Hard（3组）。
- **推理任务附加**：BBH、MATH、Arena-Hard（3组，见附录D）。
- **消融实验**：
  - 路由策略对比（KA vs CL vs PPO vs MCTS vs A2C），使用RAS和PWRS指标。
  - 参数敏感性分析（知识距离阈值、时间衰减因子）（附录B.2）。
  - 专家数量/概念数量影响（附录C，多种组合）。
  - 案例分析（附录E，展示高质量/低质量输出及错误分析）。

### 充分性评价
- **充分**：覆盖了主流对齐基准和推理任务，对比了多种单模型和集成方法，消融实验系统且公平（控制变量，同等配置对比）。
- **客观性**：采用公开基准和标准化评估协议（如AlpacaEval 2.0的LC胜率以消除长度偏差），并报告了人类评估的一致性（Fleiss κ=0.78）。
- **局限性**：部分消融（如参数敏感性）仅在BBH子集上进行，未在所有基准重复；案例分析仅展示个别样本，缺乏系统性统计。

## 6. 主要结论与发现

- **性能**：KABB在AlpacaEval 2.0上达到77.9% LC胜率，比MoA（68.1%）提升9.8%；在MT-Bench上平均9.65，优于所有非Deepseek模型；在FLASK-Hard上三分之二类别超越MoA和GPT-4。
- **成本效益**：KABB处于Pareto前沿，能以更低成本达到或超越GPT-4系列的性能；例如，仅用2个专家即可达到优于MoA（6个提议者）的结果。
- **路由机制**：知识感知（KA）路由配合MAB显著优于基于分类器的路由以及其他优化算法（PPO/MCTS/A2C）。
- **适应性**：双重适应机制有效应对专家能力的动态变化，且知识图谱的引入降低了探索复杂性（理论证明）。

## 7. 优点

1. **创新性**：将知识图谱与贝叶斯强盗有机结合，解决了传统MAB忽视语义关系的问题。
2. **可解释性**：知识距离度量、图形导引聚合、双重适应机制均提供透明的决策路径。
3. **成本-性能平衡**：动态路由能根据任务难度和专家适配度调整资源使用，实际部署经济高效。
4. **理论支撑**：提供了伪度量性质、收敛性、信息增益等严格数学证明。
5. **实验全面**：覆盖多个主流基准、多种消融设置，并引入自定义评估指标（RAS、PWRS）。

## 8. 不足与局限

1. **输出简洁性不足**：在FLASK-Hard的“简洁性”维度上得分较低，KABB倾向于生成更详细输出，可能不适用于需要精炼回答的场景。
2. **初始专家选择敏感**：案例分析显示，若初始选中不恰当的专家（如对“仙人掌土壤”问题选择了人文学者），会降低性能，尽管可通过增加专家数量部分缓解。
3. **推理任务上优势有限**：在Arena-Hard上KABB（74.8%）不如GPT-4系列（79%-82%），而MoA与之接近（74.3%），表明在闭合推理问题上多智能体可能引入噪音。
4. **计算资源未完全透明**：虽然提及单卡RTX 3090，但未报告总训练/推理时长，且需依赖外部API（Together），复现成本未知。
5. **知识图谱构建依赖人工定义**：12个概念和24个专家划分需要领域知识，自动生成方式未探讨。
6. **跨领域泛化性未验证**：实验主要集中于通用对话和推理，未涉及小众专业领域（如医学、法律）。

---

（完）
