---
title: Effective SAM Combination for Open-Vocabulary Semantic Segmentation
title_zh: 高效SAM组合用于开放词汇语义分割
authors: "Lee, Minhyeok, Cho, Suhwan, Lee, Jungho, Yang, Sunghun, Choi, Heeseung, Kim, Ig-Jae, Lee, Sangyoun"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Lee_Effective_SAM_Combination_for_Open-Vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: SAM与CLIP结合用于开放词汇语义分割
tldr: 现有开放词汇语义分割两阶段方法（SAM+CLIP）计算和内存效率低。本文提出ESC-Net，利用SAM解码器作为类无关分割模块，并通过图像-文本相关性生成伪提示嵌入到SAM框架中，实现单阶段高效推理。实验表明该方法在多个基准上取得优异分割精度且推理更快。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1815, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1792, \"height\": 928, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1799, \"height\": 1040, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 874, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lee-effective-sam-combination-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 265, \"label\": \"Table\"}]"
motivation: 两阶段SAM+CLIP方法计算和内存效率低下。
method: 提出ESC-Net，单阶段集成SAM解码器与伪提示嵌入。
result: 在多个开放词汇分割基准上实现高效高精度。
conclusion: 单阶段SAM融合可有效提升开放词汇分割效率。
---

## Abstract
Open-vocabulary semantic segmentation aims to assign pixel-level labels to images across an unlimited range of classes. Traditional methods address this by sequentially connecting a powerful mask proposal generator, such as the Segment Anything Model (SAM), with a pre-trained vision-language model like CLIP. But these two-stage approaches often suffer from high computational costs, memory inefficiencies. In this paper, we propose ESC-Net, a novel one-stage open-vocabulary segmentation model that leverages the SAM decoder blocks for class-agnostic segmentation within an efficient inference framework. By embedding pseudo prompts generated from image-text correlations into SAM's promptable segmentation framework, ESC-Net achieves refined spatial aggregation for accurate mask predictions. Additionally, a Vision-Language Fusion (VLF) module enhances the final mask prediction through image and text guidance. ESC-Net achieves superior performance on standard benchmarks, including ADE20K, PASCAL-VOC, and PASCAL-Context, outperforming prior methods in both efficiency and accuracy. Comprehensive ablation studies further demonstrate its robustness across challenging conditions.

---

## 论文详细总结（自动生成）

## 论文结构化总结：Effective SAM Combination for Open-Vocabulary Semantic Segmentation

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：开放词汇语义分割旨在对任意类别进行像素级标注。现有主流方法采用两阶段 pipeline：先使用 SAM 等强大的掩码提议生成器进行类无关预分割，再使用 CLIP 对每个区域分类。但这类方法存在两大缺陷：**高计算/内存开销**（需运行完整 SAM 图像编码器）以及**域偏移**（裁剪区域与 CLIP 训练数据分布不一致，且包含背景干扰）。
- **整体含义**：本文提出一种单阶段模型 ESC-Net，将 SAM 的类无关分割能力以伪提示（pseudo prompts）方式嵌入到 CLIP 的视觉-语言相关建模流程中，**避免了两阶段的高成本和域偏移**，同时获得比纯相关方法更精确密集的掩码预测。

### 2. 方法论：核心思想与关键技术细节
- **核心思想**：利用 CLIP 生成的图像-文本相关性图作为先验，通过 Pseudo Prompt Generator (PPG) 生成每个类别对应的伪坐标点和伪掩码，将其作为 SAM 的提示输入；随后使用预训练的 SAM 解码器块对 CLIP 图像特征进行空间聚合，再通过 Vision-Language Fusion (VLF) 模块细化相关性图，最终解码出分割掩码。
- **关键技术细节**：
  - **视觉-语言相关性计算**：对 CLIP 图像特征 \(F_v \in \mathbb{R}^{C \times H \times W}\) 与文本特征 \(F_l \in \mathbb{R}^{C \times N_c}\) 计算余弦相似度，得到相关性图 \(C_{v\&l} \in \mathbb{R}^{N_c \times H \times W}\)。
  - **Pseudo Prompt Generator (PPG)**：对每个类别的相关性图做 softmax 得到概率图，阈值二值化，k-means 聚类得到多个物体区域，从每个区域提取概率最大的点作为伪点，区域掩码作为伪掩码；每个类别生成 \(N_0=5\) 组提示。
  - **SAM 块**：采用预训练的 SAM 解码器变换器块，输入提示特征（来自 SAM 提示编码器）和 CLIP 图像特征，通过自注意力和双向交叉注意力更新图像特征 \(F_v'\)；整个过程对 \(N_c\) 个类别的提示进行批处理。
  - **Vision-Language Fusion (VLF) 模块**：将修正后的图像特征 \(F_v'\) 与相关性图 \(C_{v\&l}\) 拼接，通过 Swin Transformer 块得到视觉相关性；再以文本特征为 K/V 进行线性注意力，显式建模类别间关系，生成细化的相关性图 \(C_{v\&l}'\)。
  - **解码器**：使用 U-Net 风格的上采样层（双线性插值+3×3卷积），并利用 CLIP 图像编码器特征作为跳跃连接。
- **公式/算法流程**（文字说明）：
  1. 输入图像 \(I\) 和文本 \(T\)，经 CLIP 编码器得 \(F_v, F_l\)。
  2. 计算 \(C_{v\&l}\)（余弦相似度）。
  3. 对每个类别 \(n\)，PPG 生成伪点集合和伪掩码，经 SAM 提示编码器得 \(P_{\text{sparse}}^n, P_{\text{dense}}^n\)。
  4. SAM 块以 \(F_v\) 和提示为输入，输出聚合后的 \(F_v'\)。
  5. VLF 模块以 \(C_{v\&l}, F_v', F_l\) 为输入，输出 \(C_{v\&l}'\)。
  6. 重复步骤 3–5 共 \(N=4\) 次（ESC-Block）。
  7. 最终解码器生成预测掩码 \(M\)。

### 3. 实验设计
- **训练数据集**：COCO-Stuff（约118k 图像，171 个语义类别）。
- **评估基准**：
  - ADE20K：A-150（150 类）、A-847（847 类）
  - PASCAL-VOC：PAS-20（20 类）、PAS-20b（不含背景）
  - PASCAL-Context：PC-59（59 类）、PC-459（459 类）
- **对比方法**：包括两阶段方法（ZegFormer、ZSseg、OVSeg、ODISE 等）和单阶段方法（CAT-Seg、SAN、SCAN、EBSeg、SED、MAFT+ 等），按 VLM 类型（ViT-B/16 和 ViT-L/14）分别比较。
- **评价指标**：平均交并比（mIoU）。

### 4. 资源与算力
- **训练平台**：4 块 NVIDIA RTX A6000 GPU，PyTorch 框架。
- **关键超参数**：输入分辨率 336×336，CLIP 编码器和 SAM 块学习率 2×10⁻⁶，其余部分 2×10⁻⁴，优化器 AdamW。
- **未明确说明**：总训练时长、训练迭代次数、batch size 等未在文中给出。

### 5. 实验数量与充分性
- **主要结果**：表 1 展示了在两个 VLM 规模下多个数据集上的定量对比，涵盖共 8 项评估子集，与约 15 种现有方法比较。
- **消融实验**：
  - 表 2：SAM 块的有效性（无 SAM、随机初始化、预训练 SAM）。
  - 表 3：伪提示组合（点、边界框、掩码）的影响。
  - 图 6：可视化不同 ESC-Block 下的相关性激活图，对比有无 SAM 块。
  - 表 4：模型效率（参数量、推理时间、GFLOPs）与 CAT-Seg 等方法对比。
- **充分性评价**：实验覆盖了主流基准、多种消融设置，并提供了效率分析，对比公平（与相同 VLM 规模的方法比较）。消融实验直接验证了核心设计（SAM 块、伪提示类型）的必要性。结论充分可信。

### 6. 主要结论与发现
- ESC-Net 在 **ADE20K、PASCAL-VOC、PASCAL-Context** 所有子集上均达到 **新的最佳性能**，相比之前 SOTA（CAT-Seg、MAFT+）有显著提升，例如 A-847 上 +2.1 mIoU、PC-459 上 +3.2 mIoU。
- 与单阶段方法 CAT-Seg 相比，ESC-Net 的推理 GFLOPs 和参数量相当（2,203.5 vs 2,121.1 GFLOPS），但性能大幅超越。
- 预训练 SAM 块的引入是性能提升的关键（表 2）；使用点和掩码作为伪提示组合最佳（表 3）。
- 可视化表明 ESC-Net 能生成更准确、更密集的掩码，尤其对多尺度物体和复杂背景鲁棒。

### 7. 优点（方法/实验设计亮点）
- **单阶段高效**：无需额外运行 SAM 图像编码器，计算开销接近纯相关方法，但利用了 SAM 的强空间聚合能力。
- **伪提示机制创新**：从相关性图自动生成类感知的点和掩码提示，使 SAM 块在无需显式分割边界的情况下获得位置先验。
- **VLF 模块**：同时利用视觉和文本特征对相关性图进行双路细化，提升多类预测的判别力。
- **实验全面**：涵盖多种类别数量的基准，显示方法在稀疏/密集分类场景均有效；消融实验设计逻辑清晰，验证了各组件的贡献。
- **公平对比**：明确区分 VLM 规模、额外骨干网络和训练数据，在同等条件下进行性能比较。

### 8. 不足与局限
- **低分辨率限制**：CLIP 特征分辨率较低（336×336 输入下的特征图），导致预测掩码的边界细节不够精细，难以媲美基于高分辨率掩码提议的两阶段方法。
- **内存随类别数增长**：相关性图 \(C_{v\&l}\) 的大小与类别数 \(N_c\) 和空间分辨率成正比，当类别数极大（如 A-847）时，内存占用显著增加，可能限制实际应用。
- **未报告更长训练或更高分辨率实验**：论文仅默认使用 336×336，未探索更大输入尺寸或更长训练对性能的影响；训练资源和时长细节缺失，影响可复现性。
- **依赖预训练质量**：CLIP 和 SAM 均来自外部预训练模型，其质量直接影响 ESC-Net 的上限；若领域差异过大，伪提示生成可能失效。

（完）
