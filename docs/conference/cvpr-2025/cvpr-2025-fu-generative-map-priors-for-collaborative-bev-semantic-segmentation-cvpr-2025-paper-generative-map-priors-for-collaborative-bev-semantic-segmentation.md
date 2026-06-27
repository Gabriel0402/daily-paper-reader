---
title: Generative Map Priors for Collaborative BEV Semantic Segmentation
title_zh: 生成地图先验用于协作BEV语义分割
authors: "Fu, Jiahui, Gong, Yue, Wang, Luting, Zhang, Shifeng, Zhou, Xu, Liu, Si"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Fu_Generative_Map_Priors_for_Collaborative_BEV_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 协作BEV语义分割用于自动驾驶
tldr: 针对现有协作感知方法不适合密集特征的BEV语义分割问题，提出CoGMP框架，引入生成地图先验实现高效压缩（EFFC）和鲁棒融合（SGFF）。在多个数据集上实验表明，该方法在压缩率和分割精度上均优于现有方法，推动了协作感知在密集预测任务中的应用。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1629, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 825, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 821, \"height\": 698, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1807, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 558, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 369, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 486, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 501, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-fu-generative-map-priors-for-collaborative-bev-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 378, \"height\": 219, \"label\": \"Table\"}]"
motivation: 现有协作感知方法面向稀疏目标检测，不适合密集BEV语义分割。
method: 提出CoGMP，利用生成地图先验实现元素格式压缩和结构引导融合。
result: 实现高效压缩并保持高精度语义分割。
conclusion: 生成先验有效解决协作BEV分割中的压缩与融合挑战。
---

## Abstract
Collaborative perception aims to address the constraint of single-agent perception by exchanging information among multiple agents. Previous works primarily focus on collaborative object detection, exploring compressed transmission and fusion prediction tailored to sparse object features. However, these strategies are not well-suited for dense features in collaborative BEV semantic segmentation. Therefore, we propose CoGMP, a novel Collaborative framework that leverages Generative Map Priors to achieve efficient compression and robust fusion. CoGMP introduces two key innovations: Element Format Feature Compression (EFFC) and Structure Guided Feature Fusion (SGFF). Specifically, EFFC leverages map element priors from codebook to encode BEV features as discrete element indices for transmitted information compression. Meanwhile, SGFF utilizes a diffusion model with structural priors to coherently integrate multi-agent features, thereby achieving consistent fusion predictions. Evaluations on the OPV2V dataset show that CoGMP achieves a 6.89/7.64 Road/Lane IoU improvement and a 32-fold reduction in communication volume.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：协作感知通过多智能体信息交换突破单智能体感知限制，但现有方法主要面向**稀疏目标检测**（如3D目标检测），不适用于**密集特征的BEV语义分割**任务。密集特征在压缩时信息退化严重，在融合时存在跨智能体语义冲突。
- **核心问题**：如何针对BEV语义分割设计高效的**特征压缩**（在有限带宽下保留关键信息）和**鲁棒的融合**（解决多智能体感知冲突）策略。
- **整体含义**：利用**生成模型**学习地图的先验知识（如道路形状、车道连续性），以元素先验和结构先验分别指导压缩和融合，实现更好的性能-带宽权衡。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：提出**CoGMP**框架，包含两个创新模块：
  - **Element Format Feature Compression (EFFC)**：利用**地图元素先验**（通过VQ-VAE训练的码本）将连续BEV特征编码为**离散元素索引**，实现高效压缩。
  - **Structure Guided Feature Fusion (SGFF)**：利用**条件扩散模型**的结构先验，将多智能体特征逐步注入接收者特征，实现全局一致的融合预测。
- **关键技术细节**：
  - **EFFC**：
    - 先训练VQ-VAE（码本大小128，每个元素64维），将BEV分割标签转为离散元素表示。
    - **Element Type Inference (ETI)**：用卷积网络从BEV特征预测每个位置的元素类型概率，取argmax得到离散索引。
    - **Element Code Mapping (ECM)**：根据索引从码本检索元素特征。
    - **Critical Element Selection (CES)**：通过自注意力得分选择关键元素（保留25%），丢弃冗余元素。
    - **Masked Element Recovery (MER)**：接收端用自注意力恢复被掩码元素的索引，再利用码本重建特征。
  - **SGFF**：
    - 采用**条件潜在扩散模型**，在潜在空间（VQ-VAE编码器输出）进行扩散过程。
    - **条件**：来自其他智能体的元素特征（经相对位姿变换后拼接），通过类似ControlNet的方式注入U-Net。
    - **初始状态**：从**本车元素特征**开始（而非随机噪声），加速收敛。
    - **Uncertainty Adaptive Time Scheduler (UATS)**：根据本车预测的不确定性动态调整扩散步数，平均从10步降至5.24步。
  - **训练三阶段**：①VQ-VAE训练（地图重建）；②单智能体训练（优化EFFC）；③多智能体训练（优化SGFF的U-Net）。

## 3. 实验设计
- **数据集**：**OPV2V**（CARLA模拟器生成），包含73个场景，11464帧，每帧2-7辆车，每个车4个摄像头，关注本车周围100m×100m区域，分辨率39cm。
- **Benchmark**：BEV语义分割任务，评估**Road**和**Lane**的IoU。
- **对比方法**：F-Cooper、AttFuse、V2VNet、DiscoNet、CoBEVT。为了公平，所有基线采用相同的BEV特征压缩传输策略（按空间置信度过滤）。
- **实验设置**：通信范围70米；通信量以log2(bytes)度量；SGFF默认10次迭代；码本128种元素；潜在特征分辨率32×32。

## 4. 资源与算力
- 论文**未明确提及**使用的GPU型号、数量、训练时长等具体算力信息。仅描述训练分三阶段，但未提供硬件配置。

## 5. 实验数量与充分性
- **实验数量**：
  - **性能-带宽trade-off实验**：对不同通信量的场景（从log2=6到15）进行了9组对比。
  - **鲁棒性实验**：对位姿误差（σ=0~1）进行了6组对比。
  - **消融实验**：
    - SGFF有效性（有无SGFF，不同Na=0,2,4）4组。
    - 迭代步数Ns（1,2,5,10,20）5组。
    - UATS有效性（有无）2组。
    - CES选择策略（随机mask vs 学习mask）2组。
    - 任务导向码本 vs 生成码本对比1组。
  - **定性可视化**：多张图像展示融合过程和与其他方法对比。
- **充分性评估**：
  - **优点**：覆盖了主要性能指标（Road/Lane IoU）、通信量、位姿鲁棒性，消融实验完整验证各模块贡献，实验公平（基线统一压缩策略）。
  - **不足**：所有实验只在一个数据集（OPV2V）上进行，缺少在真实数据集或其他仿真数据集上的验证；未与其他生成式方法（如DiffBEV）直接对比；未测试不同传感器噪声或天气条件。

## 6. 主要结论与发现
- CoGMP在OPV2V上达到**SOTA性能-带宽trade-off**：Road IoU 66.19，Lane IoU 52.92，相比CoBEVT提升6.89/7.64，同时通信量减少32倍。
- 在相似带宽下，CoGMP相比其他方法提升可达10.59/11.17 Road/Lane IoU。
- 在极低带宽（仅为其他方法的1/512）下，仍保持3.03/4.33的增益。
- 在位姿误差下，鲁棒性优于所有基线，误差σ=1时仍领先9.96/9.52。
- 消融表明：SGFF贡献7.43/9.00 IoU，UATS在不损失性能情况下平均减少4.76步迭代，CES学习选择相比随机提升2.71/2.49 IoU。

## 7. 优点
- **方法创新性**：首次将生成地图先验引入协作BEV语义分割，分别利用元素先验和结构先验解决压缩和融合难题。
- **性能突出**：在压缩率和分割精度上均显著超越现有协作感知方法，尤其在高带宽下提升明显。
- **鲁棒性好**：对位姿误差具有强鲁棒性（扩散模型的结构先验可纠正冲突）。
- **高效性**：UATS动态调整迭代步数，适应不同场景复杂度，兼顾效率与精度。
- **实验公平**：基线采用统一压缩策略，对比条件一致。

## 8. 不足与局限
- **数据集局限**：仅在**模拟数据集OPV2V**上实验，未在真实数据集（如DAIR-V2X、TUMTraf V2X）上验证，泛化性存疑。
- **计算开销未量化**：未报告训练/推理所需的算力（GPU型号、数量、时间），扩散模型迭代推理可能导致延迟，未与实时性要求对比。
- **场景覆盖不全面**：未测试不同天气、光照、动态物体密度等环境变化；未评估对未见过的地图布局的泛化能力。
- **依赖VQ-VAE预训练**：需先训练码本，增加流程复杂度；码本容量（128种元素）可能限制对复杂细粒度结构的表达能力。
- **仅对比纯视觉方法**：未与融合LiDAR或毫米波雷达的多模态方法比较，实用性受限。
- **忽略协作延迟**：协作感知中通信延迟、同步问题未被纳入模型或实验。

（完）
