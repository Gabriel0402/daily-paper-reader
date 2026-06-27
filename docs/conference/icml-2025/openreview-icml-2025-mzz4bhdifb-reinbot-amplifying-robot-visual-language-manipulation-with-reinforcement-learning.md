---
title: "ReinboT: Amplifying Robot Visual-Language Manipulation with Reinforcement Learning"
title_zh: ReinboT：利用强化学习增强机器人视觉-语言操作
authors: "Hongyin Zhang, Zifeng Zhuang, Han Zhao, Pengxiang Ding, Hongchao Lu, Donglin Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Mzz4BhdIFb"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 视觉-语言-动作模型结合强化学习用于机器人操作
tldr: 视觉-语言-动作模型在机器人操作中表现出潜力，但受限于训练数据质量。本文提出ReinboT，一种端到端VLA模型，通过集成强化学习最大化累积奖励的原则，预测密集回报以理解数据质量分布，从而生成更稳健的决策动作。实验表明该方法在多种机器人操作任务上提升了性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1413, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 575, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 828, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 869, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1244, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1614, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1249, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1613, \"height\": 1121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1249, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1611, \"height\": 1116, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1249, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1609, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1577, \"height\": 952, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1237, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1210, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1234, \"height\": 561, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1270, \"height\": 561, \"label\": \"Table\"}]"
motivation: 现有VLA模型受限于训练数据质量，无法充分利用混合质量数据。
method: 提出端到端VLA模型ReinboT，集成强化学习最大化累积奖励原则，预测密集回报。
result: 在多种机器人操作任务上，ReinboT生成更稳健的决策动作，性能提升。
conclusion: 强化学习与VLA模型的结合有效提升了机器人操作的鲁棒性和数据利用率。
---

## Abstract
Vision-Language-Action (VLA) models have shown great potential in general robotic decision-making tasks via imitation learning. However, the variable quality of training data often constrains the performance of these models. On the other hand, offline Reinforcement Learning (RL) excels at learning robust policy models from mixed-quality data. In this paper, we introduce Reinforced robot GPT (ReinboT), a novel end-to-end VLA model that integrates the RL principle of maximizing cumulative reward. ReinboT achieves a deeper understanding of the data quality distribution by predicting dense returns that capture the nuances of manipulation tasks. The dense return prediction capability enables the robot to generate more robust decision-making actions, oriented towards maximizing future benefits. Extensive experiments show that ReinboT achieves state-of-the-art performance on the CALVIN mixed-quality dataset and exhibits superior few-shot learning and out-of-distribution generalization capabilities in real-world tasks.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的视觉-语言-动作（VLA）模型通过模仿学习在一般机器人决策任务中展现出潜力，但其性能严重受限于训练数据的质量分布不均。即使来自成功演示的数据，其质量也可能参差不齐，而模仿学习难以区分和充分利用这种混合质量的数据。离线强化学习（RL）虽然擅长从混合质量数据中学习鲁棒策略，但如何将RL最大化累积回报的原则高效地融入VLA模型，特别是在长时程视觉-语言操作任务中设计广泛适用的密集奖励信号，仍是一个未充分探索的挑战。
- **研究含义**：本文旨在提出一种新的端到端VLA模型——ReinboT，通过内化RL的回报最大化原则，使模型不仅学习动作的分布，还能预测并追求当前状态下可能获得的最大未来收益，从而在数据质量不均的情况下生成更稳健、更高效的操作动作，推动机器人操控能力向通用具身智能迈进。

### 2. 方法论：核心思想、关键技术细节、算法流程

#### 核心思想

- 将RL中的**最大化累积回报**（Return）原则，通过**条件回报序列建模**的方式融入VLA模型。具体地，将**ReturnToGo**（RTG，即从当前步到结束的累积奖励）作为一种新的模态数据，与语言指令、图像状态、本体感觉和动作一起进行序列建模，并利用**期望分位数回归**（Expectile Regression）使模型学习在当前条件下**能够实现的最大回报**，从而指导模型生成趋向于最大化未来收益的动作。

#### 关键技术细节

1. **奖励密集化**（Reward Densification）：
   - 将长时程操作任务轨迹自动分解为多个子目标序列（通过启发式方法：检测关节速度接近零或夹爪状态变化的关键状态）。
   - 构建包含四个方面的密集奖励函数：
     - **子目标达成奖励** \(r_1\)：基于MSE、SSIM和ORB特征匹配，衡量当前状态与子目标状态在图像、本体感觉上的相似度。
     - **任务进度奖励** \(r_2\)：根据当前所属的子目标序列位置赋予奖励，越接近最终目标奖励越大。
     - **行为平滑奖励** \(r_3\)：惩罚关节速度、加速度过大以及动作突变，鼓励平滑自然轨迹。
     - **任务完成奖励** \(r_4\)：仅当整个轨迹成功时为1，其余为0。
   - 最终密集奖励 \(r = \sum_{i=1}^4 w_i r_i\)，权重 \(w_i\) 使各分量量级可比。
2. **端到端强化VLA模型**：
   - **骨干网络**：GPT风格的Transformer（GPT2）。
   - **编码器**：CLIP编码语言指令，ViT+感知器重采样器编码图像，MLP编码本体感觉。
   - **Token嵌入**：引入三个预测token —— `[RTG]`、`[ACTION]`、`[IMAGE]`，分别预测ReturnToGo、机器人动作和未来图像。
   - **ReturnToGo预测损失** \(L_{RTG}\)：基于期望分位数回归，使预测的RTG逼近当前条件下可达到的最大回报（参数 \(m>0.5\) 时实现回报最大化）。
   - **模块化设计**：骨干网络输出 `[RTG]` 特征和 `[ACTION]` 特征，先通过RTG解码器得到隐藏特征 \(\hat{g}^{hidden}\)，再与 `[ACTION]` 特征拼接后输入动作解码器预测动作。整个推理过程只需单次模型推理，无需手动设定初始RTG。
   - 总损失函数：\(L = \lambda L_{RTG} + L_{arm} + 0.01 L_{gripper} + 0.1 L_{image}\)。

#### 算法流程（测试阶段）

1. 输入当前图像状态、本体感觉和语言指令。
2. 通过骨干网络提取 `[RTG]` 和 `[ACTION]` 特征。
3. RTG解码器预测最大化回报的隐藏特征 \(\hat{g}^{hidden}\)。
4. 动作解码器结合 \(\hat{g}^{hidden}\) 和 `[ACTION]` 特征输出动作 \(\hat{a}_{t:t+k-1}\)。
5. 执行动作，与环境交互获得下一状态（无需环境提供奖励），重复上述步骤。

### 3. 实验设计

#### 数据集 / 场景

- **模拟环境**：CALVIN（长时程语言条件操作基准），使用其**混合质量数据集**：
  - 少量带语言标注的成功轨迹（每任务约50条）。
  - 大量无语言指令的自主探索数据（>20,000条，来自原始CALVIN）。
  - 失败数据（>10,000条，由预训练VLA模型RoboFlamingo与环境CALVIN D交互产生，并加入不同高斯噪声）。
  - 测试环境：CALVIN D。
- **真实世界**：UR5机械臂上的抓取放置任务，包括杯子、碗、毛绒玩具等物体。
  - 总计约530条成功轨迹（数据分布不均，即使成功轨迹质量也有差异）。
  - 少样本学习：每个任务仅30条成功轨迹进行微调（共3个任务）。
  - OOD泛化：包含未见语言指令、桌面背景、干扰物、操作物体等4种场景。

#### benchmark 与对比方法

- **基准方法**：
  - 模仿学习类型：RoboFlamingo、GR-1、PIDM（仅在带标注数据上训练）。
  - 分层模仿学习：GR-MG。
  - 离线RL类型：RWR（Reward-Weighted Regression，复现版）。
  - 同时对比不同奖励设计：稀疏奖励、子目标稀疏奖励、单一密集奖励、完整密集奖励（各分量）。

- **评价指标**：
  - 链式指令成功率（连续5个指令的成功率）。
  - 平均长度（AL）：完成的指令个数均值。

### 4. 资源与算力

- **文中未明确说明所使用的GPU型号、数量、训练时长**。仅在附录中给出了训练超参数：
  - Epochs: 50, Batch size: 32, Learning rate: 0.001, Weight decay: 0.01。
  - 预训练权重来自GR-1在Ego4d数据集上的视频生成预训练，对于后续机器人数据微调的计算开销未提及。
- **提示**：由于缺少算力细节，难以评估复现成本。

### 5. 实验数量与充分性

- **实验数量**：
  - 模拟环境主实验（表1）：7种方法 × 多种奖励设计，共约14行结果。
  - 消融实验（表2）：5组（无ReturnToGo、去除各奖励分量）。
  - 超参数分析（图2）：\(\lambda\) 取0.0001~0.1，\(m\) 取0.5~0.99。
  - 预测回报特性分析（图3）。
  - 真实世界实验（图6）：少样本学习（3个任务）+ OOD泛化（4个场景），对比GR-1和RWR。
- **充分性与公平性**：
  - 涵盖了多种代表性的基线和不同的奖励设置，对比较为全面。
  - 消融实验验证了每个设计组件的必要性。
  - 超参数通过验证集选择，避免了过拟合。
  - 真实世界实验在少量数据下进行，体现了少样本能力。
  - 可能存在的不足：未与最新VLA+RL方法（如Q-Transformer、Steering等）直接对比；模拟环境仅使用CALVIN，缺乏在更多机器人平台（如Franka、Adroit）上的验证；真实世界数据量较小（530条），且均为成功轨迹，未实验包含失败数据的混合质量情况。

### 6. 主要结论与发现

- **ReinboT在CALVIN混合质量数据上达到SOTA**：相比最佳基线RWR（平均长度1.82），ReinboT使用完整密集奖励达到2.26，提升约24%。
- **密集奖励设计的关键性**：每个奖励分量（子目标达成、任务进度、行为平滑、任务完成）都对性能有显著贡献，去除任一组件都会导致平均长度下降14.6%~20.8%。尤其是任务进度奖励影响最大。
- **ReturnToGo预测的回报最大化效果**：通过期望分位数回归（m=0.9）可以使预测回报分布向右偏移，引导模型追求更大回报；但过高的m（如0.99）会导致过估计，性能下降。
- **真实世界表现**：少样本学习和OOD泛化显著优于GR-1和RWR，验证了方法的实用性。
- **RL理念的成功融入**：ReinboT避免了传统RL中Q函数估计的困难，通过条件回报最大化实现了类似于RL“追求更好行动”的效果，且无需手动设定初始RTG。

### 7. 优点

1. **创新性**：首次将RL回报最大化思想通过条件序列建模和期望分位数回归无缝集成到端到端VLA模型中，自成一个新的强化学习范式。
2. **奖励设计的普适性**：提出的奖励密集化方法基于机器人操作的通用物理特性（子目标、进度、平滑性、完成），可推广到多种操作任务，且自动分解子目标。
3. **模块化与效率**：模型设计为单次推理输出动作，避免了Reinformer等两阶段推理（先预测RTG再预测动作），更高效且易于部署。
4. **无需手动设定初始RTG**：在推理时自动预测当前状态下的最大化回报，极大减轻了实际部署中手动调参的负担。
5. **对混合质量数据鲁棒**：能够区分并利用不同质量的数据，在低质量数据（甚至失败数据）存在的场景下仍能提升性能。

### 8. 不足与局限

1. **实验覆盖范围有限**：
   - 仅在一个模拟基准（CALVIN）和一个真实平台（UR5）上测试，缺乏在更多机器人形态（如双臂、移动操作）、更复杂环境（家庭、工业）上的验证。
   - 未与当前流行的基于扩散策略或Q函数方法的VLA+RL工作（如Q-Transformer、Diffusion Policy结合价值引导等）进行直接对比。
2. **数据质量假设**：真实世界实验仅使用成功轨迹，未涉及混合质量数据（包含失败轨迹）的实验，削弱了对方法声称“从混合数据中学习”的直接支撑。
3. **奖励设计依赖启发式分割**：子目标自动划分基于关节速度/夹爪状态变化的启发式规则，对于某些无明确停顿或连续操作的任务可能不准确。
4. **算力与可复现性**：未报告训练所需GPU型号、数量和时长，模型规模（12层Transformer）虽不大但预训练权重来源（GR-1）仍需较大算力，复现门槛较高。
5. **期望分位数回归参数敏感性**：m值对性能影响显著（最佳0.9，过高过低均下降），需要仔细调参，可能在不同任务上需要重新调整。
6. **泛化风险**：方法在实验中表现出的OOD泛化仅针对有限场景（背景、干扰物等），对于未见物体类别或长时程任务的组合泛化能力未充分测试。

（完）
