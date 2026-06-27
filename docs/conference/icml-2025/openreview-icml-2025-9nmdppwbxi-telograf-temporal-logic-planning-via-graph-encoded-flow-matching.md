---
title: "TeLoGraF: Temporal Logic Planning via Graph-encoded Flow Matching"
title_zh: TeLoGraF：通过图编码流匹配进行时态逻辑规划
authors: "Yue Meng, Chuchu Fan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9NmdppWbXi"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 信号时态逻辑规划的图编码流匹配方法
tldr: 针对现有方法仅能处理固定或参数化信号时态逻辑（STL）规范的问题，本文提出TeLoGraF，利用图神经网络编码器提取时态逻辑信息，并结合流匹配学习通用STL规范的解决方案。构建了包含20万STL规范的数据集，在多个仿真环境中验证了该方法处理复杂STL任务的有效性，为时态逻辑规划提供了新方向。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1733, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1735, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1758, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1756, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1771, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1528, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1526, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1528, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1529, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1063, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1062, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1061, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1061, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1064, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1059, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1060, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1064, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1063, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1060, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1063, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1060, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1061, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1057, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1059, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1064, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1054, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1054, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1057, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1055, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1056, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1057, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1055, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1054, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1054, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1050, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1050, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1053, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1048, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1050, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1052, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1049, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1050, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1058, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1057, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 1060, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nmdppwbxi/fig-049.webp\", \"caption\": \"\", \"page\": 0, \"index\": 49, \"width\": 1065, \"height\": 1050, \"label\": \"Figure\"}]"
motivation: 现有方法仅能处理固定或参数化的STL规范，缺乏泛化能力。
method: 利用图神经网络编码STL模板，通过流匹配学习从规范到轨迹的映射。
result: 在多种仿真环境中，TeLoGraF成功解决了未见过的复杂STL任务。
conclusion: TeLoGraF为通用STL规划提供了可学习的框架。
---

## Abstract
Learning to solve complex tasks with signal temporal logic (STL) specifications is crucial to many real-world applications. However, most previous works only consider fixed or parametrized STL specifications due to the lack of a diverse STL dataset and encoders to effectively extract temporal logic information for downstream tasks. In this paper, we propose TeLoGraF, Temporal Logic Graph-encoded Flow, which utilizes Graph Neural Networks (GNN) encoder and flow-matching to learn solutions for general STL specifications. We identify four commonly used STL templates and collect a total of 200K specifications with paired demonstrations. We conduct extensive experiments in five simulation environments ranging from simple dynamical models in the 2D space to high-dimensional 7DoF Franka Panda robot arm and Ant quadruped navigation. Results show that our method outperforms other baselines in the STL satisfaction rate. Compared to classical STL planning algorithms, our approach is 10-100X faster in inference and can work on any system dynamics. Besides, we show our graph-encoding method's capability to solve complex STLs and robustness to out-distribution STL specifications. Code is available at https://github.com/mengyuest/TeLoGraF

---

## 论文详细总结（自动生成）

# 论文总结：TeLoGraF：通过图编码流匹配进行时态逻辑规划

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有信号时态逻辑（STL）规划方法大多只能处理固定或参数化的STL规范，缺乏处理**通用STL语法**的能力。当遇到新的STL规范时，需要重新训练网络，效率低下。同时，缺乏大规模的STL数据集和有效的STL编码器。
- **研究动机**：使机器人能够泛化到未见过的复杂STL任务（如导航、避障、顺序操作等），提供可学习的解决方案，兼具高质量和快速推理。
- **整体含义**：首次提出一种基于图神经网络（GNN）编码器和流匹配（Flow Matching）的生成式模型，能够以STL规范为条件直接生成可行轨迹，在多种动力学系统上取得优于经典方法和学习基线的效果，并实现10–100倍的推理加速。

## 2. 论文提出的方法论
### 核心思想
- 将STL规范视为**语法树**，并将其转换为**有向图**：每个运算符和原子命题作为节点，父子关系作为边（子节点指向父节点），节点特征包含运算符类型、时间区间、物体坐标/半径等信息。
- 使用**多层GNN**（图卷积网络）对STL图进行消息传递和聚合，得到固定维度的嵌入向量。
- 使用**条件流匹配**（Conditional Flow Matching）作为生成模型：以STL嵌入和初始状态为条件，学习从高斯噪声到目标轨迹的向量场。推理时通过求解ODE从噪声生成轨迹。

### 关键技术细节
- **STL模板**：定义了四种常用模板——单目标（Single-goal）、多目标（Multi-goal）、顺序（Sequential）、偏序（Partial），每种模板包含到达/避免区域、时间约束和逻辑组合。
- **图编码**：节点特征维度8（运算符类型、起始/结束时间、物体坐标、半径、是否为Until左孩子）。GNN使用4层GCN，隐藏单元256，输出嵌入256维。
- **流匹配损失**：\(\mathcal{L}_{FM} = \mathbb{E}_{t, X_0, X_1} \| H_\omega(F_\theta(G), x_0, t, X_t) - \Delta X \|^2\)，其中 \(X_t = tX_1 + (1-t)X_0\)，\(\Delta X = X_1 - X_0\)。网络预测速度场，通过欧拉法求解ODE生成轨迹。
- **网络结构**：生成器 \(H_\omega\) 采用U-Net架构（类似Janner et al. 2022），额外输入STL嵌入和初始状态。训练时流步数 \(N_s=100\)，推理时可减少至10步以加速。

## 3. 实验设计
### 数据集与场景
- 五种**仿真环境**：Linear（单积分器）、Dubins（车辆动力学）、PointMaze、AntMaze、Franka Panda（7自由度机械臂）。
- **STL规格生成**：每种环境使用四种模板，随机生成2–12个目标/障碍物，初始化随机位置。总共收集**200K个STL规范**，每个规范2条演示轨迹（共400K条轨迹）。80%训练，20%验证。
- 轨迹收集方法：可微分环境（Linear, Dubins, Panda）用梯度优化；非可微环境（PointMaze, AntMaze）用A*搜索+路径跟踪。

### Benchmark与对比方法
- **经典方法**：
  - Grad（梯度优化，多个迭代）
  - Grad-lite（少量迭代）
  - CEM（交叉熵方法）
- **学习基线**：
  - CTG（扩散模型+梯度引导）
  - LTLDoG（扩散模型+分类器引导）
- **编码器消融**：GRU、Transformer、TreeLSTM、GNN（本文），均使用相同的流匹配骨干。
- **变体**：TeLoGraD（GNN+扩散）、TeLoGraF（GNN+流匹配）、TeLoGraF (Fast)（减少ODE步数至10步）。

### 评估指标
- STL满意度（Satisfaction Rate）：采样1024条轨迹，选择最优一条，计算满足STL的比例。
- 运行时间（Runtime）。

## 4. 资源与算力
- 论文明确说明：使用**Nvidia L40S GPUs**进行训练，每个训练任务在**单GPU上耗时6–24小时**（取决于环境复杂度）。训练1000个epoch，batch size 256，优化器Adam，学习率5e-4（余弦退火至5e-5）。
- 推理时，TeLoGraF (Fast)仅需10步ODE，在Franka Panda上比Grad快123.6倍，比CEM快60.7倍。

## 5. 实验数量与充分性
- **主要实验**：在5个环境上对比TeLoGraF变体与4种基线，每个环境采样256个验证STL，重复评估。
- **消融实验**：
  1. **ODE步数**：在Dubins上测试1–100步，验证速度与质量权衡。
  2. **编码器结构**：GRU、Transformer、TreeLSTM、GNN在5个环境上的训练/验证STL满意度。
  3. **STL类型**：四种模板分别统计满意度，分析编码器在不同复杂度下的表现。
  4. **OOD鲁棒性**：对STL语法树随机复制子节点（增广节点数），测试预训练模型在修改后的STL上的性能。
- **充分性判断**：实验覆盖面广（低维至高维动力学、简单到复杂STL、多种编码器、多种基线、OOD测试），对比公平（复现基线、统一骨干）。因此实验设计比较充分、客观、公平。

## 6. 论文的主要结论与发现
- TeLoGraF（特别是TeLoGraD版本）在STL满意度上**显著优于**所有基线和经典方法，同时推理速度比经典方法快10–100倍。
- GNN编码器在泛化到未见STL时优于序列模型（GRU/Transformer），且对OOD语法修改更鲁棒。
- 流匹配模型（TeLoGraF）在大多数环境下与扩散模型（TeLoGraD）性能相当，但可大幅加速（TeLoGraF (Fast)用1/10步数仍保持相似满意度）。
- 所有编码器在训练集上满意度接近100%，但验证集表现分化，说明模型泛化能力的差距。

## 7. 优点
- **方法创新**：首次将STL规划问题转化为条件生成问题，使用图编码提取STL结构信息，结合流匹配实现快速推理。
- **通用性**：可处理任意系统动力学（黑箱/可微均适用）和灵活STL语法（四种模板+任意组合）。
- **全面数据集**：构建了包含200K STL规范的大规模数据集，覆盖多种难度层次，开源促进该领域发展。
- **系统消融**：详细比较了不同编码器、流步数、STL类型等，验证了图编码的有效性。
- **高效推理**：TeLoGraF (Fast)在保持质量的同时实现数十倍加速，适合实时应用。

## 8. 不足与局限
- **无保证性**：数据驱动方法不提供形式化正确性保证，对于安全关键任务可能需要后续验证或精化。
- **对复杂STL退化**：在顺序/偏序等复杂模板上，所有方法的满意度下降，尤其是高维环境（Linear, Dubins, Panda），表明泛化仍有瓶颈。
- **OOD鲁棒性有限**：当STL语法被大量修改（节点数增加）时，满意度下降，虽然GNN优于其他编码器，但仍有提升空间。
- **轨迹动态一致性**：模型直接预测“状态-动作”序列，但推理时仅用waypoints，未保证动态一致性；需额外跟踪控制器或逆动力学来执行。
- **实验环境局限**：只仿真了圆形/方形物体和简单障碍，未涉及更复杂的3D场景、多机器人协作或真实硬件部署。
- **训练资源**：单次训练需6–24小时，可能对资源有限的团队不友好。但推理开销很低。

（完）
