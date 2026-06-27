---
title: "BFANet: Revisiting 3D Semantic Segmentation with Boundary Feature Analysis"
title_zh: BFANet：通过边界特征分析重新审视3D语义分割
authors: "Zhao, Weiguang, Zhang, Rui, Wang, Qiufeng, Cheng, Guangliang, Huang, Kaizhu"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_BFANet_Revisiting_3D_Semantic_Segmentation_with_Boundary_Feature_Analysis_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 4.0
evidence: 先进的3D语义分割方法，关注边界特征分析
tldr: 当前3D语义分割方法只关注整体指标，忽略了边界等困难区域。本文提出错误分类框架和对应评估指标，并设计边界特征分析网络，在多个数据集上显著提升边界分割质量。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 882, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 925, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 883, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 729, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 886, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 890, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 887, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-bfanet-revisiting-3d-semantic-segmentation-with-boundary-feature-analysis-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 889, \"height\": 146, \"label\": \"Table\"}]"
motivation: 现有3D语义分割方法忽视边界等挑战区域，整体指标掩盖了细分问题。
method: 划分四类分割错误，构建边界特征分析网络。
result: 在S3DIS等数据集上边界区域mIoU提升明显。
conclusion: 细粒度错误分析和边界特征学习有助于提升分割精细度。
---

## Abstract
3D semantic segmentation plays a fundamental and crucial role to understand 3D scenes. While contemporary state-of-the-art techniques predominantly concentrate on elevating the overall performance of 3D semantic segmentation based on general metrics (e.g. mIoU, mAcc, and oAcc), they unfortunately leave the exploration of challenging regions for segmentation mostly neglected. In this paper, we revisit 3D semantic segmentation through a more granular lens, shedding light on subtle complexities that are typically overshadowed by broader performance metrics. Concretely, we have delineated 3D semantic segmentation errors into four comprehensive categories as well as corresponding evaluation metrics tailored to each. Building upon this categorical framework, we introduce an innovative 3D semantic segmentation network called BFANet that incorporates detailed analysis of semantic boundary features. First, we design the boundary-semantic module to decouple point cloud features into semantic and boundary features, and fuse their query queue to enhance semantic features with attention. Second, we introduce a more concise and accelerated boundary pseudo-label calculation algorithm, which is 3.9 times faster than the state-of-the-art, offering compatibility with data augmentation and enabling efficient computation in training. Extensive experiments on benchmark data indicate the superiority of our BFANet model, confirming the significance of emphasizing the four uniquely designed metrics. Code is available at https://github.com/weiguangzhao/BFANet.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
现有3D语义分割方法（如OctFormer、PTv3等）过度聚焦于整体性能指标（mIoU/mAcc/oAcc），忽略了对边界、小物体、易混淆区域等**挑战性区域**的精细分析。这些区域的分割错误（例如边界侵蚀/膨胀、区域误分类、虚假响应、合并错误）被整体指标掩盖，导致实际应用中的细节精度不足。论文首次系统性地将3D语义分割错误细分为四类，并设计对应的评估指标，进而提出一种**边界特征分析网络（BFANet）**，通过显式建模边界信息来克服这些错误，提升分割质量。

## 2. 方法论
### 核心思想
- 以**边界特征为桥梁**，将点云特征解耦为语义特征和边界特征，并通过注意力机制融合两者的查询序列（Query Queue），增强语义特征的边界感知能力。
- 提出**实时边界伪标签计算算法（PBPLC）**，基于CUDA并行加速，时间复杂度从O(n²)降至O(n)，支持数据增强且速度快3.9倍。

### 关键技术细节
1. **多层级特征提取**：使用OctFormer将输入点云（坐标、颜色、法线）构建为八叉树，提取最后四层特征并通过上采样和互操作得到融合特征 \( f_o \)。
2. **边界-语义模块（B-S Block）**：
   - 对 \( f_o \) 施加两个独立MLP（ \( M_b^1 \) 和 \( M_s^1 \) ），分别约束出**边界特征**和**语义特征**。
   - 利用MLP生成边界队列 \( Q_b, K_b, V_b \) 和语义队列 \( Q_s, K_s, V_s \)。
   - 拼接 \( Q_b \) 与 \( Q_s \)，通过融合MLP \( M_f^1 \) 后，与语义键值对做注意力操作，得到增强的语义特征 \( f_s \)。
3. **损失函数**：语义分支使用交叉熵+Dice损失，边界分支使用二值交叉熵+Dice损失。
4. **实时边界伪标签计算**：以每个点为中心，半径r=6cm范围内若存在不同语义标签的点，则该点标记为边界点。利用CUDA线程并行遍历所有点。

### 公式（文字说明）
- DErr θ：仅考虑预测与真值IoU大于阈值θ的样本，计算边界区域重叠度。
- FErr：预测边界中不在真值边界内的比例。
- MErr：真值边界中未被预测到的比例。
- 损失由语义交叉熵、语义Dice、边界BCE、边界Dice组合。

## 3. 实验设计
### 数据集与基准
- **ScanNet200**（200类室内场景）：1201训练/312验证/100测试（测试标签隐藏，需提交官方网站）。
- **ScanNetv2**（20类）：常用于评价。

### 对比方法
- **SOTA方法**：MinkUNet、PTv1/v2/v3、OctFormer、OA-CNN、CeCo、SPG等。
- **公平性处理**：排除PTv3+PPT（使用额外数据和大规模训练），仅对比公平条件下的结果。
- 使用传统指标（mIoU/mAcc/oAcc）以及**本文提出的新指标**（FErr/MErr/RErr/DErr）进行双重评估。

## 4. 资源与算力
- **硬件**：4张RTX 4090 GPU（24GB显存）。
- **训练参数**：400个epoch，batch size=4，优化器Adam，初始学习率0.001（余弦退火）。
- **推理速度**：每场景(约158.8K点)推理时间60.7ms（未使用TTA），模型参数量44.3M。

## 5. 实验数量与充分性
### 实验组数
- **主实验**：在ScanNet200测试集（隐藏）和验证集、ScanNetv2验证集上分别报告结果，覆盖7+种SOTA对比。
- **消融实验**：共4组（基线、加边界预测、加B-S Block、加TTA），分别用传统指标和4个新指标评估。
- **边界伪标签效率对比**：与CBL方法对比耗时（每场景46.3ms vs 179.2ms）。
- **参数敏感性**：对不同半径r（2-10cm）下的新指标表现进行对比（图4）。
- **定性可视化**：5个场景的对比图。

### 充分性评价
- 实验覆盖了主要数据集、多个SOTA、充分消融、指标全面，体现了**客观性与公平性**。
- 但仅在室内场景（ScanNet）测试，未涉及室外自动驾驶等场景，存在**场景局限性**。

## 6. 主要结论与发现
- **BFANet在ScanNet200隐藏测试集上达到mIoU 36.0%，排名第二**（排除使用额外数据的PTv3后第一），比基线OctFormer提升3.4%。
- **在新指标上**：FErr降低4.0%，MErr降低4.2%，DErr降低2.4%；相比PTv3也全面领先（FErr降低2.5%，MErr降低5.5%）。
- **边界伪标签计算速度提升3.9倍**，且支持数据增强。
- 消融证实**B-S Block**比简单加边界预测分支效果更好（mIoU提升2.7%），对**Common和Tail类**改善显著（分别+4.9%和+4.7%）。
- **TTA**导致部分边界指标（FErr/MErr）轻微恶化，但整体仍优于无TTA。

## 7. 优点
- **创新性问题定义**：首次系统分类3D语义分割错误类型并设计对应度量，为后续研究提供细粒度评估标准。
- **有效的方法设计**：边界-语义模块通过解耦和注意力融合，直观且高效地增强了边界感知能力，优于简单拼接/分支。
- **工程优化**：实时边界伪标签算法大幅提升训练效率，支持数据增广，具有实际部署价值。
- **全面实验验证**：传统指标和新指标双重评估，消融充分，对比公平，代码开源。

## 8. 不足与局限
- **新指标RErr改善较小**：论文指出在区域分类错误（RErr）上仅提升约1-2%，未来需进一步优化。
- **TTA副作用**：max-pooling ensemble和超点融合可能导致小区域边界指标退化，需要更鲁棒的集成策略。
- **场景局限性**：仅在ScanNet室内场景验证，未在户外（如自动驾驶、遥感）点云上测试，泛化性待验证。
- **对边界依赖强**：方法依赖边界伪标签的准确性，若场景边界模糊或不清晰，可能引入噪声。
- **计算资源需求较高**：4张4090训练400 epoch，对中小团队可能成本较高。

（完）
