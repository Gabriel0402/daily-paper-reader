---
title: Resilient Sensor Fusion Under Adverse Sensor Failures via Multi-Modal Expert Fusion
title_zh: 基于多模态专家融合的传感器失效下鲁棒融合方法
authors: "Park, Konyul, Kim, Yecheol, Kim, Daehun, Choi, Jun Won"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Park_Resilient_Sensor_Fusion_Under_Adverse_Sensor_Failures_via_Multi-Modal_Expert_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 自动驾驶中的多模态传感器融合感知
tldr: 自动驾驶多模态融合在传感器故障时性能骤降。本文提出MoME，利用混合专家架构解耦模态依赖，通过并行专家解码器应对LiDAR衰减、相机遮挡等故障，在nuScenes数据集上显著提升鲁棒性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 1003, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1709, \"height\": 1003, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1710, \"height\": 651, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1809, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 762, \"height\": 540, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 879, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-park-resilient-sensor-fusion-under-adverse-sensor-failures-via-multi-modal-expert-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 458, \"label\": \"Table\"}]"
motivation: 现有传感器融合在LiDAR或相机失效时性能严重下降。
method: 设计三个并行专家解码器分别处理不同模态，通过门控机制融合输出。
result: 在多种传感器失效场景下均保持高检测精度。
conclusion: MoME有效提升了自动驾驶感知系统在异常条件下的可靠性。
---

## Abstract
Modern autonomous driving perception systems utilize complementary multi-modal sensors, such as LiDAR and cameras. Although sensor fusion architectures enhance performance in challenging environments, they still suffer significant performance drops under severe sensor failures, such as LiDAR beam reduction, LiDAR drop, limited field of view, camera drop, and occlusion. This limitation stems from inter-modality dependencies in current sensor fusion frameworks. In this study, we introduce an efficient and robust LiDAR-camera 3D object detector, referred to as MoME, which can achieve robust performance through a mixture of experts approach. Our MoME fully decouples modality dependencies using three parallel expert decoders, which use camera features, LiDAR features, or a combination of both to decode object queries, respectively. We propose Multi-Expert Decoding (MED) framework, where each query is decoded selectively using one of three expert decoders. MoME utilizes an Adaptive Query Router (AQR) to select the most appropriate expert decoder for each query based on the quality of camera and LiDAR features. This ensures that each query is processed by the best-suited expert, resulting in robust performance across diverse sensor failure scenarios. We evaluated the performance of MoME on the nuScenes-R benchmark. Our MoME achieved state-of-the-art performance in extreme weather and sensor failure conditions, significantly outperforming the existing models across various sensor failure scenarios.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现代自动驾驶感知系统依赖多模态传感器（如LiDAR和相机）的互补特性，但现有融合架构在严重传感器故障（如LiDAR波束衰减、LiDAR完全丢失、视场角受限、相机丢失、遮挡等）下性能显著下降。根本原因在于当前融合框架中**模态间的依赖关系**——一个传感器的污染会级联影响整体感知质量。
- **整体含义**：提升多模态融合系统在真实世界传感器故障条件下的鲁棒性对于自动驾驶安全至关重要。论文旨在通过解耦模态依赖，避免故障传感器对正常传感器的干扰，从而在各种故障场景下保持高检测精度。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：受混合专家（Mixture of Experts, MoE）框架启发，设计三个并行专家解码器，分别仅使用相机特征、仅使用LiDAR特征、以及同时使用两种特征来解码对象查询，从而彻底解耦模态依赖。通过自适应查询路由器（Adaptive Query Router, AQR）为每个查询动态选择最合适的专家解码器。
- **关键技术细节**：
  - **Multi-Expert Decoding (MED) 框架**：包含三个独立专家解码器（LiDAR解码器、Camera解码器、LiDAR-Camera解码器），每个解码器结构基于DETR Transformer解码器。
  - **Adaptive Query Router (AQR)**：对于每个对象查询，基于其参考点位置在LiDAR BEV和相机图像上生成局部注意力掩码（Local Attention Mask），然后对局部多模态特征进行交叉注意力计算，输出模态选择概率（\(p_{l}, p_{c}, p_{lc}\)），选择概率最高的专家解码器。
  - **训练流程**：3阶段策略。
    1. 第一阶段：所有查询并行送入所有三个解码器，全监督训练所有解码器（损失为三部分检测损失之和）。
    2. 第二阶段：冻结训练好的解码器，单独训练AQR模块。采用随机传感器drop增强（1/3概率drop LiDAR, 1/3 drop相机, 1/3完整），以交叉熵损失监督AQR选择正确模态。
    3. 推理阶段：每个查询只被分配给一个专家解码器，计算复杂度与单解码器相当。
- **无需针对故障类型专门训练**：仅通过随机传感器drop训练，即可泛化到其他未见过的故障类型（如视场角受限、遮挡等）。

## 3. 实验设计：数据集、Benchmark与对比方法
- **数据集**：
  - **nuScenes**（标准验证集）
  - **nuScenes-R**：模拟LiDAR Drop、Limited FOV（±60°）、Object Failure（框内点云50%概率移除）、Camera View Drop（多视角图像置零）、Occlusion（泥浆遮挡）等5类传感器故障。
  - **nuScenes-C**：包含27种常见退化（聚焦于极端天气：雾、雪、阳光下）。
- **基准（Benchmark）**：采用nuScenes标准度量**mAP**和**NDS**，并引入**相对性能比 \(R\)**（平均故障性能/干净性能）评估鲁棒性。
- **对比方法**：包括单模态基线（DETR3D、CenterPoint）、多模态融合方法（UniBEV、TransFusion、BEVFusion、MetaBEV、DeepInteraction、CMT、UniTR、SparseFusion等）。部分方法标注†表示使用开源代码复现。

## 4. 资源与算力
- **未明确说明**：论文中未提及训练使用的GPU型号、数量、训练时长等具体资源信息。仅提供推理延迟（约4ms增加）。

## 5. 实验数量与充分性
- **实验组数**：
  - **主结果**（表1）：在nuScenes-R上对比12种方法，覆盖5种故障+干净场景，共7列指标。
  - **天气/夜间结果**（表2）：在nuScenes验证集上对比rainy和night场景。
  - **极端天气结果**（表3）：在nuScenes-C上对比fog、snow、sunlight场景。
  - **消融实验**（表4）：验证MED、AQR、LAM各组件贡献。
  - **查询分配分析**（表5）：展示AQR在不同故障下对三个专家解码器的选择分布。
  - **定性结果**（图4）：可视化对比CMT与MoME检测结果。
- **充分性评估**：
  - **全面**：覆盖了主要传感器故障类型和恶劣天气，对比方法包含当前SOTA（CMT等）。
  - **公平**：采用相同种子数据和评估协议，复现已有方法结果（†标识）。
  - **客观**：使用官方nuScenes-R和nuScenes-C基准，指标标准化。
  - **略有限制**：未测试所有27种nuScenes-C退化（仅选三种天气）；未在真实硬件平台测试实时性。

## 6. 主要结论与发现
- MoME在多数传感器故障场景下达到**SOTA**，尤其在**Limited FOV**（mAP+6.7%，NDS+4.3% vs CMT）和**LiDAR Drop**（mAP+4.2%）显著提升。
- 相对性能比R：MoME较CMT提高2.1% mAP和1.8% NDS，表明鲁棒性更优。
- 消融实验证明AQR+LAM联合工作最关键，单独使用MED（并行解码+置信度选择）反而因置信度未校准导致性能下降。
- AQR查询分配分析验证了其行为合理：干净时94%选择LiDAR-Camera专家；LiDAR故障时转向Camera；相机故障时转向LiDAR；部分退化和遮挡时混合分配。
- 在恶劣天气（雾、雪、日光）和夜间条件下，MoME表现同样优异，无需针对性训练。

## 7. 优点
- **方法创新**：将MoE思想引入多模态融合解耦，避免了传统融合的模态依赖级联问题。
- **高效性**：每个查询仅由一个专家解码器处理，推理计算量仅略高于单解码器（延迟增加4ms），远低于穷举并行解码（+40ms）。
- **可集成性**：MED框架可无缝集成到任意Transformer-based融合架构。
- **训练简洁**：仅需随机传感器drop增强即可泛化到多样故障，无需生成故障数据。
- **鲁棒性突出**：在nuScenes-R多个故障场景和nuScenes-C极端天气下均取得SOTA。

## 8. 不足与局限
- **实验覆盖不全**：仅测试了nuScenes-R和nuScenes-C中的部分故障/天气，未涵盖雷达故障、多传感器同时故障、硬件级故障（如校准偏移）。
- **训练策略简化**：仅训练随机drop（完整故障），未模拟连续退化和部分故障（如LiDAR波束减少、有限FOV），但实验显示仍能泛化；可能仍有改进空间。
- **数据集单一**：仅在nuScenes上评估，未在Waymo、KITTI等数据集验证，泛化性未知。
- **AQR依赖参考点投影**：需要已知标定参数将3D点投影到BEV和图像，标定误差可能在故障场景下放大。
- **计算资源未公开**：无法复现训练成本，不利于社区公平比较。
- **未讨论极端情况**：例如当所有模态均严重退化时，AQR可能失效，模型性能仍可能大幅下降。

（完）
