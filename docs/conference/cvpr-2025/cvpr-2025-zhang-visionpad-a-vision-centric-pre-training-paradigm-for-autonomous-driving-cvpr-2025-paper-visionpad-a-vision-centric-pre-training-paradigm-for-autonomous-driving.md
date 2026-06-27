---
title: "VisionPAD: A Vision-Centric Pre-training Paradigm for Autonomous Driving"
title_zh: VisionPAD：面向自动驾驶的视觉中心预训练范式
authors: "Zhang, Haiming, Zhou, Wending, Zhu, Yiyao, Yan, Xu, Gao, Jiantao, Bai, Dongfeng, Cai, Yingjie, Liu, Bingbing, Cui, Shuguang, Li, Zhen"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_VisionPAD_A_Vision-Centric_Pre-training_Paradigm_for_Autonomous_Driving_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 面向自动驾驶感知的自监督预训练
tldr: 针对自动驾驶视觉算法需要大量标注数据的问题，本文提出VisionPAD自监督预训练范式，利用3D高斯泼溅仅以图像为监督重建多视图表示，并通过体素速度估计和多帧光度一致性学习运动与几何线索。该方法在多项自动驾驶感知任务上显著提升性能，降低了对标注数据的依赖。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 780, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 839, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 866, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1790, \"height\": 1361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 938, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 797, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1813, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-visionpad-a-vision-centric-pre-training-paradigm-for-autonomous-driving-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1752, \"height\": 426, \"label\": \"Table\"}]"
motivation: 自动驾驶视觉预训练常需深度监督，数据获取成本高，亟需仅用图像的自监督方法。
method: 采用3D高斯泼溅重建多视图表示，结合体素速度估计与多帧光度一致性学习。
result: 在nuScenes等数据集上，预训练后微调效果显著优于从零训练。
conclusion: 自监督3D高斯泼溅是自动驾驶视觉预训练的高效方案，可推广到多种下游任务。
---

## Abstract
This paper introduces VisionPAD, a novel self-supervised pre-training paradigm designed for vision-centric algorithms in autonomous driving. In contrast to previous approaches that employ neural rendering with explicit depth supervision, VisionPAD utilizes more efficient 3D Gaussian Splatting to reconstruct multi-view representations using only images as supervision. Specifically, we introduce a self-supervised method for voxel velocity estimation. By warping voxels to adjacent frames and supervising the rendered outputs, the model effectively learns motion cues in the sequential data. Furthermore, we adopt a multi-frame photometric consistency approach to enhance geometric perception. It projects adjacent frames to the current frame based on rendered depths and relative poses, boosting the 3D geometric representation through pure image supervision. Extensive experiments on autonomous driving datasets demonstrate that VisionPAD significantly improves performance in 3D object detection, occupancy prediction and map segmentation, surpassing state-of-the-art pre-training strategies by a considerable margin.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自动驾驶视觉算法（如3D目标检测、占用预测等）依赖大量精确的3D标注数据（如LiDAR点云生成的深度图），数据采集成本极高，成为规模化应用瓶颈。现有的自监督预训练方法（如UniPAD、ViDAR）仍需显式深度监督，导致在纯视觉场景下效果不佳。
- **整体含义**：论文旨在提出一种**仅依赖多视角图像**的自监督预训练范式，使模型在预训练阶段无需任何深度标签，即可学习丰富的3D几何、运动与语义表示，从而降低下游任务对标注数据的依赖，提升在多种自动驾驶感知任务上的性能。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用高效的**3D高斯泼溅（3D-GS）**替代传统体积渲染来重建多视图图像，并引入**自监督体素速度估计**和**多帧光度一致性损失**，在纯图像监督下同时学习运动线索与几何结构。
- **关键技术细节**：
  1. **体素构建**：输入历史多帧多视图图像，通过图像骨干网络提取2D特征，经视图变换生成3D体素特征 V ∈ R^{X×Y×Z×C}。
  2. **3D高斯泼溅解码器**：以体素中心为锚点，用MLP预测每个锚点对应的多个高斯原语（位置偏移、旋转、缩放、不透明度、球谐系数），通过光栅化渲染多视图图像和深度图。
     - 采取**高斯滤波**：丢弃预测不透明度小于0的低置信度高斯，降低计算量。
  3. **自监督体素速度估计**：添加速度预测头，为每个体素回归世界坐标系下的速度向量。结合帧间时间间隔 Δt 计算体素流，将当前帧体素特征扭曲（warp）到相邻帧，再通过3D-GS解码器渲染图像，与相邻帧真实图像计算L1损失（L_vel）。反向传播仅更新速度头参数。
  4. **多帧光度一致性**：利用当前帧渲染的深度图 D_t，将相邻帧图像 I_{t'} 重投影到当前视角生成 I_{t'→t}，计算SSIM与L1混合损失（L_pc），强化3D几何表示。
- **总损失函数**：L = ω1 L_img + ω2 L_vel + ω3 L_pc，其中 ω1=0.5，ω2=1，ω3=1。

### 3. 实验设计：数据集、Benchmark、对比方法

- **数据集**：nuScenes，包含700训练、150验证、150测试场景，六摄像头环绕图像，同时提供LiDAR点云和3D标注。
- **任务与评价指标**：
  - 3D目标检测：NDS（nuScenes Detection Score）和mAP（mean Average Precision）。
  - 语义占用预测：mIoU（mean Intersection-over-Union）。
  - 地图分割：车道线IoU。
- **对比方法**：
  - 3D检测：BEVFormer、SpatialDETR、PETR、Ego3RT、3DPPE、BEVFormerV2、CMT-C、FCOS3D、UVTR、UVTR+UniPAD（有/无LiDAR监督）等。
  - 语义占用：BEVFormer、TPVFormer、FB-Occ、RenderOcc、SparseOcc、OPUS、BEVDet-Occ等。
  - 地图分割：UVTR、UVTR+UniPAD。
- **基准模型**：以UVTR为主干，使用ConvNeXt-small图像编码器。

### 4. 资源与算力

- 文中仅在“实现细节”部分说明了预训练配置：12个epoch，AdamW优化器，初始学习率2×10⁻⁴，总batch size为4。
- **未明确说明**所用GPU型号、数量及具体训练时长。推测为常见单卡或多卡（如8×V100或A100）配置，但无法从原文确定。

### 5. 实验数量与充分性

- **实验数量**：
  - 三个下游任务各一组主实验（表1、2、3），对比多个SOTA方法。
  - 数据效率实验（图4）：使用10%、25%、50%、100%标注数据进行微调，展示预训练优势。
  - 消融实验（表4）：逐步添加体积渲染→3DGS解码器→高斯滤波→速度估计→光度一致性，共6个模型变体。
  - 额外提及使用2/3/4个锚点每体素性能未提升。
- **充分性**：实验设计较为充分，覆盖了主要任务、多数据量场景、各组件贡献，且与UniPAD等强基线公平对比。但缺少跨数据集泛化实验（如Waymo）及与其他3DGS预训练方法的直接对比（因该方向尚属空白）。

### 6. 论文的主要结论与发现

- VisionPAD在纯图像监督预训练下，显著超越现有自监督预训练方法（如UniPAD），且在某些任务上甚至优于使用LiDAR深度监督的UniPAD。
- 具体增益：3D目标检测 +2.5 mAP / +1.7 NDS（单帧输入），语义占用 +4.5 mIoU，地图分割 +4.1 IoU。
- 数据效率实验中，当微调数据减少时，VisionPAD相对优势更加明显（如25%数据下mAP提升约6%）。
- 消融实验表明：3DGS解码器、高斯滤波、速度估计、光度一致性均独立贡献性能提升，其中光度一致性增益最大。

### 7. 优点

1. **纯视觉自监督**：完全摆脱对LiDAR深度标签的依赖，降低了数据成本。
2. **利用3D-GS高效渲染**：相比体积渲染，支持全分辨率图像重建，计算更高效且捕捉更精细颜色细节。
3. **新颖的体素速度估计策略**：通过无监督方式学习运动线索，仅更新速度头参数，稳定训练。
4. **多帧光度一致性**：利用渲染深度实现跨帧几何约束，显著增强几何表示。
5. **通用性强**：在3D检测、占用预测、地图分割三个任务上均验证有效，且与不同骨干（如UVTR、BEVDet）兼容。

### 8. 不足与局限

1. **实验范围有限**：仅在nuScenes单一数据集上验证，缺乏跨数据集泛化能力测试（如Waymo、KITTI）。
2. **未与其他3DGS预训练方法对比**：论文声称是首个将3D-GS用于自动驾驶预训练的工作，但未与后续可能的同类方法（如GaussianOcc）进行对比。
3. **速度估计可能存在偏差**：体素速度仅依赖帧间时间间隔，对于非刚体运动或极快运动场景可能不够准确，文中未讨论失败案例。
4. **计算成本未充分分析**：虽然3D-GS比体积渲染高效，但预训练12 epoch需要一定算力，且不同组件（如速度头、光度一致性）会增加额外开销，文中未给出详细时间或显存消耗。
5. **超参数选择缺乏敏感性分析**：损失权重（ω1, ω2, ω3）及高斯滤波阈值设为固定值，未说明是否经过调优或对结果敏感。

（完）
