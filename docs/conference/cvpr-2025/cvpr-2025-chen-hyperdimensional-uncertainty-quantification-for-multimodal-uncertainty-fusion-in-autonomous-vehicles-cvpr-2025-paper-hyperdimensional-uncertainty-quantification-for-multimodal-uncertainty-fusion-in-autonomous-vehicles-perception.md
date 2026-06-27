---
title: Hyperdimensional Uncertainty Quantification for Multimodal Uncertainty Fusion in Autonomous Vehicles Perception
title_zh: 自动驾驶多模态不确定性融合的超维不确定性量化
authors: "Chen, Luke, Wang, Junyao, Mortlock, Trier, Khargonekar, Pramod, Al Faruque, Mohammad Abdullah"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_Hyperdimensional_Uncertainty_Quantification_for_Multimodal_Uncertainty_Fusion_in_Autonomous_Vehicles_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 自动驾驶感知的多模态不确定性量化与融合
tldr: 针对多模态特征融合层次认知不确定性未被现有方法考虑且贝叶斯方法计算成本高的问题，本文提出HyperDUM，利用超维计算高效量化特征级认知不确定性，在自动驾驶感知中实现可靠的多模态不确定性融合，提升系统可靠性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1795, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 835, \"height\": 424, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 873, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 880, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 781, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-hyperdimensional-uncertainty-quantification-for-multimodal-uncertainty-fusion-in-autonomous-vehicles-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 767, \"height\": 271, \"label\": \"Table\"}]"
motivation: 现有方法未考虑多模态特征融合层面的认知不确定性且计算成本高。
method: 提出HyperDUM，利用超维计算高效量化特征级认知不确定性。
result: 实现高效的不确定性量化。
conclusion: 提升自动驾驶感知系统的可靠性。
---

## Abstract
Uncertainty Quantification (UQ) is crucial for ensuring the reliability of machine learning models deployed in real-world autonomous systems. However, existing approaches typically quantify task-level output prediction uncertainty without considering epistemic uncertainty at the multimodal feature fusion level, leading to sub-optimal outcomes. Additionally, popular uncertainty quantification methods, e.g., Bayesian approximations, remain challenging to deploy in practice due to high computational costs in training and inference. In this paper, we propose HyperDUM, a novel deterministic uncertainty method (DUM) that efficiently quantifies feature-level epistemic uncertainty by leveraging hyperdimensional computing. Our method captures the channel and spatial uncertainties through channel and patch -wise projection and bundling techniques respectively. Multimodal sensor features are then adaptively weighted to mitigate uncertainty propagation and improve feature fusion. Our evaluations show that HyperDUM on average outperforms the state-of-the-art (SOTA) algorithms by up to 2.01%/1.27% in 3D Object Detection and up to 1.29% improvement over baselines in semantic segmentation tasks under various types of uncertainties. Notably, HyperDUM requires 2.36x less Floating Point Operations and up to 38.30x less parameters than SOTA methods, providing an efficient solution for real-world autonomous systems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- 现有不确定性量化（UQ）方法主要关注任务级输出预测不确定性，忽略了多模态特征融合层面的**认知不确定性**，导致次优的融合性能。
- 流行的贝叶斯近似方法（如MC Dropout、深度集成）计算成本高，难以在实时自动驾驶系统中部署。
- 本文提出**HyperDUM**，一种确定性不确定性方法（DUM），利用**超维计算**高效量化特征级认知不确定性，在多模态融合前对特征进行不确定性加权，提升自动驾驶感知的可靠性和效率。

## 2. 方法论

### 核心思想
- 将中间层特征投影到高维超向量空间，通过**超维原型**（hyperdimensional prototypes）的相似度来估计认知不确定性。
- 创新性地提出两种投影与捆绑技术，分别捕捉**通道级**和**空间块级**不确定性。

### 关键技术细节
- **通道级投影与捆绑（CPB）**：保留特征通道维度（而非像传统方法聚合所有通道），对每个通道单独投影到超维空间，并分别捆绑形成原型。输出通道级相似度集合。
- **块级投影与捆绑（PPB）**：将空间特征划分为多个补丁（patch），每个补丁单独投影并捆绑形成原型，捕获空间上的局部不确定性。
- **不确定性加权融合**：通过相似度计算得到各模态的不确定性度量，输入可学习的加权模块，对原始特征进行缩放（0-1），再送入后续融合模块。

### 公式/算法流程（文字说明）
1. 对于每个模态，提取特征`z`。
2. 对特征进行CPB或PPB操作，得到超向量`Hz`。
3. 利用带标签的样本（按场景/天气标签）捆绑形成超维原型`H_l`。
4. 计算`Hz`与每个原型`H_l`的余弦相似度，得到不确定性集合`U`（多通道或多块）。
5. 不确定性经过加权模块（可学习）生成权重，对原始特征进行重加权。
6. 重加权后的特征送入融合模块，后续进行检测/分割任务。

## 3. 实验设计

### 数据集与场景
- **aiMotive**（3D目标检测）：包含相机、激光雷达、雷达，多场景（Highway, Urban, Night, Rain）及注入的极端情况（Motion Blur, Over-Exposure, Under-Exposure, LiDAR-Fog）。评估远距离（>75m）子实验。
- **DeLiVER**（语义分割）：包含相机、激光雷达、事件相机、深度传感器，5种天气（Cloudy, Foggy, Night, Rainy, Sunny）及5种极端情况（MB, OE, UE, LJ, EL）。

### Benchmark与对比方法
- 基线：BEVFusion（aiMotive）、CMNeXt（DeLiVER）。
- 对比方法：InfMCD（MC Dropout）、InfNoise（噪声注入）、PostNet（后验网络）、LDU（潜在判别确定性不确定性）、GeminiFusion（仅报告均值）。

### 评价指标
- 3D目标检测：all-point AP / 11-point插值AP。
- 语义分割：mIoU、ECE（期望校准误差）。

## 4. 资源与算力

- 文中在“Limitations and Future Work”部分提及：使用**单张NVIDIA A100 GPU**进行训练。
- **未明确说明训练时长**，但指出推理FLOPs大幅降低（相比LDU减少2.36x至5.44x），参数量减少（最高38.30x）。

## 5. 实验数量与充分性

- **实验数量充分**：涵盖两个数据集、两个任务（检测+分割），总计超过20个子场景/极端情况。
- **消融实验**：验证了CPB和PPB各自贡献（去除任一组件性能下降）。
- **敏感性分析**：探究超维度、补丁数量对性能与计算量的影响。
- **对比实验**：对比5种以上UQ方法，包括贝叶斯近似的基线。
- **前后融合位置对比**：证明在特征融合前进行不确定性加权优于融合后。
- **公平性**：所有方法均在同一框架下微调，仅UQ模块不同，其他部分冻结。

## 6. 主要结论与发现

- HyperDUM在3D目标检测上平均AP提升**2.01%/1.27%**，语义分割mIoU提升**1.29%**。
- ECE（校准误差）降低**0.33%**，说明模型更可靠。
- 计算效率显著：FLOPs减少**2.36x**，参数量减少**38.30x**（相比LDU）。
- 特征融合前进行不确定性量化比融合后更有效（提升更大）。
- 通道和空间不确定性两者对最终性能均有贡献，缺一不可。

## 7. 优点

- **创新性强**：首次将超维计算应用于特征级认知不确定性量化，并针对多模态融合场景设计。
- **高效实用**：单次前向传播，无需多次采样或集成，适合实时系统。
- **鲁棒性好**：对各种天气、传感器退化、极端情况均有显著性能提升。
- **消融与分析充分**：通过消融、灵敏度分析、前后对比等实验全面验证方法有效性。

## 8. 不足与局限

- **依赖标签构建原型**：基于监督学习，需预先定义场景标签（如天气、环境）进行捆绑。文中指出半监督/无监督版本缺乏理论保证。
- **实验覆盖有限**：仅测试了两种数据集（aiMotive, DeLiVER）和两种任务（检测、分割），泛化性需更多验证。
- **未讨论模态对齐问题**：文中提到跨模态对齐可能由骨干网络强制，但未深入分析。
- **FLOPs仍可优化**：作者指出超维计算的并行运算可进一步加速（如硬件加速），但本文未实现。
- **训练资源信息不完整**：未提供训练时长，仅说明使用了单张A100。

（完）
