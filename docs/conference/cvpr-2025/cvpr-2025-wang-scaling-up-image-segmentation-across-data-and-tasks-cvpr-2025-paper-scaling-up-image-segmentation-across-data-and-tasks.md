---
title: Scaling up Image Segmentation across Data and Tasks
title_zh: 跨数据与任务的图像分割规模化
authors: "Wang, Pei, Cai, Zhaowei, Yang, Hao, Swaminathan, Ashwin, Manmatha, R., Soatto, Stefano"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_Scaling_up_Image_Segmentation_across_Data_and_Tasks_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 可扩展的分割框架，采用动态查询融合机制
tldr: 针对传统分割模型难以泛化到开放场景的局限，本文提出QueryMeldNet分割框架，通过动态对象查询融合机制（query meld）将不同类型查询以交叉注意力融合，实现跨数据与任务的可扩展分割。该方法在多种分割任务上提升了泛化能力，为多模态语义分割提供了通用基础架构。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1688, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 724, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1556, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1800, \"height\": 1077, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1332, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-scaling-up-image-segmentation-across-data-and-tasks-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1784, \"height\": 476, \"label\": \"Table\"}]"
motivation: 传统分割模型在孤立任务上有效，但难以泛化到复杂开放场景，亟需可跨数据与任务扩展的统一框架。
method: 提出QueryMeldNet，基于动态对象查询机制，通过交叉注意力融合实例级与类别级查询。
result: 在多个分割基准上取得领先性能，尤其在开放词汇场景中显著提升泛化能力。
conclusion: 动态查询融合是实现跨任务可扩展分割的有效途径，为视觉基础模型的应用提供了新范式。
---

## Abstract
Traditional segmentation models, while effective in isolated tasks, often fail to generalize to more complex and open-ended segmentation problems, such as free-form, open-vocabulary, and in-the-wild scenarios. To bridge this gap, we propose to scale up image segmentation across diverse datasets and tasks such that the knowledge across different tasks and datasets can be integrated while improving the generalization ability. QueryMeldNet, a novel segmentation framework, is introduced and designed to scale seamlessly across both data size and task diversity. It is built upon a dynamic object query mechanism called query meld, which fuses different types of queries using cross-attention. This hybrid approach enables the model to balance between instance- and stuff-level segmentation, providing enhanced scalability for handling diverse object types. We further enhance scalability by leveraging synthetic data-generating segmentation masks and captions for pixel-level and open-vocabulary tasks-drastically reducing the need for costly human annotations. By training on multiple datasets and tasks at scale, QueryMeldNet continuously improves performance as the volume and diversity of data and tasks increase. It exhibits strong generalization capabilities, boosting performance in open-set segmentation tasks SeginW by 7 points. These advancements mark a key step toward universal, scalable segmentation models capable of addressing the demands of real-world applications.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统图像分割模型（如语义、实例、全景分割等）通常针对单一任务或数据集设计，难以泛化到开放世界、自由形式、开放词汇等复杂场景。现有统一分割框架（如X-Decoder、OpenSeeD等）在跨任务和跨数据集的可扩展性上存在局限：X-Decoder使用可学习查询在实例分割上表现差；OpenSeeD需要严格区分“thing/stuff”类别，限制了数据集兼容性。
- **整体含义**：本文旨在设计一个可同时随数据规模和任务多样性扩展的分割模型，使知识跨任务和数据集融合，提升在真实开放场景中的泛化能力。作者提出MQ-Former（Mixed-Query Transformer），通过**混合查询（mixed query）**机制整合可学习查询和条件查询的优点，实现跨任务、跨数据集的统一训练，并利用合成数据进一步扩展。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
- 引入**混合查询（mixed query）**：将可学习查询（learnable queries，擅长“stuff”类大区域背景）与条件查询（conditional queries，擅长“thing”类局部实例）通过双查询交叉注意力（dual-query cross-attention）融合，实现动态、样本自适应的查询选择，无需硬性分配查询类型到特定类别或任务。
- 统一训练格式：所有数据集统一为三元组 `(image, annotations)`，每个标注包含 `(class label / text description, bounding box, mask)`，类标签可直接为自然语言，无需额外标注thing/stuff属性。
- 利用合成数据：用SAM生成合成掩码（将目标检测数据集转化为分割数据），用OFA-like模型生成对象级合成描述（扩展指代分割数据），低成本扩大训练规模。

### 2.2 关键技术细节
- **架构**：图像编码器+文本编码器（CLIP）+分割编码器+分割解码器（基于Mask DINO）。解码器使用混合查询（100个可学习+300个条件查询）。
- **混合查询机制**：每个解码层中，先进行条件→可学习交叉注意力，再进行可学习→条件交叉注意力，实现双向信息交换。匈牙利匹配时混合所有查询，不区分类型。
- **训练损失**：分类损失（focal loss，类嵌入与文本嵌入点积）、边界框损失（GIoU+L1）、掩码损失（generalized dice loss）。

### 2.3 公式/算法流程（文字说明）
- 数据集统一格式：`D = {(xi, yi)}`，其中每个 `yi` 包含多个 `(cj, bj, mj)`，`cj` 为文本。
- 总损失：`L = Σ Lc + Lb + Lm`，其中 `Lc` 为类嵌入与文本嵌入的focal loss，`Lb` 为GIoU+L1损失，`Lm` 为dice loss。
- 推理时：给定图像和文本提示（类别名或短语），模型输出对应的掩码、边界框和分类。

## 3. 实验设计：数据集、benchmark、对比方法

### 3.1 训练数据集
- **封闭集任务**：COCO（语义/实例/全景）、ADE20K（语义/全景）、LVIS（实例）、RefCOCO/RefCOCO+/RefCOCOg（指代分割）、HRSOD等6个前景分割数据集、Objects365和Visual Genome（目标检测，通过合成掩码转化为分割）。
- **合成数据**：COCO-syn（合成指代描述）、Objects365-syn-m（合成掩码）、Objects365-syn（合成掩码+描述）。
- **总规模**：约220万张图像、5700万个掩码标注，覆盖6种任务。

### 3.2 评估benchmark
- **封闭集**：COCO（PQ, Mask AP, Box AP）、ADE20K（mIoU, PQ）、RefCOCOg（mIoU）、UHRSD（前景分割MSE）。
- **开放集/开放词汇**：SeginW（25个数据集，Mask AP）、Pascal Context（mIoU）、BDD（mIoU）、ADE PC-59/459（mIoU）。

### 3.3 对比方法
- **通用模型**：Mask2Former、Mask DINO、UNINEXT、OneFormer、X-Decoder、OMG-Seg、DaTaSeg、OpenSeeD。
- **专业模型**：LAVT、PolyFormer（指代分割）、PGNet、InSPyReNet（前景分割）。
- **开放词汇**：LSeg+、SPNet、ZS3Net、MaskCLIP、GroupViT、OpenSeg、ODISE。

## 4. 资源与算力

论文未明确说明具体的GPU型号、数量及训练时长。仅在实验设置中提及“超参数遵循Mask DINO”，并使用了预训练的Swin Transformer和CLIP语言编码器。从规模（220万图像+5700万掩码）可推断训练成本较高，但文中未提供具体算力信息。

## 5. 实验数量与充分性

- **实验组数**：包含至少三类主要实验：
    - **查询策略消融**（Table 2）：3种查询（learnable, conditional, mixed）在3种数据/任务规模下的对比，共9组。
    - **数据/任务扩展消融**（Figure 6）：5组子图，分别展示数据扩展（指代分割、开放分割）、任务扩展（固定100K图像逐步增加任务）、同时扩展（两种任务下的性能曲线）。
    - **与SOTA对比**（Table 3）：封闭集和开放集共11个指标，对比15+方法。
    - **定性结果**：图7展示各任务的分割效果。
- **充分性**：实验设计较全面，覆盖了封闭集、开放集、开放词汇、指代分割、前景分割等多种场景，并验证了混合查询在不同规模下的优势。消融实验清晰证明了混合查询优于单一查询。但缺少对合成数据质量的分析（如伪掩码错误率）、不同查询比例的影响、以及推理速度的对比。

## 6. 论文的主要结论与发现

- **混合查询机制**显著提升跨任务可扩展性：在封闭集实例/全景/语义分割上均优于纯可学习或纯条件查询，尤其在开放词汇基准SeginW上提升6.3个点（相比纯可学习查询）。
- **数据与任务扩展**持续改进性能：在指代分割上，扩展数据（从0.1M到1.8M）使RefCOCOg mIoU从57.8提升至62.6；同时扩展数据与任务使SeginW Mask AP从33.2提升至43.2（利用合成数据）。
- **合成数据有效**：通过SAM生成掩码和OFA生成描述，可低成本扩增训练集，进一步将SeginW Mask AP提升4.6个点。
- **单一模型覆盖多任务**：MQ-Former在封闭集几乎持平或超越专业模型，在开放集达到SOTA（SeginW 43.4 Mask AP）。

## 7. 优点：方法或实验设计亮点

- **创新点**：
    - 混合查询机制巧妙结合两种查询的互补优势，无需硬性分配，实现动态自适应。
    - 统一训练格式避免thing/stuff标注，兼容指代分割等自由形式任务。
    - 利用合成数据低成本扩展，有效缓解标注瓶颈。
- **实验设计**：
    - 逐步扩展实验（从1数据集1任务到多个数据集多个任务）清晰地验证了可扩展性。
    - 对比了与X-Decoder、OpenSeeD等当前主流统一模型的性能，且在同一实验设置下比较。
    - 在SeginW开放词汇基准上大幅领先（43.4 vs X-Decoder 32.3），证明了泛化能力。

## 8. 不足与局限

- **算力未公开**：缺少GPU型号、数量及训练时长，难以评估实际训练成本。
- **合成数据质量未分析**：未对SAM生成的伪掩码或OFA生成的描述的准确性进行定量评估，可能存在噪声影响下游性能。
- **查询比例固定**：混合查询默认100可学习+300条件，未消融不同比例的影响。
- **推理速度缺失**：未报告模型参数量或推理时间，实际部署效率不明。
- **开放集评测局限**：SeginW虽包含25个数据集，但可能对某些罕见类别或域外场景仍有偏倚；未在自动驾驶等特定领域充分验证。
- **指代分割性能**：RefCOCOg mIoU 68.2仍低于专业模型（如LAVT 63.3？实际对比显示MQ-Former为68.2，但表3中LAVT为63.3，MQ-Former更高，但文中未讨论专业模型如PolyFormer的71.2，可能因模型设定不同）。说明在单一任务上可能不如最佳专用模型。
- **可解释性**：混合查询的动态选择机制（图5）虽然展示了趋势，但未提供量化分析（如切换频率、置信度）。

（完）
