---
title: "EvOcc: Accurate Semantic Occupancy for Automated Driving Using Evidence Theory"
title_zh: "EvOcc: 基于证据理论的自动驾驶精确语义占据估计"
authors: "Kälble, Jonas, Wirges, Sascha, Tatarchenko, Maxim, Ilg, Eddy"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Kalble_EvOcc_Accurate_Semantic_Occupancy_for_Automated_Driving_Using_Evidence_Theory_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 6.0
evidence: 基于证据理论的自动驾驶语义占据映射
tldr: "针对自动驾驶语义占据映射中未观测空间和矛盾测量的不确定性问题，本文提出EvOcc框架，包含基于证据理论计算高精度语义占据地图真值的方法，以及通过新损失函数训练图像占据估计模型的方法，在射线mIoU指标上分别提升15.8%和5.5%。"
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1816, \"height\": 552, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1366, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kalble-evocc-accurate-semantic-occupancy-for-automated-driving-using-evidence-theory-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1811, \"height\": 523, \"label\": \"Table\"}]"
motivation: 现有语义占据地图未显式建模未观测空间或矛盾测量的不确定性。
method: 提出EvOcc框架，包括证据理论真值计算和新损失函数的图像占据模型训练。
result: "在射线mIoU指标上，真值改进至少15.8%，训练模型改进5.5%。"
conclusion: 显式建模不确定性得到更强模型，用于自动驾驶感知。
---

## Abstract
We present EvOcc, a novel evidential semantic occupancy mapping framework. It consists of two parts: (1) an evidential approach for calculating the ground-truth 3D semantic occupancy maps from noisy LiDAR measurements, and (2) a method for training image-based occupancy estimation models through a new loss formulation. In contrast to state-of-the-art semantic occupancy maps, our approach explicitly models the uncertainty introduced by unobserved spaces or contradicting measurements and we show that using it results in significantly stronger models. Evaluated as ray-based mIoU, our evidential semantic occupancy mapping approach improves over the baselines by at least 15.8\% for the ground truth and 5.5\% for the trained model. Overall, we make a significant contribution towards more detailed and uncertainty-aware 3D environment understanding and safe operation in autonomous driving.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自动驾驶中，从相机图像预测三维语义占据地图（Semantic Occupancy）需要高质量的真实标签（Ground Truth），但现有方法通常依赖启发式规则将稀疏、带噪声的LiDAR点云转换为占据网格，无法显式建模未观测空间或矛盾测量带来的不确定性，导致标签不准确。
- **整体含义**：本文利用证据理论（Evidence Theory, ET）提出EvOcc框架，从LiDAR数据生成更精准的语义占据真值，并用该真值训练基于图像的占据预测模型，显著提升几何与语义精度，对自动驾驶安全环境感知有推动作用。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将每个体素的状态建模为证据理论中的基本信度赋值（Basic Belief Assignment, BBA），显式表示“自由”“被某类占据”“一般占据”“完全不确定”等假设，从而处理数据中的冲突与缺失。
- **关键技术细节**：
  - **阶段一：证据语义占据映射（Evidential Semantic Occupancy Mapping）**
    - 定义辨识框架（Frame of Discernment）Ω = {free, c1, ..., cC}。
    - 从LiDAR测量中提取：每个类别的反射测量 \( z(C_i) \)、无标签反射测量 \( z(O) \)、透射测量 \( z(F) \)，并引入超参数 α_r, α_t 缩放。
    - 计算每个假设 ω 的信度（Belief）：
      \[
      bel(ω) = \left(1 - \exp\left(-\sum_{X\subseteq ω} z(X)\right)\right) \exp\left(-\sum_{X\cap ω=\emptyset} z(X)\right)
      \]
    - 通过线性系统 \( \mathbf{b} = \mathbf{S} \mathbf{m} \) 从信度向量反解BBA质量向量 \( \mathbf{m} \)。（S矩阵元素由包含关系定义，可逆）。
    - 使用球面传感器映射、多帧聚合、体素归一化等步骤。
  - **阶段二：证据语义占据预测（Evidential Semantic Occupancy Prediction）**
    - 保持原有网络架构（如BEVDet4D-Occ），但将输出层改为预测BBA质量向量。
    - 使用一种可微的BBA交叉熵损失（Dezert & Dambreville, 2023）进行监督：
      \[
      CE_{BBA}(m^{gt}_i, m^{pred}_i) = \sum_{X\subseteq Ω} \left[ -m^{gt}_i(X)(1-u^{gt}_i(X))\log m^{pred}_i(X) + u^{gt}_i(X)(1-m^{pred}_i(X)) \right]
      \]
    - 引入频率加权 \( w_i \) 缓解类别不平衡。
    - 推理时通过最小相对熵决策：先判断占据/自由，再确定语义类别。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：nuScenes（主要实验）、Waymo（补充材料）。
- **Benchmark**：采用射线基评估（ray-based evaluation），包括深度对比（MAE, RMSE, 相对误差δ阈值）和语义对比（类IoU及mIoU），并计算两者结合的δ<sub>cls</sub>指标。
- **对比方法**：
  - 占据真值生成：SurroundOcc, Scene as Occupancy, Occ3D, OpenOccupancy, Kälble et al. (2024) [仅二值占据]。
  - 模型预测：BEVDet4D-Occ（分别用Occ3D真值与EvOcc真值训练）。

### 4. 资源与算力

- **文中未明确说明**：未提及使用的GPU型号、数量、总训练时长等具体算力信息。仅提到从Occ3D预训练checkpoint开始，额外训练24 epoch + 24 epoch（降低学习率），但未详述硬件配置。

### 5. 实验数量与充分性：大概做了多少组实验，是否充分、客观、公平

- **实验数量**：
  - 真值生成对比：在nuScenes上对0.4m和0.2m两种体素分辨率分别评估深度与语义指标，对比4~5种方法（SurroundOcc, Scene as Occ, Occ3D, OpenOcc, Kälble et al.）。共两组分辨率 × 两类指标，约十余个指标。
  - 模型预测对比：BEVDet4D-Occ分别用Occ3D和EvOcc真值训练，在0.4m分辨率上评估深度与语义。
  - 补充材料中提供了Waymo结果。
  - 无明显消融实验（如超参数α_r, α_t的影响仅在补充中提及，超参数搜索空间扩展）。
- **充分性与公平性**：
  - 实验覆盖了主流基线，评估指标较全面（深度+语义+联合）。
  - 公平性：固定模型架构，仅改变训练数据与损失函数，且使用相同训练策略。
  - 不足：缺少对不同网络结构（如TPVFormer, FB-OCC）的泛化验证；缺少对损失函数中加权策略的消融；超参数α_r, α_t的影响分析不充分。

### 6. 论文的主要结论与发现

- 基于证据理论的语义占据真值生成方法，在深度指标（MAE 1.21→0.84 m @0.4m，RMSE 2.98→2.62 m @0.2m）和语义mIoU（51.2%→67.0% @0.4m，54.1%→74.4% @0.2m）上显著优于SOTA方法。
- 用该真值训练BEVDet4D-Occ模型，深度与语义预测精度均提升（mIoU从43.1%提高到48.6%，深度δ<1.25从58.8%提高到88.6%），证明真值质量直接提升模型性能。
- 模型能输出不确定性（m(Ω)），在高遮挡区域高不确定，低遮挡区域低不确定，有助于安全决策。

### 7. 优点：方法或实验设计上有哪些亮点

- **方法亮点**：首次在语义占据映射中系统应用证据理论（Dempster-Shafer），处理部分标注标签和测量冲突；提出通用的BBA构造方法，通过线性系统从信度反解质量；设计了适配BBA的交叉熵损失，可端到端训练。
- **实验亮点**：采用射线基评估，同时评价深度与语义；保持模型架构不变仅改标签和损失，直接验证真值质量影响；定量和定性结果（图3、4）显示明显改善。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖**：仅验证了BEVDet4D-Occ一种模型，未测试其他主流占据预测架构（如TPVFormer, FB-OCC），模型泛化性未知。
- **偏差风险**：超参数α_r, α_t的选取未做系统消融，可能引入调参偏差；类别不平衡加权策略（公式14）的单独贡献未验证。
- **应用限制**：依赖LiDAR传感器和语义标签（nuScenes中仅1/10扫描有标注），对无标签数据依赖无标签反射假设（O假设）；实时性未讨论；仅适用于固定场景（nuScenes, Waymo），道路形态差异可能影响泛化。
- **其他**：未提供GPU资源消耗，复现成本不透明；代码已开源但实验可重复性依赖于特定数据预处理流程。

（完）
