---
title: "Spotting the Unexpected (STU): A 3D LiDAR Dataset for Anomaly Segmentation in Autonomous Driving"
title_zh: 发现意外（STU）：用于自动驾驶异常分割的3D LiDAR数据集
authors: "Nekrasov, Alexey, Burdorf, Malcolm, Worrall, Stewart, Leibe, Bastian, Perez, Julie Stephany Berrio"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Nekrasov_Spotting_the_Unexpected_STU_A_3D_LiDAR_Dataset_for_Anomaly_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 自动驾驶多模态异常分割数据集
tldr: 自动驾驶中异常检测对安全至关重要。本文提出STU数据集，首个面向道路异常分割的3D LiDAR数据集，包含LiDAR和相机数据，并提供密集3D语义标注。数据集支持多种范围下的异常检测，为自动驾驶感知研究提供了宝贵资源。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1812, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1781, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1743, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 791, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1814, \"height\": 759, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-nekrasov-spotting-the-unexpected-stu-a-3d-lidar-dataset-for-anomaly-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 345, \"label\": \"Table\"}]"
motivation: 现有3D数据集缺乏高质量多模态异常分割标注。
method: 构建包含LiDAR和相机数据的道路异常分割数据集，提供密集3D语义标签。
result: 数据集涵盖多种异常场景，为3D异常分割提供了标准基准。
conclusion: STU数据集推动了自动驾驶中3D异常感知的研究。
---

## Abstract
To operate safely, autonomous vehicles (AVs) need to detect and handle unexpected objects or anomalies on the road. While significant research exists for anomaly detection and segmentation in 2D, research progress in 3D is underexplored. Existing datasets lack high-quality multimodal data that are typically found in AVs. This paper presents a novel dataset for anomaly segmentation in driving scenarios. To the best of our knowledge, it is the first publicly available dataset focused on road anomaly segmentation with dense 3D semantic labeling, incorporating both LiDAR and camera data, as well as sequential information to enable anomaly detection across various ranges. This capability is critical for the safe navigation of autonomous vehicles. We adapted and evaluated several baseline models for 3D segmentation, highlighting the challenges of 3D anomaly detection in driving environments. Our dataset and evaluation code will be openly available, facilitating the testing and performance comparison of different approaches.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：自动驾驶汽车必须能够检测和应对道路上意外出现的异常物体（如道路碎片）。然而，现有的异常检测和分割研究主要集中在2D图像领域，3D LiDAR点云上的异常分割进展缓慢，且缺乏高质量的多模态数据集。
- **背景**：已有2D异常分割基准（如Lost and Found、Fishyscapes、SegmentMeIfYouCan）主要依赖相机数据，忽略了现代自动驾驶车辆普遍配备的LiDAR传感器。少数3D相关数据集（如SOD、TOR4D）要么分辨率低、要么不公开、要么对象与训练集存在重叠，无法严格满足异常分割中“异常物体不出现在训练集”的要求。
- **意义**：本文首次提出一个公开可用的、面向道路异常分割的3D LiDAR数据集（STU），包含密集的语义和实例标注，并配合同步的环视相机数据，旨在填补3D异常分割领域的空白，推动自动驾驶感知系统的安全性研究。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：构建一个真实的、经过严格标注的3D LiDAR点云异常分割数据集，避免异常物体与训练集内分布（ID）标签重叠，并提供多种评估基线。
- **关键技术细节**：
    - **数据采集**：使用配备8个硬件触发相机和128线高分辨率LiDAR的车辆平台，在自然（真实道路上发现异常）和受控（在安全道路上放置各种物体）两种环境下采集数据。采集时安排安全人员，确保不干扰交通。
    - **标注流程**：使用SemanticKITTI标注工具，通过预训练模型生成伪标签后由三名标注员交叉验证精修。定义三类标签：**inlier**（训练集中出现的类别）、**outlier/anomaly**（异常物体）、**unlabeled**（忽略区域，如训练集中出现的“其他对象”类，避免干扰）。提供实例级和语义级标注。
    - **训练数据**：联合SemanticKITTI、Panoptic-CUDAL以及额外录制的无异常场景“STU-inlier”进行模型训练，以减小域间差距。特别注意排除了训练集中“other-object”、“Movable Object.Debris”等类别的物体，确保异常物体不与训练集重叠。
    - **基线方法**：将2D异常分割方法（Deep Ensembles、MC Dropout、MaxLogit、Void Classifier、RbA）适配到3D领域。基础模型采用Mask4Former-3D（掩码Transformer架构），通过查询停用机制处理不确定区域。RbA利用“未被任何查询预测”的区域作为异常评分；Void Classifier将未标注区域作为额外语义类进行训练。

## 3. 实验设计与基准

- **数据集与场景**：
    - **训练集**：SemanticKITTI（11个序列）、Panoptic-CUDAL（6个训练序列+1个验证）、STU-inlier（1个训练+1个验证）。
    - **测试/验证集**：STU数据集包含51个测试序列（封闭测试集）和19个验证序列；另有2个自然场景序列。评估时限制在车辆半径50米内且至少5个点。
- **Benchmark**：提供点级指标（AUROC、FPR@95、AP）和对象级指标（Panoptic Quality PQ、未知质量UQ，包括分割质量SQ、识别质量RQ、召回质量RecallQ）。
- **对比方法**：Deep Ensemble（3个Mask4Former-3D集成）、MC Dropout（50次前向）、MaxLogit、Void Classifier、RbA。

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量及训练时长。仅提及训练了多个Mask4Former-3D模型（包括Deep Ensembles的三个模型、MC Dropout一个模型等），但无具体硬件信息。因此无法评估计算资源消耗。

## 5. 实验数量与充分性

- **实验组数**：
    - **Inlier性能**：在SemanticKITTI验证集和STU-inlier验证集上评测了Mask-PLS和Mask4Former-3D模型（含仅SemanticKITTI训练和联合训练两种设置），共约4组结果（表3）。
    - **OOD性能**：在STU验证集上评估了5种基线方法（Deep Ensemble、MC Dropout、MaxLogit、Void Classifier、RbA），并报告了点级和对象级指标（表2）。
    - 此外，论文提供了异常实例的统计分析（图4-6）和一些定性结果（图7）。
- **充分性与公平性**：
    - 作为数据集论文，实验主要展示baseline效果，而非提出新算法。实验数量基本合理，覆盖了多种主流异常分割策略。
    - 但**缺乏消融实验**（如不同训练数据组合的影响、模型容量变化等），且**未利用数据集的时间序列信息**（仅做单帧评估）。此外，所有方法均基于Mask4Former-3D，未对比其他3D分割架构（如RangeNet++、SPVNAS），可能不够全面。
    - 指标选择标准（遵循2D异常分割和3D全景分割社区），但点级指标因严重类别不平衡（异常点极少）而偏低，对象级UQ指标不惩罚假阳性，与实际安全需求可能不完全一致。整体而言，实验设计客观但可进一步扩展。

## 6. 论文的主要结论与发现

- STU数据集是首个公开的、面向LiDAR点云异常分割的真实道路数据集，具有高分辨率传感器和密集标注。
- 直接将2D异常分割方法迁移到3D效果不佳。点云中异常物体通常只有极少数点（图6），且模型对熟悉场景中的异常物体（如椅子被预测为“其他车辆”）具有高置信度，导致假阳性率高、平均精度低。
- Deep Ensemble方法在点级FPR@95和对象级PQ上表现相对较好，但AP仍远低于2D水平（表2），说明任务极具挑战性。
- 当前基线无法可靠检测小体积、远距离的异常物体，这为未来研究指明了方向——需要利用时序信息、多模态融合或更精细的评分机制。

## 7. 优点

- **数据集高质量**：采用128线LiDAR和8台相机，真实道路与受控场景结合，标注精细（语义+实例），且严格排除训练集中出现的“其他对象”类，符合异常分割定义。
- **公开可用**：数据集和评估代码将开源，便于社区复现和比较。
- **提供标准化基线**：适配多种主流2D方法到3D，并定义统一的评估协议（点级+对象级指标），为后续研究奠定基础。
- **关注安全问题**：针对自动驾驶实际风险（道路碎片导致事故），具有现实意义。

## 8. 不足与局限

- **计算资源未报告**：无法评估训练成本，不利于可重复性。
- **基线方法局限**：仅使用了Mask4Former-3D一种架构，未尝试其他3D分割模型（如基于稀疏卷积或Transformer）。且未对方法进行超参数调优或针对3D点云特性做专门设计。
- **未利用时间信息**：数据集包含时序序列，但所有实验仅基于单帧，实际上多帧融合可能显著提升小物体检测。
- **域间差距**：STU-inlier序列与异常场景之间存在一定域差（训练时虽加入STU-inlier，但验证时仍可能受到光照、环境变化影响）。
- **忽略“其他对象”类影响**：将训练集中的“other-object”标注为unlabeled，但该类仍可能出现在评估场景中，导致部分假阳性未被惩罚。
- **远距离性能未知**：尽管标注距离可达150米，但评估仅限制在50米，未探究模型在更远距离的表现。
- **物体多样性有限**：异常物体多为静态、小型（如水桶、椅子、显示器等），缺乏移动、变形或极端形状的异常。
- **没有消融实验**：未分析训练数据组成、模型组件等对性能的影响，难以判断关键因素。

（完）
