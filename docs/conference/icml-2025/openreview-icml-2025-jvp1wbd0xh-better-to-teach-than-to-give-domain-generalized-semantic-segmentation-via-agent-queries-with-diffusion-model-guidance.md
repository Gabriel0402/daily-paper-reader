---
title: "Better to Teach than to Give: Domain Generalized Semantic Segmentation via Agent Queries with Diffusion Model Guidance"
title_zh: 授人以渔：基于代理查询与扩散模型引导的域泛化语义分割
authors: "Fan Li, Xuan Wang, Min Qi, Zhaoxiang Zhang, Yuelei Xu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=jvP1wbD0xh"
tags: ["query:mmseg"]
score: 9.0
evidence: 域泛化语义分割，利用扩散模型引导和代理查询
tldr: 针对域泛化语义分割中难以捕捉底层场景分布的问题，提出基于代理查询的框架。利用扩散模型丰富的场景分布先验知识，通过代理查询学习域不变特征。在多个域泛化分割数据集上达到最优性能，验证了扩散模型引导的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 808, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1509, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 185, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jvp1wbd0xh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 424, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 686, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 563, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jvp1wbd0xh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 649, \"height\": 91, \"label\": \"Table\"}]"
motivation: 现有域泛化语义分割方法难以捕捉底层场景分布。
method: 提出基于代理查询的框架，利用扩散模型的先验知识引导分割模型学习域不变特征。
result: 在多个域泛化分割数据集上达到最优性能。
conclusion: 扩散模型引导的代理查询学习框架能有效提升语义分割的域泛化能力。
---

## Abstract
Domain Generalized Semantic Segmentation (DGSS) trains a model on a labeled source domain to generalize to unseen target domains with consistent contextual distribution and varying visual appearance.
Most existing methods rely on domain randomization or data generation but struggle to capture the underlying scene distribution, resulting in the loss of useful semantic information. 
Inspired by the diffusion model's capability to generate diverse variations within a given scene context, we consider harnessing its rich prior knowledge of scene distribution to tackle the challenging DGSS task.
In this paper, we propose a novel agent \textbf{Query}-driven learning framework based on \textbf{Diff}usion model guidance for DGSS, named QueryDiff. 
Our recipe comprises three key ingredients: (1) generating agent queries from segmentation features to aggregate semantic information about instances within the scene; 
(2) learning the inherent semantic distribution of the scene through agent queries guided by diffusion features; 
(3) refining segmentation features using optimized agent queries for robust mask predictions.
Extensive experiments across various settings demonstrate that our method significantly outperforms previous state-of-the-art methods. 
Notably, it enhances the model's ability to generalize effectively to extreme domains, such as cubist art styles. Code is available at https://github.com/FanLiHub/QueryDiff.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机

- **核心问题**：域泛化语义分割（Domain Generalized Semantic Segmentation, DGSS）旨在利用标注的源域数据训练模型，使其能够泛化到具有相同上下文分布但视觉外观变化的未知目标域。现有主流方法（如域随机化、数据生成）难以捕捉底层场景分布（即实例之间的空间布局和上下文依赖关系），导致模型仅对特定变化模式鲁棒，泛化性能有限。
- **研究动机**：扩散模型具备强大的场景分布先验知识，能生成高质量的多样化样本。但现有工作仅将扩散模型用作数据生成器，无法覆盖目标域的无限分布变化，且生成大量数据会带来高昂计算成本。作者提出“授人以渔”的理念：**直接利用扩散模型中嵌入的场景分布先验来提升分割泛化能力**，而非仅仅依赖其生成的数据。
- **整体含义**：本文提出 **QueryDiff**，一种基于代理查询（Agent Queries）的域泛化语义分割框架，通过扩散模型特征引导代理查询学习场景语义分布，从而提升模型对域偏移的鲁棒性，在多个基准上达到最先进性能。

## 2. 方法论：核心思想与关键技术

### 核心思想
- 使用**代理查询**作为整个流水线的接口，代替直接使用高计算成本的扩散特征。
- 代理查询从分割骨干网络聚合实例级语义信息，然后在扩散特征引导下学习场景的语义分布，最后用优化后的代理查询细化分割解码器特征，生成鲁棒的预测。

### 关键技术细节

#### （1）Agent Queries 生成
- **聚合层级视觉特征**：对分割骨干网络的每一层特征 `f_l_seg`，构造层查询 `q_layer_l`，所有层共享同一 MLP 权重。
- **渐进合并**：采用多阶段合并策略，将不同层的查询逐步合并为统一的代理查询 `q_agent`。每个阶段使用可学习查询 `q_init` 与上一阶段输出进行交叉注意力，基于相似度矩阵合并较小的组，最终平均得到全局代理查询（长度 r=100）。

#### （2）扩散引导的代理查询优化
- **提取扩散特征**：使用预训练 Stable Diffusion v2-1 编码器将图像映射到潜在空间，并在不同时间步（弱噪声 `t_w`=0，强噪声 `t_s`=100）下提取扩散特征 `f_d`。弱噪声特征包含细粒度外观细节，强噪声特征保留粗粒度语义信息。
- **扩散一致性损失（DCL）**：
  - 计算代理查询与弱噪声扩散特征的相似度图 `S_tw_j`，该图天然包含场景分布先验，但也混入不必要的视觉细节。
  - 利用强噪声扩散特征作为监督，约束由 `S_tw_j` 和代理查询重构的特征 `ˆf_jd` 与原始强噪声特征之间的分布差异（KL散度），从而消除 `S_tw_j` 中的视觉细节。
  - 使用 `S_tw_j` 更新代理查询得到 `q_opt`，并利用 Huber 损失监督代理查询逼近 `q_opt`。
- DCL 损失 `L_diff = L_sup + L_dist`，使代理查询专注于学习场景语义分布，忽略外观细节。

#### （3）特征细化与掩码预测
- 将优化后的代理查询通过交叉注意力与多尺度像素特征交互，并用不同膨胀率的深度可分离卷积融合，得到细化特征。
- 细化特征输入 Transformer 解码器（Mask2Former），生成掩码嵌入并进行分类预测。
- 总损失 `L_total = L_seg + α L_diff`（α 控制权重，实验中默认 α=1.0？文中未明确给出，但消融研究表3包含了DCL）。推理时省略扩散特征提取步骤。

## 3. 实验设计

### 数据集与场景
- **合成到真实（Synthetic-to-Real）**：训练于 GTA5，测试于 Cityscapes、BDD100K、Mapillary。
- **真实到真实（Real-to-Real）**：训练于 Cityscapes，测试于 BDD100K、Mapillary。
- **正常到恶劣天气（Normal-to-Adverse）**：训练于 Cityscapes，测试于 ACDC 的 fog、night、rain、snow 子集。

### Benchmark 设置
根据标准域泛化设置，使用三种骨干架构并对比同类方法：
- **ResNet based**：WildNet、SHADE、SAW、TLDR、DIDEX、BlindNet、FAMix。
- **Transformer based**：HRDA、HGFormer、DGInStyle。
- **VFM based（视觉基础模型）**：CLOUDS、Rein。

### 对比评估指标
主要使用 **mIoU（平均交并比）**，并报告类别的 IoU 及定性结果。

## 4. 资源与算力

- 文中**未明确说明**具体的 GPU 型号、数量及训练时长。
- 仅提及训练配置：使用 AdamW 优化器，骨干学习率 1e-5，解码器与可学习查询 1e-4，训练 60,000 次迭代，batch size 4，图像裁剪 512×512。扩散模型（Stable Diffusion v2-1）保持冻结。
- 虽未详细报告，但基于典型 DGSS 实验推断，该方法相比直接使用扩散模型进行迭代采样更为高效，因为推理阶段完全无需扩散模型参与。

## 5. 实验数量与充分性

- **实验数量丰富**：涵盖 3 种骨干架构（ResNet50、MiT-B5、DINOv2-L），在 4 个数据集和多个测试场景下进行了对比，共计约 12 个主表实验场景（表1、表2）。
- **消融实验充分**：表3验证了三个核心组件（Agent Queries、L_sup、L_dist）的贡献；表4测试了三种 VFM 骨干（CLIP、SAM、DINOv2）在不同训练策略（全微调、冻结、轻量微调）下的性能；图5探索了代理查询长度 r 的影响；表5研究时间步选择；表6比较不同版本 Stable Diffusion。
- **公平性**：对比方法均采用官方或可复现设置，同一骨干下进行公平比较，实验客观性良好。

## 6. 主要结论与发现

1. **QueryDiff 在所有基准上显著优于现有 SOTA**：
   - 合成到真实：G→C, B, M 平均 mIoU 分别提升 2.4%（ResNet50 上相比 FAMix 提升 2.4%，MiT-B5 上相比 DGInStyle 提升 2.4%，DINOv2-L 上相比 Rein 提升 2.4%）。
   - 真实到真实：C→B, M 平均 mIoU 提升 2.2%（DINOv2-L 上 71.0% vs Rein 68.8%）。
   - 正常到恶劣天气：C→A 平均 mIoU 提升 2.3%（DINOv2-L 上 79.9% vs Rein 77.6%）。
2. **有效泛化到极端域**：在立体主义、印象派等艺术风格图像上分割结果明显优于基线。
3. **组件有效性**：Agent Queries、L_sup、L_dist 三者结合带来最大提升，且对扩散模型版本不敏感。
4. **轻量化推理**：推理时不需扩散模型，保持简洁高效。

## 7. 亮点与优点

### 方法亮点
- **新颖的“代理查询”范式**：将学习场景分布的任务从扩散生成转移为查询优化，避免扩散模型的高计算开销。
- **扩散一致性损失（DCL）**：巧妙利用强弱噪声扩散特征的差异，消除视觉细节干扰，使代理查询专注于语义分布的学习，具有理论创新性。
- **即插即用设计**：可无缝集成多种骨干（ResNet、MiT-B5、DINOv2）和 VFM，在冻结骨干或轻量微调下均有效。
- **推理高效**：推理阶段无需扩散模型，保持原始分割模型的计算成本。

### 实验亮点
- **覆盖广泛域偏移**：包括合成→真实、真实→真实、正常→恶劣天气，以及极端艺术风格。
- **严格的消融与参数分析**：对每个组件、查询长度、时间步选择、不同扩散模型等进行了系统探究。
- **与多种 VFM 骨干兼容**：证明了方法在 CLIP、SAM、DINOv2 上的泛化能力。

## 8. 不足与局限

- **计算资源未明确**：虽然推理高效，但训练阶段仍需要运行扩散模型前向传播提取特征（尽管冻结），文中未报告具体 GPU 类型、数量及训练耗时，不利于复现评估。
- **对语义一致性假设的依赖**：方法假设源域和目标域具有相同的类别集合和上下文分布（如“车在路上”），若目标域场景结构发生根本变化（如室内场景），可能仍存在挑战。
- **代理查询长度的选择**：实验显示 r=100 最优，但这一设定是否通用？对于类别数极多或极少的数据集是否需要调整？
- **跨域极端情况测试有限**：虽提到艺术风格，但只给出了定性图，缺少定量指标（如在该类风格数据集上的 mIoU），泛化能力的边界不够清晰。
- **消融实验可更深入**：例如 α 权重的影响、不同合并阶段数的比较、跨注意力层放置位置的影响等未讨论。
- **潜在偏差风险**：扩散模型预训练数据（LAION5B）可能存在场景或地域偏差，可能影响其对某些目标域（如非城市驾驶场景）的先验质量。
- **应用限制**：该方法主要用于驾驶场景的域泛化语义分割，对医疗图像、遥感等其他领域的有效性尚未验证。

（完）
