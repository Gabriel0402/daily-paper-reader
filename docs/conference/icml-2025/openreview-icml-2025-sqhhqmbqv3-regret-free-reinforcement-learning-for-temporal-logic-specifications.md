---
title: Regret-Free Reinforcement Learning for Temporal Logic Specifications
title_zh: 针对时态逻辑规范的无遗憾强化学习
authors: "R Majumdar, Mahmoud Salamati, Sadegh Soudjani"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SqhhqMbqV3"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 针对线性时态逻辑规范的无遗憾强化学习
tldr: 该论文提出首个针对线性时态逻辑（LTL）规范的无遗憾在线强化学习算法。假设未知动态系统为有限状态MDP，核心是将LTL合成问题归约为无限视界可达-规避问题，并证明了亚线性遗憾界。该方法适用于高维控制任务，且无需事先知道图结构。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 530, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 611, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 612, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 591, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sqhhqmbqv3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 584, \"height\": 583, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sqhhqmbqv3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sqhhqmbqv3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 1078, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sqhhqmbqv3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 1392, \"label\": \"Table\"}]"
motivation: 现有RL方法处理时态逻辑规范时通常需要已知模型或导致遗憾累积，缺乏理论与算法保证。
method: 将LTL规范归约为可达-规避问题，设计基于乐观探索的无遗憾RL算法。
result: 在多个LTL任务上实现首个亚线性遗憾界，实验验证了算法的有效性和鲁棒性。
conclusion: 该工作为时态逻辑约束下的RL提供了坚实的理论基础和实用算法，推动安全AI控制。
---

## Abstract
Learning to control an unknown dynamical system with respect to high-level temporal specifications is an important problem in control theory. 
We present the first regret-free online algorithm for learning a controller for linear temporal logic (LTL) specifications for systems with unknown dynamics.
We assume that the underlying (unknown) dynamics is modeled by a finite-state and action Markov decision process (MDPs).
Our core technical result is a regret-free learning algorithm for infinite-horizon reach-avoid problems on MDPs.
For general LTL specifications, we show that the synthesis problem can be reduced to a reach-avoid problem once the graph structure is known.
Additionally, we provide an algorithm for learning the graph structure, assuming knowledge of a minimum transition probability, which operates independently of the main regret-free algorithm. Our LTL controller synthesis algorithm provides sharp bounds on how close we are to achieving optimal behavior after a finite number of learning episodes.
In contrast, previous algorithms for LTL synthesis only provide asymptotic guarantees, which give no insight into the transient performance during the learning phase.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：在未知动态系统中，学习一个能最大化满足线性时态逻辑（LTL）规范概率的控制策略。经典的强化学习方法通常只能提供渐近收敛保证，无法在学习过程中量化当前策略与最优策略之间的差距。
- **重要性**：控制与机器人领域核心问题，尤其在高安全性要求场景下（如自主驾驶），需要知道策略何时接近最优。
- **现有局限**：
  - 已有LTL强化学习方法大多缺乏有限时间性能保证。
  - 纯LTL的PAC可学习性曾被认为不可能（Yang et al., 2022），只有在假设已知最小转移概率pmin时才变得可行。
  - 已有的无遗憾算法（如UCRL2）只适用于通信MDP，而LTL与自动机乘积后通常变为非通信MDP。
- **本文贡献**：首次提出针对LTL规范的无遗憾（regret-free）在线学习算法，证明该算法遗憾随回合数亚线性增长，因此可以在有限回合后以高置信度停止并获取接近最优的策略。

## 2. 方法论：核心思想、技术细节与算法流程

### 核心思想

- **乐观面对不确定性**（Optimism in the Face of Uncertainty）：在每个回合，根据历史观测构造一个区间MDP（iMDP），使其以高概率包含真实MDP；然后在此iMDP中通过扩展值迭代（EVI）选取一个最乐观的MDP和策略，并执行该策略直到碰到目标状态或达到回合特定截止时间。
- **归约为可达-规避问题**：
  - 对“直到”公式（¬Avoid U Goal），直接使用无遗憾算法（Algorithm 1）。
  - 对一般LTL，先构建确定性Rabin自动机（DRA），与MDP乘积得到乘积MDP；识别乘积MDP中的接受极大端部件（AMEC）作为目标集G×，非接受极大端部件作为规避集B×，从而将原始问题转化为可达-规避问题。
- **重设机制**：当访问到规避状态（B）时，人工将下一个状态重设为初始状态，从而使系统可在有限时间内到达目标，并定义合适截止时间Hk。

### 关键技术细节

- **构造iMDP**：基于经验转移概率构造1-半径球，半径βk(s,a)依赖于访问次数Nk(s,a)和置信参数δ。
- **扩展值迭代（Algorithm 2, 3）**：迭代计算乐观值函数，内层最大化利用InnerMax将概率质量优先分配给高价值后继状态。
- **截止时间Hk**：由式(7)定义，满足‖Q̃_k^Hk‖_∞ ≤ 1/√k，保证亚线性增长（对数级）。
- **图学习（Algorithm 5）**：假设已知最小转移概率pmin，通过采样验证每条转移是否存在，用于获取一般LTL所需的乘积MDP图结构。该算法独立于主算法，可预先执行一次。

### 遗憾界

- 定理4.2：对可达-规避问题，以概率≥1−2δ，累积遗憾R(K) = O(√K)，其中αK ~ O(log K)。
- 定理5.1：对一般LTL，以概率≥1−δ，遗憾R(K) = O(√K)。

## 3. 实验设计

- **场景**：网格世界（gridworld），边长l（实验中用l=4,6,16）。动作{上、下、左、右}，成功概率0.9，失败不动。墙壁为吸收状态且被标记为规避集B，目标格为G。规格ϕ = ¬Avoid U Goal。
- **基准方法**：ω-PAC算法（Perez et al., 2024）——唯一支持无限视界时态规范保证的策略合成方法，提供(ε,δ)-PAC保证。
- **对比指标**：
  - 归一化遗憾 R(K)/K 随回合数变化（图3、4）。
  - 截止时间Hk变化（图5）。
  - 样本复杂度 k*_reg(δ,ε) vs. k*_PAC(δ,ε) 随状态空间大小变化（图6）。
- **数据集/随机性**：没有标准数据集，而是使用固定网格世界布局；做了10次独立运行（δ=0.1）以展示平均行为。

## 4. 资源与算力

- **文中明确说明**：实验在一台配备Core i7 CPU（3.10GHz）和8GB RAM的笔记本电脑上进行。
- **未提及GPU、模型参数量或大规模分布式训练**等算力细节。因此，该工作主要依赖CPU单机运行，算力需求较低，符合理论驱动型研究特点。

## 5. 实验数量与充分性

- **实验组数**：
  - 图3：l=6，单次运行展示归一化遗憾趋势（图3看似10次平均后的曲线，原文说“δ=0.1 over 10 runs”）。
  - 图4：l=4，与ω-PAC对比，展示10次平均后的归一化遗憾。
  - 图5：l=6，展示截止时间Hk随回合变化。
  - 图6：l从4到16变化，对比两种算法的样本复杂度 k*_reg(0.1,0.1) vs k*_PAC(0.1,0.1）。
- **充分性评估**：
  - **优点**：覆盖不同状态空间大小，与唯一可比基准进行了定量对比，展示了算法的快速收敛和更低的样本复杂度。
  - **局限**：仅使用一个网格世界场景，未展示在不同地形、随机转移概率分布或连续控制任务上的性能。未进行消融实验（如不同pmin假设、不同置信水平δ）。实验公平性方面，由于ω-PAC本身不是在线无遗憾算法，其样本复杂度定义不同，直接比较k*值需谨慎；但本文指出自己是首个无遗憾算法，故已在方法论上取得进步。

## 6. 主要结论与发现

- ✅ **首次提出针对LTL规范的无遗憾在线学习算法**，遗憾界为O(√K)，满足亚线性增长。
- ✅ **将一般LTL归约为可达-规避问题**，结合图学习算法实现完整框架。
- ✅ **实验表明**：算法能在较少的回合内使归一化遗憾快速下降至接近零，相比ω-PAC样本复杂度更低。
- ✅ **理论保证强于现有方法**：以前算法只有渐近保证，本文提供有限时间界和置信水平。

## 7. 优点

- **理论创新性**：首次证明LTL合成的无遗憾性，核心技巧包括乐观探索、截止时间设计与重设机制，有效处理非通信MDP。
- **算法完整性**：提供图学习模块（Algorithm 5），使得即使在未知图结构下也可工作（只需已知pmin）。
- **边界紧凑**：遗憾界为O(√K)，且αK仅对数增长，具有良好的实用潜力。
- **对比优越**：在网格世界实验中，归一化遗憾下降速度明显快于ω-PAC的样本复杂度曲线。
- **实现简单**：算法只涉及iMDP构造和扩展值迭代，无需深度神经网络，可解释性强。

## 8. 不足与局限

- **假设限制**：
  - 假设MDP状态和动作空间有限（finite MDP），无法直接应用于连续空间。
  - 需要已知最小转移概率pmin的正下界（用于图学习），在完全未知环境中可能难以获得。
  - 假设LTL公式可满足且最优概率>0（平凡情况）。
- **实验范围有限**：
  - 只在网格世界测试，缺乏真实机器人场景或高维控制任务验证。
  - 未进行消融研究（如不同pmin值的敏感性、不同置信度δ的影响）。
  - 与ω-PAC的对比中，两种指标（归一化遗憾 vs. 非ε-最优回合数）并不完全等价，可能影响直接结论的严谨性。
- **计算效率**：虽然算力需求低，但EVI迭代在每个回合都要执行，状态空间较大时可能较慢（论文未报告运行时间）。
- **对非LTL规范（如概率约束、鲁棒性）未涉及**。

（完）
