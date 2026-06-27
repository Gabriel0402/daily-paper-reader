---
title: "SAM2Act: Integrating Visual Foundation Model with A Memory Architecture for Robotic Manipulation"
title_zh: SAM2Act：集成视觉基础模型与记忆架构的机器人操作
authors: "Haoquan Fang, Markus Grotz, Wilbert Pumacay, Yi Ru Wang, Dieter Fox, Ranjay Krishna, Jiafei Duan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=anSWDvJm8v"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 视觉基础模型用于机器人操作
tldr: "本文针对机器人操作在多样动态环境中泛化能力不足的问题，提出SAM2Act，一种集成视觉基础模型SAM2与记忆架构的多视角机器人transformer策略。通过多分辨率上采样和视觉表示，在RLBench 18个任务上达到86.8%的平均成功率，展现了强大的泛化能力。该工作为视觉基础模型在机器人操作中的应用提供了新思路。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1326, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1396, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1249, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-answdvjm8v/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 912, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1647, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 785, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 719, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1778, \"height\": 794, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1787, \"height\": 844, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-answdvjm8v/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1780, \"height\": 247, \"label\": \"Table\"}]"
motivation: 现有机器人操作方法在复杂环境泛化和记忆依赖任务上表现不足。
method: 提出SAM2Act，使用多视角transformer策略，结合SAM2视觉基础模型的多分辨率上采样和记忆架构。
result: "在RLBench基准的18个任务上达到86.8%平均成功率，展示鲁棒泛化。"
conclusion: 视觉基础模型结合记忆架构可有效提升机器人操作的泛化能力。
---

## Abstract
Robotic manipulation systems operating in diverse, dynamic environments must exhibit three critical abilities: multitask interaction, generalization to unseen scenarios, and spatial memory. While significant progress has been made in robotic manipulation, existing approaches often fall short in generalization to complex environmental variations and addressing memory-dependent tasks. To bridge this gap, we introduce **SAM2Act**, a multi-view robotic transformer-based policy that leverages multi-resolution upsampling with visual representations from large-scale foundation model. SAM2Act achieves a state-of-the-art average success rate of **86.8% across 18 tasks** in the RLBench benchmark, and demonstrates robust generalization on *The Colosseum* benchmark, with only a **4.3% performance gap** under diverse environmental perturbations. Building on this foundation, we propose **SAM2Act+**, a memory-based architecture inspired by SAM2, which incorporates a memory bank, an encoder, and an attention mechanism to enhance spatial memory. To address the need for evaluating memory-dependent tasks, we introduce ***MemoryBench***, a novel benchmark designed to assess spatial memory and action recall in robotic manipulation. SAM2Act+ achieves an average success rate of **94.3% on memory-based tasks** in *MemoryBench*, significantly outperforming existing approaches and pushing the boundaries of memory-based robotic systems.
Project page: [sam2act.github.io](https://sam2act.github.io/).

---

## 论文详细总结（自动生成）

# 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：机器人操作系统在多样、动态环境中需要具备多任务交互、对未知场景的泛化能力以及空间记忆能力。现有方法（如 PerAct、RVT、RVT-2）在多任务操作和简单环境中表现良好，但在复杂环境变化和需要记忆依赖的任务（如需要回溯过去动作）上仍存在明显不足。
- **整体含义**：本文旨在通过将大规模视觉基础模型（SAM2）与记忆架构集成到机器人操作策略中，同时解决高精度操控、环境泛化以及空间记忆三大挑战。论文提出 SAM2Act（基础策略）和 SAM2Act+（带记忆扩展版本），在多个模拟和真实基准上取得了最优结果，并首次提出了专门评估空间记忆的基准 MemoryBench。

# 2. 方法论：核心思想、关键技术细节

- **核心思想**：利用 SAM2 图像编码器提取多分辨率视觉嵌入，通过多分辨率上采样机制增强特征表示，再结合多视角 transformer 预测 6-DoF 动作。进一步，受 SAM2 对象跟踪的启发，设计记忆银行、记忆编码器和记忆注意力模块，使模型能够基于历史动作和观察进行推理，解决非马尔可夫任务。
- **关键技术细节**：
  - **SAM2Act 架构**（无记忆版）：
    - 从多视角 RGB-D 图像重建点云，从三个虚拟相机视角渲染图像。
    - 使用 LoRA (rank=16) 微调 SAM2 图像编码器，生成多分辨率嵌入（三个分辨率层级）。
    - 多分辨率上采样：通过级联凸上采样器逐步融合特征图与 SAM2 嵌入，并进行层归一化，生成精确的平移热图。
    - 粗-细两阶段：粗分支预测平移热图，细分支进一步预测旋转等精细动作。
  - **SAM2Act+ 架构**（记忆扩展版）：
    - 在 SAM2Act 粗分支中引入三个组件：记忆银行（FIFO 队列，每视图独立）、记忆编码器（将预测热图与 MVT 输出的嵌入融合）、记忆注意力（利用过去记忆特征对当前嵌入进行交叉注意力）。
    - 训练策略：先预训练 SAM2Act，然后冻结图像编码器、MVT 和细分支，仅微调粗分支中的记忆模块与多分辨率上采样；采用连续关键帧采样，顺序前向传播。
  - **MemoryBench 任务设计**：
    - 三个任务（`reopen drawer`、`put block back`、`rearrange block`）故意破坏马尔可夫性质，使当前观察不足以决策，必须依赖历史动作记忆。例如，按下按钮后所有抽屉关闭，场景视觉相同，需记住之前打开的抽屉。

# 3. 实验设计

- **数据集/场景**：
  - **RLBench**：18 个任务，共 249 种变化（放置、颜色、尺寸、类别等）。使用 100 个演示/任务训练，25 个未见演示测试，每任务评估 4 次。
  - **The Colosseum**：20 个任务，13 种环境扰动类型（如物体颜色、纹理、大小、光照、桌面颜色、干扰物、相机位姿等）。训练于 20 个任务，测试时应用每种扰动。
  - **MemoryBench**：3 个空间记忆任务（单任务训练），每个任务 2-4 种变化，共 100 个演示训练，25 个测试，评估 4 次。
  - **真实机器人**：Franka Panda + Robotiq 2F-85 夹爪，RealSense D455 相机。4 个任务：`turn on the lamp`（高精度）、`push buttons in sequence`、`stack cubes`、`push the same button`（记忆任务）。每个任务收集 10-15 个演示，测试 10 次（in-distribution）和 10 次（out-of-distribution，含扰动）。
- **对比方法**：
  - 模拟：PerAct、RVT、RVT-2、SAM-E、Act3D、3D Diffuser Actor、3D-LOTUS、ARP+ 等。
  - 真实：RVT-2。
- **消融实验**：
  - 替换 SAM2 编码器为 SAM、DINOv2、Depth Anything V2。
  - 移除多分辨率嵌入输入或替换为原始上采样。
  - 在 RLBench 和 The Colosseum 上进行消融。

# 4. 资源与算力

- 文中明确说明：所有模型使用 **32 块 NVIDIA H100/A100 GPU** 训练。部分实验也使用 16 或 8 块 GPU，但保持总 batch size 一致以保证公平。
- 训练超参数示例：SAM2Act 在 RLBench 上 batch size=256, learning rate=3.2e-3（按 batch size 线性缩放），训练 56.25K 步（90 epoch）。SAM2Act+ 在 MemoryBench 上 training steps 12.5K（20 epoch）。未提及总训练时长，但可推测每阶段需数小时至数天。

# 5. 实验数量与充分性

- **实验数量**：非常充分。
  - 模拟：18 个 RLBench 任务（含完整对比表，附录 C 列出 12 种方法的结果）、The Colosseum 20 个任务（13 种扰动）、MemoryBench 3 个任务。
  - 真实：4 个任务，每个分 in-distribution 和 out-of-distribution 共 20 次试验。
  - 消融：三种不同编码器替换、两种上采样变体，在 RLBench 和 The Colosseum 上均执行。
  - 额外：在 The Colosseum 上还对比了 SAM2Act 的变体（SAM→SAM、w/o Multi-res Input）。
- **充分性与公平性**：
  - 所有方法使用相同演示数量、相同评估次数（4 次或 3 次），报告均值和标准差。
  - MemoryBench 采用单任务训练隔离记忆因素；真实实验随机化场景变化。
  - 与 RVT-2 对比时，保持训练 pipeline 和 augmentation 一致。
  - 消融实验严格控制除目标变量外的超参数（LoRA rank、学习率等）。
- **客观性**：结果表格完整，包括所有方法在每项任务上的成功率，且附录提供详细统计数字。真实实验也明确列出了失败/成功次数。

# 6. 主要结论与发现

- **SAM2Act** 在 RLBench 18 个任务上平均成功率 86.8%，超越之前 SOTA（RVT-2 的 81.4%）5.4 个百分点，尤其在 `insert peg`（44%提升）和 `sort shape`（29%提升）等高精度任务上优势明显。
- **泛化能力**：在 The Colosseum 的 13 种扰动下，SAM2Act 平均性能仅下降 4.3%，优于 RVT-2（下降 19.5%）和其他变体；对光照、桌面颜色等环境扰动具有显著鲁棒性。
- **记忆能力**：SAM2Act+ 在 MemoryBench 上平均成功率 94.3%，远超无记忆的 SAM2Act（55.0%）和 RVT-2（54.0%），证明了显式记忆建模的重要性。
- **真实世界**：SAM2Act 在高精度任务（turn on the lamp）上成功率 60% vs RVT-2 的 0%；SAM2Act+ 在记忆任务（push the same button）上成功率 70% vs 40%。
- **消融验证**：SAM2 编码器、多分辨率输入、多分辨率上采样模块均贡献显著，缺失任一模块均导致性能下降。

# 7. 优点

- **创新性**：首次将 SAM2 的多分辨率特性与凸上采样结合，用于机器人操作策略，并借鉴 SAM2 的记忆机制解决空间记忆问题。
- **全面性**：既关注通用操作性能（RLBench），又专门设计记忆基准（MemoryBench）和环境泛化基准（The Colosseum），实验覆盖全面。
- **有效性**：在多个基准上取得显著提升（RLBench +5.4%、MemoryBench +39.3%），且消融实验清晰验证每个组件的贡献。
- **实用性**：真实机器人实验验证了方法在低数据量下的可用性和泛化能力（如 out-of-distribution 测试）。
- **公开性**：提供项目页面和代码（sam2act.github.io），便于复现。

# 8. 不足与局限

- **不足**：
  - **任务覆盖有限**：MemoryBench 仅 3 个记忆任务，且均为表格场景，未测试更复杂的长期记忆（如多步骤、环境变化后的记忆）。
  - **固定记忆窗口**：SAM2Act+ 依赖于固定长度的 FIFO 记忆窗口，窗口大小需针对不同任务手动调节，缺乏自适应能力。
  - **笨拙操控**：论文明确指出当前方法无法直接扩展到灵巧连续控制（dexterous continuous control），动作空间仍为离散关键帧。
  - **仅行为克隆**：采用纯行为克隆训练，未结合强化学习或在线调整，可能限制了在未见场景中的进一步优化。
- **偏差风险**：
  - 模拟环境与真实世界仍有差距（如视觉质量、物理参数），真实实验仅 4 个任务，样本量较小（每个任务 20 次试验），统计显著性有限。
  - SAM2Act+ 的训练需要两阶段（预训练+微调），且微调阶段需连续采样，导致 batch 多样性下降，可能对数据量敏感。
- **应用限制**：
  - 依赖深度感知和点云重建，在不可靠深度数据或遮挡严重的场景下可能失效。
  - 记忆模块仅在粗分支引入，细分支未受益，可能限制精细动作的记忆能力。

（完）
