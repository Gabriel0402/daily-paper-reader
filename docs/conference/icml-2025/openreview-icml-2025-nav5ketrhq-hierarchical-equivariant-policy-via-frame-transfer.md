---
title: Hierarchical Equivariant Policy via Frame Transfer
title_zh: 基于帧传输的层次化等变策略
authors: "Haibo Zhao, Dian Wang, Yizhe Zhu, Xupeng Zhu, Owen Lewis Howell, Linfeng Zhao, Yaoyao Qian, Robin Walters, Robert Platt"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=nAv5ketrHq"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 层次化多智能体策略与大模型
tldr: 针对层次化策略学习中层间接口未充分探索且忽略对称性的问题，本文提出层次化等变策略（HEP），通过帧传输接口将高层智能体输出作为低层智能体的坐标框架，提供强归纳偏置。该方法在多种连续控制任务中显著减少了所需演示次数，提高了样本效率，为多智能体层次化策略设计提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 1061, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 888, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1781, \"height\": 2052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nav5ketrhq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 1040, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1686, \"height\": 702, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 277, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 369, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 649, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1238, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 550, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nav5ketrhq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 691, \"height\": 170, \"label\": \"Table\"}]"
motivation: 现有层次化策略忽略对称性，需要大量演示才能获得鲁棒性能。
method: 提出帧传输接口，利用高层智能体输出为低层提供坐标框架，实现层次化等变策略。
result: 在多个连续控制任务中，HEP以更少的演示达到了更优的性能。
conclusion: HEP通过利用对称性提升了层次化策略的样本效率和鲁棒性。
---

## Abstract
Recent advances in hierarchical policy learning highlight the advantages of decomposing systems into high-level and low-level agents, enabling efficient long-horizon reasoning and precise fine-grained control. However, the interface between these hierarchy levels remains underexplored, and existing hierarchical methods often ignore domain symmetry, resulting in the need for extensive demonstrations to achieve robust performance. To address these issues, we propose Hierarchical Equivariant Policy (HEP), a novel hierarchical policy framework. We propose a frame transfer interface for hierarchical policy learning, which uses the high-level agent's output as a coordinate frame for the low-level agent, providing a strong inductive bias while retaining flexibility. Additionally, we integrate domain symmetries into both levels and theoretically demonstrate the system's overall equivariance. HEP achieves state-of-the-art performance in complex robotic manipulation tasks, demonstrating significant improvements in both simulation and real-world settings.

---

## 论文详细总结（自动生成）

# 论文《Hierarchical Equivariant Policy via Frame Transfer》详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：层次化策略学习（high-level + low-level）中，层间接口设计不够灵活（现有方法常将高层输出硬性作为低层轨迹终点），且大多忽略任务中固有的空间对称性（如平移和平面旋转），导致需要大量演示数据才能获得鲁棒性能。
- **目标**：提出一种既提供强归纳偏置（通过将高层输出作为低层坐标框架）又保留灵活性、同时融入对称性的层次化策略框架，从而大幅提升样本效率和泛化能力。
- **背景**：机器人操作任务常具有平移和绕竖直轴的旋转对称性（T(3)×SO(2)），端到端策略难以利用该结构；而现有层次方法（如Chained Diffuser）要么硬约束低层，要么未利用对称性。

## 2. 方法论
### 核心思想与框架
- **整体结构**：高层策略 $\pi_{\text{high}}$ 预测一个3D平移 $t_{\text{high}}$（作为子目标的关键点位置）；通过 **Frame Transfer** 接口将观测和动作转换到以 $t_{\text{high}}$ 为原点的相对坐标系；低层策略 $\pi_{\text{low}}$ 在该局部坐标系下预测完整的SE(3)轨迹。
- **关键创新**：  
  - **Frame Transfer**：$\tau(o, t_{\text{high}}) = o - t_{\text{high}}$，$\tau(a, t_{\text{high}}) = a - t_{\text{high}}$。高层仅输出平移而非完整位姿，低层在相对框架下学习，既保持译码不变性又允许灵活调整。  
  - **等变设计**：高层使用SO(2)-等变3D U-Net从体素热图预测平移；低层使用等变扩散策略（Equivariant Diffusion Policy）；整体策略满足T(3)×SO(2)等变性（论文提供理论证明）。  
  - **堆叠体素编码器**：替代传统体素下采样，为每个体素内的点云用等变PointNet聚合特征（保留细粒度几何信息），且保持等变性。

### 关键公式与流程
- $\pi(o) = \pi_{\text{low}}(o, t_{\text{high}}), \quad t_{\text{high}} = \pi_{\text{high}}(o)$  
- 高层损失：交叉熵（预测体素热图 vs. 专家标注热图）  
- 低层损失：扩散模型噪声预测MSE（在帧转移后的观测和动作上）  
- 等变性证明：所有组件（$\pi_{\text{high}}, \pi_{\text{low}}, \tau$）在SO(2)和T(3)下满足对应条件，整体策略等变。

## 3. 实验设计
- **仿真环境**：RLBench（CoppeliaSim + PyRep），30个任务（20个常用任务 + 10个新增高难度任务，如Lamp On, Push 3 Buttons等）。  
- **真实环境**：UR5e机器人 + 3个Intel Realsense D455摄像头，三个长程任务（Pot Cleaning, Blocks to Drawer, Blocks Stacking）。  
- **对比方法**：  
  - 开环设置：Chained Diffuser（层次式基线）、3D Diffuser Actor（非层次式基线）  
  - 闭环设置：Equivariant Diffusion Policy（EquiDiff，非层次式等变基线）  
  - 额外对比：Hierarchical Diffusion Policy (HDP) 在7个共同任务上  
- **训练数据**：每个任务使用100个演示（仿真），真实世界任务20-30个演示；单次泛化实验仅1个演示。

## 4. 资源与算力
- **文中未明确说明** GPU 型号、数量及训练时长。仅提到使用 AdamW 优化器，学习率 1e-4，weight decay 5e-4，批量大小 16，训练 100,000 次迭代，DDPM 100步去噪。未提供硬件配置细节。

## 5. 实验数量与充分性
- **仿真实验**：30个任务 × 两种控制设置（开环/闭环），共约60组主要对比；每个任务100次评估（最后检查点）。  
- **消融实验**：6个任务上检验5种变体（无层次、无等变、无帧转移、无堆叠体素、组合消融），共约30组消融。  
- **真实世界**：3个任务 × 20次试次（10次相似/10次新摆放），单次泛化实验（20次），环境变化实验（3种条件）。  
- **充分性**：任务覆盖广泛（短/长程、精细/粗放操作），消融系统，真实环境验证，统计显著。不足之处：仿真中未报告多随机种子（仅一个最后检查点）；闭环实验仅10个任务，选择性较强。

## 6. 主要结论与发现
- HEP 在仿真开环设置30个任务上平均成功率比最强基线（Chained Diffuser）高 10%，闭环设置（10个任务）比 EquiDiff 高 23%。  
- 消融表明：等变性影响最大（-24%），帧转移次之（-16%），堆叠体素编码（-10%）。  
- 真实世界：开环成功率达0.8-0.9，显著优于 Chained Diffuser（0.2-0.4）；单次演示下泛化成功率达80%（基线5%）；环境变化（颜色/杂物）下仍保持0.6-0.9成功率。  
- 证明：整体层次策略满足T(3)×SO(2)等变性，是首个将等变性引入层次化策略的工作。

## 7. 优点
- **方法设计**：Frame Transfer 接口新颖，巧妙解耦高层粗定位与低层精控制，同时自然引入平移不变性；等变性分层结合（全局+局部）提升样本效率。  
- **泛化能力**：小样本（单演示）及环境变化下表现突出，验证了对称性先验的有效性。  
- **灵活性**：支持开环/闭环两种控制模式，而许多基线仅支持其中之一。  
- **全面性**：30个仿真任务 + 真实世界三类实验 + 详细消融，验证充分。

## 8. 不足与局限
- **实验覆盖**：仅限桌面操作任务，未推广到人形机器人、移动操作等更复杂场景。  
- **闭环表现**：Pot Cleaning 任务中闭环陷入重复循环，提示缺乏历史记忆机制。  
- **资源信息缺失**：未报告GPU型号、数量及训练时间，影响可复现性。  
- **潜在偏差**：仿真基于RLBench，且真实世界任务数量有限（3个）；某些任务（如Take Money）存在过拟合风险。  
- **未来方向**：需加入记忆模块（如Transformer）处理时间依赖；扩展Frame Transfer到旋转分量（目前仅平移）；验证更高维对称性（如SE(3)）。

（完）
