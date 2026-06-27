---
title: "Sim-to-Real Causal Transfer: A Metric Learning Approach to Causally-Aware Interaction Representations"
title_zh: Sim-to-Real因果迁移：度量学习实现因果感知交互表征
authors: "Rahimi, Ahmad, Luan, Po-Chien, Liu, Yuejiang, Rajič, Frano, Alahi, Alexandre"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Rahimi_Sim-to-Real_Causal_Transfer_A_Metric_Learning_Approach_to_Causally-Aware_Interaction_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 5.0
evidence: 多智能体系统的因果感知交互表征
tldr: 针对多智能体交互表征的因果意识评估问题，本文从计算形式化到实际应用深入分析现有表征，通过度量学习发现这些表征对非因果代理扰动已有部分韧性，但间接因果效应（中介代理）的建模仍具挑战，为多智能体强化学习和模拟到真实迁移提供因果感知基础。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 583, \"height\": 230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 485, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1631, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1608, \"height\": 471, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1304, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-rahimi-sim-to-real-causal-transfer-a-metric-learning-approach-to-causally-aware-interaction-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 551, \"height\": 322, \"label\": \"Table\"}]"
motivation: 现代表征能否捕捉智能体交互中的因果关系尚不清楚。
method: 采用度量学习来评估和学习因果感知的交互表征。
result: 显示现有表征对非因果扰动已有部分韧性，但中介效应建模仍有挑战。
conclusion: 为多智能体交互的因果建模和模拟到真实迁移提供新视角。
---

## Abstract
Modeling spatial-temporal interactions among neighboring agents is at the heart of multi-agent problems such as motion forecasting and crowd navigation. Despite notable progress, it remains unclear to which extent modern representations can capture the causal relationships behind agent interactions. In this work, we take an in-depth look at the causal awareness of these representations, from computational formalism to real-world practice. First, we revisit the notion of non-causal robustness studied in the recent CausalAgents benchmark. We show that existing representations are already partially resilient to perturbations of non-causal agents, and yet modeling indirect causal effects involving mediator agents remains challenging. To address this challenge, we introduce a metric learning approach that regularizes latent representations with causal annotations. Our controlled experiments show that this approach not only leads to higher degrees of causal awareness but also yields stronger out-of-distribution robustness. To further operationalize it in practice, we propose a sim-to-real causal transfer method via cross-domain multi-task learning. Experiments on trajectory prediction datasets show that our method can significantly boost generalization, even in the absence of real-world causal annotations, where we acquire higher prediction accuracy by only using 25% of real-world data. We hope our work provides a new perspective on the challenges and potential pathways toward causally-aware representations of multi-agent interactions. Our code is available in supplementary materials. Our code is available at https://github.com/vita-epfl/CausalSim2Real.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：在多智能体交互建模（如轨迹预测、人群导航）中，现代表征能否捕捉智能体之间的**因果关系**？尤其是间接因果效应（通过中介代理传递）的建模能力如何？
- **背景与动机**：
  - 现有深度神经网络在统计相关性学习上表现出色，但在环境变化（OOD）下泛化能力差，且需大量标注数据。
  - 因果感知表征（causally-aware representations）被认为能提升鲁棒性，但真实场景中因果标注难以获取。
  - 最近CausalAgents基准（CVPR 2022）提供了因果-非因果标注，但其标注和评估存在缺陷，导致对鲁棒性的衡量有偏。
  - 本文旨在深入分析现有表征的因果意识，提出基于度量学习的正则化方法，并扩展到**模拟到真实（sim-to-real）因果迁移**框架，在无真实因果标注下提升预测性能。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
- 利用**反事实模拟**（ORCA仿真器）生成成对场景（原始场景 vs. 移除单个智能体后的场景），获取**真实因果效应** \( E_i \)（原始与反事实轨迹的欧氏距离）。
- 将因果效应嵌入到表征空间中：期望表征距离 \( d_i = 1 - \cos(\mathbf{p}_\varnothing, \mathbf{p}_i) \) 与 \( E_i \) 单调一致。
- 提出两种基于**因果标注粒度**的正则化方法：
  - **Causal Contrastive Regularization**：利用二分类标注（因果/非因果），拉近非因果反事实嵌入、推远因果反事实嵌入。
  - **Causal Ranking Regularization**：利用连续因果效应值，通过**Margin Ranking Loss**强制不同因果效应的反事实嵌入保持相对距离顺序。

### 2.2 关键技术细节
- **编码器-解码器结构**：使用AutoBots等作为基准模型，编码器 \( f \) 输出潜表征 \( z \)，投影头 \( h \) 得到特征 \( p \)。
- **反事实场景生成**：移除单个智能体 \( i \)，重新仿真得到反事实轨迹。
- **损失函数**：
  - 主任务：预测损失 \( L_{\text{real}}^{\text{pred}} \)（如MSE）。
  - 辅助因果任务：\( L_{\text{contrast}} \) 或 \( L_{\text{ranking}} \)。
  - 总体损失：\( L = L_{\text{real}}^{\text{pred}} + \lambda L_{\text{syn}}^{\text{causal}} \)。
- **Sim-to-Real迁移**：在模拟数据上训练因果任务，在真实数据上训练预测任务，两者共享编码器，实现跨域多任务学习。

### 2.3 公式与算法流程（文字说明）
- 流程：输入历史观测 → 编码器 → 潜表征 → 投影头 → 特征向量。对于每个场景，计算原始场景特征 \( p_\varnothing \) 和所有单智能体移除后的特征 \( p_i \)。排序后按因果效应进行对比或排序损失优化。
- 对比损失：正样本为因果智能体移除后的特征（应远离 \( p_\varnothing \)），负样本为非因果智能体移除后的特征（应接近 \( p_\varnothing \)）。
- 排序损失：\( \max(0, d_i - d_j + m) \)，其中 \( E_i < E_j \)，要求 \( d_i < d_j \)。

## 3. 实验设计

### 3.1 数据集与场景
- **模拟诊断数据集**：基于ORCA仿真器，生成含8~18个智能体的场景（开放区域布局）。
  - 包含**全局因果标注**（真实因果效应 \( E_i \) ）及细粒度分类（非因果、直接因果、间接因果）。
  - 额外构建OOD数据集：
    - **密度OOD**：改变智能体密度，增加非因果智能体。
    - **上下文OOD**：将布局变为窄街道（一端到另一端）。
- **真实世界数据集**：
  - **ETH-UCY**（行人轨迹预测）。
  - **NBA Rebound**（篮球运动员运动预测）。

### 3.2 Benchmark与对比方法
- **对比方法**：
  - 基线：D-LSTM, S-LSTM, Trajectron++, STGCNN, Multi-TraMotion, AutoBots等。
  - 鲁棒性对比：Non-causal data augmentation（移除非因果智能体训练，同CausalAgents）。
  - Sim-to-Real对比：Vanilla sim-to-real transfer（直接联合训练模拟与真实数据）。
  - 本文方法：Causal Contrastive, Causal Ranking。
- **评价指标**：
  - **ADE / FDE**（预测精度）。
  - **ACE**（平均因果误差），分为 ACE-NC（非因果）、ACE-DC（直接因果）、ACE-IC（间接因果）。

### 3.3 实验设置
- 预测任务：历史8步 → 未来12步的单一轨迹。
- 训练/测试：模拟数据自生成；真实数据按比例使用（25%、50%、100%）。

## 4. 资源与算力
- **文中未明确说明**：未提及使用的GPU型号、数量、训练时长等具体算力信息。仅在Acknowledgement提及受Honda R&D和Hasler Foundation资助，但无技术细节。

## 5. 实验数量与充分性

### 5.1 实验组数
- **诊断实验**：在模拟诊断数据集上评估所有基线模型（8个模型），报告ACE各子项（Table 1）。
- **正则化有效性**：在AutoBots上对比三种方法（baseline, augment, contrast, ranking），分ID和OOD测试（Figure 6, Figure 7）。
- **Sim-to-Real迁移**：
  - ETH-UCY上测试不同数据量（25%, 50%, 100%）下的ADE/FDE（Figure 8）。
  - NBA Rebound上测试完整数据（Table 2）。
- **消融与分析**：图5显示因果效应低估现象；图2-3说明间接效应和联合移除问题。

### 5.2 充分性与公正性
- **优点**：覆盖in-distribution和out-of-distribution；对比了多个现代模型；采用了多次随机种子（results averaged over five random seeds）；可视化定性结果。
- **不足**：未做更细致的消融（如不同超参数 \(\lambda\)、对比/排序损失的具体影响）；仅使用ORCA仿真，未对比其他仿真器（如CausalCity）；对间接因果的建模提升有限，仍有较大误差（Figure 6显示排名方法大幅降低但仍非0）；未在真实世界因果标注上进行评估（因为真实标注难以获取）。

## 6. 主要结论与发现
- **发现1**：现代表征已对**非因果智能体扰动**具有部分韧性（ACE-NC很小），但对**间接因果效应**严重低估（ACE-DC和ACE-IC大）。
- **发现2**：提出的**因果对比正则化**和**因果排序正则化**均能显著提升因果意识，其中**排序正则化**效果更优，尤其在强因果效应区间。
- **发现3**：因果感知表征有助于**OOD泛化**（密度和上下文偏移），且因果意识与泛化能力呈正相关。
- **发现4**：**Sim-to-Real因果迁移**在无真实因果标注下有效：仅用25%真实数据即可超越基线，用50%真实数据即可超越所有对比方法。
- **结论**：通过度量学习对齐反事实表征距离与真实因果效应，可有效提升多智能体交互表征的鲁棒性和迁移性。

## 7. 优点
- **问题定义清晰**：明确定义了间接因果效应，并揭示了之前工作的不足。
- **方法论简洁有效**：基于对比/排序的度量学习，易于集成到现有预测模型。
- **实用性强**：提出Sim-to-Real迁移，无需真实因果标注，在低数据场景显著提升性能。
- **实验设计全面**：包含模拟诊断、OOD测试、真实世界数据集，以及不同数据量条件下的评估。
- **开源代码**：公开了代码和数据集，促进可复现性。

## 8. 不足与局限
- **依赖模拟标注**：因果标注必须从ORCA仿真器获取，其仿真特性（如确定性、简单交互规则）与真实世界存在**域差距**，迁移时可能丢失部分复杂社交因果。
- **仅考虑单一智能体移除**：未扩展到多智能体联合因果效应，且忽略高阶间接链式效应。
- **技术局限**：正则化仅提供监督信号，未引入结构归纳偏置，在高阶因果推理上仍有不足（Figure 6中排序方法仍有较大ACE）。
- **算力未说明**：缺乏对训练资源的具体描述，不利于复现和比较效率。
- **应用范围**：仅验证了行人/篮球运动员，未在自动驾驶车辆等更复杂场景（如Waymo数据集）上测试（论文提及CausalAgents但未用其真实标注）。
- **消融深度不足**：未研究不同超参数的影响（如\(\lambda\), margin \(m\), 温度\(\vartheta\)），未对比不同编码器结构的鲁棒性。

（完）
