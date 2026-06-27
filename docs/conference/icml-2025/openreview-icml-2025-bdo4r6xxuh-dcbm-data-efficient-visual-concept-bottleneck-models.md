---
title: "DCBM: Data-Efficient Visual Concept Bottleneck Models"
title_zh: DCBM：数据高效的视觉概念瓶颈模型
authors: "Katharina Prasse, Patrick Knab, Sascha Marton, Christian Bartelt, Margret Keuper"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BdO4R6XxUH"
tags: ["query:mmseg"]
score: 4.0
evidence: 利用视觉基础模型（分割/检测）在概念瓶颈模型中定义概念
tldr: 概念瓶颈模型需要大量数据提取概念。本文提出数据高效概念瓶颈模型（DCBM），利用分割或检测基础模型从图像区域生成多种粒度的概念，从而减少对大规模样本的依赖。实验表明DCBM在细粒度分类和分布外任务上表现优异，展示了视觉基础模型在可解释性中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 834, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1761, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1707, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 774, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1190, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1072, \"height\": 874, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1194, \"height\": 1159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1759, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bdo4r6xxuh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1763, \"height\": 951, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 603, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1236, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1233, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 764, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 790, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 896, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 826, \"height\": 664, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1757, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1297, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1759, \"height\": 994, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1669, \"height\": 1445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1592, \"height\": 1871, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1756, \"height\": 947, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1752, \"height\": 1656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1755, \"height\": 1707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1394, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1755, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 745, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bdo4r6xxuh/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 594, \"height\": 386, \"label\": \"Table\"}]"
motivation: 概念瓶颈模型提取概念需要大量样本。
method: 使用分割/检测基础模型从图像区域生成多粒度概念。
result: 在细粒度分类和分布外任务上有效。
conclusion: 视觉基础模型可提升概念瓶颈模型的数据效率。
---

## Abstract
Concept Bottleneck Models (CBMs) enhance the interpretability of neural networks by basing predictions on human-understandable concepts. However, current CBMs typically rely on concept sets extracted from large language models or extensive image corpora, limiting their effectiveness in data-sparse scenarios. We propose Data-efficient CBMs (DCBMs), which reduce the need for large sample sizes during concept generation while preserving interpretability. DCBMs define concepts as image regions detected by segmentation or detection foundation models, allowing each image to generate multiple concepts across different granularities. Exclusively containing dataset-specific concepts, DCBMs are well suited for fine-grained classification and out-of-distribution tasks. Attribution analysis using Grad-CAM demonstrates that DCBMs deliver visual concepts that can be localized in test images. By leveraging dataset-specific concepts instead
of predefined or general ones, DCBMs enhance adaptability to new domains. The code is available at: https://github.com/KathPra/DCBM.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统的概念瓶颈模型（CBM）在概念生成阶段通常依赖大规模语言模型或庞大的图像语料库（如CC3M、ImageNet全量数据），导致在数据稀疏场景（如小样本、细粒度分类）中效果受限，且难以快速迁移到新领域。
- **研究动机**：现有CBM生成的文本对齐概念存在模态间隙（CLIP图文不对齐问题），而视觉域概念提取又往往需要大量预训练数据。作者希望设计一种**数据高效、完全在视觉域、可适应任意数据集**的概念瓶颈模型。
- **整体含义**：通过利用分割/检测基础模型从图像本身提取多粒度区域作为概念，大幅降低概念生成所需样本量，同时保持可解释性，并提升在细粒度分类和分布外任务中的表现。

## 2. 论文提出的方法论

### 核心思想
- 将概念定义为**图像区域**，通过分割/检测基础模型为每张图像生成多个不同粒度的候选区域（concept proposals），然后通过聚类得到最终概念集，并用于训练线性CBM。

### 关键技术细节（三步流程）
1. **概念提议生成（Step 1）**  
   - 从训练集中每类随机选取**50张图像**（CUB因样本少则用全部）。  
   - 使用SAM2、Mask-RCNN、DETR、GroundingDINO等基础模型进行分割/检测，得到图像区域（bounding box），裁剪后加入概念提议集合S。  
   - 可通过面积阈值过滤过大/过小区域。

2. **概念生成（Step 2）**  
   - 用冻结的CLIP视觉编码器（如ViT-L/14）将S中的所有提议嵌入，得到S_enc。  
   - 对S_enc进行**K-Means聚类**（默认k=2048），取每个簇的**中位数（或均值）嵌入作为概念**，形成概念集C ∈ ℝ^(k×m)。  
   - 可选：利用CLIP图文对齐能力，通过文本提示移除不期望的概念（如“石头”），实现概念干预。

3. **概念瓶颈模型训练（Step 3）**  
   - 对于训练图像x_i，计算其嵌入与每个概念向量的归一化点积作为**概念激活值** a(x_i)。  
   - 训练线性层 h(·)：t(x_i) = ω⊤a(x_i)，损失函数为 cross-entropy + L1稀疏正则化（λ∥ω∥₁）。  
   - 超参数：学习率1e-4，稀疏度1e-4，训练200 epochs，batch size依数据集大小调整。

4. **概念命名（可选 Step 4）**  
   - 使用高频英语单词（如google-10000-english），将每个视觉概念与其最近的文本嵌入匹配，得到可读名称。

### 公式（文字说明）
- 概念激活：a_j(x_i) = ⟨f(x_i), c_j⟩ / ∥c_j∥₂²  
- 预测：t(x_i) = ω^T a(x_i)  
- 损失：L = CE(t, y) + λ∥ω∥₁

## 3. 实验设计

### 数据集
- **标准基准**：ImageNet、Places365、CUB-200-2011、CIFAR-10、CIFAR-100。  
- **细粒度/领域特定**：ImageNette、ImageWoof（均ImageNet子集）、CUB。  
- **分布外测试**：ImageNet-R（200类ImageNet的多种渲染）。  
- **额外新域**：MiT-States（对象-状态组合）、ClimateTV（气候变化社交媒体图）、AWA2（动物属性）、CelebA（人脸属性，经改造为110类）。  
- **消融/提速集**：CUB、ImageNette、ImageWoof做超参数消融；CIFAR、Places365等用于效率分析。

### 对比方法
- **CBM类**：LF-CBM（Oikarinen 2023）、LaBo（Yang 2023）、CDM（Panousis 2023）、DCLIP（Menon & Vondrick 2023）、DN-CBM（Rao 2024，任务无关视觉CBM）。  
- **基线**：Linear Probe（线性探测）、Zero-shot CLIP。

### 评价指标
- **主要指标**：Top-1准确率。  
- **可解释性**：Grid Pointing Game（GPG）度量概念定位能力（Gini指数、正确象限百分比、绝对分数）。  
- **OOD泛化**：ImageNet-R上的错误率及IID→OOD性能下降幅度。  
- **概念质量**：可视化聚类样本、Grad-CAM热力图。

## 4. 资源与算力

- **硬件**：单张 NVIDIA RTX A6000 GPU。  
- **训练时长**：  
  - 小型数据集（CIFAR、CUB）：约5分钟完成概念聚类+CBM训练。  
  - 大型数据集（ImageNet、Places365）：约2小时。  
- **概念生成**：仅需每类50张图像（ImageNet共5万张），比DN-CBM使用的CC3M（330万图文对）减少约96%的数据量，且无需额外预训练。  
- **内存**：概念提议占用约6 GB（假设256×256分辨率），远低于DN-CBM的约850 GB（估算）。  
- 论文**未明确说明**总实验的GPU小时数，但上述效率在文中多次强调。

## 5. 实验数量与充分性

- **实验数量**：非常丰富。  
  - **主实验**：5个基准数据集 × 3种概念生成方法（SAM2、GDINO、Mask-RCNN）× 3个CLIP骨干（RN50、ViT-B/16、ViT-L/14），外加多个对比方法。  
  - **消融实验**：  
    1. 聚类数k（128~4096）影响（Table 16）。  
    2. 稀疏度λ和学习率（1e-4, 1e-3, 1e-2）组合（Table 17-18）。  
    3. 每类图像数（5,10,25,50 vs 全量）影响（Table 19）。  
    4. 背景移除影响（Table 12）。  
    5. PCA降维影响（Table 13）。  
    6. 聚类算法（K-Means vs 层次聚类）比较（Table 14）。  
    7. 质心选择（均值 vs 中位数）比较（Table 15）。  
    8. 概念尺寸过滤（Table 20）。  
  - **额外数据集**：AWA2（Table 22）、CelebA（Table 23）、MiT-States/ClimateTV（Table 3）、ImageNet-R OOD（Table 2）。  
  - **可解释性**：GPG度量（Table 4）、概念可视化（Figure 5-6）、干预案例（Figure 11）。

- **充分性与公平性**：  
  - 所有超参数在独立验证集上选取（CUB、ImageNette、ImageWoof上消融），然后固定用于主实验。  
  - 对比方法使用公开报告的最高值（标注*号），未报告的值用短横线标注，没有自行复现对比方法。  
  - 消融覆盖全面（聚类、稀疏度、样本量、背景、骨干网络等），但**缺少对CLIP嵌入空间的更深入分析**（如使用其他视觉编码器如DINOv2的对比）。  
  - OOD实验直接使用全ImageNet训练的DCBM评估，未专门在IN-R类上重新训练，更接近实际应用但公平性略逊于针对性训练方法（Hendrycks等原论文做法）。

## 6. 论文的主要结论与发现

1. **数据高效**：DCBM仅需每类50张图像即可生成有效概念，在ImageNet上比DN-CBM减少96%概念生成数据，且性能保持在线性探测的5%以内。  
2. **细粒度表现优**：在CUB（鸟类细粒度分类）上取得82.4%准确率，优于大多数文本对齐CBM。  
3. **OOD泛化强**：在ImageNet-R上错误率比DN-CBM低约7-10个百分点，性能下降幅度更小（22.4% vs 38.8%）。  
4. **概念可定位**：GPG实验表明DCBM概念在测试图像中能有效激活于正确区域（Gini 0.47、正确象限占比65%等）。  
5. **概念可干预**：可移除不期望概念（如“石头”），模型仍保持甚至微升准确率。  
6. **框架通用**：SAM2、GroundingDINO、Mask-RCNN等不同基础模型均可无缝集成，性能相近；且能快速适应MiT-States、ClimateTV等新域。  
7. **可视化揭示模型行为**：概念解释能暴露CLIP空间中的假相关（如“救护车”概念激活了“注射器”），为调试提供线索。

## 7. 优点

- **数据极高效**：概念生成仅需每类50张图像，无需预训练或大规模外部语料库，适合小样本场景。  
- **完全视觉域**：避免图文对齐中的模态间隙，所有概念可追溯到图像区域，提升忠实度。  
- **多粒度自然支持**：分割/检测可给出不同层级（整体、部件、子部件）的概念，优于固定数量概念的方法。  
- **可干预性与透明度**：概念集可在训练前通过文本移除；每一步（提议、聚类、CBM权重、Grad-CAM定位）均可独立检查。  
- **Ablation全面**：涵盖了几乎所有关键超参数的选择依据，方法论坚实。  
- **OOD泛化与细粒度**：在两类场景下显著优于或持平于现有方法。  
- **开源代码**：提供完整实现，易于复现和扩展。

## 8. 不足与局限

1. **性能上界有限**：在ImageNet、Places365等大规模通用数据集上，DCBM略低于DN-CBM（约5个百分点），可能存在性能与数据效率的权衡。  
2. **依赖基础模型质量**：概念质量受限于SAM2、Mask-RCNN等的分割效果；若基础模型在目标域上表现差（如模糊小物体），概念也会退化。  
3. **CLIP空间依赖**：仅使用CLIP嵌入，未探索其他视觉编码器（如DINOv2、ConvNeXt），可能限制了可迁移性。  
4. **概念命名偏差**：通过英语词表匹配可能产生不准确名称（如“thirds”对应冰球三节比赛时间），导致用户误判。  
5. **假相关未彻底解决**：虽然可移除概念，但训练中仍可能依赖假相关（如背景水印），需要后续自动检测工具。  
6. **实验覆盖局限**：缺少对**回归任务、视频/3D等非图像模态**的扩展；CLIP骨干仅三种，未与其它视觉模型（如SigLIP、BLIP）对比。  
7. **算力细节不详**：仅给出粗略训练时长，未报告总实验消耗的GPU小时数，可复现性信息不够完整。  
8. **对比方法复现不足**：未自行重现其他CBM（如LaBo、CDM）在相同硬件/数据分割下的结果，使用了文献报告值，可能存在环境差异。

（完）
