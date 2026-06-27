---
title: Multi-agent Architecture Search via Agentic Supernet
title_zh: 通过智能体超网络进行多智能体架构搜索
authors: "Guibin Zhang, Luyang Niu, Junfeng Fang, Kun Wang, LEI BAI, Xiang Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=imcyVlzpXh"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 基于大语言模型的多智能体架构搜索
tldr: 构建大模型驱动的多智能体系统通常需要人工设计。本文提出MaAS框架，放弃静态单一架构，转而优化概率性智能体超网络，根据查询难度和领域动态分配推理资源。实验证明该方法在多个任务上提升效率与性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1741, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 833, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 838, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1739, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 1256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 674, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 1066, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imcyvlzpxh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 680, \"height\": 565, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 796, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1818, \"height\": 979, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 969, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1207, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-imcyvlzpxh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1205, \"height\": 233, \"label\": \"Table\"}]"
motivation: 人工设计多智能体系统成本高，且静态架构无法根据查询动态分配资源。
method: 提出MaAS框架，优化概率性和连续分布的智能体架构超网络，实现动态推理资源分配。
result: 在多个任务上，MaAS提升了多智能体系统的效率和性能。
conclusion: 概率性超网络可自动化设计高效的多智能体架构。
---

## Abstract
Large Language Model (LLM)-empowered multi-agent systems extend the cognitive boundaries of individual agents through disciplined collaboration and interaction, while constructing these systems often requires labor-intensive manual designs. Despite the availability of methods to automate the design of agentic workflows, they typically seek to identify a static, complex, one-size-fits-all system, which, however, fails to dynamically allocate inference resources based on the difficulty and domain of each query. To address this challenge, we shift away from the pursuit of a monolithic agentic system, instead optimizing the \textbf{agentic supernet}, a probabilistic and continuous distribution of agentic architectures. We introduce \textbf{MaAS}, an automated framework that samples query-dependent agentic systems from the supernet, delivering high-quality solutions and tailored resource allocation (\textit{e.g.}, LLM calls, tool calls, token cost). Comprehensive evaluation across six benchmarks demonstrates that MaAS \textbf{(I)} requires only $6\\sim45\\%$ of the inference costs of existing handcrafted or automated multi-agent systems, \textbf{(II)} surpasses them by $0.54\\%\sim11.82\\%$, and \textbf{(III)} enjoys superior cross-dataset and cross-LLM-backbone transferability.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与研究动机

- **背景**：大语言模型（LLM）驱动的多智能体系统通过智能体协作超越单智能体能力，但现有系统通常需要人工设计，或采用静态、复杂的“一刀切”工作流，无法根据查询难度和领域动态分配推理资源（如LLM调用次数、工具调用、token成本）。
- **核心问题**：现有自动设计方法（如AFlow、GPTSwarm、AgentSquare）只搜索一个固定的最优多智能体架构，导致资源浪费（对简单问题使用复杂系统）且跨任务泛化性差（不同领域需要不同架构）。
- **解决思路**：放弃搜索单一静态系统，转而优化一个**概率性、连续分布的智能体架构超网络**（Agentic Supernet），针对每个查询采样定制化的多智能体系统。

## 2. 方法论：MaAS框架

- **核心思想**：构建一个级联多层的**智能体超网络**，包含多个可选的**智能体算子**（如CoT、多智能体辩论、ReAct、自修正等）以及每层的参数化概率分布。训练时，一个**控制器网络**根据输入查询条件概率地采样一个子架构（多智能体系统），并根据环境反馈联合更新分布参数和算子本身。
- **关键技术细节**：
  - **搜索空间定义**：每个算子定义为复合LLM调用过程，包含LLM、提示词、工具；多智能体系统表示为有向无环图。
  - **采样机制**：控制器网络使用MoE（混合专家）风格的门控网络，根据查询嵌入计算各算子激活分数，按累积分数超过阈值（thres）依次选择算子，并引入**提前退出算子**（O_exit）使采样深度可自适应。
  - **优化目标**：最大化效用（准确率）与成本（token成本）的加权差，损失函数为$ \min_{\pi, O} \mathbb{E}[-p(a|q,\pi,O) + \lambda \cdot C(G;q)] $。
  - **梯度估计**：对分布参数$\pi$使用经验贝叶斯蒙特卡洛采样（式11）；对算子$O$使用**文本梯度**（Textual Gradient），即由LLM生成自然语言格式的改进建议（如修改提示词、调整温度、合并/拆分算子节点）。
- **算法流程**：对每个查询，逐层采样算子直至达到最大层数或遇到退出算子 → 执行采样的系统 → 根据反馈更新分布和算子。

## 3. 实验设计

- **数据集/场景**：覆盖三大领域：
  - 数学推理：GSM8K、MATH、MultiArith。
  - 代码生成：HumanEval、MBPP。
  - 工具使用：GAIA（多模态、文件读写、网页搜索等）。
- **Benchmark**：六个公开标准基准。
- **对比方法**：
  - 单智能体：Vanilla、CoT、ComplexCoT、Self-Consistency。
  - 手工多智能体：MultiPersona、LLM-Debate、LLM-Blender、DyLAN、AgentVerse、MacNet。
  - 自动多智能体：AutoAgents、GPTSwarm、ADAS、AgentSquare、AFlow。
- **基础LLM**：统一使用gpt-4o-mini（闭源）及Qwen-2.5-72b、Llama-3.1-70b（开源）。
- **超参**：层数L=4，成本惩罚系数λ∈{1e-3,5e-3,1e-2}，采样次数K=4，阈值thres=0.3。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量、显存等详细算力配置。仅报告了token消耗、API成本及墙钟时间：
  - 训练成本：MATH基准上MaAS仅需3.38美元（AFlow需22.50美元）；训练墙钟时间53分钟（DyLAN需508分钟）。
  - 推理成本：MaAS推理API成本0.42美元，AFlow为1.66美元。
- 依赖外部API（OpenAI及开源模型API），未说明本地部署细节。

## 5. 实验数量与充分性

- **实验数量较多**：在6个基准上对比14种基线方法（数学+代码）和10种方法（GAIA），另包含成本分析、消融实验、参数敏感性分析、跨模型/跨数据集迁移性实验、归纳能力实验。
- **充分性与客观性**：
  - 控制基础LLM一致（gpt-4o-mini）进行公平对比。
  - 消融实验分析了缺失文本梯度、缺失提前退出、缺失成本约束的影响。
  - 敏感性分析覆盖层数L、λ、采样次数K。
  - 迁移实验验证了超网络在Qwen-2.5-70b和Llama-3.1-70b上的泛化性。
  - 归纳实验展示了模型对未见算子（Debate）的适应能力。
- **综合评价**：实验设计全面，覆盖多样场景，对比基线全面，公平性较好。

## 6. 主要结论与发现

1. **性能领先**：MaAS在6个基准上平均超越SOTA自动方法（AFlow）0.54%~16.89%，在GAIA上提升尤其显著（Level 1/2提升18.38%/17.61%）。
2. **成本高效**：仅需AFlow训练成本的15%、推理成本的25%即可取得更优结果；推理API成本最低，wall-clock时间最短。
3. **查询自适应**：可视化显示，简单问题MaAS倾向于早期退出（概率高达0.37~0.47），困难问题则调用更多层和更复杂的算子，实现按需分配资源。
4. **迁移性强**：在跨数据集（如MATH→GSM8K）和跨LLM主干（gpt-4o-mini→Qwen-2.5-70b）上保持性能增益。
5. **归纳能力强**：能够合理运用训练时未见过的算子（Debate）。

## 7. 优点

- **范式创新**：首次将多智能体系统设计从搜索单一静态系统转变为优化概率性超网络，实现动态资源分配，灵感来自神经架构搜索中的超网络技术。
- **实用性**：方法端到端自动化，无需人工干预；通过提前退出和MoE门控实现轻量级推理。
- **文本梯度**：巧妙利用LLM自身生成自然语言格式的梯度，替代不可微的算子优化，具有启发性。
- **实验扎实**：覆盖多个领域，消融、迁移、归纳实验完备，成本分析详细。

## 8. 不足与局限

- **算力细节缺失**：未报告GPU型号、数量、训练时间（仅报告了API成本），无法评估本地部署硬性需求。
- **依赖API**：文本梯度和算子执行依赖LLM API，可能引入额外延迟和成本，且对API稳定性敏感。
- **搜索空间限制**：算子集合需预先定义，且数量较少（7个初始算子+1个退出）。扩展更多算子可能增加采样复杂度。
- **超参数敏感**：阈值thres、成本系数λ、层数L等需人工设定，不同任务可能需调整。
- **未探讨大规模场景**：实验最大任务数约1055（GSM8K），未测试超大规模多智能体系统或超长序列。
- **缺乏与其他超网络方法直接对比**：虽然引用了NAS中的超网络，但未与类似超网络搜索方法（如DARTS、SNAS）在多智能体场景下对比。
- **伦理/社会影响讨论较简短**：仅提及无伦理风险、可能民主化智能自动化，未深入分析潜在的偏见、滥用或安全风险。

（完）
