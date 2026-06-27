---
title: "Divide and Conquer: Grounding LLMs as Efficient Decision-Making Agents via Offline Hierarchical Reinforcement Learning"
title_zh: 分而治之：通过离线分层强化学习将大语言模型化为高效决策智能体
authors: "Zican Hu, Wei Liu, Xiaoye Qu, Xiangyu Yue, Chunlin Chen, Zhi Wang, Yu Cheng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=pdNtji3ktF"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 通过离线分层强化学习将LLM化为决策智能体
tldr: 针对大语言模型在长期稀疏奖励决策任务中探索不足和信用分配困难，提出GLIDER框架。引入参数高效的分层结构，高层策略生成抽象计划指导低层控制器。在多个基准上显著提升了LLM的决策效率和成功率，验证了分层离线RL的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 742, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-pdntji3ktf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 476, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1680, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 825, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 1139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-pdntji3ktf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1229, \"height\": 606, \"label\": \"Table\"}]"
motivation: 大语言模型在长期决策任务中探索不足和信用分配困难。
method: 提出GLIDER框架，引入分层结构，高层策略生成抽象计划指导低层控制器。
result: 在稀疏奖励决策任务中显著提升了LLM的决策效率和成功率。
conclusion: 分层离线RL能有效增强LLM在决策任务中的性能。
---

## Abstract
While showing sophisticated reasoning abilities, large language models (LLMs) still struggle with long-horizon decision-making tasks due to deficient exploration and long-term credit assignment, especially in sparse-reward scenarios. Inspired by the divide-and-conquer principle, we propose an innovative framework **GLIDER** (**G**rounding **L**anguage Models as Eff**I**cient **D**ecision-Making Agents via Offline Hi**E**rarchical **R**einforcement Learning) that introduces a parameter-efficient and generally applicable hierarchy to LLM policies. We develop a scheme where the low-level controller is supervised with abstract, step-by-step plans that are learned and instructed by the high-level policy. This design decomposes complicated problems into a series of coherent chain-of-thought reasoning sub-tasks, providing flexible temporal abstraction to significantly enhance exploration and learning for long-horizon tasks. Furthermore, GLIDER facilitates fast online adaptation to non-stationary environments owing to the strong transferability of its task-agnostic low-level skills. Experiments on ScienceWorld and ALFWorld benchmarks show that GLIDER achieves consistent performance gains, along with enhanced generalization capabilities.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大语言模型（LLM）在长时域决策任务中面临两大挑战：**探索不足**（尤其是在稀疏奖励场景下）和**长程信用分配困难**。尽管LLM在推理方面表现优异，但在涉及多步交互、需要结构化探索的任务中，性能严重受限。
- **整体含义**：论文旨在通过**分而治之**的思路，引入层次化结构，将LLM策略分解为高层规划与低层执行两个层次，从而提升LLM在复杂决策任务中的**样本效率、探索能力与泛化能力**。该方法将复杂问题拆解为一系列连贯的链式推理子任务，实现灵活的时间抽象，显著增强了长时任务的学习效率，并支持从离线到在线的快速适应。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：基于分治原则，设计一个参数高效、普遍适用的离线分层强化学习框架（GLIDER），包含：
  - **高层策略（π_h）**：基于任务描述和当前观测，每c步生成一个抽象子目标（subtask），实现时间抽象。
  - **低层控制器（π_l）**：在给定子目标下，每个时间步生成原始动作，并接收高层提供的内在奖励（子任务是否完成）。
- **关键技术细节**：
  1. **层次化架构**：高层和底层共享同一个 frozen LLM backbone，通过不同的提示（prompt）区分层级，并采用LoRA进行参数高效微调。Critic由额外MLP层构建，实现token级actor（输出词序列）和sentence级critic（评估整句价值）。
  2. **训练流水线**：三阶段：
     - **SFT（行为克隆）**：使用专家示范数据训练基础agent，加入长度正则化鼓励简洁输出。
     - **ORL（离线强化学习）**：使用奖励标注的离线数据（含专家与中等质量轨迹，比例1:2）训练actor-critic。Critic：Q函数通过Bellman误差更新（L_Q），V函数使用非对称损失（L_τ2）保守估计；Actor：通过优势加权MLE（类似AWAC）优化策略（L_π），避免分布偏移。
     - **O2O（离线到在线适应）**：冻结低层技能（因内在奖励训练，具备跨任务泛化性），仅微调高层策略，实现快速在线适应。
  3. **数据构建**：高层数据集包含高层转移（d, o_t, g_t, R_t, o_{t+c}），其中R_t = Σr_{t:t+c-1}；低层数据集包含c步原始转移（g_t, o_t, a_t, r̂_t, o_{t+1}）。内在奖励r̂由观测自动判断子任务是否完成，无需人工设计。

- **算法流程**（文字说明）：
  1. SFT阶段：最小化BC损失（式3），同时最小化输出长度正则化项。
  2. ORL阶段：循环采样batch，先用TD学习更新critic（式4、5），再用优势加权策略梯度更新actor（式7），并软更新目标网络。
  3. O2O阶段（可选）：固定低层策略，用新收集的高层转移数据仅更新高层策略与critic。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - **ScienceWorld**：文本化科学实验环境，30个任务，10个类别，提供0-1的密集奖励。包含Text-Seen和Text-Unseen测试集。
  - **ALFWorld**：家庭环境操作任务，6类，稀疏二元奖励（成功得1，否则0），同样有seem和unseen测试集。
- **离线数据构建**：结合专家示范（作者用GPT-4分解为层次结构）和中等质量轨迹（两种采样策略：同分布采样和跨任务泛化采样），混合比例1:2。
- **对比方法**：
  - **基于提示**：ReAct、Reflexion、SwiftSage（不更新参数）。
  - **基于微调**：NAT（学习失败轨迹）、ETO（DPO优化）。
- **模型骨干**：Mistral-7B、Gemma-7B、Llama-3-8B。

## 4. 资源与算力

- **未明确说明**：论文中未提及使用的GPU型号、数量、训练时长等具体算力信息。仅提到采用LoRA进行参数高效微调，训练超参数包括batch size、学习率等，但未报告硬件资源。读者需自行估计或参考附录。

## 5. 实验数量与充分性

- **实验数量**：
  - **主实验**（表1）：5组baseline × 3个骨干 × 2个benchmark × 2个测试集（seen/unseen）= 60个结果点。
  - **消融实验**（图3）：6种配置（有无层次 × 3种训练阶段） × 3个骨干 = 18个结果。
  - **模型规模消融**（表2）：3个规模（Llama-1B/3B/8B）× 6种配置 = 18个结果。
  - **在线微调泛化**（图4）：3个新任务 × 3种方法 = 9条曲线。
  - **数据混合比影响**（图5）：9种比例 × 2种配置 = 18个结果点。
- **充分性与公平性**：
  - 实验设计全面，覆盖了不同骨干、不同规模、不同训练阶段、在线与离线、不同数据比例。
  - 对比方法包括主流提示方法和最新微调方法，基准广泛。
  - 消融实验清晰分离了层次结构、SFT、ORL各组件贡献。
  - 在线实验设计了三个不同领域（电、生物、热力学）的新任务，评估泛化能力。
  - 但对baseline的调优细节（如是否对所有方法进行了相同规模的超参搜索）未充分说明，可能影响公平性。且仅使用两种benchmark，领域覆盖有限。

## 6. 论文的主要结论与发现

- GLIDER在所有骨干和基准上**显著优于所有baseline**，在ScienceWorld unseen任务上最高提升30.59%（用Llama-3-8B）。
- **层次结构**和**多阶段训练（SFT+ORL）**共同贡献最大：消融实验显示，有层次且经过完整SFT+ORL的配置最优。
- **模型规模影响**：层次结构即使在较小模型（Llama-3B）上也表现优异，甚至超越无层次的大模型（如Mistral-7B），体现参数效率。
- **在线适应能力强**：GLIDER在零样本和快速在线微调中均优于传统AC和AWAC算法，归因于任务无关的低层技能具有强迁移性。
- **数据混合比**：专家数据与中等数据比例1:2时性能最佳，纯专家或纯中等数据均不如混合数据，说明RL能从次优数据中学习。

## 7. 优点：方法或实验设计上的亮点

1. **参数高效且通用**：高层与低层共享相同LLM backbone，仅用不同prompt区分，避免了传统分层RL中参数成倍增加的问题。
2. **无需人工设计子任务奖励**：内在奖励通过观测自动判断子任务是否完成，降低领域知识要求。
3. **三阶段流水线逻辑清晰**：SFT初始化 → ORL强化学 → O2O在线适应，逐步提升性能。
4. **强泛化能力**：低层技能基于内在奖励训练，可跨任务复用，支持快速在线适应。
5. **消融实验全面**：系统分析了层次结构、训练阶段、模型规模、数据比例等因素，验证了方法稳健性。
6. **开放代码**：提供GitHub仓库，可复现。

## 8. 不足与局限

1. **训练流程复杂**：三阶段（SFT、ORL、O2O）需要多次数据收集和调参，实际部署成本较高。
2. **领域覆盖有限**：仅在ScienceWorld和ALFWorld两个文本交互环境评估，未在更复杂的具身或现实任务中验证。
3. **数据依赖**：需要大量离线数据（包括专家和中等质量轨迹），且数据构建依赖GPT-4分解子任务，可能引入偏差。
4. **算力资源未报告**：无法评估方法的实际计算开销和可扩展性。
5. **基线调优细节不足**：未对baseline进行同等的超参数搜索或公平的微调步骤控制，可能不够严谨。
6. **未讨论失败案例**：未分析在哪些任务上GLIDER性能较差或存在局限性。

（完）
