---
title: Generalizable Multi-Camera 3D Object Detection from a Single Source via Fourier Cross-View Learning
title_zh: 基于傅里叶跨视角学习的单源泛化多相机3D目标检测
authors: "Xue Zhao, Qinying Gu, Xinbing Wang, Chenghu Zhou, Nanyang Ye"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=R6ORNPrIdv"
tags: ["query:mmseg"]
score: 4.0
evidence: 面向自动驾驶的多相机感知与域泛化
tldr: 该论文提出FCVL框架，用于提升多相机3D目标检测对未知域的泛化能力。核心是傅里叶层次增强（FHiAug）增加域多样性，以及跨视角语义一致性损失学习域不变特征。仅用单源数据训练，在多个自动驾驶数据集上展现了出色的跨域性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 928, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 689, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1719, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 838, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 834, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 699, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 791, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 853, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r6ornpridv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 880, \"height\": 586, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 868, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 517, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 856, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r6ornpridv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 735, \"height\": 169, \"label\": \"Table\"}]"
motivation: 多相机3D检测在单源数据下泛化到新域困难，收集多域数据成本高。
method: 提出傅里叶层次增强和跨视角语义一致性损失，学习域不变特征。
result: 在多个自动驾驶数据集上仅用单源数据训练即实现优异的跨域检测性能。
conclusion: FCVL有效解决了多相机3D检测的域泛化问题，对自动驾驶实际部署有价值。
---

## Abstract
Improving the generalization of multi-camera 3D object detection is essential for safe autonomous driving in the real world. In this paper, we consider a realistic yet more challenging scenario, which aims to improve the generalization when only single source data available for training, as gathering diverse domains of data and collecting annotations is time-consuming and labor-intensive. To this end, we propose the Fourier Cross-View Learning (FCVL) framework including Fourier Hierarchical Augmentation (FHiAug), an augmentation strategy in the frequency domain to boost domain diversity, and Fourier Cross-View Semantic Consistency Loss to facilitate the model to learn more domain-invariant features from adjacent perspectives. Furthermore, we provide theoretical guarantees via augmentation graph theory. To the best of our knowledge, this is the first study to explore generalizable multi-camera 3D object detection with a single source. Extensive experiments on various testing domains have demonstrated that our approach achieves the best performance across various domain generalization methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：多相机3D目标检测在真实世界中面临严重的域偏移（domain shift）问题，当训练数据仅来自单一源域时，模型对未见过的目标域（如恶劣天气、光照变化、设备故障等）泛化能力极差。
- **动机**：现有域泛化方法大多依赖多源域数据，但采集和标注多域数据成本高昂、费时费力。因此，本文重点关注更具挑战性的**单源域泛化（Single Domain Generalization, SDG）** 场景，即仅用单一源域数据训练，提升模型对多个未知目标域的检测性能。
- **意义**：该工作首次系统性地探索多相机3D目标检测的单源域泛化问题，旨在为自动驾驶的安全部署提供实用解决方案。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用**傅里叶变换**分离图像的幅度（风格）与相位（语义）信息，在频率域对图像和特征进行层次化增强，以增加数据多样性；同时，借助多相机固有的**跨视角数据**，设计语义一致性损失，促使模型学习域不变特征。
- **关键技术细节**：
  - **Fourier Hierarchical Augmentation (FHiAug)**：
    - **图像级：Frequency Jitter**：对输入图像的傅里叶幅度和相位分别乘以随机扰动因子 $α \sim U(η,1)$ 和 $β \sim U(λ,1)$，产生多样化的亮度与结构变化。
    - **特征级：Amplitude Transfer**：在中间特征图上提取幅度分量的通道均值和标准差，通过不确定性估计生成新的风格统计量（$\beta, \gamma$），再替换原始幅度实现风格迁移，增强特征级别域多样性。
  - **Fourier Cross-View Semantic Consistency Loss**：利用多相机系统的相邻视角，将同一实例在不同视角下的特征（经FHiAug增强后）作为正样本，将不同类别的对象作为负样本，计算相位分量的三元组损失，拉近相同语义特征、推远不同语义特征。
  - **理论支撑**：基于扩张图理论（augmentation graph theory）证明FHiAug能增强源域与目标域之间的图连通性，同时保持相位语义一致性，从而降低泛化误差上界。
- **算法流程**（文字说明）：
  1. 对每个训练样本以概率 $p_i$ 执行图像级 Frequency Jitter；
  2. 在网络中间层特征上以概率 $p_f$ 执行特征级 Amplitude Transfer；
  3. 对相邻视角特征计算跨视角语义一致性损失；
  4. 联合检测损失与一致性损失优化网络参数。

### 3. 实验设计：使用数据集/场景、benchmark、对比方法
- **数据集**：
  - **nuScenes** 作为单源训练集；**nuScenes-C** 作为测试集，包含8种退化场景：Bright, Dark, Fog, Snow, Motion Blur, Color Quant, Camera Crash, Frame Lost。
  - **Argoverse 2**：取Miami晴天数据作为训练，其他五个城市晴天与阴天数据作为OOD测试。
  - 额外收集**真实昼/夜场景**数据集：61716个白天样本训练，8200个夜晚样本测试。
- **基准模型**：BEVFormer（transformer）、BEVDepth（LSS）、BEVDet（LSS）、Far3D（稀疏查询）、Sparse4Dv3、BEVFusion（多模态）等。
- **对比方法**：CPerb、DSU、DAC-SC、FACT、PD-BEV等SOTA域泛化方法，以及相应的Baseline模型。

### 4. 资源与算力
- 论文中提到所有实验均在**4块GPU**上完成，使用**ResNet50**作为骨干网络，训练24个epochs，batch size为2 per GPU，优化器为AdamW（lr=0.0002）。
- 未明确说明GPU具体型号（可能为V100或A100等），也未给出总训练时长。

### 5. 实验数量与充分性
- **实验数量**：涵盖了三个主要数据集（nuScenes + nuScenes-C、Argoverse 2、真实场景），多种基准模型（6种以上），多个对比方法（5个以上），并进行了详细的消融研究（包括不同增强组件、插入位置、超参数分析等）。此外还做了效率分析、t-SNE可视化、随机种子稳定性测试。
- **充分性**：实验设计较为全面，涵盖了不同框架（transformer、LSS、稀疏查询、多模态）、不同退化类型（天气、光照、运动模糊等）、不同场景（城市、昼夜），结果重复性较好（标准偏差仅0.0002~0.0003）。消融实验验证了各组件的贡献。对比方法的选择覆盖了频域和风格迁移类主流方法。整体实验设计客观、公平。

### 6. 论文的主要结论与发现
- 所提出的**FCVL框架**在多个测试域上显著优于所有对比方法，例如在BEVFormer上平均NDS从0.3028提升至0.3567，在BEVDepth上提升5.05%，在BEVDet上提升6.07%。
- 在Argoverse 2上基于Far3D，FCVL将OoD mAP从0.0970提升至0.1346。
- 消融实验表明图像级与特征级增强可协同提升，跨视角一致性损失进一步改善域不变特征。
- 超参数在合理范围内鲁棒，且FCVL仅在训练阶段引入额外计算（+0.11s/step），推理阶段无延迟，适合实际部署。

### 7. 优点
- **创新性**：首次将单源域泛化引入多相机3D检测，并充分利用多视角固有特性设计一致性损失。
- **有效性**：方法简单、无参数模块（非参数化），可即插即用，无需额外训练策略或生成模型，稳定高效。
- **理论性**：通过扩张图理论提供理论保障，论证增强操作对泛化边界的益处。
- **实验全面**：跨不同检测范式（BEV/非BEV、单帧/多帧、单模态/多模态）验证，并给出真实场景结果，实用性强。

### 8. 不足与局限
- **超参数依赖**：FHiAug中存在多个超参数（η, λ, p_i, p_f, γ），虽然文中指出在一定范围内性能稳定，但仍需调参。
- **极端场景性能有限**：对于“Snow”场景，虽然提升10%，但绝对NDS仍远低于其他场景（如Bright），表明对强遮挡/雾雪等极端天气的鲁棒性仍有较大提升空间。
- **设备与算力未详述**：未提供GPU型号和训练总耗时，可能影响复现与他人评估训练成本。
- **仅依赖单源域**：虽然这是设定特色，但在极端分布偏移下（如完全不同的传感器配置），其泛化能力可能仍有限。

（完）
