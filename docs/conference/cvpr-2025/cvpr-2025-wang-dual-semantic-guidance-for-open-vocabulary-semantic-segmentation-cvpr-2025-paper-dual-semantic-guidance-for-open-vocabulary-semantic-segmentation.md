---
title: Dual Semantic Guidance for Open Vocabulary Semantic Segmentation
title_zh: 开放词汇语义分割的双语义引导
authors: "Wang, Zhengyang, Feng, Tingliang, Lyu, Fan, Shang, Fanhua, Feng, Wei, Wan, Liang"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_Dual_Semantic_Guidance_for_Open_Vocabulary_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 基于CLIP引导的开放词汇语义分割
tldr: 本文针对开放词汇语义分割中仅依靠文本引导的偏差，提出从图像和文本双向捕获语义信息的双语义引导方法，在多个基准上取得最优性能，有效提升了CLIP模型在像素级识别上的微调效果。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1787, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1793, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1783, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1796, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1793, \"height\": 576, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1785, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 886, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 890, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 900, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 896, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-dual-semantic-guidance-for-open-vocabulary-semantic-segmentation-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 895, \"height\": 281, \"label\": \"Table\"}]"
motivation: 现有方法仅利用文本引导存在语义偏差，且缺乏像素级监督信息。
method: 同时利用图像和文本中的语义信息构造双语义引导，对CLIP模型进行微调。
result: 在多个开放词汇分割数据集上达到新高度。
conclusion: 双语义引导能有效提升CLIP在像素级任务上的表现。
---

## Abstract
Open-vocabulary semantic segmentation aims to enable models to segment arbitrary categories. Currently, though pre-trained Vision-Language Models (VLMs) like CLIP have established a robust foundation for this task by learning to match text and image representations from large-scale data, their lack of pixel-level recognition necessitates further fine-tuning. Most existing methods leverage text as a guide to achieve pixel-level recognition. However, the inherent biases in text semantic descriptions and the lack of pixel-level supervisory information make it challenging to fine-tune CLIP-based models effectively. This paper considers leveraging image-text data to simultaneously capture the semantic information contained in both image and text, thereby constructing Dual Semantic Guidance and corresponding pixel-level pseudo annotations. Particularly, the visual semantic guidance is enhanced via explicitly exploring foreground regions and minimizing the influence of background. The dual semantic guidance is then jointly utilized to fine-tune CLIP-based segmentation models, achieving decent fine-grained recognition capabilities. As the comprehensive evaluation shows, our method outperforms state-of-art results with large margins, on eight commonly used datasets with/without background.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
开放词汇语义分割（OVSS）的目标是分割任意类别，区别于传统固定类别分割。预训练的视觉-语言模型（如CLIP）通过大规模图文匹配学习，奠定了开放词汇识别的基础，但缺乏像素级识别能力。现有方法大多仅利用文本作为引导进行微调，面临两个关键问题：一是文本语义描述存在**固有偏差**（例如粗粒度名词“动物”无法区分“猫”和“狗”）；二是缺乏像素级监督信息，导致粗糙或错误的分割结果仍能与文本匹配。本文提出**双语义引导**，同时从图像和文本中提取语义信息，生成更细粒度的像素级伪标签，从而有效微调CLIP模型，提升细粒度分割能力。

### 2. 论文提出的方法论
- **核心思想**：利用图像-文本对，从视觉和文本两个维度构建语义引导，并生成对应的像素级伪标签，协同指导模型训练。
- **关键技术细节**：
  - **双语义引导生成（DSGG）**：
    - 视觉引导：使用SAM生成初始实例掩码，通过**区域感知注意力（RAA）** 增强前景区域特征，抑制背景干扰；再经K-means聚类和筛选，得到K_v个独立的视觉语义引导及其伪掩码。
    - 文本引导：从文本中提取名词，经文本编码，并与视觉引导匹配（过滤阈值T_A=0.8, T_B=36），得到K_t个文本语义引导及其伪掩码。
  - **区域感知注意力（RAA）**：构造两个注意力矩阵——**Patch Awareness Matrix**（增强前景区域内部自注意力）和**Class Awareness Matrix**（增强类别token对前景区域的关注），在注意力层添加偏置，使模型聚焦于前景。
  - **双语义引导分割（DSGS）**：
    - 使用MaskCLIP的图像编码器提取特征图。
    - 对文本引导：采用**掩码特征对比损失（MFC Loss）**，拉近区域内平均特征与对应文本引导的距离，同时推离负样本。
    - 对视觉引导：采用**引导增强（Guidance Enhance）**，通过相似度加权平均将像素特征与视觉引导融合，作为更优的优化方向，再配合BCE损失。
    - **背景筛选模块**：结合特征图和语义引导，通过Transformer解码器从空间和类别维度联合预测背景区域，优于固定阈值方法。
- **训练损失**：总损失L = λ_I * L_BCE(图像) + λ_T * L_BCE(文本) + L_MFC + L_BCE(背景)，λ_I=2.5，λ_T=2.0。

### 3. 实验设计
- **训练数据集**：CC3M（300万对），随机采样10%（约30万对）进行训练。
- **评估数据集**：8个常用语义分割数据集，其中3个**有背景**（VOC21、Context60、COCO Object），5个**无背景**（VOC20、Context59、COCO Stuff、ADE20K、Cityscapes）。评价指标为mIoU。
- **对比方法**：包括TCL、CoDe、CLIP-DINOiser、PixelCLIP、GroupViT、SegCLIP、PGSeg等10余种SOTA方法，所有结果均无后处理（如PAMR、DenseCRF）。

### 4. 资源与算力
论文明确说明：
- **GPU**：2块NVIDIA RTX 3090
- **训练时长**：约5小时
- **超参数**：batchsize=128，初始学习率6.4e-4，训练30000次迭代，额外再用文本引导单独训练1000次迭代，采用余弦学习率调度、AdamW优化器（weight decay=0.05）。

### 5. 实验数量与充分性
- **主要对比实验**：表1覆盖8个数据集，与13种方法公平对比，结果均无后处理。
- **消融实验**：共6组（表2-6）：
  - DSGG各阶段消融（初始过滤、RAA、聚类）
  - RAA组件消融（Patch Attention、Class Attention、不同阶段设置）
  - 双引导分割组件消融（视觉/文本引导、MFC Loss、Guidance Enhance）
  - RAA替代方案比较（Gaussian噪声、背景掩码、可学习类token、mask pooling）
  - MFC Loss替代方案比较（MSE、TCL损失、不同池化方式）
- **充分性**：实验设计系统，对核心模块逐一验证，替代方案对比公平，消融结果与主实验结论一致，证明方法有效。但未进行更大规模数据集（如完整CC3M）或不同骨干网络的测试，略有局限。

### 6. 论文的主要结论与发现
- 双语义引导方法在8个数据集上均取得SOTA结果：有背景数据集平均mIoU达48.3%（较次优提升5.2%），无背景数据集平均42.8%（提升6.1%）。
- 视觉引导更适合无背景场景（能提供更细粒度、无偏的语义），文本引导更适合有背景场景（与推理阶段类别名模态一致），两者结合发挥协同优势。
- RAA能有效抑制背景干扰，大幅提升实例特征提取质量；MFC Loss和Guidance Enhance分别优化文本和视觉引导的训练过程。
- 背景筛选模块基于特征图与语义引导的联合推理，优于简单阈值判断。

### 7. 优点
- **创新性**：首次同时利用图像实例和文本名词构建双语义引导，克服了单一文本引导的语义偏差和缺乏像素级监督的问题。
- **技术亮点**：
  - RAA模块无需额外训练，通过注意力偏置引导模型关注前景，效率高且有效。
  - MFC loss针对文本引导的语义漂移设计，结合正负样本约束。
  - Guidance Enhance融合像素级相似度，使视觉引导成为更准确的优化方向。
  - 背景筛选模块利用Transformer解码器，融合空间和语义信息，比阈值方法更鲁棒。
- **公平性和泛化性**：在8个不同规模、不同类别数的数据集上验证，结果全面；与SOTA对比均无后处理，保证了公平。

### 8. 不足与局限
- **计算开销**：DSGG依赖SAM生成大量掩码，虽为离线但耗时，且K-Means聚类K值固定为5（可能不适用于所有图像）。
- **分割边界**：可视化结果显示分割边界仍然粗糙，与密集监督方法存在差距。
- **实验覆盖**：仅使用CC3M的10%进行训练，未探索更大数据量或不同训练设置下的性能；骨干网络仅用ViT-B/16，未测试其他规模。
- **模式局限**：训练时使用了视觉引导，但推理时仅使用文本和图像编码器，存在模态不一致（作者通过最后1000次文本单独训练缓解，但未完全消除）。
- **偏差风险**：对SAM生成的实例质量敏感，若SAM产生错误掩码可能引入噪声；K-Means聚类可能将语义相近但不同的实例合并，造成类别混淆。

（完）
