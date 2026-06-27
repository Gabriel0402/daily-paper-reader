---
title: "Bring Reason to Vision: Understanding Perception and Reasoning through Model Merging"
title_zh: 将推理融入视觉：通过模型合并理解感知与推理
authors: "Shiqi Chen, Jinghan Zhang, Tongyao Zhu, Wei Liu, Siyang Gao, Miao Xiong, Manling Li, Junxian He"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ntCAP6tMoX"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 通过模型合并向VLM迁移推理能力
tldr: VLM如何组合视觉感知与语言推理尚不明确。本文提出跨模态模型合并方法，将大语言模型的推理能力迁移到视觉语言模型中，无需额外训练。实验表明，该方法有效提升了VLM的推理能力，为VLM增强提供了轻量级方案，可间接支持多智能体系统中VLM的部署。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 765, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 993, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1692, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1076, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 625, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 779, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntcap6tmox/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 799, \"height\": 588, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1083, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1777, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1775, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1122, \"height\": 838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntcap6tmox/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1610, \"height\": 335, \"label\": \"Table\"}]"
motivation: VLM的感知与推理组合机制不明确。
method: 提出跨模态模型合并，将LLM推理参数融入VLM。
result: 无训练条件下显著提升VLM推理能力。
conclusion: 模型合并是一条有效的VLM推理增强路径。
---

## Abstract
Vision-Language Models (VLMs) combine visual perception with the general capabilities, such as reasoning, of Large Language Models (LLMs). However, the mechanisms by which these two abilities can be combined and contribute remain poorly understood.
In this work, we explore to compose perception and reasoning through model merging that connects parameters of different models.  
Unlike previous works that often focus on merging models of the same kind, we propose merging models **across modalities**, enabling the incorporation of the reasoning capabilities of LLMs into VLMs. 
Through extensive experiments, we demonstrate that model merging offers a successful pathway to transfer reasoning abilities from LLMs to VLMs in a **training-free** manner.
Moreover, we utilize the merged models to understand the internal mechanism of perception and reasoning and how merging affects it. We find that perception capabilities are predominantly encoded in the early layers of the model, whereas reasoning is largely facilitated by the middle-to-late layers. After merging, we observe that all layers begin to contribute to reasoning, whereas the distribution of perception abilities across layers remains largely unchanged. These observations shed light on the potential of model merging as a tool for multimodal integration and interpretation.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉语言模型（VLM）虽然结合了视觉感知和大语言模型（LLM）的通用能力（如推理），但其内部机制——特别是感知能力与推理能力如何组合和贡献——仍不清楚。当前VLM在复杂多模态推理任务上表现不佳，部分原因是缺乏多模态推理训练数据，导致其推理能力远落后于纯文本LLM。
- **研究动机**：探索能否通过模型合并（model merging），将LLM的强大推理能力“注入”到VLM中，从而在不进行额外训练的情况下提升VLM的推理性能。
- **整体含义**：提出跨模态模型合并方法，表明LLM的推理能力可以通过参数级别的算术操作成功迁移到VLM中，并借此揭示VLM内部感知与推理能力的分层分布机制，为多模态融合与模型可解释性提供新思路。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：基于模型合并中的“任务向量”概念，对VLM的语言模型部分（θ_vlm）与推理专用LLM（θ_reason）进行线性权重合并，保持视觉编码器和投影器不变。
- **关键技术细节**：
  - **任务向量定义**：给定基础模型θ_base和微调模型θ_ft，任务向量τ = θ_ft − θ_base。
  - VLM语言组件适配向量：τ_vlm = θ_vlm − θ_base。
  - 推理LLM的向量：τ_reason = θ_reason − θ_base。
  - **合并公式**：θ'_vlm = θ_base + λ·τ_vlm + (1−λ)·τ_reason，其中λ控制VLM原始能力与推理能力的平衡。
- **合并策略**：主实验采用线性合并（linear merging），附加实验对比TIES合并、Dare合并、层交换等方法，结果均与线性合并性能相当，表明简单线性合并已足够有效。

## 3. 实验设计：数据集、基准、对比方法

- **数据集与基准**：
  - **数学推理基准**：MathVista（含General VQA和Math VQA子集）、MathVerse（含Text-Dominant、Text-Lite、Vision-Integrated、Vision-Dominant、Vision-Only等多种模式）、MathVision、DynaMath、MMStar（All和Math split）。
  - **额外通用基准**：MM-Math（附录）。
- **VLM模型**：
  - LLaVA-Next-LLaMA3-8B（主模型）
  - Idefics2-8B（Mistral基座）
  - InternVL2-LLaMA3-76B（大尺度模型）
  - Qwen2-VL-7B（附录补充）
- **推理任务向量（LLM）**：
  - 数学专用：Dart-Math（两种变体Dart-Uniform和Dart-Prop）、MAmmoTH-1/2、MetaMath、Magpie-v0.3、DeepSeek-R1-Distill。
  - 逻辑推理（附录）：基于LogiCoT微调的LLM。
- **对比方法**：各VLM基线（无合并） vs. 合并不同推理LLM后的结果；不同合并策略（TIES、Dare、层交换）对比。
- **超参数**：λ在{0.8, 0.85, 0.9}中基于MathVista上Dart-Prop调优，主实验统一λ=0.9。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量或具体训练时长。由于方法为“训练免”（training-free），仅需参数合并（一次权重平均），计算开销极低，推测可在单张消费级GPU上短时间内完成。文中未提及推理计算资源。

## 5. 实验数量与充分性

- **实验数量**：共有约13组主实验（三个VLM × 5~6个推理LLM + 不同基准），外加附录中更多组合（如逻辑推理、Qwen2-VL、MM-Math、不同合并方法消融等）。总计超过20组对比实验。
- **充分性评价**：
  - **充分**：覆盖了8B-76B多种VLM、不同基座架构（LLaMA、Mistral）、多个数学推理基准（5个），并做了显著性检验（p<0.05标记）。消融实验包括不同合并方法、不同λ、不同任务向量（数学vs通用逻辑）等。
  - **客观公平**：对所有任务向量采用相同超参数设置，并在同一基准上调优后固定应用到其他基准，避免了过拟合适配。附录中补充了Qwen2-VL等更强模型的结果，显示一致趋势。
  - **主观风险低**：结果趋势清晰（数学推理提升显著，视觉主导任务略有下降），解释合理。

## 6. 论文的主要结论与发现

- **主要结论**：模型合并是一种有效、无训练的跨模态推理能力迁移方法，能显著提升VLM在数学推理任务上的性能（最高相对提升30%）。
- **关键发现**：
  1. 感知能力主要编码在模型**早期层**，而推理能力集中在**中后期层**。
  2. 合并推理模型后，所有层都开始对推理有贡献，而感知能力的层分布基本不变。
  3. 合并带来的推理提升主要体现为“推理时扩展能力”（推理链变长、更多中间步骤），与视觉主导任务（如图表问答）感知瓶颈无关。
  4. 不同合并方法（线性、TIES、Dare）性能接近，简单线性合并已足够。

## 7. 优点

- **方法简洁高效**：无需额外训练或数据，仅通过参数加权平均即可实现能力迁移，计算成本极低。
- **跨模态可扩展性**：首次系统验证了不同模态模型（纯文本LLM vs. VLM）可被合并，且效果显著。
- **强大的可解释性分析**：利用掩码（masking out）技术定位感知与推理能力在层间的分布，揭示了VLM内部功能分层的机理。
- **实验设计全面**：涵盖多种VLM规模、多个推理数据集、多种合并策略，并提供了显著性检验，结论稳健。

## 8. 不足与局限

- **实验覆盖的局限**：
  - 主要聚焦数学推理，对通用推理（如常识、逻辑）的迁移效果仅有一个逻辑推理的补充实验，证明较弱。
  - 视觉主导任务（如图表QA）性能轻微下降，说明合并可能导致感知能力或世界知识的部分损失，未提出补偿策略。
- **偏差风险**：
  - 超参数λ仅在MathVista上调优，可能在其他基准上非最优，但文中后续统一使用固定λ（0.9）进行跨基准评估，引入一定偏差。
  - 仅针对VLM的语言模型部分合并，未探索同时调整视觉编码器的可能性。
- **应用限制**：
  - 依赖基础模型相同或兼容的架构（如LLaMA-3与Mistral-7B不可互换），限制了跨系列合并。
  - 对已预训练过大量数学数据的VLM（如Idefics、Qwen2-VL）提升有限，说明存在“饱和效应”。
- **算力信息缺失**：未提供任何关于推理或合并的时间/GPU成本量化指标，不利于实际部署评估。

（完）
