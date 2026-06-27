---
title: "Text Augmented Correlation Transformer For Few-shot Classification & Segmentation"
title_zh: 文本增强的相关性变换器用于少样本分类与分割
authors: "Nandam, Srinivasa Rao, Atito, Sara, Feng, Zhenhua, Kittler, Josef, Awais, Muhammad"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Nandam_Text_Augmented_Correlation_Transformer_For_Few-shot_Classification__Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 将文本线索集成到少样本分割中
tldr: 针对少样本分类与分割任务中视觉信息有限导致边界模糊与类重叠的问题，本文提出多模态框架，将文本支持线索引入支持数据，通过文本增强的相关性变换器实现语义消歧与精细分割。实验证明文本线索显著提升了少样本场景下的分割精度，为多模态少样本学习提供了新范式。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 788, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1735, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 879, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 870, \"height\": 365, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1809, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1807, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 896, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1810, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 518, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 895, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nandam-text-augmented-correlation-transformer-for-few-shot-classification-segmentation-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 642, \"height\": 269, \"label\": \"Table\"}]"
motivation: 少样本任务中视觉数据难以捕获高层语义，文本线索未被充分利用。
method: 设计文本增强的相关性变换器，将文本支持作为额外查询，与视觉特征融合。
result: 在少样本分类与分割任务上优于纯视觉方法，mIoU提升明显。
conclusion: 文本线索有效弥补视觉信息不足，是多模态少样本学习的关键方向。
---

## Abstract
Foundation models like CLIP and ALIGN have transformed few-shot and zero-shot vision applications by fusing visual and textual data, yet the integrative few-shot classification and segmentation (FS-CS) task primarily leverages visual cues, overlooking the potential of textual support. In FS-CS scenarios, ambiguous object boundaries and overlapping classes often hinder model performance, as limited visual data struggles to fully capture high-level semantics. To bridge this gap, we present a novel multi-modal FS-CS framework that integrates textual cues into support data, facilitating enhanced semantic disambiguation and fine-grained segmentation. Our approach first investigates the unique contributions of exclusive text-based support, using only class labels to achieve FS-CS. This strategy alone achieves performance competitive with vision-only methods on FS-CS tasks, underscoring the power of textual cues in few-shot learning. Building on this, we introduce a dual-modal prediction mechanism that synthesizes insights from both textual and visual support sets, yielding robust multi-modal predictions. This integration significantly elevates FS-CS performance, with classification and segmentation improvements of +3.7/6.6% (1-way 1-shot) and +8.0/6.5% (2-way 1-shot) on COCO-20^i, and +2.2/3.8% (1-way 1-shot) and +4.3/4.0% (2-way 1-shot) on Pascal-5^i. Additionally, in weakly supervised FS-CS settings, our method surpasses visual-only benchmarks using textual support exclusively, further enhanced by our dual-modal predictions. By rethinking the role of text in FS-CS, our work establishes new benchmarks for multi-modal few-shot learning and demonstrates the efficacy of textual cues for improving model generalization and segmentation accuracy.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **任务背景**：少样本学习（Few-shot Learning）在数据稀缺场景中至关重要，传统方法分为少样本分类（FS-C）和少样本分割（FS-S）。但FS-C假设每张查询图像仅含一个目标类，FS-S要求查询图像中至少出现一个目标类，限制了实际应用。
- **现有挑战**：综合少样本分类与分割（FS-CS）任务虽然统一了二者，但现有方法主要依赖视觉数据，忽视了文本线索（如类标签）的潜力。在FS-CS中，视觉数据有限导致对象边界模糊、类重叠等语义歧义问题。
- **研究动机**：探索利用文本支持集（仅类标签）独立完成FS-CS的可能性，并设计多模态（文本+图像）框架，通过融合文本线索增强语义消歧和精细化分割能力。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：基于CLIP的视觉和文本编码器，利用相关性变换器生成查询-支持间的相关性图，分别处理视觉-视觉相关性和视觉-文本相关性，并通过融合二者提升FS-CS性能。
- **关键技术细节**：
  - **双相关性变换器（Dual Correlation Transformer）**：两个独立的变换器模块，分别处理视觉-视觉相关性和视觉-文本相关性。前者计算查询图像与支持图像的类/块token点积；后者将查询视觉token与支持文本token投影到公共空间后计算点积。
  - **特征增强模块（Feature Enrichment Module）**：采用单层注意力，但通过空洞卷积（dilation rates 3,6,10）生成多尺度Key-Value（粒状KV），同时捕获细粒度局部细节和全局语义，避免复杂多层交叉注意力。
  - **零样本知识蒸馏（Zero-Shot Knowledge Distillation）**：在纯文本支持时，利用CLIP的零样本分类能力（通过正负提示）生成零样本预测，并引入蒸馏损失对齐模型输出，补偿训练数据不足导致的分类精度下降。
  - **多模态预测融合**：分别从视觉相关性和视觉-文本相关性得到分类和分割预测，通过可学习缩放因子（α, β）加权合并。
  - **损失函数**：对于文本增强模式，使用交叉熵损失（分类+分割）加零样本蒸馏损失；对于纯文本模式，额外包含蒸馏损失。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集**：
  - **Pascal-5^i**（4折交叉验证）
  - **COCO-20^i**（4折交叉验证）
- **场景**：
  - 标准FS-CS（1-way 1-shot和2-way 1-shot）
  - 弱监督FS-CS（使用DINO生成伪掩码）
- **基准**：CST（原始DINO-S/8骨干）、CST(CLIP-B/16)*、ASNet、HSNet、PFENet、PANet等，并报告CLIP-B/16零样本结果。
- **对比方法**：包括纯视觉方法和先前使用文本（如GPT-4Vision）的方法。

## 4. 资源与算力

- **文中明确说明**：
  - 使用**RTX-3060 GPU**测量运行时和内存，批量大小为8。
  - 比较了模型速度：CST (DINO-S/8) 1.77 it/s，CST (CLIP-B/16) 1.42 it/s，本方法(文本增强) 1.7 it/s。
  - 内存占用：CST (DINO-S/8) 8.9G，CST (CLIP-B/16) 4.7G，本方法(文本增强) 5.6G。
- **未明确**：训练所需GPU数量、总训练时长、是否多卡训练。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验（表1、表2）：在Pascal-5^i和COCO-20^i上报告1-way 1-shot和2-way 1-shot的分类准确率（exact ratio）和分割mIoU。
  - 弱监督实验（表3）在Pascal-5^i上一组对比。
  - 消融实验：文本增强比例（表5）、单模态vs多模态（表6）、特征增强模块组件对比（表7）、零样本蒸馏组件（表8）。
  - 额外提供图4的N-way 1-shot性能对比。
- **充分性**：
  - 覆盖了主要FS-CS基准，比较了多个强基线（CST, ASNet, HSNet等）。
  - 消融实验系统：分别验证文本贡献、特征增强模块设计（ASPP、粒状Q/KV等）、蒸馏损失的必要性。
  - 总体实验设计客观、公平，通过复现CST (CLIP-B/16)作为公平基线。

## 6. 主要结论与发现

- **纯文本支持可行**：仅使用类标签的文本支持即可达到与领先视觉方法竞争的性能，尤其在COCO-20^i上优势明显。
- **多模态融合显著提升**：文本增强模式在COCO-20^i上1-way 1-shot分类+3.7%、分割+6.6%；2-way 1-shot分类+8.0%、分割+6.5%；在Pascal-5^i上也有显著提升。
- **特征增强模块有效**：比ASPP、标准注意力、粒状Q/QKV等均更优，能同时捕获多尺度和全局语义。
- **零样本蒸馏改善分类**：在纯文本设置下，蒸馏损失可弥补CLIP泛化能力，尤其在Pascal-5^i小数据集上效果明显。
- **弱监督场景同样受益**：文本增强在弱监督FS-CS中超越纯视觉方法。

## 7. 优点（亮点）

- **创新性**：首次系统性探索文本线索在FS-CS中的独立作用，并设计多模态融合框架，重新定义了支持集的构成。
- **简单高效**：使用冻结CLIP，不额外增加可学习参数，运行时和内存开销比原始CST (DINO-S/8)还低。
- **特征增强模块设计巧妙**：通过单层注意力+空洞卷积实现多尺度，避免复杂架构。
- **零样本蒸馏**：针对纯文本场景的轻量化解决方案，提升分类泛化。
- **实验全面**：覆盖标准、弱监督场景，消融实验清晰验证各组件贡献。

## 8. 不足与局限

- **实验覆盖**：仅在Pascal-5^i和COCO-20^i上测试，未涉及更复杂的开放世界或细粒度数据集。
- **偏差风险**：COCO-20^i文本类标签较为明确，对于抽象类或细粒度类别文本支持效果可能下降。
- **应用限制**：
  - 依赖CLIP的预训练，若领域偏移严重（如医学图像）可能受限。
  - 纯文本设置下，小数据集仍弱于最佳视觉方法（如Pascal-5^i分割略低）。
  - 文本增强需要支持集中有类标签，对于无标签场景不适用。
- **资源信息不完整**：未提供完整训练超参数、GPU数量及总耗时。

（完）
