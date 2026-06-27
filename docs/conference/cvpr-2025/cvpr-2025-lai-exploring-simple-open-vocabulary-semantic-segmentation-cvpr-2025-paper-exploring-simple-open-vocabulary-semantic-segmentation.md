---
title: Exploring Simple Open-Vocabulary Semantic Segmentation
title_zh: 探索简单的开放词汇语义分割
authors: "Lai, Zihang"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Lai_Exploring_Simple_Open-Vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM在语义分割中的应用
tldr: 开放词汇语义分割通常依赖CLIP和SAM等组件。本文提出S-Seg，仅使用伪掩码和语言训练MaskFormer，无需依赖上述元素。在多个基准上S-Seg表现出与依赖SAM的方法相当甚至更好的性能。这项工作表明简单设计也能取得优异结果，为开放词汇分割提供了新视角。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1810, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1544, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 820, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 806, \"height\": 181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 816, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1748, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1684, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 860, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 842, \"height\": 691, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lai-exploring-simple-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 875, \"label\": \"Table\"}]"
motivation: 现有开放词汇分割方法过度依赖CLIP和SAM等组件，流程复杂。
method: 提出S-Seg，利用伪掩码和语言直接训练MaskFormer，无需预训练视觉语言模型。
result: 在多个数据集上达到与复杂方法相当或更优的分割性能。
conclusion: S-Seg证明简洁的流水线也能实现强大的开放词汇语义分割。
---

## Abstract
Open-vocabulary semantic segmentation models aim to accurately assign a semantic label to each pixel in an image from a set of arbitrary open-vocabulary texts. In order to learn such pixel-level alignment, current approaches typically rely on a combination of (i) image-level VL model (e.g. CLIP), (ii) ground truth masks, (iii) custom grouping encoders, and (iv) the Segment Anything Model (SAM). In this paper, we introduce S-Seg, a simple model that can achieve surprisingly strong performance without depending on any of the above elements. S-Seg leverages pseudo-mask and language to train a MaskFormer, and can be easily trained from publicly available image-text datasets. Contrary to prior works, our model directly trains for pixel-level features and language alignment. Once trained, S-Seg generalizes well to multiple testing datasets without requiring fine-tuning. In addition, S-Seg has the extra benefits of scalability with data and consistently improving when augmented with self-training. We believe that our simple yet effective approach will serve as a solid baseline for future research. Our code and demo will be made publicly available soon.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

开放词汇语义分割旨在为图像中每个像素分配来自任意开放文本集合中的语义标签。现有方法通常依赖以下一种或多种组件：
- 图像级视觉语言模型（如 CLIP）的迁移；
- 人工标注的 ground truth 掩码（仅对部分类别）；
- 自定义分组编码器（如 GroupViT）；
- Segment Anything Model（SAM）的适配。

这些复杂的依赖导致训练流程繁琐、对大规模预训练模型和数据过度依赖。作者提出 S-Seg，探索**能否完全不依赖以上元素**，仅使用公开的图像-文本对（如 CC3M、CC12M、RedCaps）直接训练一个简单的 MaskFormer，实现像素级特征与语言的直接对齐。

---

## 2. 方法论

### 核心思想
- 使用 **MaskFormer** 作为基础分割架构，去掉分类头，直接输出 N 个二进制掩码和 N 个掩码特征。
- 通过**伪掩码生成器**（class-agnostic）提供掩码监督；通过**图像-文本对比损失**提供语义监督。
- 训练时**解耦**掩码监督与语义监督，不依赖密集标注。

### 关键技术细节

#### 伪掩码生成器
- 使用 DINO 预训练的 ViT-S/8 提取图像特征 token。
- 对 token 进行 **K-means 聚类**，每个 token 分配一个聚类索引，重排为分割图。
- 优点：高质量、速度快（每批 128 样本约 0.002 秒），远超 K-Means/RGB 或 Spectral Clustering。
- 在 PASCAL VOC 上的 oracle mIoU 达 78.8%，PAS. Context 达 66.3%。

#### 语言监督
- 文本编码器为 Transformer（12 层，隐层 256），取 [EOS] token 作为文本特征。
- 视觉特征：将 N 个掩码特征平均池化得到整图特征。
- 训练采用 **图像-文本对比损失**（InfoNCE-like），包含图像→文本和文本→图像两个方向。
- 使用 2 层 MLP 将视觉和文本特征映射到公共空间（维度 256）。

#### 训练损失
- 总损失：`L = L_mask + L_contrastive`，权重均为 1.0。
- 掩码损失：Dice Loss + Focal Loss（权重 1.0 和 20.0）。
- 使用二分图匹配将 N 个预测掩码与 K 个伪掩码匹配。

#### 推理阶段
- 输入测试图像和候选类别文本，MaskFormer 预测 N 个掩码和特征，文本编码器生成类别特征。
- 计算掩码特征与各文本特征的余弦相似度，经 softmax 得到类别概率，进行零样本分类。
- 通过阈值获取背景预测（遵循 GroupViT 做法）。

#### 自训练（S-Seg+）
- 使用 S-Seg 在测试集上生成伪标签，再用这些伪标签作为监督训练新模型。
- 无需额外人工标注，利用测试集未标注图像和类别信息进一步提升性能。

---

## 3. 实验设计

### 训练数据
- **CC3M**（3M 对）、**CC12M**（12M 对）、**RedCaps**（前 11M 对），最大 26M 对。
- 均为公开图像-文本数据，无需任何像素级标注。

### 测试基准
- **PASCAL VOC 2012**：20 前景类 + 背景，1449 张测试图。
- **PASCAL Context**：59 前景类 + 背景，5104 张测试图。
- **COCO**：80 前景类 + 背景，5000 张测试图。

### 对比方法
| 类别 | 方法（无标注） | 方法（有标注） |
|------|----------------|----------------|
| 无掩码标注训练 | CLIP, MaskCLIP, ViL-Seg, CLIPpy, GroupViT, SegCLIP, OVSegmentor, TCL, SAM-CLIP | ZS3Net, LSeg, OpenSeg, ZegFormer, GKC, ODISE, DeOp, OVSeg, SAN, FC-CLIP, SED, CAT-Seg |
| 全监督基线 | DeepLabV3+, MaskFormer | - |

### 评价协议
1. **带背景评估**（标准无标注方法）：背景通过阈值处理。
2. **无背景评估**（有标注方法常用）：排除背景像素，仅在前景类上计算 mIoU。

---

## 4. 资源与算力

论文**未明确说明**使用的 GPU 型号、数量或训练时长。仅在实现细节中提到训练分辨率 448×448，最大训练数据量 26M 对，但未提及硬件配置。因此无法给出具体算力消耗。

---

## 5. 实验数量与充分性

论文进行了以下多组实验，覆盖了不同维度的评估：

| 实验类型 | 具体内容 | 充分性 |
|----------|----------|--------|
| 主实验（带背景） | 在 3 个数据集上与 11 种无标注方法对比 | 充分，包含所有主流基准 |
| 主实验（无背景） | 与 13 种有标注方法对比（含全监督） | 充分，体现了与复杂方法的竞争性 |
| 简单基线对比 | 验证“伪掩码+CLIP”和“伪掩码ViT”均远不如 S-Seg | 有力论证了联合训练的必要性 |
| 消融：伪掩码生成器 | 比较 oracle mIoU 和速度（vs. K-Means/谱聚类/GroupViT） | 明确，验证设计有效性 |
| 消融：自训练 | 3 个数据集 × 3 个数据量，共 9 组对比，均有提升 | 系统、可靠 |
| 消融：数据规模 | 3 种数据量（12M/15M/26M），3 个数据集，共 9 组 | 证明了可扩展性 |
| 定性结果 | 提供多张可视化对比（与 CLIP/MaskCLIP/GroupViT） | 补充展示优势 |

总体而言，实验设计较全面，对比公平（遵循官方或已有协议），消融覆盖关键组件，**充分且客观**。

---

## 6. 主要结论与发现

- S-Seg **完全不依赖 CLIP、SAM、人工标注掩码或自定义分组编码器**，在开放词汇语义分割上取得具有竞争力的结果。
- 在带背景协议下，S-Seg 在 3 个数据集上平均 mIoU 37.1%，与依赖 SAM 的 SAM-CLIP（40.4%）差距不大，远超 GroupViT（34.0%）。
- S-Seg+（自训练）平均提升 5.5% mIoU，达到 42.6%，接近甚至超越部分使用 SAM 的方法。
- 数据规模从 12M 增至 26M 时，S-Seg 和 S-Seg+ 持续提升，表明方法**具有良好的可扩展性**。
- 伪掩码生成简而有效，DINO + K-means 在速度和精度上均优。
- 提出的简单方案表明**对复杂组件（CLIP/SAM）的依赖可能并非必需**，为后续研究提供了简洁基线。

---

## 7. 优点

- **极简设计**：仅用 MaskFormer + DINO + 对比学习，无需 CLIP、SAM、Frozen encoder 等庞然大物，易于复现和扩展。
- **弱监督/无监督**：仅使用公开图像-文本对，无需任何像素级标注，大幅降低数据成本。
- **直接像素-语言对齐**：避免了先做图像级对齐再微调的间接步骤，更高效。
- **灵活性**：子模块可替换（如伪掩码生成、文本编码器），可集成更先进技术。
- **自训练策略简单有效**：无需额外人工标注，利用测试集伪标签即可稳定提升。
- **实验覆盖全面**：在多个基准和协议下对比，消融充分，结论可靠。
- **开源计划**：论文承诺公开代码和 demo，利于社区复现和后续研究。

---

## 8. 不足与局限

- **伪掩码质量依赖预训练 DINO**：若 DINO 无法很好分离复杂场景或小物体，可能影响掩码监督质量。
- **自我训练可能引入偏差**：S-Seg+ 使用测试集伪标签，若基础模型存在系统性错误，自训练可能放大偏差。
- **未在更大规模数据集上验证**：最大 26M 数据，而 CLIP 使用 400M，ODISE 使用扩散模型等；在更具挑战的数据集（如 ADE20K）上表现未知。
- **背景处理简单**：采用阈值法，对背景类多样性处理不够精细，可能限制在背景丰富的场景下的性能。
- **缺乏与最新最强方法（如 FC-CLIP、CAT-Seg）的直接对比**：这些方法使用了更多标注或更大的预训练模型，但 S-Seg 在没有它们的情况下已表现不错，仍属竞争短板。
- **未提供训练资源细节**：缺少 GPU 型号/数量/时间，影响复现性评估。
- **文本编码器规模较小**：12 层 256 维，相比 CLIP 文本分支可能容量不足，制约开放词汇能力。

（完）
