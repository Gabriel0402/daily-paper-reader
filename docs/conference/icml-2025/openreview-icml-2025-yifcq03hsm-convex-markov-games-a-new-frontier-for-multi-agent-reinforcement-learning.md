---
title: "Convex Markov Games: A New Frontier for Multi-Agent Reinforcement Learning"
title_zh: 凸马尔可夫博弈：多智能体强化学习的新前沿
authors: "Ian Gemp, Andreas Alexander Haupt, Luke Marris, Siqi Liu, Georgios Piliouras"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yIfCq03hsM"
tags: ["query:gt-mai"]
score: 8.0
evidence: 凸马尔可夫博弈将博弈论引入多智能体强化学习
tldr: 论文提出凸马尔可夫博弈类，允许一般凸偏好（如公平性、安全性），理论上证明即使在无限时域下纯策略纳什均衡也存在，并可通过可剥削性上界的梯度下降近似。实验展示了在重复博弈、协作博弈和机器人仓库中实现公平和安全的行为，为多智能体强化学习提供了新的博弈论基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1296, \"height\": 162, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yifcq03hsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 270, \"height\": 151, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 646, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 819, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1166, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yifcq03hsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 381, \"height\": 151, \"label\": \"Table\"}]"
motivation: 多智能体系统中的偏好（如公平、安全）不能加性分解，需要新的博弈模型。
method: 定义凸马尔可夫博弈，允许任意凸偏好映射，通过梯度下降逼近均衡。
result: 在多个场景中实现了公平、安全等复杂偏好的平衡解。
conclusion: 凸马尔可夫博弈为多智能体系统提供了理论框架和实用算法。
---

## Abstract
Behavioral diversity, expert imitation, fairness, safety goals and others give rise to preferences in sequential decision making domains that do not decompose additively across time. We introduce the class of convex Markov games that allow general convex preferences over occupancy measures. Despite infinite time horizon and strictly higher generality than Markov games, pure strategy Nash equilibria exist. Furthermore, equilibria can be approximated empirically by performing gradient descent on an upper bound of exploitability. Our experiments reveal novel solutions to classic repeated normal-form games, find fair solutions in a repeated asymmetric coordination game, and prioritize safe long-term behavior in a robot warehouse environment. In the prisoner's dilemma, our algorithm leverages transient imitation to find a policy profile that deviates from observed human play only slightly, yet achieves higher per-player utility while also being three orders of magnitude less exploitable.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：传统马尔可夫博弈（MG）假设每个智能体的收益是状态-动作占用度量的线性函数，无法表达无法沿时间加性分解的复杂偏好，例如行为多样性、专家模仿、公平性和安全性。单智能体领域已推广到凸马尔可夫决策过程（cMDP），解决了这类偏好问题；但在多智能体领域，尚缺乏统一的正式框架和纳什均衡存在性证明。
- **整体含义**：论文定义了**凸马尔可夫博弈（Convex Markov Game, cMG）**，将单智能体 cMDP 拓展至多智能体环境，允许每个智能体的效用是其长期占用度量的任意连续凹函数。证明了即使在无限时域下纯策略纳什均衡（NE）仍然存在，并提出了基于可剥削性上界梯度下降的实用近似算法，为多智能体强化学习中非线性偏好（如公平、安全、创意、模仿）的均衡选择提供了理论基⽯和计算工具。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将博弈模型从线性效用推广到凸（凹）效用，利用占用度量空间（occupancy measure space）的凸性与约束线性性质，通过拓扑方法证明纯策略NE存在。同时，构造可微分的可剥削性上界损失函数，通过梯度下降直接优化策略参数来逼近NE。
- **关键技术细节**：
  - **凸马尔可夫博弈（cMG）定义**：每个玩家 i 的效用 \( u_i(\mu_i, \pi_{-i}) \) 对自身占用度量 \(\mu_i\) 连续凹，对对手策略 \(\pi_{-i}\) 连续。
  - **存在性证明**：利用 Kosowsky（2023）或 Debreu（1952）的拓扑不动点定理，证明最佳响应集在策略空间中虽非凸但可缩（contractible），从而保证纯策略NE存在。
  - **可剥削性上界**：对于熵正则化效用 \( u_i^\tau = u_i + \tau H(\mu_i) \)，推导出不可剥削性界限（定理2）：
    \[
    \epsilon_i(\pi) \le \tau \log(|S||A_i|) + \sqrt{2}\,\|\Pi_{T\mathcal{U}_i}(\nabla_i^\tau \mu_i)\|
    \]
    其中 \(\Pi_{T\mathcal{U}_i}\) 是到占用度量可行集切空间的正交投影。
  - **损失函数**：定义
    \[
    L^\tau(\pi) = \sum_i \|\Pi_{T\mathcal{U}_i}(\nabla_i^\tau \mu_i)\|^2
    \]
    该损失是可微分的，可联合所有玩家策略进行优化。
  - **算法（PGL，算法1）**：初始化策略 \(\pi\)，按照温度退火计划 \(\tau_t\) 循环：
    1. 计算梯度 \(\nabla_\pi L^{\tau_t}\)；
    2. 使用 Adam 等无约束优化器更新策略（对数几率表示）；
    3. 退火 \(\tau_t\) 趋向零。
    无需显式求解每个玩家的凸优化子问题，仅需一次前向传播和自动微分。

## 3. 实验设计：使用了哪些数据集/场景，its benchmark 是什么，对比了哪些方法

- **场景/域**（共7个）：
  1. **多智能体路径规划**（创造力学）：两机器人通过瓶颈门到达同一目标点，奖励加熵正则化。
  2. **迭代囚徒困境（IPD）**（创造力/模仿）：两玩家反复选择合作或背叛，状态为上一步联合行动。
  3. **迭代公共物品博弈（IPGG）**（创造力）：三玩家选择全投或不投。
  4. **El Farol 酒吧问题**（创造力）：三玩家决定是否去酒吧（<3人则收益高）。
  5. **Bach-Stravinsky 博弈**（公平性）：两玩家偏好不同，利用状态占用差异惩罚鼓励公平。
  6. **合成安全域**（安全性）：两状态两动作，定义“安全”占用度量区域，违反则凸惩罚。
  7. **机器人仓库安全域**：两机器人移动快慢，惩罚在共同收货区频繁快速行动。
- **基准方法（Baselines）**：
  - **minϵ**：直接用 CVXPYLAYERS 求解可剥削性最小的凸优化问题。
  - **Sim**：所有玩家同时对各自损失执行梯度下降，并报告策略轨迹的平均。
  - **RR**：轮流（round-robin）梯度下降。
  - **SGAMESOLVER**：基于同伦方法的马尔可夫博弈求解器（Eibelshäuser & Poensgen, 2019）。
- **对比指标**：可剥削性（exploitability）、玩家效用、策略模式（如是否对称、是否状态依赖）。

## 4. 资源与算力

- **硬件说明**：除路径规划实验外，所有实验在 **单 CPU** 上运行，每次求解约 **1 分钟**；使用 CVXOPT 报告精确可剥削性时，运行时间增加约 **10 倍**。路径规划使用 **1 个 GPU**，但未明确 GPU 型号和具体训练时长。
- 论文未报告更详细的算力消耗（如总 GPU 小时数、显存占用等），因此算力信息有限。

## 5. 实验数量与充分性

- **实验数量**：涵盖了 7 个不同的域（4 个重复博弈 + 1 个路径规划 + 1 个合成 + 1 个安全仓库），每个域有特定超参数和对比基线。
- **充分性评价**：
  - 多样化的偏好类型（创意、模仿、公平、安全）展示了框架的通用性。
  - 对比了至少 3 种主流方法（minϵ、Sim、RR、SGAMESOLVER），且结果量化（可剥削性、效用值）。
  - 在公平性实验中报告了 10 次随机初始化的结果；安全域中提供了有无惩罚的对比。
  - **不足**：未进行大规模超参数调优或统计显著性检验；缺少在更大规模、更高维度状态动作空间的验证；未做消融实验（如移除退火的影响）；路径规划实验未与其他多智能体协调算法对比。

## 6. 论文的主要结论与发现

- **理论贡献**：凸马尔可夫博弈中纯策略纳什均衡存在（定理1），突破了非凸最佳响应集合的困难。
- **算法有效性**：所提 PGL 算法能在多个域中找到可剥削性极低（甚至为 \(10^{-5}\) 量级）的近似均衡，且优于同时梯度下降和 minϵ（后者常崩溃）。
- **均衡特性发现**：
  - 在 IPD 中，PGL 找到了一个与“以牙还牙”非常相似的策略模式（合作后倾向合作，背叛后倾向背叛），且效用（0.47）高于 Defect-Defect（0.33），并具有状态依赖性。
  - 在 IPGG 中，PGL 找到的合作/贡献策略（当其他人都贡献时倾向贡献）显著优于零贡献均衡。
  - 在 Bach-Stravinsky 中，找到公平均衡（每位玩家偏好自己更喜欢的作品概率约 60%，但长期出席两种演出的次数相等）。
  - 在机器人仓库安全域中，安全惩罚有效降低了在危险状态做出快速动作的频率（从 69% 降至 42%）。
- **模仿实验**：在 IPD 中，通过退火 KL 散度正则化到人类实践数据，得到策略与人类接近但可剥削性降低三个数量级（从 0.47 降至 \(1.4\times10^{-4}\)），且效用更高。

## 7. 优点：方法或实验设计上的亮点

- **理论深度**：利用拓扑可缩性证明纯策略 NE 存在，避免了传统 Kakutani 不动点定理所需的凸性假设，为后续理论工作开辟新路径。
- **算法创新**：将可剥削性上界转化为可微损失，一键式优化全部智能体策略，避免了逐玩家求解凸优化子问题的计算开销；结合温度退火（同伦路径），从熵正则化游戏逐渐过渡到原始游戏，提高求解稳定性。
- **统一框架**：将创意、模仿、公平、安全等不同偏好纳入同一模型，展示了一致的方法论价值。
- **实验设计**：选择了经典的重复博弈和定制化安全域，结果直观且具有启发性（如 IPD 中的暂态模仿策略具有低可剥削性和高福利）。

## 8. 不足与局限

- **收敛性保证缺失**：论文明确指出 PGL 算法无收敛性证明（Algorithm 1 does not come with any convergence guarantees），其有效性仅凭经验验证。
- **模型依赖**：方法需要已知转移动力学（model-based），并采用集中式梯度计算，不适合纯模型无关或分散式环境。
- **可扩展性**：投影算子 \(\Pi_{T\mathcal{U}_i}\) 涉及矩阵求逆，计算复杂度与状态数 \(|S|\) 的立方相关，难以扩展到大规模连续状态空间。
- **无偏梯度困难**：作者说明在动态模型未知时，投影算子无法获得无偏估计，限制了应用范围。
- **实验覆盖有限**：未与最新的多智能体强化学习算法（如 MAPPO、QMIX）在类似非线性偏好问题上对比；未展示在更复杂机器人或游戏环境（如 StarCraft II）中的表现；消融实验（如退火策略的重要性、不同温度计划的影响）缺失。
- **偏差风险**：IPD 模仿实验使用的人类数据仅来自一个特定实验设置，可能不具备广泛代表性；安全域中的惩罚阈值（10%）是人为设定的，未进行敏感性分析。

（完）
