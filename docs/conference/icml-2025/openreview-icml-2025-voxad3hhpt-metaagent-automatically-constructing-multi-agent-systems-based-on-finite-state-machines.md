---
title: "MetaAgent: Automatically Constructing Multi-Agent Systems Based on Finite State Machines"
title_zh: MetaAgent：基于有限状态机自动构建多智能体系统
authors: "Yaolun Zhang, Xiaogeng Liu, Chaowei Xiao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vOxaD3hhPt"
tags: ["query:vlm-rl"]
score: 4.0
evidence: 基于大语言模型的多智能体系统构建
tldr: 本文针对现有手动设计多智能体框架场景有限、自动化设计缺乏工具集成等问题，提出MetaAgent，基于有限状态机和LLM自动生成多智能体系统。给定任务描述后，系统通过优化算法自动设计并迭代完善。实验表明该方法能灵活适应多种任务，并有效集成工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1743, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1702, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1813, \"height\": 2157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1821, \"height\": 1895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1820, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1828, \"height\": 1394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-voxad3hhpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1810, \"height\": 889, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1555, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 757, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1606, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 808, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1020, \"height\": 941, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 586, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-voxad3hhpt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 409, \"height\": 205, \"label\": \"Table\"}]"
motivation: 现有手动设计的多智能体框架场景有限，自动化方法缺乏灵活性和工具集成。
method: 提出基于有限状态机的框架，利用大语言模型自动生成并优化多智能体系统。
result: 在多种任务上验证了自动构建系统的有效性和灵活性。
conclusion: 有限状态机与LLM结合可实现灵活的多智能体系统自动构建。
---

## Abstract
Large Language Models (LLMs) have demonstrated the ability to solve a wide range of practical tasks within multi-agent systems. However, existing human-designed multi-agent frameworks are typically limited to a small set of pre-defined scenarios, while current automated design methods suffer from several limitations, such as the lack of tool integration, dependence on external training data, and rigid communication structures. In this paper, we propose \textbf{MetaAgent}, a  \textbf{finite state machine} based framework that can automatically generate a multi-agent system. Given a task description, MetaAgent will design a multi-agent system and polish it through an optimization algorithm. When the multi-agent system is deployed, the finite state machine will control the agent's actions and the state transitions. To evaluate our framework, we conduct experiments on both text-based tasks and practical tasks. The results indicate that the generated multi-agent system surpasses other auto-designed methods and can achieve a comparable performance with the human-designed multi-agent system, which is optimized for those specific tasks.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）在多智能体系统中展现出解决实际任务的能力，但现有系统存在两大局限：一是手动设计的框架（如 MetaGPT）通常只适用于少数预设场景，泛化性差且需要大量人工迭代；二是已有的自动化设计方法（如 SPP、AutoAgents、EvoAgent、ADAS、Symbolic-Learning）存在工具集成缺失、依赖外部训练数据、通信结构僵化（线性、无回溯能力）等缺陷。
- **整体含义**：论文旨在提出一种**通用、自动、无需外部数据**的多智能体系统构建方法，利用有限状态机（FSM）作为组织框架，使系统能够灵活地处理各类复杂任务，并具备工具使用、状态回退和自优化能力。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将多智能体系统的组织结构建模为**有限状态机（FSM）**，每个状态对应一个任务求解子环节，包含一个任务求解 Agent、条件验证器（Condition Verifier）、状态指令以及监听器（Listener）。LLM 作为“设计师”根据任务描述自动生成 Agent 集合、状态集合和状态转移条件，再通过优化算法合并冗余状态，最后部署执行。
- **关键技术细节**：
  - **Agent 设计**：设计师 LLM 先生成任务分析、系统目标，然后定义最少且必要的 Agent，包括名称、系统提示、分配的工具（如代码解释器、搜索引擎）。
  - **状态与转移条件设计**：每个状态指定执行指令、分配 Agent、条件验证器（检查输出是否满足自然语言转移条件）、监听器（接收当前状态输出的 Agent）；转移条件允许向前、回溯或空转移（Null-Transition，即反馈后重试当前状态）。
  - **优化算法**：遍历所有状态对，利用 LLM 判断是否可合并（依据角色区分度、信息传递必要性、工具重叠性），迭代合并冗余状态，降低系统复杂度。
  - **部署流程**：从初始状态开始，Agent 执行指令，条件验证器判断输出，若满足条件则转移到目标状态（可能回溯到之前状态），并保存输出到监听器；若不满足条件则执行空转移，最多允许 M 次重试。
- **公式/算法**：论文给出了 FSM 的形式化定义 M = (Σ, S, s₀, F, δ)，并提供了优化算法（Algorithm 1）和部署算法（Algorithm 2）的伪代码描述（文字说明即可）。

## 3. 实验设计

- **数据集/场景**：
  - **文本任务**：Trivial Creative Writing（100个任务，每个含多个问题，故事需覆盖所有答案）和 GPQA(Diamond)（198个研究生级科学多选题）。
  - **实际任务**：Machine Learning Bench（ML Bench，5个数据集：Titanic, House Prices, SCTP, ICR, SVPC）和软件开发任务（5个：2048游戏、贪吃蛇、打砖块、Excel应用、天气应用）。
- **基准对比方法**：
  - 文本任务：Direct, CoT, CoT-SC, llm-debate, Self-Refine, SPP。
  - ML Bench：AutoGen, OpenInterpreter, TaskWeaver, MetaGPT, DataInterpreter, SPP, AutoAgents。
  - 软件开发：MetaGPT, AutoAgents, SPP。
- **评估指标**：
  - 文本任务：成功率（Trivial Creative Writing 为问题答案覆盖率，GPQA 为正确率）。
  - ML Bench：归一化性能得分（NPS）。
  - 软件开发：客观检查点通过率（每个软件4个检查点，如界面可打开、操作正常等）。

## 4. 资源与算力

- **未明确说明**：论文未提及具体使用的 GPU 型号、数量或训练时长。基础模型采用 GPT-4o（温度设为 0），仅提及 token 成本分析（设计阶段+部署阶段的总 token 消耗），并未对计算资源做量化描述。

## 5. 实验数量与充分性

- **实验数量**：共计超过 8 组主要对比实验 + 消融实验：
  - 文本任务：2 个数据集，7 种基线方法对比。
  - ML Bench：5 个数据集，对比 7 种基线方法。
  - 软件开发：5 个任务，对比 3 种基线方法。
  - 消融实验：工具使用、优化、回溯（每个消融均在文本任务和实际任务中测试，共 4 组×3 项 = 12 项结果）。
  - 基础模型质量分析：不同设计师/执行器组合（GPT-4o vs GPT-3.5-Turbo）在 ML Bench 上的测试。
- **充分性与公平性**：实验覆盖了文本、机器学习、软件开发三种不同类型任务，对比了多种手动和自动设计方法，并进行了充分的消融分析。所有实验均采用 GPT-4o 作为基础模型（温度=0）以保证可复现性；消融实验设计了等价的对照组；公平性较好。但未在更多真实工业场景（如大规模数据处理、多模态任务）中验证，泛化边界需进一步探索。

## 6. 主要结论与发现

- 自动生成的 FSM 多智能体系统在文本任务上超越所有对比方法（写作任务 0.86、GPQA 0.60），在 ML Bench 上平均 NPS 为 0.83，仅次于任务专用系统 DataInterpreter（0.86），在软件开发任务上平均通过率 0.85，显著高于 MetaGPT（0.35）和其他自动方法。
- 工具使用（代码解释器、搜索引擎）能显著提升信息获取与任务执行能力，在写作和 GPQA 上分别提升 8.1% 和 13.3%。
- 回溯机制（空转移和状态回溯）能有效处理错误和漏洞，尤其在软件开发任务中，去掉回溯后性能下降 58.8%。
- 优化算法可减少冗余状态，提升系统鲁棒性，在 ML Bench 和软件开发上性能分别下降 26.5% 和 35.3% 当移除优化后。
- 执行器质量比设计师质量对系统性能影响更大（GPT-4o 执行器比 GPT-3.5-Turbo 执行器高 47 分），说明基础模型的能力是关键瓶颈。

## 7. 优点

- **自动化程度高**：只需任务描述即可自动生成完整多智能体系统，无需人工设计代码或外部训练数据。
- **灵活性与鲁棒性**：FSM 支持空转移、状态回溯，能处理复杂流程中的错误和迭代；合并冗余状态的优化算法增强了系统稳定性。
- **工具集成**：支持代码解释器和搜索引擎，提升实际任务中的信息获取和代码执行能力。
- **通用性**：在文本、机器学习、软件开发等多类任务上均取得优异或可比性能。
- **成本较低**：相比手动设计或 case 级自动设计（如 AutoAgents），token 消耗更低（总成本约 4.7 万 tokens 用于 5 个 ML 任务）。

## 8. 不足与局限

- **算力资源未公开**：未说明 GPU 型号、数量及训练时长，可复现性需要更多硬件细节。
- **实验覆盖有限**：仅测试了 GPT-4o 和 GPT-3.5-Turbo 作为基础模型，未探究其他 LLM（如 Claude、Llama）的效果；任务类型未涵盖多模态、对话、实时交互等场景。
- **状态数限制**：优化后状态数仍然较少（ML Bench 从 5 个优化到 3 个），在极复杂任务中可能仍需人工干预或更多状态设计。
- **对 LLM 质量高度依赖**：执行器模型质量下降会严重影响性能，若使用低成本模型可能无法复现结果。
- **缺乏与最新自动化方法的对比**：未与 ADAS、Symbolic-Learning 等近期方法在相同任务上直接比较（仅在特性表格中提及），且这些方法需外部数据，公平性需进一步分析。
- **评估指标主观性风险**：软件开发任务采用人工检查点，尽管列出了具体标准，但可能存在评估人员的主观差异（论文未说明评估人员数量及一致性检验）。

（完）
