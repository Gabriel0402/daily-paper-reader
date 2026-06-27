---
title: "One is Plenty: A Polymorphic Feature Interpreter for Immutable Heterogeneous Collaborative Perception"
title_zh: 一个足矣：用于不可变异构协作感知的多态特征解释器
authors: "Xia, Yuchen, Yuan, Quan, Luo, Guiyang, Fu, Xiaoyuan, Li, Yang, Zhu, Xuanhan, Luo, Tianyou, Chen, Siheng, Li, Jinglin"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Xia_One_is_Plenty_A_Polymorphic_Feature_Interpreter_for_Immutable_Heterogeneous_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 异构智能体协作感知用于自动驾驶
tldr: 针对协作感知中不可变异构网络引起的语义鸿沟，提出多态特征解释器（Polymorphic Feature Interpreter），可统一处理多种异构特征而不需要为每种新类型训练新解释器，避免了累积语义损失。实验证明该方法在保持低通信开销的同时提升了异构协作感知的精度和扩展性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1532, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 640, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1620, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 825, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 816, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 381, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1533, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xia-one-is-plenty-a-polymorphic-feature-interpreter-for-immutable-heterogeneous-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 355, \"label\": \"Table\"}]"
motivation: 现有异构协作感知解释器扩展性差或存在语义损失。
method: 提出多态特征解释器，无需重训练即可适配多种异构特征。
result: 在异构协作感知任务中实现高精度和强可扩展性。
conclusion: 多态解释器有效解决异构协作感知中的语义鸿沟问题。
---

## Abstract
Collaborative perception in autonomous driving significantly enhances the perception capabilities of individual agents. Immutable heterogeneity in collaborative perception, where agents have different and fixed perception networks, presents a major challenge due to the semantic gap in their exchanged intermediate features without modifying the perception networks. Most existing methods bridge the semantic gap through interpreters. However, they either require training a new interpreter for each new agent type, limiting extensibility, or rely on a two-stage interpretation via an intermediate standardized semantic space, causing cumulative semantic loss. To achieve both extensibility in immutable heterogeneous scenarios and low-loss feature interpretation, we propose PolyInter, a polymorphic feature interpreter. It contains an extension point through which emerging new agents can seamlessly integrate by overriding only their specific prompts, which are learnable parameters intended to guide the interpretation, while reusing PolyInter's remaining parameters. By leveraging polymorphism, our design ensures that single interpreter is sufficient to accommodate diverse agents and interpret their features into the ego agent's semantic space. Experiments conducted on OPV2V dataset demonstrate that PolyInter improves collaborative perception precision by up to 11.1% compared to SOTA interpreters, while comparable results can be achieved by training only 1.4% of PolyInter's parameters when adapting to new agents.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与研究动机（背景）

- **问题**：自动驾驶中，不同车辆（智能体）通常使用异构且不可修改的感知网络（如 PointPillar、VoxelNet、SECOND 等）。这些网络产生的中间特征在语义和粒度上存在巨大差异（即语义鸿沟），导致无法直接用于协作感知。
- **现有方法局限**：
  - 单阶段解释器：为每种新类型邻居智能体训练一个专用解释器，可扩展性差（存储和训练代价高）。
  - 两阶段解释器：先转换到标准语义空间再转换回自车空间，存在累积语义损失，精度下降。
- **目标**：设计一种既具备高扩展性（能快速适配新类型智能体）又能实现低语义丢失的特征解释方法。

## 2. 方法论：核心思想与关键技术

### 核心思想
- **多态特征解释器（PolyInter）**：通过“一个解释器网络 + 共享通用提示 + 每个邻居智能体专属特定提示”的结构，实现单一网络处理多种异构特征。利用**提示（prompt）**作为可学习参数，引导特征解释，新智能体仅需微调其特定提示即可继承整个解释器。

### 训练分为两个阶段

#### 阶段一：基础模型训练（Phase I）

- **输入**：自车特征 \(F_{ego}\) 与 n 个已知邻居智能体的异构特征 \(F_{neb,i}\)。
- **通道选择模块**：通过余弦相似度计算自车与邻居特征通道的相似矩阵 \(M\)，然后对邻居特征进行加权重组，对齐通道维度。公式：
  \[
  Q = F'_{ego}W_q, \quad K = F'_{neb}W_k
  \]
  \[
  M = \text{SoftMax}\left(\frac{QK^\top}{\sqrt{d_k}}\right)
  \]
  \[
  F^r_{neb} = \text{LN}(M F_{neb}), \quad S^r_i = \text{LN}(M S_i)
  \]
- **空间注意力模块**：使用3D融合轴向注意力机制，对齐空间维度上的语义。
- **提示初始化**：
  - **通用提示 G**：从训练集采样 N 个点云，经自车编码器平均池化得到。
  - **特定提示 \(S_i\)**：从训练集采样 N 个点云，经对应邻居编码器平均池化得到。
- **损失函数**：
  - 特定特征 \(F^s_{neb}\)：单智能体检测损失 \(L_{single}\) + 风格损失 \(L^s_{style}\)（对齐均值和方差）。
  - 通用特征 \(F^g_{neb}\)：对抗损失 \(L_{adversary}\)（使判别器无法区分特征来源） + 风格损失 \(L^g_{style}\)。
  - 总损失：\(L_{phaseI} = L_{collab} + \lambda_s L_s + \lambda_g L_g\)。

#### 阶段二：泛化阶段（Phase II）

- **冻结**：解释器网络、通用提示 G。
- **仅训练**：新邻居智能体的特定提示 \(S_i\) 和必要的尺寸调整器（resizer）。
- **损失**：\(L_{phaseII} = L_{collab} + \lambda_s L_s\)（与阶段一类似，但仅针对特定特征）。

### 关键技术细节

- **低秩分解**：为减少特定提示参数量，将 \(S_i\) 分解为 \(C \times R \times (H+W)\)，进一步可缩小通道维度（T 倍）。
- **应用范式**：自车仅需维护一个 PolyInter 网络、一组通用提示和多个特定提示，推理时根据邻居类型激活对应提示。

## 3. 实验设计

### 数据集

- **主要数据集**：OPV2V（大规模车-路协作感知公开基准）。
- **补充实验**：V2XSet（模拟）和 DAIR-V2X（真实世界），见补充材料。

### 异构编码器配置

| 编码器 | 配置代号 | 体素分辨率 | 特点 |
|--------|----------|------------|------|
| PointPillar | pp8, pp6, pp4 | 0.8/0.6/0.4 | 2D CNN |
| VoxelNet | vn6, vn4 | 0.6/0.4 | 3D CNN |
| SECOND | sd2, sd1 | 0.2/0.1 | 3D+2D混合 |

### 实验场景

- **阶段一训练组合**：pp8-vn4-sd2 和 pp8-pp4-vn4。
- **阶段二测试**：自车 pp8 分别与新的邻居 pp4、sd1、vn6 进行两智能体协作。
- **融合方法**：F-cooper 和 CoBEVT。

### 对比方法

- **PnPDA**[25]（两阶段解释器）
- **MPDA**[36]（单阶段解释器）
- **PolyInter（本文）**：在泛化阶段仅微调特定提示。

### 评估指标

- **AP@0.5 和 AP@0.7**（平均精度，IoU 阈值 0.5 和 0.7）。

## 4. 资源与算力

- **论文未明确说明**所使用的 GPU 型号、数量、训练时长等具体算力信息。仅在代码链接中暗示可以复现，但无详细硬件参数。实验设计保持公平公开，但资源细节缺失。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 性能对比（表2）：3种异构场景 × 2种融合方法 = 6组主结果，每组与两个 baseline 对比。
  - 可扩展性参数对比（图4）：3种邻居逐步增加，比较参数总量。
  - 消融实验（表3）：5个组件（通道选择、空间注意力、通用提示、特定提示、提示初始化方法）在3个场景下的影响 = 15组。
  - 提示低秩分解实验（图5）：2个场景下不同参数量的精度曲线。
  - 定性可视化：4张特征图（图6）。
- **充分性评估**：
  - **充分**：覆盖了多种异构程度（从相似 pp8-pp4 到差异大 pp8-vn6），测试了两种融合器，进行了详细的消融和参数效率分析。
  - **客观公平**：与 SOTA 方法相比，均保持相同融合器和固定编码器/检测头；但未在更多数据集（如 DAIR-V2X 的定量结果未在正文展示）或真实路侧场景中验证，可能缺乏泛化性证明。

## 6. 主要结论与发现

1. **精度提升**：PolyInter 在三个异构场景下，相比 PnPDA 和 MPDA，AP@0.5 最高提升 12.6%，AP@0.7 最高提升 14.3%（综合平均提升 7.9% 和 11.1%）。
2. **扩展性优势**：添加新邻居时，仅需训练 1.4%（对比 MPDA 需训练整个解释器和融合网络）的参数即可达到可比甚至更优性能。
3. **组件有效性**：通道选择、空间注意力、通用提示、特定提示和提示初始化方法均对性能有显著贡献，缺失任一组件均导致精度下降。
4. **低秩分解可行性**：即使将特定提示参数量降至极低（0.04M），仍能超越 baseline，提示机制提供了良好的适应性。

## 7. 优点

- **创新性设计**：首次将多态提示（polymorphic prompt）引入异构协作感知，实现“一个解释器处理所有异构特征”，兼具扩展性和低语义损失。
- **高效扩展**：新智能体仅需微调少量参数（特定提示），无需重新训练整个解释器，存储开销低。
- **细粒度对齐**：通道选择模块和空间注意力模块分别解决通道和空间异质性，提示机制兼顾共享语义和智能体特定语义。
- **实验严谨**：在多种异构程度、两种融合方式下对比，消融实验完整，参数效率分析充分。

## 8. 不足与局限

- **未公开算力信息**：缺少训练时间、GPU 型号等资源细节，难以评估实际部署成本。
- **数据集覆盖有限**：正文仅使用 OPV2V，补充材料虽提及 V2XSet 和 DAIR-V2X，但未在正文展示定量结果；真实世界场景的验证可能不足。
- **假设依赖**：假定所有编码器固定且不可修改（immutable），若未来出现可微调的开放架构，本方法可能需要调整。
- **多智能体协作未充分探索**：正文仅测试两智能体协作，三智能体协作实验放在补充材料，缺乏多车复杂场景的全面分析。
- **提示初始化依赖采样**：采样质量可能影响初始性能，且需要预先收集邻居特征，实际部署需额外传输或协商步骤。
- **仅关注 3D 对象检测**：未验证在语义分割、轨迹预测等下游任务上的泛化性。

（完）
