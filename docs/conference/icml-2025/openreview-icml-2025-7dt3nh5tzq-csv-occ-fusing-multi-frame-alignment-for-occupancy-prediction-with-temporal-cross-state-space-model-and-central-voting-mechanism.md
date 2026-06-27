---
title: "CSV-Occ: Fusing Multi-frame Alignment for Occupancy Prediction with Temporal Cross State Space Model and Central Voting Mechanism"
title_zh: CSV-Occ：融合多帧对齐的占用预测，基于时序交叉状态空间模型和中央投票机制
authors: "Ziming Zhu, Yu Zhu, Jiahao Chen, LingXiaofeng, Huanlei Chen, Lihua Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=7Dt3nH5TZq"
tags: ["query:mmseg"]
score: 7.0
evidence: 面向自动驾驶的3D语义占用预测
tldr: 本文提出CSV-Occ方法，针对自动驾驶中的3D语义占用预测任务。现有方法融合时序信息时注意力机制复杂度高。作者扩展状态空间模型支持多输入序列交互，通过级联架构进行时序建模，并引入中央投票机制。实验表明该方法在高效捕获时序信息的同时提升了场景理解精度，有助于自动驾驶后续决策规划。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 656, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1330, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1333, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1738, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1669, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1736, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-7dt3nh5tzq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1155, \"height\": 506, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1758, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1470, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 638, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1025, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 881, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 683, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-7dt3nh5tzq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1487, \"height\": 298, \"label\": \"Table\"}]"
motivation: 现有占用预测方法在时序融合中受限于注意力的高复杂度，需要更高效的时序建模方案。
method: 扩展状态空间模型支持多输入序列交互，采用级联架构进行时序建模，并结合中央投票机制融合多帧信息。
result: 该方法在多个自动驾驶数据集上实现了高效且准确的3D语义占用预测。
conclusion: CSV-Occ通过创新的时序融合策略推动了自动驾驶场景理解的发展。
---

## Abstract
Recently, image-based 3D semantic occupancy prediction has become a hot topic in 3D scene understanding for autonomous driving. 
Compared with the bounding box form of 3D object detection, the ability to describe the fine-grained contours of any obstacles in the scene is the key insight of voxel occupancy representation, which facilitates subsequent tasks of autonomous driving. In this work, we propose CSV-Occ to address the following two challenges: (1) Existing methods fuse temporal information based on the attention mechanism, but are limited by high complexity. We extend the state space model to support multi-input sequence interaction and conduct temporal modeling in a cascaded architecture, thereby reducing the computational complexity from quadratic to linear. (2) Existing methods are limited by semantic ambiguity, resulting in the centers of foreground objects often being predicted as empty voxels. We enable the model to explicitly vote for the instance center to which the voxels belong and spontaneously learn to utilize the other voxel features of the same instance to update the semantics of the internal vacancies of the objects from coarse to fine. Experiments on the Occ3D-nuScenes dataset show that our method achieves state-of-the-art in camera-based 3D semantic occupancy prediction and also performs well on lidar point cloud semantic segmentation on the nuScenes dataset. Therefore, we believe that CSV-Occ is beneficial to the community and industry of autonomous vehicles.

---

## 论文详细总结（自动生成）

# 论文《CSV-Occ》详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：基于图像的3D语义占用预测是自动驾驶领域的新兴任务，相比3D目标检测的边界框，体素占用表示能描述场景中任意障碍物的细粒度轮廓，有助于下游规划与控制。
- **核心问题**：
  - **时序融合复杂度高**：现有方法（如BEVFormer）基于注意力机制融合多帧特征，计算复杂度为二次方（O(n²)），在大空间分辨率下开销巨大。
  - **内部语义空洞（Internal Occupancy Vacancy, IOV）**：前景物体（如汽车、卡车）的中心区域常被预测为空体素，即使增加输入帧数也无法解决，因为模型忽略了前景体素具有实例聚合性（同一实例的多个体素特征可互补）。
- **动机**：设计高效的时序融合模块（降低复杂度至线性），并通过让模型显式学习体素所属的实例中心，从粗到细填充物体内部空缺语义，提升预测精度。

## 2. 论文提出的方法论

### 核心思想
- 将状态空间模型（SSM）扩展为支持多输入序列交互的**Cross State Space Module (Cross SSM)**，实现线性复杂度的时序特征融合。
- 提出**Voting-based Enhancement Mechanism (VEM)**，包含**相对中心回归（RCR）**和**并行交互策略（PIS）**，让模型自发学习利用同实例其他体素特征，更新内部空缺语义。

### 关键技术细节
1. **整体架构**（图3）：
   - 输入多视角图像 → 图像骨干提取多尺度特征 → **时间视图变换（TVT）**：通过可变形注意力将图像特征投影到体素空间，再用级联的Cross SSM融合历史帧体素特征 → 体素特征提取器（上采样） → 粗语义占用预测 → VEM模块细化 → 细语义占用输出。

2. **Cross State Space Module**（图4）：
   - 将当前帧体素特征 \( V_T' \) 和历史帧特征 \( V_{T-i} \) 同时作为SSM输入。
   - 历史帧特征作为 \( x \)，经MLP得到 \( B, \Delta \)；当前帧特征经MLP得到 \( C \)（类似Cross Attention中Query的作用）。
   - 通过SSM递推公式（式20）实现线性复杂度的多帧交互。
   - 输入输出通过**Patch Partition**（池化+展平）和**Patch Merger**（reshape+插值上采样）处理。

3. **Voting-based Enhancement Mechanism (VEM)**：
   - **Relative Central Regression (RCR)**（图5）：根据粗占用预测筛选前景体素（10类），通过MLP预测每个前景体素到所属实例中心的三维偏移 \( \hat{\delta}_{\text{cen}} \)。
   - **Parallel Interaction Strategy (PIS)**（图6）：对于每个中心体素，其投票体素集合先以中心体素为K/V、投票体素为Q做交叉注意力更新投票体素特征；再对投票体素特征按全局池化排序后，以排序后的特征为K/V、中心体素为Q更新中心体素特征。

4. **损失函数**：
   - 占用分类损失 \( \mathcal{L}_{\text{Occ}} \)：focal loss + Lovasz loss + scene-class affinity loss（分别对语义和几何标签计算）。
   - 中心回归损失 \( \mathcal{L}_{\text{RCR}} \)：MSE loss监督预测偏移与真值偏移。
   - 总损失 \( \mathcal{L} = \mathcal{L}_{\text{Occ}} + \lambda_{\text{RCR}} \mathcal{L}_{\text{RCR}} \)。

## 3. 实验设计

- **数据集**：
  - **Occ3D-nuScenes**：用于3D语义占用预测（17类，空间200×200×16，体素0.4m）。
  - **nuScenes**：用于LiDAR点云语义分割评测（将占用预测结果投影到点云）。
- **Benchmark**：验证集上的mIoU。
- **对比方法**：
  - 占用预测：MonoScene, BEVDet, OccFormer, TPVFormer, CTF-Occ, BEVFormer, BEVDet4d, PanoOcc, FB-OCC, OctreeOcc等。
  - LiDAR语义分割：RangeNet++, PolarNet, SalsaNext, Cylinder3D++, RPVNet, BEVFormer, TPVFormer, PanoOcc等。
- **主要实验结果**（表1、表2）：
  - CSV-Occ-B（R101, 4帧）在Occ3D-nuScenes上mIoU达44.93，超越所有现有方法，尤其在前景小物体（barrier, pedestrian, bicycle, car）和大场景结构（driveable surface, sidewalk）上领先。
  - 在nuScenes LiDAR语义分割上mIoU达73.4，在所有基于图像的方法中最佳，接近部分基于LiDAR的方法。

## 4. 资源与算力

- **硬件**：4块NVIDIA A40（48GB显存）GPU。
- **训练配置**：
  - Batch size: 4（每GPU? 总batch size 4）。
  - 优化器：AdamW，学习率2e-4，权重衰减0.05，余弦退火调度。
  - 训练24个epochs。
- 文中未说明总训练耗时，但提供了推理速度与内存对比（图8、9），例如在BEV size 200×200时，Cross SSM的SPS（每秒样本数）约为5.8，内存约19.6GB。

## 5. 实验数量与充分性

- **实验组数充足**：
  - 主表（表1、表2）与多种state-of-the-art方法对比。
  - 消融实验（表3~表8）覆盖：
    - 多帧融合方法（Cross SSM vs TSA/MLP-Mixer/直接拼接）
    - TVT与VEM的有无（表4）
    - 损失函数权重（表5）
    - 体素查询尺寸（表6）
    - 帧数与帧间隔（表7）
    - 并行交互策略中的排序方式（表8）
  - 时序计算复杂度分析（图8、9）：改变BEV size和推理帧数，对比Cross SSM、TSA、MLP-Mixer的速度和内存。
  - 定性可视化（图7、10）展示了IOV改善效果。
  - 附录中还有实例级占用预测对比（表9）和背景类别性能下降分析（图11、12）。
- **充分性与公平性**：
  - 对比方法均采用公开代码或官方结果，对FB-OCC等调整了图像骨干和分辨率以保证公平。
  - 消融实验控制变量，结果清晰。
  - 但存在一定局限（见第8点）。

## 6. 论文的主要结论与发现

- CSV-Occ在相机3D语义占用预测任务上达到SOTA（mIoU 44.93），且高效（线性复杂度）。
- **Cross SSM** 相比传统的时序自注意力和MLP-Mixer，在相近参数量下取得更好性能且计算效率更优。
- **VEM** 能有效缓解IOV问题，尤其在前景物体（如车、卡车）上显著提升mIoU（从42.18提升至44.93，见表4）。
- 时间跨度（而非单纯帧数）对性能影响显著，过多帧或过长时间跨度会因动态模糊导致性能下降（表7）。
- 将占用结果投影到点云，CSV-Occ在LiDAR语义分割上也取得了基于图像方法的最佳性能（mIoU 73.4），接近部分纯LiDAR方法。

## 7. 优点

- **创新性**：首次将状态空间模型扩展到多序列输入以实现时序特征融合，并在占用预测中引入基于投票的实例中心细化机制。
- **效率**：Cross SSM将计算复杂度从二次降至线性，推理速度快、内存更低（图8、9），适合实际部署。
- **效果**：在前景物体上mIoU提升明显，且对大场景结构也友好，整体mIoU显著超越先前方法。
- **消融全面**：从融合方法、组件、损失权重、时空配置等多个角度进行了细致分析，验证了每个模块的有效性。
- **跨任务验证**：不仅做了占用预测，还投影到点云做语义分割，展示了泛化能力。

## 8. 不足与局限

- **背景类别性能下降**（附录E图11、12）：VEM依赖于粗语义预测筛选前景，当粗预测不准时，会对背景体素错误地预测中心，导致背景类（如drivable surface, manmade, vegetation）的mIoU下降。该问题未被完全解决。
- **实例级占用预测较弱**（表9）：CSV-Occ可以直接输出实例级结果，但需要后处理（中心聚类），且缺少3D包围框尺寸监督，导致实例分割指标（PQ 48.3）远低于PanoOcc（62.1）。论文承认“弱于实例级预测”。
- **实验仅基于nuScenes**：未在更多数据集（如Waymo, KITTI）上验证，泛化性存疑。
- **训练细节未完全公开**：如训练总时间、每帧图像的具体预处理等未提及。
- **仅使用单模态（相机）**：不包含LiDAR或多传感器融合，与多模态方法相比仍有差距。

（完）
