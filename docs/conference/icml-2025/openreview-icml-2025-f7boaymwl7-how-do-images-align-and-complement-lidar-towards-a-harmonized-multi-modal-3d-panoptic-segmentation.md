---
title: How Do Images Align and Complement LiDAR? Towards a Harmonized Multi-modal 3D Panoptic Segmentation
title_zh: 图像如何对齐并补充LiDAR？迈向和谐的多模态3D全景分割
authors: "Yining Pan, Qiongjie Cui, Xulei Yang, Na Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=F7BOaYmWl7"
tags: ["query:mmseg"]
score: 9.0
evidence: 用于自动驾驶感知的多模态融合
tldr: 针对LiDAR点云稀疏性导致远距离小物体识别困难的问题，本文提出IAL多模态3D全景分割框架，通过引入图像信息辅助LiDAR。提出模态同步数据增强和无需后处理的端到端融合策略，显著提升了自动驾驶场景下对小物体和远处物体的分割精度，在nuScenes等数据集上达到了新的最佳性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1741, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f7boaymwl7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1759, \"height\": 1721, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 579, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1779, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 473, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 869, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1246, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 609, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f7boaymwl7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 980, \"height\": 295, \"label\": \"Table\"}]"
motivation: LiDAR数据稀疏难以准确识别小物体，现有多模态方法存在数据增强未对齐和依赖后处理的问题。
method: 提出IAL框架，包含模态同步数据增强和端到端融合，无需后处理。
result: 在多个自动驾驶数据集上，IAL在全景分割指标上显著优于现有方法。
conclusion: IAL有效融合了LiDAR与图像信息，提升了自动驾驶感知的准确性。
---

## Abstract
LiDAR-based 3D panoptic segmentation often struggles with the inherent sparsity of data from LiDAR sensors, which makes it challenging to accurately recognize distant or small objects. Recently, a few studies have sought to overcome this challenge by integrating LiDAR inputs with camera images, leveraging the rich and dense texture information provided by the latter. While these approaches have shown promising results, they still face challenges, such as misalignment during data augmentation and the reliance on post-processing steps. To address these issues, we propose **I**mage-**A**ssists-**L**iDAR (**IAL**), a novel multi-modal 3D panoptic segmentation framework.
In IAL, we first introduce a modality-synchronized data augmentation strategy, PieAug, to ensure alignment between LiDAR and image inputs from the start. Next, we adopt a transformer decoder to directly predict panoptic segmentation results. To effectively fuse LiDAR and image features into tokens for the decoder, we design a Geometric-guided Token Fusion (GTF) module. Additionally, we leverage the complementary strengths of each modality as priors for query initialization through a Prior-based Query Generation (PQG) module, enhancing the decoder’s ability to generate accurate instance masks. Our IAL framework achieves state-of-the-art performance compared to previous multi-modal 3D panoptic segmentation methods on two widely used benchmarks. Code and models are publicly available at https://github.com/IMPL-Lab/IAL.git.

---

## 论文详细总结（自动生成）

# 论文总结：How Do Images Align and Complement LiDAR? Towards a Harmonized Multi-modal 3D Panoptic Segmentation

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：基于LiDAR的3D全景分割受限于点云稀疏性，难以准确识别远处或小物体（如行人、自行车）。现有融合图像的多模态方法（如LCPS、Panoptic-FusionNet）存在两个主要缺陷：
  - 数据增强时仅对LiDAR增广，导致多模态间不对齐，模型过度依赖LiDAR；
  - 依赖聚类等后处理步骤进行实例分割，效率低且无法利用全局上下文。
- **整体含义**：本文提出一种端到端的多模态3D全景分割框架IAL，旨在通过对齐图像与LiDAR信息的增强、融合与查询初始化，提升对小物体和远处物体的感知能力，无需后处理。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用图像的丰富纹理信息辅助LiDAR，通过三方面创新实现和谐融合：
  1. **模态同步增强（PieAug）**：提出通用多模态数据增强策略，将LiDAR柱状体素与对应图像区域配对，同步进行实例粘贴和场景交换（沿半径/角度/高度轴切割“派”式交换），确保两者增强后仍对齐。
  2. **几何引导的Token融合（GTF）**：为解决柱状体素大小不一导致的对齐误差，利用LiDAR物理点（而非虚拟中心）投影到图像获取对应特征，并设计尺度感知位置编码（SPE），将体素8个角点作为极值点编码尺度信息，实现一致的感受野表示，进而融合多模态token。
  3. **基于先验的查询生成（PQG）**：利用LiDAR的几何先验（通过BEV热图+NMS）和图像的纹理先验（通过Grounding-DINO+SAM提取2D掩码，再投射到3D并聚类）生成实例查询，同时引入可学习的无先验查询，配合语义查询输入Transformer解码器直接预测掩码和类别。
- **算法流程**：输入点云→柱状体素化→PieAug同步增强→3D编码器（Cylinder3D）和2D编码器（ResNet-18+SwiftNet）提取特征→GTF融合token（包含SPE）→PQG生成三类实例查询+语义查询→Transformer解码器迭代更新→直接输出全景分割结果（无后处理）。

## 3. 实验设计
- **数据集**：
  - **nuScenes**：32线LiDAR，6个摄像头，10个“thing”类+6个“stuff”类，约4万帧。使用验证集（6019帧）和测试集。
  - **SemanticKITTI**：64线LiDAR，2个前视摄像头，8个“thing”类+11个“stuff”类，约2万帧训练、4千帧验证。
- **评估指标**：Panoptic Quality (PQ) 为主要指标，包含RQ（识别质量）、SQ（分割质量），以及针对thing/stuff的子指标，还有PQ†（用mIoU替换stuff的PQ）。
- **对比方法**：
  - LiDAR-only方法：DS-Net, EfficientLPS, Panoptic-PolarNet, Panoptic-PHNet, CFNet, CenterLPS, P3Former等。
  - 多模态方法：LCPS（ICCV 2023），Panoptic-FusionNet（2024）。
  - 额外包含使用时间信息或检测标注的方法（如4DFormer, LidarMultiNet*）。
- **实验结果**：
  - nuScenes验证集：IAL达到PQ 82.3%，比LCPS（79.8%）高2.5%，比Panoptic-FusionNet（77.2%）高5.1%。
  - nuScenes测试集：IAL达到PQ 82.0%，在所有方法中排名第一或第二。
  - SemanticKITTI验证集：IAL（PQ 63.1%）比LCPS（59.0%）高4.1%。

## 4. 资源与算力
- 文中明确说明：使用4张NVIDIA A40 GPU，batch size=2。
- 训练轮次：nuScenes训练80个epoch，SemanticKITTI训练36个epoch。
- 学习率0.0008，在设定epoch时减半。
- **注**：未提及总训练时间具体数值，但给出了推理速度对比（IAL核心组件4.0 FPS，LCPS 1.7 FPS）。

## 5. 实验数量与充分性
- **实验组数**：
  - 主实验：2个数据集（nuScenes验证+测试，SemanticKITTI验证），共3个表格（Table 2,3,4）。
  - 消融实验：
    - 模块消融（Table 5）：逐步验证PieAug、GTF、PQG的贡献。
    - PQG内部消融（Table 6）：对比几何先验、纹理先验、无先验查询组合。
    - 增强策略对比（Table 7）：与PolarMix、LaserMix对比，含是否同步图像增广。
    - GTF内部消融（补充材料Table 8）：Token选择与位置编码的不同设计。
  - 附加实验：夜间/雨天子集性能（Table 10）、推理速度与参数量（Table 9）。
- **充分性评价**：实验设计较全面，覆盖主流数据集、多模态对比方法、关键模块消融、鲁棒性测试（恶劣天气），且补充材料提供了更多细节。公平性方面，所有实验使用相同超参，未采用测试时增强（TTA），对比方法均引用官方结果或复现。总体充分客观。

## 6. 主要结论与发现
- IAL通过同步增强、几何引导融合和先验查询生成三个模块，有效解决了多模态数据不对齐和依赖后处理的问题，显著提升了3D全景分割性能。
- 图像信息在识别小物体、远处物体以及区分外观相似类（如车与卡车）方面提供关键补充。
- 提出的PieAug可作为通用多模态增强框架，兼容现有LiDAR增强方法。
- 在不使用任何TTA的情况下，IAL在nuScenes和SemanticKITTI上均达到SOTA，验证了方法的有效性和泛化能力。

## 7. 优点（方法或实验设计亮点）
- **方法创新**：
  - PieAug首次实现LiDAR与图像同步增强，且可扩展为已有LiDAR增强的通用形式。
  - GTF中尺度感知位置编码（SPE）利用体素角点编码感受野，比仅用中心点更合理，有效缓解投影误差。
  - PQG将图像和LiDAR先验以查询形式显式注入Transformer解码器，同时保留可学习无先验查询，平衡了难易样本。
- **实验设计**：
  - 在nuscene夜间/雨天子集上测试，验证了方法的鲁棒性。
  - 提供了推理速度和模型大小对比，表明IAL在精度和效率上均优于LCPS（2倍以上推理速度）。
  - 补充材料中深入分析了GTF不同设计的性能差异。

## 8. 不足与局限
- **实验覆盖**：仅在两个数据集上验证，且均为自动驾驶场景（城市道路），未涉及室内或更复杂环境。泛化性有待更多场景验证。
- **纹理先验依赖外部模型**：PQG中纹理先验通过Grounding-DINO和SAM提取，这些模型本身有局限（如对遮挡、极端光照敏感），且增加了额外计算开销（文中表9显示包括掩码生成时FPS为0.9）。
- **查询数量固定**：PQG中几何/纹理/无先验查询数量固定为128+128=256，未自适应场景复杂度，可能导致冗余或不足。
- **采样方法较简单**：作者在Limitations部分承认，PQG中的采样（FPS）较为通用，未针对任务进行定制，未来可探索更精细的采样策略。
- **风险**：未讨论模型对对抗攻击的鲁棒性，以及在恶劣天气下（如暴雨、浓雾）图像和LiDAR同时退化时的性能边界。

（完）
