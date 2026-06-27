---
title: Distilling Spectral Graph for Object-Context Aware Open-Vocabulary Semantic Segmentation
title_zh: 提炼谱图实现目标上下文感知的开放词汇语义分割
authors: "Kim, Chanyoung, Ju, Dayun, Han, Woojung, Yang, Ming-Hsuan, Hwang, Seong Jae"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Kim_Distilling_Spectral_Graph_for_Object-Context_Aware_Open-Vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 利用谱图实现目标上下文感知的开放词汇语义分割
tldr: 针对开放词汇语义分割缺乏目标级上下文导致复杂目标分割不佳的问题，本文引入谱图提炼方法，将目标级上下文融入分割过程，增强模型在任意查询提示下对语义一致元素的聚类和精确定位能力，提升开放词汇分割性能。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 938, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1791, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1807, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 865, \"height\": 640, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1800, \"height\": 826, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kim-distilling-spectral-graph-for-object-context-aware-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 266, \"label\": \"Table\"}]"
motivation: 开放词汇语义分割缺乏目标级上下文考虑。
method: 引入谱图提炼方法，融入目标级上下文信息。
result: 提升复杂目标的分割能力。
conclusion: 为开放词汇语义分割提供上下文感知方案。
---

## Abstract
Open-Vocabulary Semantic Segmentation (OVSS) has advanced with recent vision-language models (VLMs), enabling segmentation beyond predefined categories through various learning schemes. Notably, training-free methods offer scalable, easily deployable solutions for handling unseen data, a key goal of OVSS. Yet, a critical issue persists: lack of object-level context consideration when segmenting complex objects in the challenging environment of OVSS based on arbitrary query prompts. This oversight limits models' ability to group semantically consistent elements within object and map them precisely to user-defined arbitrary classes. In this work, we introduce a novel approach that overcomes this limitation by incorporating object-level contextual knowledge within images. Specifically, our model enhances intra-object consistency by distilling spectral-driven features from vision foundation models into the attention mechanism of the visual encoder, enabling semantically coherent components to form a single object mask. Additionally, we refine the text embeddings with zero-shot object presence likelihood to ensure accurate alignment with the specific objects represented in the images. By leveraging object-level contextual knowledge, our proposed approach achieves state-of-the-art performance with strong generalizability across diverse datasets.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有开放词汇语义分割（OVSS）方法，尤其是训练免费（training-free）的方法，在分割复杂物体时缺乏**目标级上下文**（object-level context）考虑。模型无法将属于同一物体的不同部件（如卡车车轮、车身、货箱）统一分割为一个语义实体，而是常常将它们分散或错分到相近类别。这一缺陷源于CLIP视觉编码器主要学习全局图像语义，对密集的物体级语义关系捕捉不足。
- **背景**：OVSS旨在对用户任意指定的类别（如专有名词“Space Needle”）进行像素级分割。训练免费方法无需额外标注数据，可扩展性强，更契合OVSS的泛化目标。然而，现有训练免费方法（如CLIP、MaskCLIP、SCLIP、NACLIP、ProxyCLIP等）在物体级语义一致性上表现不佳，限制了真实场景中的实用性。

## 2. 方法论：核心思想、关键技术细节与算法流程
- **核心思想**：将视觉基础模型（VFM，如DINO）中蕴含的物体级上下文知识，通过谱图蒸馏的方式注入CLIP的注意力机制，同时利用CLIP的零样本物体分类能力（物体存在先验）调整文本嵌入和补丁-文本相似度，从而在不需要额外训练的情况下，增强对同一物体内部一致性的分割。
- **关键技术细节**：
  1. **谱图目标级上下文蒸馏（Spectral Object-Level Context Distillation）**：
     - 将VFM的注意力图视作图结构（`A_VFM`），CLIP的注意力图（`A_CLIP`）也视为图。
     - **互补谱图匹配**：对每个注意力头分别做特征分解得到特征值，用Wasserstein距离构造代价矩阵，通过匈牙利算法匹配VFM头与CLIP头中结构对比最鲜明的头对，使得VFM能够补充CLIP缺乏的物体级上下文。
     - **低秩动态特征缩放**：对VFM的注意力图进行低秩近似（基于能量占比选择前k个特征值），并应用动态特征缩放函数`φ(·)`，放大较大特征值（突出物体结构），抑制噪声。
     - **蒸馏聚合**：将缩放后的VFM低秩图与CLIP图按互补权重（Wasserstein距离）加权融合，得到增强后的注意力图`A_ψ`，替换原CLIP的注意力矩阵用于后续特征计算。
  2. **物体存在先验驱动的物体级上下文（Object Presence-Driven Object-Level Context）**：
     - **文本嵌入调整**：利用CLIP全局图像特征计算每个类别的物体存在先验概率`P(i)`。在层次聚类后的同类组内，选出置信度最高的类别，并用其对应的补丁特征均值引导该文本嵌入向物体特异性方向微调，避免物体部件被分到模糊类别。
     - **补丁-文本相似度精炼**：将物体存在先验（来自全图）与窗口级的补丁-文本相似度`Ŝ`加权融合，得到最终相似度`Ŝ*`，使分割图更具物体视角的全局一致性。
- **算法流程简示**：
  - 输入图像 → 切分为滑动窗口 → 分别通过VFM和CLIP视觉编码器 → 提取注意力图 → 谱图匹配与低秩蒸馏 → 得到增强注意力 → 计算视觉特征 → 结合CLIP文本编码器 → 文本嵌入调整 + 相似度精炼 → 输出分割图。

## 3. 实验设计
- **数据集**：共8个常用语义分割数据集，包括：
  - PASCAL VOC 2012（带背景V21，无背景V20）
  - PASCAL Context（带背景PC60，无背景PC59）
  - COCO（带背景C-Obj，无背景C-Stf）
  - ADE20K（ADE）
  - Cityscapes（City）
- **Benchmark**：与传统训练免费方法对比，同时与使用额外支撑数据集或微调的方法（如GroupViT、TCL、CLIP-DINOiser等）对比，但公平比较列中仅标记“Fair”（表示与CASS相同的无额外训练/数据设置）。
- **对比方法**：
  - 无额外训练/数据：CLIP、MaskCLIP、GEM、CaR、PNP-OVSS、CLIPtrase、ClearCLIP、SCLIP、LaVG、ProxyCLIP、NACLIP等。
  - 使用额外数据：GroupViT、TCL、CoDe、CLIP-DINOiser、ReCo、FOSSIL、FreeDa等。
- **主要指标**：平均IoU（mIoU）、像素准确率（pAcc）。

## 4. 资源与算力
- 论文提及所有实验在**NVIDIA RTX A6000 Ada**显卡上完成，但未明确说明使用的显卡数量、训练时长（因方法为训练免费，仅需推理时间），也未提供具体推理耗时。

## 5. 实验数量与充分性
- **实验数量**：主表（Table 1）包含14种对比方法在8个数据集上的mIoU；Table 2为pAcc对比；另设消融实验（Table 3）分析各组件贡献（共8组实验，逐步增减模块）；Fig.7为可视化消融；Fig.8比较不同距离度量；Table 4验证不同CLIP骨干（ViT-B/32、ViT-L/14）。总共约20+组实验/图表。
- **充分性**：覆盖了主流多领域数据集（通用物体、街景、室内等），消融实验拆解了蒸馏、低秩、特征缩放、物体先验各模块。对比方法全面，包括近年SOTA。实验设置公平（统一窗口大小、不采用后处理）。**充足且客观**。

## 6. 主要结论与发现
- CASS在8个数据集上的平均mIoU达44.4%，超越第二名3.0个百分点；在V20上提升5.3个百分点，显著改进对复杂物体的分割一致性。
- 光谱蒸馏有效提高了CLIP的注意力聚焦度，低秩动态缩放进一步滤除噪声并突出物体结构。
- 物体存在先验驱动的文本调整和相似度精炼能纠正物体部件错分，使分割图更符合物体级语义。
- 方法在多个CLIP骨干上一致优于现有方法，鲁棒性强。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将谱图（spectral graph）技术用于训练免费OVSS，通过图匹配和低秩蒸馏巧妙地将VFM的物体级上下文注入CLIP，无需额外训练。
- **有效性**：在多个数据集上显著提升mIoU和pAcc，尤其改善细长部件（如人臂、动物腿）的分割。
- **互补性**：通过图匹配选取结构对比最强的头对进行蒸馏，最大化互补信息；低秩动态缩放而非简单截断，更精细化保留物体结构。
- **实验公平性**：严格控制窗口大小、不使用后处理（如PAMR/DenseCRF），与基线在同一设置下对比，结果可信。
- **稳健性**：不同骨干、不同距离度量下均保持优势。

## 8. 不足与局限
- **实验覆盖**：未报告在更大尺度或视频场景下的泛化能力；未与其他视觉基础模型（如SAM）结合尝试。
- **偏差风险**：依赖CLIP的零样本分类先验，若CLIP本身对某些罕见类别偏见强，可能影响文本调整效果。
- **应用限制**：滑动窗口推理计算量较大（需多次前向），实时性可能受限；方法虽为训练免费，但仍需两阶段特征提取（VFM+CLIP），对算力仍有要求。
- **未提供的细节**：论文补全材料声称给出k选取动态特征缩放细节，但摘要中未完全展示；未讨论对噪声或遮挡场景的鲁棒性。
- **与有监督方法差距**：尽管在训练免费中SOTA，但与使用额外标注的完全监督方法相比仍有不小差距（如GroupViT等使用大规模图文预训练，但CASS仍优于它们）。

（完）
