---
title: "unMORE: Unsupervised Multi-Object Segmentation via Center-Boundary Reasoning"
title_zh: unMORE：基于中心-边界推理的无监督多目标分割
authors: "Yafei YANG, Zihui Zhang, Bo Yang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vF5F7cL76i"
tags: ["query:mmseg"]
score: 5.0
evidence: 真实图像上的无监督多目标分割
tldr: 现有无监督多目标分割方法仅能处理简单合成物体或少量真实物体。本文提出unMORE两阶段流水线，第一阶段学习三种精细定义的目标中心表示（中心、边界、区域），第二阶段利用这些先验进行多目标推理。在多个真实图像数据集上，unMORE能够分割大量复杂物体，拓展了无监督分割的实用性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 455, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1721, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1703, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1637, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1577, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 191, \"height\": 188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1504, \"height\": 1797, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1413, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1422, \"height\": 867, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1425, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1421, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1425, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vf5f7cl76i/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 800, \"height\": 597, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 876, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1586, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1759, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1582, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1344, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1391, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1784, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1384, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1754, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vf5f7cl76i/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1452, \"height\": 2117, \"label\": \"Table\"}]"
motivation: 现有方法在真实复杂场景中难以分割多个物体，需要更强大的无监督表示。
method: 提出两阶段流水线，第一阶段学习目标中心、边界和区域的三级表示，第二阶段进行多目标推理。
result: unMORE在真实图像上实现了多目标分割，超越了现有无监督方法。
conclusion: 精细的目标中心表示是无监督分割复杂场景的关键。
---

## Abstract
We study the challenging problem of unsupervised multi-object segmentation on single images. Existing methods, which rely on image reconstruction objectives to learn objectness or leverage pretrained image features to group similar pixels, often succeed only in segmenting simple synthetic objects or discovering a limited number of real-world objects. In this paper, we introduce unMORE, a novel two-stage pipeline designed to identify many complex objects in real-world images. The key to our approach involves explicitly learning three levels of carefully defined object-centric representations in the first stage. Subsequently, our multi-object reasoning module utilizes these learned object priors to discover multiple objects in the second stage. Notably, this reasoning module is entirely network-free and does not require human labels. Extensive experiments demonstrate that unMORE significantly outperforms all existing unsupervised methods across 6 real-world benchmark datasets, including the challenging COCO dataset, achieving state-of-the-art object segmentation results. Remarkably, our method excels in crowded images where all baselines collapse. Our code and data are available at https://github.com/vLAR-group/unMORE.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
- **研究动机**：现有无监督多目标分割方法（如基于图像重构的Slot Attention及其变体、基于自监督特征蒸馏的方法）在处理真实世界复杂图像时表现有限，通常只能分割简单合成物体或发现少量真实物体。这些方法依赖弱目标性定义或简单的特征分组，难以应对拥挤场景和物体边界模糊的问题。
- **整体目标**：提出一种新的两阶段流水线 **unMORE**，能够从单张真实图像中无监督地识别众多复杂物体，并在多个基准数据集上达到最先进水平。

### 2. 方法论
- **核心思想**：模仿人类先学习物体概念（存在性、位置、形状）再在新场景中推理的能力。第一阶段学习三种显式的物体中心表示；第二阶段利用预训练好的物体性网络进行无网络的多物体推理。
- **第一阶段：物体性网络（Objectness Network）**
  - 从大规模ImageNet图像（使用VoteCut生成粗略单物体掩码）中学习三个层次表示：
    - **物体存在性分数** \(f^e\)：二值标签（正样本包含物体，负样本为背景裁剪）。
    - **物体中心场** \(f^c\)：物体内每个像素指向物体中心（紧包围框中心）的单位向量，背景为零向量。
    - **物体边界距离场** \(f^b\)：基于有符号距离场归一化，前景为正、背景为负，最大值反映物体大小；具有梯度性质可用于边界搜索。
  - 网络架构：ResNet50（存在性）+ DPT-large + 两个CNN头（中心场和边界场），使用交叉熵、L2和L1损失联合训练。
- **第二阶段：多物体推理模块（Multi-Object Reasoning）**
  - 步骤#0：在场景图像上生成初始边界框提议（类似Faster R-CNN的锚点，5种尺度×3种长宽比）。
  - 步骤#1（存在性检查）：裁剪提议输入物体性网络，丢弃存在性分数低于阈值 \(\tau_e\) 的提议。
  - 步骤#2（中心推理）：利用中心场检测是否包含多个物体。通过预定义的5×5内核（向量指向外）与中心场卷积得到反中心图，若最高值超过阈值 \(\tau_c\)，则在最高点将提议切分为四个子提议（左/右/上/下）；否则，使用连通分量法分离远距离物体。子提议重复步骤#1。
  - 步骤#3（边界推理）：对单物体提议，利用边界距离场更新边界框四个边界。通过计算边框上最大边界距离值及其梯度方向，使边框扩张（含物体）或收缩（含背景）。迭代至收敛。
  - 后处理：对收敛的提议应用NMS去重，并根据存在性、中心场和边界场计算置信度。
- **可选训练检测器**：将发现的多物体作为伪标签训练类无关检测器（Cascade Mask R-CNN），进一步提升性能（unMORE）。

### 3. 实验设计
- **数据集与Benchmark**：
  - 主实验：**COCO* val**（作者手动扩充标注的COCO验证集，新增197个类别，共287类，47,117个物体），评估AP/AR。
  - 零样本检测：**COCO20K, LVIS, PASCAL VOC, KITTI, Object365, OpenImages**。
- **对比方法**：
  - 直接物体发现（无学习模块）：FreeMask, MaskCut (K=3/10), VoteCut。
  - 直接物体发现（有学习模块）：DINOSAUR, FOUND, **unMORE disc** (Ours)。
  - 训练了检测器的方法：UnSAM, CutLER, CuVLER, **unMORE** (Ours)。
- **评价指标**：AP/AR at IoU thresholds 50/75 for bounding boxes and masks。

### 4. 资源与算力
- **训练时间**（同一硬件配置）：
  - 物体性网络训练：约10小时。
  - unMORE disc 推理时间：45.3秒/图（较慢，但后续检测器unMORE仅0.1秒/图）。
  - 检测器训练：unMORE仅需30小时（baseline CutLER 75小时，CuVLER 60小时，UnSAM 90小时）。
- **GPU型号与数量**：论文未明确说明，但提及“same hardware configurations”。

### 5. 实验数量与充分性
- **实验组数**：
  - 主实验（COCO* val）：对比9种方法，报告详细AP/AR。
  - 零样本检测：6个数据集 × 4种方法（含多组设置）。
  - 消融实验：8种表示组合、3种阈值（存在性/中心/边界）的广泛扫描、步长选择、随机裁剪增强、粗糙掩码来源等。
  - 按物体数量分组的分析（[0-4], [5-9], [10-14], [15+)）。
  - 时间效率对比。
- **充分性与公平性**：
  - 方法分组清晰，对比了不同类别方法。
  - 对每个baseline采用其最优设置（如CutLER使用3轮训练，CuVLER使用4个设置）。
  - 消融实验全面，验证了每个组件的贡献。
  - 实验设计客观，统计指标完整。

### 6. 主要结论与发现
- unMORE在COCO* val上大幅超越所有现有方法：AP box 50达到32.6（次优CuVLER为28.0），AP mask 50达到29.6（次优CuVLER为24.4）。
- 在拥挤图像（≥15个物体）上，unMORE保持较好性能，而baseline几乎崩溃。
- 边界距离场是贡献最大的单一表示（AP提升最大），结合三者达到最佳。
- 零样本泛化到多个数据集均取得最高精度，证明其强泛化能力。

### 7. 优点
- **新颖的两阶段流水线**：将物体概念学习与场景推理分离，模仿人类认知过程。
- **精心设计的三级表示**：存在性、中心场、边界场联合捕获物体完整信息，有效解决过度分割和欠分割。
- **网络自由推理**：第二阶段无需额外网络，仅通过查询预训练的物体性网络进行非学习推理，计算高效。
- **无需人工标注**：全过程无监督，仅利用ImageNet + 自监督特征（DINO/v2）生成的粗略掩码。
- **在拥挤场景优势显著**：反中心图机制能有效分割紧邻物体。
- **开源代码与数据**：包括扩充的COCO*标注。

### 8. 不足与局限
- **推理效率**：unMORE disc（直接发现）速度较慢（45.3秒/图），依赖大量初始提议和迭代优化；虽然后续检测器推理快，但整体流程仍需预处理。
- **分离重叠相似纹理物体困难**：论文承认对形态相似、重叠的物体（如图11）分离效果不佳。
- **依赖粗糙掩码质量**：第一阶段使用VoteCut生成的粗糙掩码，其质量影响最终性能；若使用更强预训练模型（如SAM）可提升，但SAM需监督。
- **域差距限制**：训练数据为自然图像（ImageNet），在医学图像等显著域差异场景可能失效。
- **实验覆盖**：虽然数据集多样，但未涉及视频或3D场景；COCO*标注为作者手动扩充，可能存在标注偏差。

（完）
