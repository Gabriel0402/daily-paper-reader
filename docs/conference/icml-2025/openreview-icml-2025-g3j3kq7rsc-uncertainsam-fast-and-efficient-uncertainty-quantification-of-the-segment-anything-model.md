---
title: "UncertainSAM: Fast and Efficient Uncertainty Quantification of the Segment Anything Model"
title_zh: "UncertainSAM: Segment Anything模型的快速高效不确定性量化"
authors: "Timo Kaiser, Thomas Norrenbrock, Bodo Rosenhahn"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=G3j3kq7rSC"
tags: ["query:mmseg"]
score: 8.0
evidence: SAM模型在语义分割中的不确定性量化
tldr: 该论文提出UncertainSAM，一种轻量级后验不确定性量化方法，基于贝叶斯熵公式同时考虑偶然不确定性、认识不确定性和新增的任务不确定性。该模型能追溯不确定性根源（模型欠参数化、提示不足或图像模糊），且计算高效，提升了SAM在关键任务中的可靠性和可解释性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1677, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1770, \"height\": 1927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-g3j3kq7rsc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 1954, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1772, \"height\": 1228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 856, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 853, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 860, \"height\": 1222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 863, \"height\": 1224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 860, \"height\": 1218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 858, \"height\": 1973, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 854, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 853, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-g3j3kq7rsc/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 855, \"height\": 441, \"label\": \"Table\"}]"
motivation: SAM作为类无关基础模型，其分割结果缺乏不确定性量化，影响在安全关键任务中的使用。
method: 提出基于贝叶斯熵的轻量级后验不确定性量化模型USAM，融合三类不确定性。
result: 在多个分割数据集上，USAM实现了快速准确的不确定性估计，且能解释不确定性来源。
conclusion: UncertainSAM为SAM提供了实用的不确定性量化工具，增强其在高风险场景的适用性。
---

## Abstract
The introduction of the Segment Anything Model (SAM) has paved the way for numerous semantic segmentation applications. For several tasks, quantifying the uncertainty of SAM is of particular interest. However, the ambiguous nature of the class-agnostic foundation model SAM challenges current uncertainty quantification (UQ) approaches. This paper presents a theoretically motivated uncertainty quantification model based on a Bayesian entropy formulation jointly respecting aleatoric, epistemic, and the newly introduced task uncertainty. We use this formulation to train USAM, a lightweight post-hoc UQ method. Our model traces the root of uncertainty back to under-parameterised models, insufficient prompts or image ambiguities. Our proposed deterministic USAM demonstrates superior predictive capabilities on the SA-V, MOSE, ADE20k, DAVIS, and COCO datasets, offering a computationally cheap and easy-to-use UQ alternative that can support user-prompting, enhance semi-supervised pipelines, or balance the tradeoff between accuracy and cost efficiency.

---

## 论文详细总结（自动生成）

# 论文中文总结：UncertainSAM: Segment Anything 模型的快速高效不确定性量化

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：Segment Anything Model (SAM) 是一个强大的类无关基础分割模型，能根据多模态提示（点、框、文本等）分割任意物体，已在许多应用中被广泛使用。然而，SAM 的预测结果本身缺乏可靠的不确定性度量，这在医疗诊断、自动驾驶等安全关键领域是一个严重缺陷。
- **核心问题**：SAM 的类无关特性使其面临一种独特的不确定性——**任务不确定性**（task uncertainty）：用户通过提示定义要分割的物体，但同一提示可能对应多种有效任务，或者 SAM 可能无法正确解码用户的意图。现有的不确定性量化（UQ）方法（如测试时增强、熵计算等）往往只考虑模型不确定性（epistemic）和数据不确定性（aleatoric），忽略了这种任务不确定性，且计算代价高。
- **整体含义**：本文旨在为 SAM 建立一套完整的不确定性量化框架，既能分离不同来源的不确定性，又能以轻量级的方式实现，从而帮助用户判断是否需要改进提示、是否需要监督、或者是否应切换更大的模型以平衡精度与效率。

## 2. 论文提出的方法论

### 2.1 贝叶斯熵近似（Bayesian Formulation）
- 将 SAM 的预测不确定性分解为三个部分：
  - **认知不确定性（Epistemic）**：来自模型参数（不同大小的 backbone，如 Tiny, Small, Base+, Large）。
  - **偶然不确定性（Aleatoric）**：进一步细分为**提示不确定性（Prompt Uncertainty）**（由用户定义的提示质量、位置等引起）和**任务不确定性（Task Uncertainty）**（由图像或提示本身的歧义导致，例如一个点可能对应多个物体）。
- 通过蒙特卡洛采样近似：
  - 对图像进行5种数据增强（翻转、JPEG压缩、高斯模糊、噪声等）→ 近似 aleatoric 不确定性。
  - 对每个物体从真实掩码中均匀采样8个点作为坐标提示 → 近似 prompt 不确定性。
  - 使用 SAM 的3个候选掩码（不同随机嵌入）→ 近似 task 不确定性。
  - 使用4种规模的预训练 SAM 模型（Tiny, Small, Base+, Large）→ 近似 epistemic 不确定性。
- 利用 SAM 自身的 SamScore（预测的 IoU）归一化后作为任务概率权重，计算加权熵作为不同不确定性的度量（H_Y, H_Θ, H_XP, H_A）。

### 2.2 USAM：确定性估计器
- **核心思想**：用轻量级 MLP 直接从 SAM 的潜在表示（mask token 和 IoU token 拼接的 512 维向量 l）中回归不确定性指标，避免蒙特卡洛采样。
- **网络结构**：3层 MLP，隐藏层 512 维，Sigmoid 激活，输出标量。
- **训练目标**：
  - USAM_θ(l)：预测使用模型 θ 时的期望 IoU。
  - USAM_xP*(l)：预测使用“精炼提示”（多个点）时的期望 IoU。
  - USAM_SAM(l)：预测使用 SamScore 自动选择掩码时的期望 IoU。
- **不确定性指标计算（测试时）**：
  - 预测不确定性：1 − USAM_θ(l)。
  - 模型不确定性 gap：Δ_Θ = USAM_L(l) − USAM_T(l)（或直接训练Δ*_Θ）。
  - 提示不确定性 gap：Δ_XP = USAM_xP*(l) − USAM_θ(l)。
  - 任务不确定性 gap：Δ_A = USAM_θ(l) − USAM_SAM(l)。
- **损失函数**：均方误差（MSE），优化器为 SGD，超参数通过 SMAC3 自动调优。

## 3. 实验设计

### 3.1 数据集
- **训练/评估数据集**：SA-V（大规模视频分割数据集，用于训练 USAM）、MOSE、ADE20k、DAVIS、COCO。
- 训练仅在各自数据集的训练集上进行，不使用验证集；评估在验证集上（DAVIS, COCO, ADE20k 无公开测试集）。

### 3.2 Benchmark 任务
1. **模型不确定性评估**：用 Tiny 模型预测，将最不确定的样本替换为 Large 模型的预测，测量 mIoU 提升的 AUC。
2. **提示不确定性评估**：用单个坐标点提示预测，将最不确定的样本替换为8个点精炼提示的预测。
3. **任务不确定性评估**：用 SamScore 自动选择掩码，将最不确定的样本替换为与 ground truth 最匹配的掩码。
4. **分割不确定性（整体）**：将最不确定的样本替换为 ground truth（即纠正），测量 AUC。

### 3.3 对比方法
- **SAM 自带的**：SamScore（逆 SamScore 作为不确定性）、掩码平均熵（HStd）。
- **本文的贝叶斯近似的四种熵**：H_Y, H_Θ, H_XP, H_A。
- **USAM 及其变体**：Δ_Θ, Δ_XP, Δ_A, USAM_θ，以及直接估计 gap 的 Δ*_θ, Δ*_XP, Δ*_A。
- **Oracle**：理想的不确定性排序（上界）。

## 4. 资源与算力

论文中**没有明确说明**训练 USAM 所用的 GPU 型号、数量或训练时长。仅提到使用了 SGD 优化器，超参数由 SMAC3 在少量 epochs（5~80）和 batch size（16~256）范围内调优。但指出 USAM 的 MLP 极为轻量，训练后可快速推理（表7显示，Large 模型+USAM 仅需 0.441 秒/张图，比原 SAM 0.437 秒几乎无额外开销）。因此可以推测训练成本较低，但具体算力信息缺失。

## 5. 实验数量与充分性

- **主要实验**：在5个数据集上进行了4类不确定性评估（模型、提示、任务、整体），每个评估报告了相对 AUC（表1-4），以及对应的绝对 AUC（附录表11-14）。
- **消融实验**：
  - Token 消融（表6）：移除 mask token 或 IoU token，观察性能变化。
  - 相关性分析（表5，表15-17）：计算不同 UQ 度量与真实 IoU 的 Pearson 相关系数。
  - 模型大小对比（附录表9-10）：不同 backbone 在不同数据集上的表现及对噪声的鲁棒性。
  - 超参数调优示例（附录表8）。
- **充分性**：实验覆盖了多种主流分割数据集、多种不确定性源分离、与现有方法（SamScore, HStd, 贝叶斯熵）的充分对比，消融实验验证了设计选择。但未包含真实应用中的主动学习或人机交互场景，所有评估基于离线指标。总体而言，实验较为充分且公平（统一使用相对 AUC 归一化）。

## 6. 论文的主要结论与发现

1. **USAM 在几乎所有任务上优于或持平于贝叶斯近似**，且计算开销极低（几乎零额外延迟）。
2. **USAM 能有效分离三种不确定性**：模型、提示、任务不确定性，并给出可解释的 gap 值。
3. **SamScore 作为不确定性指标表现较差**，尤其在任务不确定性场景下远不如 USAM。
4. **贝叶斯近似中的 H_XP 和 H_Θ 有效，但 H_Y（整体预测熵）效果不佳**，说明综合考虑所有采样维度反而会引入噪声。
5. **模型不确定性是 SAM 预测不确定性的主要来源之一**（与 H_Θ 高相关），提示和任务不确定性也显著。
6. **USAM 可直接用于模型选择（小模型 vs 大模型）、提示质量评估、监督需求判断**，有助于降低应用能耗和提升可靠性。

## 7. 优点

- **理论完备**：提出了全新的贝叶斯公式，明确区分了 SAM 特有的任务不确定性。
- **实用高效**：USAM 作为后验轻量 MLP，无需重新训练 SAM，推理时几乎不增加时间。
- **解释性强**：能够追溯不确定性根源（模型、提示、任务），便于用户或系统做出针对性改进。
- **广泛验证**：在5个公开数据集上、多种评估协议下全面测试，对比了多种 baselines。
- **代码开源**：提供了易于使用的实现。

## 8. 不足与局限

- **算力信息缺失**：未报告训练 USAM 的具体硬件和时长，降低了可重现性。
- **任务不确定性评估的贝叶斯基线失效**：论文中贝叶斯 H_A 在任务不确定性量化上表现很差（远低于 USAM），但未深入分析原因（可能是采样方式或概率归一化问题）。
- **未在实际应用场景中测试**：例如主动学习、交互式分割等真实人机协同场景，所有评估基于离线指标（纠正替换）。
- **依赖 ground truth**：训练 USAM 时需要 ground truth 计算 IoU 作为回归目标，无法完全实现无监督。
- **任务定义依赖用户**：论文假设用户能精确定义任务，但在开放世界场景中，任务本身可能先验不明。
- **OOD 样本处理未验证**：未评估 USAM 在分布外图像或未见过的分割任务上的泛化能力。

（完）
