---
title: "InstanceGaussian: Appearance-Semantic Joint Gaussian Representation for 3D Instance-Level Perception"
title_zh: InstanceGaussian：面向3D实例级感知的外观-语义联合高斯表示
authors: "Li, Haijie, Wu, Yanmin, Meng, Jiarui, Gao, Qiankun, Zhang, Zhiyao, Wang, Ronggang, Zhang, Jian"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_InstanceGaussian_Appearance-Semantic_Joint_Gaussian_Representation_for_3D_Instance-Level_Perception_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 外观-语义联合高斯表示的3D实例分割
tldr: 3D高斯泼溅在场景理解中面临外观与语义不平衡、边界不一致等问题。InstanceGaussian提出语义脚手架高斯表示，联合学习外观和语义特征，并通过渐进训练自适应聚合实例。在多个室内外数据集上提升了实例分割精度。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1613, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 783, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 813, \"height\": 162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1616, \"height\": 1011, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1618, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1636, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1624, \"height\": 592, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-instancegaussian-appearance-semantic-joint-gaussian-representation-for-3d-instance-level-perception-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 219, \"label\": \"Table\"}]"
motivation: 现有3D高斯表示存在外观语义失衡和边界模糊问题。
method: 设计语义脚手架高斯表示，联合学习外观和语义，渐进训练聚合实例。
result: 在3D实例分割任务上达到先进性能。
conclusion: 联合学习与自适应聚合可提升3D场景理解的实例级精度。
---

## Abstract
3D scene understanding is vital for applications in autonomous driving, robotics, and augmented reality. However, scene understanding based on 3D Gaussian Splatting faces three key challenges: (i) an imbalance between appearance and semantics, (ii) inconsistencies in object boundaries, and (iii) difficulties with top-down instance segmentation. To address these challenges, we propose InstanceGaussian, a method that jointly learns appearance and semantic features while adaptively aggregating instances. Our contributions are as follows: (i) a new Semantic-Scaffold-GS representation to improve feature representation and boundary delineation, (ii) a progressive training strategy for enhanced stability and segmentation, and (iii) a category-agnostic, bottom-up instance aggregation approach for better segmentation. Experimental results demonstrate that our approach achieves state-of-the-art performance in category-agnostic, open-vocabulary 3D point-level segmentation, validating the effectiveness of our proposed method.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

3D场景理解在自动驾驶、机器人和增强现实中至关重要。基于3D高斯泼溅（3DGS）的方法在场景理解中面临三个关键挑战：  
- **外观与语义的不平衡**：同一物体或区域需要多个外观各异的高斯体来表示纹理细节，但语义仅需单一属性，导致高斯数量对外观不足、对语义冗余。  
- **外观与语义的不一致性**：纯外观重建时，一个高斯可能同时表示不同物体或区域（如边界处的前景和背景），而现有语言嵌入高斯方法（如LangSplat、OpenGaussian）采用解耦学习策略，忽略了颜色与语义的相互依赖，造成不一致，妨碍分割。  
- **自上而下实例分割的困难**：现有方法（如GaussianGrouping、OpenGaussian）依赖先验类别信息或固定编码本数量，容易在复杂场景中产生过分割或欠分割。

**研究动机**：为了同时解决这三个问题，作者提出InstanceGaussian，通过联合学习外观与语义、自适应自下而上地聚合实例，实现更准确、鲁棒的3D实例级感知。

### 2. 论文提出的方法论

#### 核心思想
提出一种**外观-语义联合高斯表示**，在Scaffold-GS框架的基础上，让每个锚点（anchor）携带外观嵌入和实例特征，其子高斯共享相同实例特征但拥有不同外观属性，从而平衡外观与语义的表示。同时，采用**渐进式联合训练策略**逐步引入语义约束，保证一致性。最后，通过**自下而上、类别无关的实例聚合**方法（先过分割，再基于图连通性聚集）自适应得到最终实例。

#### 关键技术细节
1. **Semantic-Scaffold-GS表示**  
   - 每个锚点A包含位置μ'、外观嵌入e、实例特征f。  
   - 从每个锚点衍生n个神经高斯点G（n=5n'），子高斯的颜色c、旋转R、缩放S、偏移o由锚点的外观嵌入e经MLP解码得到，而实例特征f直接共享锚点的f。  
   - 这样同一锚点下的5个子高斯有不同外观但相同语义，缓解了表示不平衡。

2. **渐进式外观-语义联合训练**  
   - 分为三个阶段：  
     - 0-10k步：仅训练外观属性（RGB重建损失L_rgb）。  
     - 10-20k步：独立训练外观与语义（实例特征冻结外观）。  
     - 20-30k步：联合训练外观与语义。  
   - 语义损失沿用OpenGaussian的帧内平滑损失L_s和帧间对比损失L_c，但对L_c进行截断改进：只有当两个不同掩码的平均特征距离小于阈值τ（0.4）时才施加对比损失，避免迫使所有对象无限远离，提高联合训练稳定性。

3. **自下而上、类别无关的实例聚合**  
   - **过分割**：在高斯点云上使用最远点采样（FPS）选取s个种子点（默认1000），结合位置编码和实例特征进行k-means聚类，得到s个子对象。  
   - **子对象聚合**：将子对象作为节点，构建图，边权重由两个准则计算：  
     - 节点特征的L2距离（语义相似性）；  
     - 空间邻近性（体素化后判断是否相邻，指示函数返回0/1）。  
   - 边权重 = 特征距离 × 空间指示函数。  
   - 对权重在(0, γ]（γ=0.1）内的节点进行图连通分量分析（如BFS或并查集），自适应聚合为完整对象，得到最终实例标签和特征。

### 3. 实验设计

- **数据集与基准**  
  - **ScanNet**：用于类别无关3D实例分割和开放词汇语义分割任务。采用OpenGaussian选定的10个场景，计算实例级mIoU和mAcc（@0.25）。  
  - **LeRF数据集**：用于开放词汇3D目标选择与渲染任务，评估渲染后2D掩码的mIoU和mAcc。  
  - **基准**：主要对比高斯基方法（OpenGaussian、GaussianGrouping、LangSplat、LEGaussians），并列出深度辅助方法MaskClustering作为参考。

- **对比方法**  
  - 类别无关实例分割：OpenGaussian [34]、GaussianGrouping [38]、MaskClustering [37]（深度辅助）。  
  - 开放词汇语义分割：LangSplat [25]、LEGaussians [29]、OpenGaussian [34]、MaskClustering。  
  - 开放词汇3D选择与渲染：LangSplat、LEGaussians、OpenGaussian。

### 4. 资源与算力

论文中**未明确说明**训练所使用的GPU型号、数量、训练时长等算力信息。仅在结论部分提到“更长的训练时间，因为需要通过MLP计算外观属性”，但未给出具体数值。因此，无法量化算力需求。

### 5. 实验数量与充分性

- **实验数量**：共进行了四组主要实验：  
  1. 类别无关3D实例分割（表1）。  
  2. 开放词汇语义分割（表2）。  
  3. 开放词汇3D目标选择与渲染（表3）。  
  4. 消融实验（表4、表5）：分别验证联合表示与联合训练的有效性，以及聚合条件中特征与空间邻近性的贡献。  
- **充分性**：实验覆盖了三个核心下游任务，且消融实验针对两个关键设计（表示/训练策略、聚合条件）进行了分析。对比方法均为近期相关工作，评测指标（mIoU、mAcc）是标准度量。但仅在ScanNet的一个子集（10个场景）上评估，未在完整的ScanNet或更大规模数据集（如Replica、S3DIS）上报告，存在一定的推广风险。总体而言，实验设计较充分且公平，但覆盖广度可以扩大。

### 6. 论文的主要结论与发现

- Semantic-Scaffold-GS表示能有效平衡外观与语义，改善物体边界质量。  
- 渐进式联合训练避免了解耦学习导致的语义-外观不一致，提升了模型稳定性。  
- 自下而上的自适应聚合方法无需预设类别数，避免了过/欠分割，优于OpenGaussian的朴素k-means。  
- 在类别无关实例分割、开放词汇语义分割和3D目标选择渲染任务上均达到当前最佳（SOTA），显著超越高斯基方法，甚至某些指标超越了使用深度信息的MaskClustering。

### 7. 优点

1. **创新性强**：同时解决了外观-语义不平衡、不一致和实例分割自顶向下依赖的三个问题，提出了统一的解决方案。  
2. **设计合理**：语义-脚手架表示共享实例特征，兼顾效率；渐进训练稳定；自下而上聚合自适应，无需预定义实例数。  
3. **性能优异**：在多个任务上显著领先，尤其开放词汇语义分割提升明显（19类mIoU从OpenGaussian的24.73提升至40.66）。  
4. **消融充分**：通过消融实验验证了每个组件的必要性，逻辑清晰。

### 8. 不足与局限

1. **训练效率低**：由于需要通过MLP解码外观属性，渲染速度较慢，训练时间更长。  
2. **依赖SAM掩码质量**：当场景中大部分图像被SAM错误分割时，分割精度会受影响（论文在结论中指出）。  
3. **算力信息缺失**：未报告训练资源消耗，不利于公平比较和复现。  
4. **评估场景有限**：仅在ScanNet的10个场景上评估，未在更大规模或多样化数据集（如多物体堆叠、室外场景）上验证，泛化性有待进一步确认。  
5. **超参数敏感性**：默认设置s=1000、γ=0.1等，未讨论超参数的影响范围，可能在不同场景需要调整。

（完）
