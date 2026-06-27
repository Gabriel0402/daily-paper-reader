---
title: "DriveGPT: Scaling Autoregressive Behavior Models for Driving"
title_zh: DriveGPT：扩展自动驾驶的自回归行为模型
authors: "Xin Huang, Eric M Wolff, Paul Vernaza, Tung Phan-Minh, Hongge Chen, David S Hayden, Mark Edmonds, Brian Pierce, Xinxin Chen, Pratik Elias Jacob, Xiaobai Chen, Chingiz Tairbekov, Pratik Agarwal, Tianshi Gao, Yuning Chai, Siddhartha Srinivasa"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SBUxQakoJJ"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 可扩展的自回归行为模型用于自动驾驶
tldr: 针对自动驾驶中行为模型扩展性不足的问题，提出DriveGPT。将驾驶建模为序列决策，用Transformer自回归预测智能体状态。通过大规模扩展模型参数和数据，在规划任务上超越基线，预训练进一步提升预测性能，展示了扩展规律。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1752, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 765, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 756, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 860, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 862, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 855, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 851, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 854, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 853, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 681, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 862, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sbuxqakojj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 838, \"height\": 359, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 771, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 889, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1277, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 842, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sbuxqakojj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 710, \"height\": 322, \"label\": \"Table\"}]"
motivation: 现有驾驶模型扩展性不足，难以应对复杂场景。
method: 将驾驶建模为序列决策任务，使用Transformer自回归预测智能体状态，并扩展到大规模数据。
result: 在规划任务上超越基线，预训练进一步提升预测性能。
conclusion: 扩展模型参数和数据规模能有效提升驾驶行为模型性能。
---

## Abstract
We present DriveGPT, a scalable behavior model for autonomous driving. We model driving as a sequential decision-making task, and learn a transformer model to predict future agent states as tokens in an autoregressive fashion. We scale up our model parameters and training data by multiple orders of magnitude, enabling us to explore the scaling properties in terms of dataset size, model parameters, and compute. We evaluate DriveGPT across different scales in a planning task, through both quantitative metrics and qualitative examples, including closed-loop driving in complex real-world scenarios. In a separate prediction task, DriveGPT outperforms state-of-the-art baselines and exhibits improved performance by pretraining on a large-scale dataset, further validating the benefits of data scaling.

---

## 论文详细总结（自动生成）

# DriveGPT: Scaling Autoregressive Behavior Models for Driving 论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：尽管 Transformer 基础模型在 NLP、时序预测等领域通过“数据+模型”大规模扩展取得了显著成功，但**在自动驾驶行为建模中，缩放规律是否同样成立尚不清楚**，主要原因包括：输入模态多（轨迹、地图）、需要空间推理和物理动力学理解、大规模驾驶数据收集困难。
- **问题定义**：现有行为模型受限于模型参数（大多 < 100M）和训练数据（通常 < 2.2M 段），**缺乏对数据、模型、计算三者缩放规律的系统性研究**。
- **整体含义**：DriveGPT 将驾驶建模为**序列决策任务**，通过自回归 Transformer 预测未来智能体状态，并首次将参数扩展到 **1.4B**、训练数据扩大到 **120M 段**（比已有工作大 3 倍参数和 50 倍数据），探究是否遵循类似 LLM 的缩放定律，从而提升规划与预测性能。

## 2. 论文提出的方法论
### 核心思想
- 将驾驶视作**条件化序列预测问题**：给定上下文 c（目标智能体历史、附近智能体历史、地图），以自回归方式预测未来位置序列 \( s_{1:T} \)：  
  \[
  P(s_{1:T} \mid c) = \prod_{t=1}^{T} P(s_t \mid s_{0:t-1}, c)
  \]
- 采用**Verlet 动作表示**：预测位移的二阶导数（加速度），通过公式 \( s_{t+1} = s_t + (s_t - s_{t-1}) + a_t \) 恢复位置，保证平滑性。

### 关键技术细节
1. **场景编码器**：类 PointNet 编码 + Transformer 自注意力，将目标/邻车历史及地图向量化后融合为一组场景嵌入 token。
2. **LLM 式轨迹解码器**：对每一时刻的位置嵌入（线性层+LayerNorm+ReLU），逐时间步与场景嵌入交叉注意力，输出离散 Verlet 动作的类别分布（交叉熵损失）。
3. **训练**：Teacher Forcing，使用真值位置作为输入，并行预测所有未来步骤；单分类损失。
4. **推理**：自回归滚动生成轨迹，批量采样多个轨迹后用 K-Means 提取模态（通常 6 条）。

## 3. 实验设计
### 数据集
- **内部研究数据**：从数百万英里的真实驾驶中精选 **120M 段**，覆盖美、日、阿联酋等多城市，平衡白天/夜晚，包含双停车、施工区、行人/自行车等挑战场景。
- **外部公开数据集**：Waymo Open Motion Dataset (WOMD)，约 44k 场景，用于预测任务评估。

### Benchmark 与对比方法
- **规划任务（内部）**：对比大小版本模型，指标包括 minADE、minFDE、miss rate、offroad rate、collision rate。
- **预测任务（WOMD）**：对比 MTR、HDGT、HPTR、ControlMTR、MTR++、Wayformer（集成）、MotionLM（集成）等 SOTA 方法。指标为 minADE、minFDE、miss rate、soft mAP（三种预测时长 3s/5s/8s，三类代理：车、行人、自行车）。

## 4. 资源与算力
- **训练硬件**：16 块 NVIDIA H100 GPU（内部规划实验）。
- **模型训练**：每个模型仅训练 **1 epoch**（符合 LLM 缩放研究惯例）；使用 Adam 优化器 + 余弦学习率衰减；具体总训练时长未明确给出。
- **外部 WOMD 训练**：30 epoch，学习率从 epoch 20 起每 2 epoch 衰减 0.5，batch size 80，优化器 AdamW。

## 5. 实验数量与充分性
- **数量**：包含三大类缩放实验（数据、模型、计算），每类覆盖 4~10 个量级点。消融实验包括：
  - 注意力头数对性能的影响（固定隐藏维度）。
  - 解码器单独缩放 vs 编码器-解码器同时缩放。
  - 编码器单独缩放。
  - 自回归解码器 vs 一次性解码器（one-shot）对比。
- **内部规划**：不同数据量（2.2M、21M、85M、120M）和不同模型大小（8M、26M、94M、163M）的指标对比。
- **外部 WOMD**：直接训练和预训练+微调两种模式，报告整车/自行车/行人细分指标。
- **公平性**：所有缩放实验使用**固定验证集**（10M 样本），每个模型单独调优最优学习率；对比基线使用官方公开结果或相同 encoder 实现。
- **充分性**：覆盖了数据、模型、计算三个维度的系统缩放，并引入驾驶专用语义指标（offroad、collision），但**内部数据集未公开**，可复现性受限。

## 6. 主要结论与发现
1. **数据缩放持续有效**：训练数据增加（从 2.2M→120M）在所有指标上显著改进，且**数据仍是主要瓶颈**（10% 损失改进需 350M 新样本）。
2. **模型缩放依赖数据量**：仅当训练数据足够大（>21M）时，更大模型才带来收益；在 120M 数据上，模型增大到 94M 仍有效，之后出现饱和，**与 LLM 缩放律一致**。
3. **自回归架构更可扩展**：相比一次性解码器，自回归解码器随模型变大性能持续提升，在 >8M 参数后反超。
4. **WOMD 预测 SOTA**：DriveGPT 在 minADE/minFDE 上超越所有非集成和集成基线，但 soft mAP 较低（因自回归概率累积误差）。
5. **预训练收益**：在内部 120M 数据上预训练后微调 WOMD 可额外提升 2~3% 几何指标，证明跨域数据缩放的价值。

## 7. 优点
- **系统性缩放研究**：首次在驾驶行为建模中横跨 3 个数量级的模型参数（1.5M→1.4B）和数据量（2.2M→120M），并验证了计算缩放规律。
- **大规模实际部署验证**：在 8M 参数版本上实现 <50ms 闭环实时规划，展示真实城市交通中处理双停车、车道变化等复杂场景。
- **架构选择合理**：自回归解码器优于一次性解码器，且结合 Verlet 动作表示保证轨迹平滑性。
- **预训练泛化性好**：即使在数据分布（城市/传感器/语义）差异大时，大规模预训练仍能提升 WOMD 性能，说明模型学到了通用驾驶知识。

## 8. 不足与局限
- **概率校准问题**：自回归概率通过长序列连乘易累积噪声，导致 soft mAP 较低，论文承认这是限制，并提出未来可训练额外概率头。
- **内部数据不公开**：核心缩放实验依赖 Cruise 内部 120M 段数据，外部研究者难以复现或对比。
- **模型缩放收益递减**：在 120M 数据上，超过 94M 参数后几何指标改善缓慢，可能需要在更大数据上进一步测试。
- **仅支持单智能体预测**：当前 DriveGPT 预测目标智能体位置，未扩展至多智能体联合交互预测（如 MTR++ 集成对称场景建模）。
- **缺乏在线交互评估**：客观指标虽好，但未提供量化碰撞率或驾驶安全性的独立测试（如通过模拟库）。

（完）
