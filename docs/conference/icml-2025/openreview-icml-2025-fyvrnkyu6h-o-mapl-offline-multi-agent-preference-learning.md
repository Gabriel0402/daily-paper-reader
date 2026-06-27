---
title: "O-MAPL: Offline Multi-agent Preference Learning"
title_zh: O-MAPL：离线多智能体偏好学习
authors: "The Viet Bui, Tien Anh Mai, Thanh Hong Nguyen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FYvrNKYu6H"
tags: ["query:vlm-rl"]
score: 4.0
evidence: 离线多智能体偏好学习用于奖励推断
tldr: 多智能体强化学习中从偏好推断奖励函数具有挑战。本文利用合作MARL中奖励函数与Q函数的固有联系，提出端到端偏好学习方法，避免两阶段训练的不稳定性。实验证明该方法在多人游戏等任务中有效恢复奖励并提升策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1502, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 905, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 975, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1170, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1407, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1160, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1405, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1169, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1403, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1158, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fyvrnkyu6h/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1410, \"height\": 681, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 908, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1781, \"height\": 1052, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1237, \"height\": 1054, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1176, \"height\": 1023, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1188, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1277, \"height\": 823, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1271, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1357, \"height\": 828, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1192, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1279, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1267, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1357, \"height\": 831, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1779, \"height\": 613, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1778, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1607, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fyvrnkyu6h/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1167, \"height\": 972, \"label\": \"Table\"}]"
motivation: 现有MARL偏好学习分两阶段训练，过程不稳定且效率低。
method: 利用奖励函数与Q函数的联系，设计端到端偏好学习框架。
result: 在多人协作任务中，O-MAPL成功恢复奖励函数并提升策略性能。
conclusion: 端到端偏好学习可稳定高效地解决MARL奖励推断问题。
---

## Abstract
Inferring reward functions from demonstrations is a key challenge in reinforcement learning (RL), particularly in multi-agent RL (MARL). The large joint state-action spaces and intricate inter-agent interactions in MARL make inferring the joint reward function especially challenging. While prior studies in single-agent settings have explored ways to recover reward functions and expert policies from human preference feedback, such studies in MARL remain limited. Existing methods typically combine two separate stages, supervised reward learning, and standard MARL algorithms, leading to unstable training processes. In this work, we exploit the inherent connection between reward functions and Q functions in cooperative MARL to introduce a novel end-to-end preference-based learning framework.
Our framework is supported by a carefully designed multi-agent value decomposition strategy that enhances training efficiency. Extensive experiments on two state-of-the-art benchmarks, SMAC and MAMuJoCo, using preference data generated by both rule-based and large language model approaches demonstrate that our algorithm consistently outperforms existing methods across various tasks.

---

## 论文详细总结（自动生成）

# O-MAPL: Offline Multi-agent Preference Learning — 中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：在多智能体强化学习（MARL）中，从人类偏好数据中推断奖励函数是一项关键但极具挑战的任务。传统方法通常采用两阶段流程：先通过监督学习训练一个奖励模型，再使用该奖励模型配合标准的MARL算法优化策略。这种分离式方法存在两个主要缺点：(i) 需要大量偏好数据覆盖状态-动作空间；(ii) 两阶段之间的“错位”会降低策略质量。
- **研究背景**：单智能体领域的偏好学习（PbRL）已取得显著进展，尤其是端到端方法（如IPL）绕过了显式奖励建模。然而，多智能体环境下由于智能体策略间的复杂依赖关系，直接扩展单智能体方法是不够的。目前仅有的少数多智能体PbRL工作仍采用两阶段框架。
- **整体含义**：本文旨在解决多智能体离线偏好学习中的两阶段不稳定问题，提出一种端到端的学习框架——O-MAPL，直接利用奖励函数与软Q函数之间的内在联系，将偏好学习转化为Q空间中的优化问题，从而避免显式奖励建模，提升训练稳定性和一致性。

## 2. 论文提出的方法论

- **核心思想**：利用最大熵RL中的逆软贝尔曼算子性质：存在一个从Q函数到奖励函数的双向映射 `r(s,a) = (T*Q)(s,a) = Q(s,a) - γE_{s'}[V(s')]`。因此，偏好概率可基于Q函数直接定义，无需显式恢复奖励。通过最大化偏好似然得到Q函数，再通过软策略公式 `π(a|s) ∝ μ(a|s) exp((Q(s,a)-V(s))/β)` 直接提取策略。
- **关键技术细节**：
  - **值分解**：在集中训练分布式执行（CTDE）框架下，引入线性混合网络（Mixing Network）聚合局部Q函数和V函数得到全局Q和V。采用单层线性混合网络（而非两层非线性网络），以保持偏好学习目标函数的凸性（Proposition 4.1），避免过拟合，并提供全局-局部一致性保证。
  - **端到端训练**：同时优化三个组件：Q函数和混合网络参数通过最大化偏好似然 `L(q,v,w)` 更新；V函数通过最小化极端V损失 `J(v)` 更新，使其逼近log-sum-exp形式；策略网络通过局部加权行为克隆（WBC）损失更新，该过程保证全局-局部一致性（Theorem 4.3），且不要求混合网络为线性。
  - **偏好数据**：假设可获取成对轨迹偏好数据集 `P`，每个比较 `(σ1 ≻ σ2)` 的似然基于Q函数计算，使用Bradley-Terry模型。
- **算法流程**（Algorithm 1）：
  1. 输入：全局混合网络参数θ，局部Q网络参数ψq，局部V网络参数ψv，各智能体策略网络参数ωi，离线偏好数据集P。
  2. 循环执行：
     - 更新ψq和θ以最大化偏好似然L(ψq,ψv,θ)。
     - 更新ψv以最小化极端V损失J(ψv)。
     - 更新ωi以最大化局部WBC损失Ψ(ωi)。
  3. 输出本地优化策略πi。

## 3. 实验设计

- **数据集/场景**：
  - **SMACv1**：4个任务（2c vs 64zg, 5m vs 6m, 6h vs 8z, corridor）。
  - **SMACv2**：按种族分Protoss、Terran、Zerg，每个种族包含5 vs 5、10 vs 10、10 vs 11、20 vs 20、20 vs 23等15个任务。
  - **MAMuJoCo**：3个连续控制任务（Hopper-v2、Ant-v2、HalfCheetah-v2）。
  - 偏好数据集通过两种方式生成：(i) 基于规则的标签（依据轨迹源数据集质量）；(ii) 基于LLM（GPT-4o）的标签，提取轨迹最终状态信息构建提示。共约1k（MAMuJoCo）至2k（SMAC）对轨迹。
- **基准方法**：
  - BC（行为克隆）
  - IIPL（独立IPL，将单智能体IPL直接应用于每个智能体）
  - IPL-VDN（类似O-MAPL但使用VDN方式的简单求和聚合）
  - SL-MARL（两阶段方法：先学习奖励函数，再用OMIGA算法训练策略）
- **评估指标**：平均回报（MAMuJoCo、SMAC）和胜率（仅SMAC），每个实验使用4个随机种子，汇报均值和标准差。

## 4. 资源与算力

- 文中仅提到“所有实验均使用PyTorch实现，并在单个NVIDIA H100 NVL Tensor Core GPU上并行运行”。未明确说明总训练时长、使用的GPU数量细节或总计算量。因此，无法提供精确的算力统计。

## 5. 实验数量与充分性

- **实验数量**：涵盖两大基准（SMAC和MAMuJoCo）共22个任务（SMACv1 4个、SMACv2 15个、MAMuJoCo 3个），每个任务2种标签生成方式（规则和LLM），共约44组实验（部分任务仅规则）。另外包含了消融实验：
  - 数据保留比例实验（25%、50%、75%、100%）。
  - 1层 vs 2层混合网络对比。
  - GPT-4o vs GPT-4o-mini对比。
- **充分性与公平性**：实验设计较为充分，覆盖了离散和连续动作空间、不同规模与难度的任务。所有对比方法均使用相同的官方实现或合理扩展，使用相同的数据集，报告均值和标准差，并统一种子数。消融实验系统探究了数据量、混合网络结构和LLM质量对性能的影响。因此，实验公平且充分。

## 6. 论文的主要结论与发现

- O-MAPL在所有任务上（除个别）均显著优于所有基线方法，尤其是在复杂任务（如SMACv2的Protoss 20 vs 20、Terran 20 vs 23）中胜率提升明显。
- 使用LLM生成的偏好标签通常比规则标签带来更好性能，表明LLM可以提供更丰富、更准确的偏好信号。
- 单层线性混合网络远优于两层非线性混合网络，验证了凸性假设和过拟合问题。
- 端到端方法（O-MAPL）显著优于两阶段方法（SL-MARL），尤其在需要强协调的导航任务（如corridor）中表现突出。
- 训练曲线显示O-MAPL收敛更快、更稳定，早期就取得高胜率/回报。

## 7. 优点

- **方法创新**：首次将端到端偏好学习（无需显式奖励模型）成功引入多智能体场景，提出基于Q空间的偏好似然最大化。
- **理论支撑**：证明了在单层线性混合网络下损失函数的凸性（Proposition 4.1）和全局-局部一致性（Theorem 4.3, 4.4），保证了训练的稳定性和策略最优性。
- **实用设计**：采用局部WBC策略提取，避免局部值函数可能导致的非法概率分布问题，且不依赖混合网络线性结构。
- **实验全面**：覆盖多种离散/连续任务、多种标签来源、多维度消融，对比方法设置合理。

## 8. 不足与局限

- **数据依赖**：方法仍需要大量偏好对（1k~2k对），样本效率不高。尽管LLM可以快速生成，但若需真实人类反馈，成本依然较高。
- **仅限合作场景**：方法基于共享奖励函数的合作博弈，未考虑混合合作-竞争环境，限制了应用范围。
- **POMDP假设的简化**：实际训练中使用联合观测代替全局状态，论文认可这一点，但未深入分析部分可观测性带来的影响。
- **LLM标签的局限性**：仅适用于具有可提取最终状态信息的任务（如SMAC），对于连续控制任务（如MAMuJoCo）或图像观测的任务不适用。且依赖于GPT-4o API，有成本（约42美元）和隐私风险。
- **资源描述不详细**：未提供训练时长、总计算量等关键信息，不利于复现和资源估算。
- **未与在线交互的MARL方法对比**：所有实验均为离线设定，未与在线交互的MARL方法比较，无法说明离线数据的有效性边界。

（完）
