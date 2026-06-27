---
title: Re-ranking Reasoning Context with Tree Search Makes Large Vision-Language Models Stronger
title_zh: 用树搜索重排序推理上下文增强大型视觉语言模型
authors: "Qi Yang, Chenghao Zhang, Lubin Fan, Kun Ding, Jieping Ye, Shiming Xiang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DJcEoC9JpQ"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 大型视觉语言模型的推理与检索增强
tldr: 针对大型视觉语言模型在视觉问答中知识稀少且检索响应不稳定的问题，本文提出多模态RAG框架RCTS，通过自一致评估机制构建富含推理模式的知识库，并采用蒙特卡洛树搜索重排序方法提升答案质量。实验表明该方法在多个VQA基准上显著提升了正确答案的召回率和准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 827, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1617, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1567, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1568, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1577, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1803, \"height\": 74, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 72, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 1487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1737, \"height\": 2017, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1748, \"height\": 1851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1746, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1703, \"height\": 2195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1738, \"height\": 2176, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 887, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1703, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 203, \"label\": \"Table\"}]"
motivation: 现有方法知识稀缺且检索响应不稳定，限制了LVLM在VQA中的表现。
method: 构建推理上下文知识库，并采用蒙特卡洛树搜索重排序方法提升答案质量。
result: 在多个VQA数据集上显著优于现有RAG方法。
conclusion: RCTS有效增强了LVLM的推理能力，为多模态检索增强生成提供了新方案。
---

## Abstract
Recent advancements in Large Vision Language Models (LVLMs) have significantly improved performance in Visual Question Answering (VQA) tasks through multimodal Retrieval-Augmented Generation (RAG). However, existing methods still face challenges, such as the scarcity of knowledge with reasoning examples and erratic responses from retrieved knowledge. To address these issues, in this study, we propose a multimodal RAG framework, termed RCTS, which enhances LVLMs by constructing a Reasoning Context-enriched knowledge base and a Tree Search re-ranking method. Specifically, we introduce a self-consistent evaluation mechanism to enrich the knowledge base with intrinsic reasoning patterns.  We further propose a Monte Carlo Tree Search with Heuristic Rewards (MCTS-HR) to prioritize the most relevant examples.  This ensures that LVLMs can leverage high-quality contextual reasoning for better and more consistent responses. Extensive experiments demonstrate that our framework achieves state-of-the-art performance on multiple VQA datasets, significantly outperforming In-Context Learning (ICL) and Vanilla-RAG methods. It highlights the effectiveness of our knowledge base and re-ranking method in improving LVLMs.

---

## 论文详细总结（自动生成）

# 中文总结

## 1. 核心问题与整体含义
- **研究动机**：大型视觉语言模型（LVLMs）在视觉问答（VQA）中展现强大能力，但面临两大挑战：现有多模态检索增强生成（RAG）方法中，知识库缺乏蕴含推理过程的示例，导致检索到的知识难以帮助模型进行有效推理；检索结果不稳定，可能产生不一致或错误的响应。
- **整体目标**：通过构建富含推理上下文的知识库，并利用树搜索方法对检索样本进行重排序，使LVLMs从“知道答案”提升到“理解推理过程”，从而获得更准确、更一致的答案。

## 2. 方法论
- **核心思想**：提出RCTS框架，由三部分组成：推理上下文知识库构建、混合嵌入检索、蒙特卡洛树搜索与启发式奖励（MCTS-HR）重排序。
- **推理上下文生成**：基于知识库中已有问答对，利用LVLM生成多个候选推理上下文（如逐步推理过程），然后通过自一致评估：用每个候选上下文+问题生成预测答案，与真实答案对比，选择得分最高的上下文作为该样本的推理上下文。
- **混合嵌入检索**：同时使用文本编码器（BERT-base）和图像编码器（ViT-L+MLP）对用户查询和知识库中样本进行编码，拼接所有token嵌入，通过计算最大相似度得分为用户查询检索Top-N个相关样本。
- **MCTS-HR重排序**：将检索到的N个样本作为动作空间，构建树状搜索。传统MCTS基础上，提出两种启发式奖励：
  - **自一致奖励**：对当前分支预测的答案，多次生成并计算与原始预测的一致性得分。
  - **互启发奖励**：从动作空间中选取其他样本，将当前预测作为上下文，评估这些样本的答案准确率。
  - 最终奖励为两者加权和，通过回传更新节点价值，实现最优样本顺序选择。算法迭代直至达到最大rollout次数或满足早停条件。

## 3. 实验设计
- **数据集**：
  - 推理类：ScienceQA（测试4241题，知识库16967题）、MMMU-Dev（150题，知识库MMMU-Val 900题）、MathV testmini（304题，知识库MathV test 2736题）
  - 非推理类：VizWiz val（4319题，知识库train 20523题）、VSR-MC test（1181题，知识库trainval 4440题）
- **对比方法**：Zero-Shot（零样本）、ICL（随机选取样本进行上下文学习）、Vanilla-RAG（直接使用Top检索样本）
- **骨干模型**：Qwen2-VL（2B/7B）、InternVL-2（8B）
- **评估指标**：准确率（Accuracy）

## 4. 资源与算力
- 文中明确提及：对于7B以上参数量的LVLM，采用4-bit量化（AWQ）部署于单张NVIDIA 4090 24GB GPU上。未报告具体训练时长，因为RCTS是无需微调的训练自由框架（training-free），仅需在知识库上生成推理上下文（一次处理）和运行时MCTS推理。

## 5. 实验数量与充分性
- **主要实验**：表2展示了在三个推理数据集上，三种LVLM下RCTS与基线对比，共9个组合。表3展示了两个非推理数据集上的结果（仅Qwen2-VL 7B）。
- **消融实验**：表4分别消融推理上下文和MCTS-HR两个核心组件；表5探讨不同奖励权重α；图5比较不同奖励策略（自奖励、互奖励、混合奖励）及不同rollout次数对性能的影响。
- **推理上下文可靠性**：表6评估生成推理上下文的准确性（100%/99.89%/96.67%等）。
- **定性分析**：附录给出了多个案例的MCTS重排序过程可视化。
- **充分性评价**：实验覆盖了2B~8B不同规模的LVLM、推理与非推理任务、多种基线、核心组件消融及超参数分析，较为全面客观。但存在对小模型或小数据集的偏差风险（如MMMU知识库样本少导致提升有限）。

## 6. 主要结论与发现
- RCTS在所有数据集上显著优于Zero-Shot、ICL和Vanilla-RAG，平均提升约3%~4.2%。
- 推理上下文和MCTS-HR两者互补：单独使用任一组件均有正向效果，联合使用时达到最佳性能。
- 混合奖励（自一致+互启发）优于单一奖励策略；适当数量的rollout（10次）可平衡性能与计算开销。
- 生成的推理上下文具有高可靠性（在ScienceQA上可达100%准确），为后续重排序提供坚实基础。

## 7. 优点
- **自动化推理上下文生成**：无需人工标注，通过自一致评估获得高质量推理过程，丰富知识库信息。
- **训练自由**：RCTS无需微调模型参数，可即插即用，易于扩展到新领域。
- **重排序机制创新**：将MCTS应用于样本排序，结合自启发和互启发奖励，有效缓解检索噪声，提升上下文质量。
- **模块化设计**：检索、重排序、生成各模块可独立替换或升级，便于后续改进。
- **广泛适用性**：在多种LVLM和多种VQA任务上均验证了有效性，包括复杂推理和简单定位任务。

## 8. 不足与局限
- **依赖知识库覆盖度**：若知识库中缺乏与用户查询相似的样例，RCTS提升有限（如MMMU数据集因领域广泛、相似样本少，仅提升3.33%）。
- **计算开销增加**：MCTS-HR需要进行多轮rollout（默认10次），每次需调用LVLM生成和评估，相比简单Top检索增加了推理延迟，需要在性能与效率间权衡。
- **早停策略依赖零样本答案**：早停条件要求根节点（零样本）与叶子节点答案一致，若零样本错误则该策略可能提前终止，导致错过更优序列。
- **未探讨跨数据集泛化**：实验中知识库与评估集为同域划分，未测试知识库与目标域不同时的零样本泛化能力。
- **数据集规模有限**：MMMU仅用150题评估，统计显著性可能不足。

（完）
