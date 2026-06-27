---
title: "HetSSNet: Spatial-Spectral Heterogeneous Graph Learning Network for Panchromatic and Multispectral Images Fusion"
title_zh: HetSSNet：用于全色和多光谱图像融合的空间-光谱异质图学习网络
authors: "Mengting Ma, Yizhen Jiang, Mengjiao Zhao, Jiaxin Li, Wei Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=8EUR45XguK"
tags: ["query:mmseg"]
score: 7.0
evidence: 多模态遥感图像融合
tldr: 针对遥感图像全色和多光谱融合中空间-光谱属性重建的挑战，本文提出HetSSNet空间-光谱异质图学习网络，通过构建定制化图结构捕获不规则地物的空间-光谱关系，并设计了特征学习机制。实验证明该方法在全色锐化任务上优于CNN和Transformer方法，为遥感融合任务提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1796, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1793, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1326, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1292, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1822, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1791, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8eur45xguk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1844, \"height\": 896, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 891, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 890, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 886, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1714, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8eur45xguk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1050, \"height\": 752, \"label\": \"Table\"}]"
motivation: CNN和Transformer难以处理遥感图像中不规则地物的空间-光谱关系。
method: 构建异质图结构，利用图学习网络建模空间-光谱先验关系。
result: 在全色锐化基准上，HetSSNet在空间和光谱精度上均达到最优。
conclusion: HetSSNet验证了图网络在遥感图像融合中的优越性。
---

## Abstract
Remote sensing pansharpening aims to reconstruct spatial-spectral properties during the fusion of panchromatic (PAN) images and low-
resolution multi-spectral (LR-MS) images, finally generating the high-resolution multi-spectral (HR-
MS) images. In the mainstream modeling strategies, i.e., CNN and Transformer, the input images are treated as the equal-sized grid of pixels in the Euclidean space. They have limitations in facing remote sensing images with irregular ground objects. Graph is the more flexible structure, however, there are two major challenges when modeling spatial-spectral properties with graph: 1) constructing the customized graph structure for spatial-spectral relationship priors; 2) learning the unified spatial-spectral representation through the graph. To address these challenges, we propose the spatial-spectral heterogeneous graph learning network, named HetSSNet.
Specifically, HetSSNet initially constructs the heterogeneous graph structure for pansharpening, which explicitly describes pansharpening-specific relationships. Subsequently, the basic relationship pattern generation module is designed to extract the multiple relationship patterns from the heterogeneous graph. Finally, relationship pattern aggregation module is exploited to collaboratively
learn unified spatial-spectral representation across different relationships among nodes with adaptive importance learning from local and global perspectives. Extensive experiments demonstrate the significant superiority and generalization of HetSSNet.

---

## 论文详细总结（自动生成）

# 论文总结：HetSSNet：用于全色和多光谱图像融合的空间-光谱异质图学习网络

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：遥感图像全色锐化（pansharpening）旨在融合高分辨率全色（PAN）图像和低分辨率多光谱（LR-MS）图像，生成高分辨率多光谱（HR-MS）图像。现有主流方法（CNN和Transformer）将输入视为欧氏空间中的规则像素网格，难以有效处理遥感图像中**不规则地物对象**（如森林、建筑、街道等）的空间-光谱关系。
- **核心挑战**：
  1. 如何为空间-光谱关系先验（PAN的空间关系、LR-MS的谱内关系、PAN与LR-MS之间的光谱关系）构建定制化的图结构。
  2. 如何通过单一图结构学习统一的空间-光谱表征，同时保持空间和光谱属性重建的平衡。
- **整体意义**：提出首个针对全色锐化的空间-光谱异质图学习网络，将图结构引入非欧空间，有望突破CNN/Transformer在遥感融合任务中的性能瓶颈。

## 2. 方法论

### 核心思想
- 构建一个**属性多重异质图（Attributed Multiplex Heterogeneous Graph）**，包含两种类型的节点（PAN图像块节点、LR-MS各波段节点）和三种类型的边（PAN内部空间关系、LR-MS内部谱间关系、PAN与LR-MS之间的光谱关系），显式编码全色锐化特定的关系先验。
- 通过**基本关系模式生成模块**，从异质图中提取所有可能的空间-光谱关系模式矩阵（最多7种）。
- 通过**关系模式聚合模块**，从**局部视角**（自适应加权聚合各关系模式，输入GCN）和**全局视角**（基于节点间全局关系模式相似性构建相似矩阵，再输入GCN）分别学习节点表征，并利用**对比学习**最大化局部与全局表征的一致性，最终融合得到统一表征。

### 关键技术细节
- **节点构建**：将PAN图像分割为N个重叠块，每个块提取d维特征作为第一类节点；将LR-MS图像每个波段也分割为N个重叠块，每个波段提取d维特征作为第二类节点（每位置4个节点）。
- **边构建**：使用k近邻算法（k-NN）分别为PAN节点、LR-MS节点建立内部邻接边，以及PAN与LR-MS之间的跨类型邻接边，边权重由余弦相似度度量。
- **基本关系模式提取**：将异质图的邻接矩阵按边类型解耦为{A_r}，通过XNOR与逻辑变量操作，再经bitwise AND生成所有基本关系模式矩阵˜A_r。
- **局部聚合**：使用可学习权重α_r加权求和所有˜A_r得到˜A_Local，输入简化GCN（无非线性激活，多层聚合后取平均）得到HLocal。
- **全局聚合**：对每个˜A_r按行求和得到列向量，可学习权重β拼接得到全局关系模式矩阵B，计算B×B^T并归一化得到相似矩阵˜A_Global，再输入GCN得到HGlobal。
- **对比损失**：L_cl = - Σ_i log [exp(s(HLocal,i, HGlobal,i)/τ) / Σ_j exp(s(HLocal,i, HGlobal,j)/τ)]，τ为温度超参数。
- **最终输出**：H = 0.5*(HLocal + HGlobal)，与真实HR-MS图像计算L1损失，联合优化L = L1 + γL_cl。

### 算法流程
1. 输入PAN和LR-MS图像。
2. 分块并特征编码，构造异质图节点和边。
3. 提取所有基本关系模式矩阵。
4. 局部聚合：加权求和→GCN→HLocal。
5. 全局聚合：计算全局模式相似矩阵→GCN→HGlobal。
6. 对比学习增强表征。
7. 输出融合后的节点特征，重塑为HR-MS图像。
8. 使用L1损失和对比损失联合优化。

## 3. 实验设计

### 数据集与场景
- **三个数据集**：WorldView-3、QuickBird、GaoFen-2（均为多光谱4波段，PAN分辨率更高）。
- **数据生成**：严格遵循Wald协议，LR-MS图像尺寸32×32×4，PAN图像128×128×1，目标HR-MS 128×128×4。
- **训练/测试划分**：GaoFen-2：35725训练 / 3370测试；QuickBird：12119 / 356；WorldView-3：11856 / 3639。

### Benchmark
- **对比方法**：
  - 传统方法：SFIM、BROVEY、GS。
  - 深度学习方法（CNN/Transformer）：SRPPNN、DCFNet、CTINN、SFIINet、Hyperformer、MDCUN、BiMPan、LGTEUN、MSDDN、FAMENet、WINet、HFIN、FusionMamba。
  - 其他图方法：GPCNet（使用独立GCN建模空间和光谱关系）。
- **全部重新训练**，确保公平比较。

### 评估指标
- **降分辨率**：PSNR↑、SSIM↑、SAM↓、ERGAS↓、SCC↑。
- **全分辨率（无GT）**：Dλ↓、Ds↓、QNR↑。

## 4. 资源与算力
- **GPU**：4块 NVIDIA RTX A6000。
- **框架**：PyTorch。
- **优化器**：Adam（β1=0.9, β2=0.999）。
- **训练超参数**：
  - 迭代次数：WorldView-3: 30000；QuickBird、GaoFen-2: 28000。
  - 批大小：4。
  - 初始学习率：1×10⁻⁴，每3000次衰减0.85。
- **计算资源描述清晰**，较充分。

## 5. 实验数量与充分性
- **定量实验**：在三个数据集上报告了5个指标的平均值，每个方法均对比。
- **可视化实验**：提供了降分辨率场景的融合结果和误差图（WorldView-3、QuickBird、GaoFen-2）。
- **全分辨率泛化实验**：对每个数据集20张未见全分辨率图像，评估3个无参考指标。
- **消融实验**（GaoFen-2数据集）：
  - 基本关系模式生成模块：对比元路径采样、解耦邻接矩阵。
  - 关系模式聚合模块：去除局部或全局聚合。
  - 聚合层数（1~4层）。
  - 超参数γ（0, 0.01, 0.5, 1）。
- **八波段WorldView-3额外实验**：展示泛化能力。
- **充分性评价**：实验覆盖了主要方法、多数据集、多指标、消融、泛化，且全部重新训练保证公平，实验设计合理、充分、客观。

## 6. 主要结论与发现
- HetSSNet在几乎所有的指标上（PSNR、SSIM、SAM、ERGAS、SCC、QNR）均显著优于现有SOTA方法，尤其在空间纹理重建和光谱保真度方面表现突出。
- 传统方法（SFIM、BROVEY、GS）性能明显低于深度学习方法。
- CNN和Transformer（如DCFNet、Hyperformer）在QuickBird等数据集上表现较差，说明刚性网格结构对不规则地物建模的局限性。
- GPCNet直接使用GCN破坏了空间-光谱平衡，而HetSSNet通过异质图结构统一学习，实现了更好性能。
- 消融实验验证了基本关系模式生成和局部-全局聚合模块均不可或缺，对比学习（γ≈0.03）能提升性能。
- 全分辨率场景的泛化能力也优于对比方法。

## 7. 优点
- **创新性**：首次将异质图结构引入遥感全色锐化，突破了CNN/Transformer在非欧空间建模的局限。
- **定制化设计**：明确建模PAN空间关系、LR-MS谱内关系、PAN-LR光谱关系三种先验，更贴合任务特性。
- **双视角聚合**：局部聚合保留邻域特性，全局聚合利用节点间关系模式相似性，配合对比学习增强表征一致性。
- **实验充分**：多数据集、多方法、多指标、消融、可视化、全分辨率泛化，且全部重训，公平性高。
- **性能领先**：在三个数据集上均取得SOTA结果，尤其在空间和光谱指标上大幅提升。

## 8. 不足与局限
- **过平滑问题未深入讨论**：文中提到层数增加到2~3层时性能下降（可能是GCN过平滑），但未提出针对性解决方案，仅通过少量层数规避。
- **计算复杂度**：局部和全局聚合的时间复杂度为O((N+dl)n² + ...)，空间复杂度为O(Nn² + ...)，大图场景下效率可能成为瓶颈（文中未提供实际推理时间对比）。
- **场景局限性**：论文主要测试静态遥感场景，未涉及快速移动物体、多时相或复杂遮挡等更具挑战的场景（作者也提到未来方向）。
- **消融实验仅在一个数据集（GaoFen-2）上进行**，未在其他数据集重复消融，泛化稳健性验证稍弱。
- **对比方法未覆盖最新基于Mamba的方法（如FusionMamba）虽已包含，但可能忽略某些2025年新方法**（本文发表于ICML 2025，属于前沿，但仍有未纳入的方法）。
- **全分辨率评估仅使用三指标**，缺乏与更多无参考方法的对比。

（完）
