---
title: "Exploring CLIP's Dense Knowledge for Weakly Supervised Semantic Segmentation"
title_zh: 探索CLIP的密集知识用于弱监督语义分割
authors: "Yang, Zhiwei, Meng, Yucong, Fu, Kexue, Tang, Feilong, Wang, Shuo, Song, Zhijian"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yang_Exploring_CLIPs_Dense_Knowledge_for_Weakly_Supervised_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 利用CLIP密集知识进行弱监督语义分割
tldr: 该论文提出ExCEL方法，探索CLIP在弱监督语义分割中的密集知识，通过新颖的块-文本对齐范式代替传统的图像-文本对齐。具体地，文本语义增强（TSE）模块利用大语言模型丰富文本嵌入，视觉校准（VC）模块改善视觉表示。ExCEL在多个基准上显著优于现有方法，证明了CLIP的块级知识在弱监督分割中的巨大潜力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1798, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1801, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 878, \"height\": 313, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 881, \"height\": 857, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 870, \"height\": 856, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 876, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 876, \"height\": 560, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-exploring-clips-dense-knowledge-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 873, \"height\": 444, \"label\": \"Table\"}]"
motivation: 现有CLIP-based WSSS方法仅利用图像-文本对齐，忽略了块-文本对齐的潜力。
method: 提出块-文本对齐范式，结合TSE和VC模块挖掘CLIP密集知识。
result: 在PASCAL VOC等数据集上达到弱监督语义分割的新先进水平。
conclusion: CLIP的块级知识可以显著提升弱监督分割性能，而不仅仅是图像级对齐。
---

## Abstract
Weakly Supervised Semantic Segmentation (WSSS) with image-level labels aims to achieve pixel-level predictions using Class Activation Maps (CAMs). Recently, Contrastive Language-Image Pre-training (CLIP) has been introduced in WSSS. However, recent methods primarily focus on image-text alignment for CAM generation, while CLIP's potential in patch-text alignment remains unexplored. In this work, we propose ExCEL to explore CLIP's dense knowledge via a novel patch-text alignment paradigm for WSSS. Specifically, we propose Text Semantic Enrichment (TSE) and Visual Calibration (VC) modules to improve the dense alignment across both text and vision modalities. To make text embeddings semantically informative, our TSE module applies Large Language Models (LLMs) to build a dataset-wide knowledge base and enriches the text representations with an implicit attribute-hunting process. To mine fine-grained knowledge from visual features, our VC module first proposes Static Visual Calibration (SVC) to propagate fine-grained knowledge in a non-parametric manner. Then Learnable Visual Calibration (LVC) is further proposed to dynamically shift the frozen features towards distributions with diverse semantics. With these enhancements, ExCEL not only retains CLIP's training-free advantages but also significantly outperforms other state-of-the-art methods with much less training cost on PASCAL VOC and MS COCO. Code is available at https://github.com/zwyang6/ExCEL.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题定义**：弱监督语义分割（WSSS）任务使用图像级标签（而非像素级标注）来训练分割模型，通常依赖类激活图（CAM）提供定位线索。然而，传统CAM往往只关注物体最判别性部分，定位不完整。
- **现有方法局限**：近期工作引入CLIP（对比语言-图像预训练）来提升WSSS性能，但主要聚焦于**全局图像-文本对齐**（如CLIMS、CLIP-ES、WeCLIP），而CLIP在**块（patch）与文本之间的密集对齐**能力尚未被充分挖掘。
- **本文动机**：提出ExCEL方法，旨在**探索CLIP的密集知识**，通过一种新颖的**块-文本对齐范式**来生成更精确的CAM，进而提升WSSS性能，同时保持CLIP训练免费和低训练成本的优势。

## 2. 方法论：核心思想、关键技术细节、流程

### 核心思想
- 利用CLIP的视觉编码器和文本编码器进行**逐块（patch-wise）相似度计算**生成CAM（即 patch-text alignment），而非传统的全局图像-文本相似度。
- 为克服CLIP文本语义稀疏和视觉特征细粒度不足的问题，设计两个模块：**文本语义增强（TSE）** 和 **视觉校准（VC）**。

### 关键技术细节
- **TSE（文本语义增强）**：
  - 使用大语言模型（GPT-4）为每个类别生成n=20个详细描述（外观、颜色、形状等）。
  - 用CLIP文本编码器编码所有描述，构建**数据集级知识库**。
  - 对知识库进行K-means聚类（聚类数B=112/224），得到**隐式属性特征空间**（每个中心为一个属性）。
  - 输入全局文本模板（如“a photo of [CLASS]”）的嵌入 \( t_c \)，在属性空间中**搜索最相关的TOPK个属性**（属性狩猎），然后加权聚合为最终文本表示 \( T_c \)：
    \[
    T_c = t_c + \lambda \sum_{j=1}^{K} \text{softmax}(t_c^T A_c) a_j
    \]
  - 提升文本嵌入的语义丰富性和跨类别互补能力。

- **VC（视觉校准）**：
  - **SVC（静态视觉校准）**：用**内相关（Intra-correlation）** 操作替代原始CLIP中平滑化的q-k自注意力。在最后N=5个中间层，分别计算q、k、v自身的注意力图并加权求和，从而保留细粒度空间细节，避免特征同质化。得到静态校准特征 \( P_s \)。
  - **LVC（可学习视觉校准）**：在SVC基础上，设计一个**轻量适配器**（卷积+MLP），从CLIP各层冻结特征中学习一个**动态偏移项 \( R \)**（通过式(8)(9)生成动态token关系），叠加到SVC的注意力图上，实现特征分布动态偏移。同时使用**多样性损失 \( L_{div} \)**（基于SVC生成的静态伪标签像素亲和度）监督适配器学习，促使相似语义的token聚集、不相似的分开。
  - 最终动态校准特征 \( P_d \) 与增强文本 \( T_c \) 计算得到动态CAM。

- **总损失**：
  \[
  L_{ExCEL} = L_{seg} + \gamma L_{div}
  \]
  其中 \( L_{seg} \) 为分割交叉熵损失（使用动态CAM经后处理作为伪标签），\( \gamma=0.1 \)。

### 训练流程
1. 冻结CLIP编码器；2. TSE生成丰富文本表示；3. SVC生成静态CAM；4. LVC生成动态CAM及伪标签；5. 训练轻量适配器和分割头（Transformer-based）。

## 3. 实验设计：数据集、评估指标、对比方法

### 使用数据集
- **PASCAL VOC 2012**：增加后训练集10582、验证集1449、测试集1456张图像，共21类（含背景）。
- **MS COCO 2014**：训练集82081、验证集40137张图像，共81类。

### 评估指标
- **mIoU（平均交并比）**：主要评价指标。

### 对比方法
- **多阶段方法**：L2G、RCA、OCR、BECO、MCTformer+、CTI、CLIMS、CLIP-ES、PSDPM、CPAL等。
- **单阶段方法**：AFA、ViT-PCM、ToCo、DuPL、SeCo、DIAL、WeCLIP（最先进CLIP-based方法）等。
- 对比方式包括分割性能（Tab.1）和CAM种子质量（Tab.2），以及全监督基线（Tab.6）和训练效率（Tab.7）。

## 4. 资源与算力

- **硬件**：单张RTX 3090 GPU。
- **训练成本**：
  - 训练状态下：**仅90分钟**完成整个训练流程（包括CAM生成和分割头训练），GPU内存占用**3.2GB**。
  - 训练免费模式：无需训练，仅2.9GB内存即可生成CAM，且性能已超越多数需训练方法。
  - 相比之下，WeCLIP需270分钟、6.2GB；MCTformer+需1496分钟、18GB。
- **参数**：LVC仅含轻量卷积和MLP，额外参数量很少。

## 5. 实验数量与充分性

- **主要实验**：
  - 分割性能对比（Tab.1）：在VOC val/test、COCO val上与10+方法对比，包括有无CRF的结果。
  - CAM种子质量对比（Tab.2）：在VOC训练集上与12+方法对比，包括训练免费和训练需要的设置。
  - 消融实验（Tab.3-5）：对TSE、SVC、LVC、属性数量、注意力类型（q-k、v、内相关等）分别进行ablation。
  - 属性数量分析（Tab.4）：B=32/64/112/144/196对比。
  - 全监督对比（Tab.6）：与DeepLabV2、WeCLIP-Full等全监督方法对比。
  - 训练效率对比（Tab.7）：时间、内存、CAM质量、分割性能综合对比。
  - 超参数分析（补充材料）：TOP-K、缩放因子α/β、SVC层数N等。
- **可视化**：Fig.3分割结果、Fig.4 CAM可视化、Fig.5属性响应、Fig.6注意力图对比。
- **充分性评价**：实验覆盖主流数据集，与最新SOTA对比，消融完整，超参数探讨，且报告了训练免费和训练模式两种设置。**实验设计客观、公平**（采用统一设置，复现官方代码等）。

## 6. 主要结论与发现

- ExCEL在PASCAL VOC上达到**78.4% mIoU**（val集）和78.5%（test集），在COCO上达到**50.3% mIoU**，显著超越所有现有WSSS方法（包括多阶段方法）。
- 训练免费模式（仅SVC+TSE）即可达**74.6% mIoU**，超过CLIP-ES等需要训练的方法。
- 证明了**块-文本对齐范式**比传统图像-文本对齐更适合WSSS，能更充分挖掘CLIP的密集知识。
- TSE通过隐式属性狩猎有效丰富文本语义；VC（SVC+LVC）通过内相关和动态偏移显著改善视觉特征细粒度。
- 训练成本极低（90分钟、3.2GB内存），仅为现有方法的6%~33%，同时保持或超越SOTA性能。

## 7. 优点：方法和实验设计亮点

- **范式创新**：首次在WSSS中系统探索CLIP的**块-文本密集对齐**，而非仅全局对齐。
- **双模块设计巧妙**：TSE利用LLM生成描述+聚类得到隐式属性，避免了简单拼合描述；VC通过非参数内相关和轻量可学习适配器结合，无需修改预训练权重。
- **训练免费与高效学习双模式**：ExCEL既可以零训练获得强结果，又可通过仅训练适配器和分割头实现SOTA，灵活性高。
- **资源友好**：显存和训练时间需求极低，易于复现和实际部署。
- **实验充分且公平**：与多种类型（多阶段、单阶段、基于CLIP、非CLIP）方法对比，消融实验逐一验证每个组件贡献，可视化全面。

## 8. 不足与局限

- **依赖LLM**：TSE需调用GPT-4生成描述，可能引入外部模型计算成本、以及潜在描述偏差（如某些类描述不准确），且未探讨其他LLM或自动生成描述方式的影响。
- **模型规模限制**：仅使用ViT-B作为CLIP视觉编码器，未探索更大规模（如ViT-L）的效果，可能限制性能上限。
- **弱监督类型单一**：仅针对图像级标签，未在点、涂鸦或边界框等其他弱监督方式上验证泛化性。
- **数据集局限**：只在通用物体分割数据集（VOC、COCO）上评估，未涉及医学图像、遥感等特殊领域，可能存在领域偏移风险。
- **后处理依赖**：最终伪标签仍需经过CRF等后处理步骤（论文中报告了无CRF结果仍领先，但最佳结果使用了CRF），增加了流程复杂性。
- **理论分析不足**：未对CLIP内部注意力机制为何造成特征同质化进行深入理论推导，仅凭实验观察。

（完）
