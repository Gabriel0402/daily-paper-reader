---
title: Breaking the Curse of Multiagency in Robust Multi-Agent Reinforcement Learning
title_zh: 打破鲁棒多智能体强化学习中的多智能体诅咒
authors: "Laixi Shi, Jingchu Gai, Eric Mazumdar, Yuejie Chi, Adam Wierman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=fFBnsYRsPg"
tags: ["query:gt-mai"]
score: 7.0
evidence: 基于博弈论的鲁棒多智能体强化学习
tldr: 本文针对多智能体强化学习在模拟到现实差距下的脆弱性，提出一类基于行为经济学的分布鲁棒马尔可夫博弈。通过合理定义不确定性集，克服了多智能体诅咒（样本复杂度随智能体数量指数增长）。所提算法在理论上具有更优的样本效率，为鲁棒MARL提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ffbnsyrspg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1677, \"height\": 375, \"label\": \"Table\"}]"
motivation: 标准MARL算法易受模拟到现实差距影响，且现有鲁棒方法面临样本复杂度高的问题。
method: 提出基于行为经济学的分布鲁棒马尔可夫博弈，每个代理人使用熵正则化策略。
result: 理论上克服了多智能体诅咒，实现了与智能体数量无关的样本复杂度。
conclusion: 分布鲁棒博弈可有效提升MARL的鲁棒性和样本效率。
---

## Abstract
Standard multi-agent reinforcement learning (MARL) algorithms are vulnerable to sim-to-real gaps. To address this, distributionally robust Markov games (RMGs) have been proposed to enhance robustness in MARL by optimizing the worst-case performance when game dynamics shift within a prescribed uncertainty set. RMGs remains under-explored, from reasonable problem formulation to the development of sample-efficient algorithms. Two notorious and open challenges are the formulation of the uncertainty set and whether the corresponding RMGs can overcome the curse of multiagency,  where the sample complexity scales exponentially with the number of agents. In this work, we propose a natural class of RMGs inspired by behavioral economics, where each agent's uncertainty set is shaped by both the environment and the integrated behavior of other agents. We first establish the well-posedness of this class of RMGs by proving the existence of game-theoretic solutions such as robust Nash equilibria and coarse correlated equilibria (CCE). Assuming access to a generative model, we then introduce a sample-efficient algorithm for learning the CCE whose sample complexity scales polynomially with all relevant parameters. To the best of our knowledge, this is the first algorithm to break the curse of multiagency for RMGs, regardless of the uncertainty set formulation.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：标准多智能体强化学习（MARL）算法在面对模拟到现实（sim-to-real）差距时表现脆弱，导致训练时学到的策略在部署时性能大幅下降。现有鲁棒MARL方法（分布鲁棒马尔可夫博弈，RMGs）存在两个关键挑战：
  - **不确定性集的构造不切实际**：现有研究多采用`(s,a)-矩形性`条件，即每个智能体独立考虑每个联合动作下的最差情况，这与行为经济学中人类决策模式不符（人类倾向于整体评估其他智能体不确定性，而非逐动作平均）。
  - **多智能体诅咒**：样本复杂度随智能体数量呈指数增长，严重限制了可扩展性。
- **整体含义**：本文试图通过设计更合理的不确定性集（虚构不确定性集，满足`others-integrated (s, a_i)-rectangularity`），并开发能打破多智能体诅咒的样本高效算法，为鲁棒MARL提供新的理论基础与实用工具。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：受行为经济学启发，每个智能体在构建不确定性集时，将环境动态与其他智能体策略的扰动**整体**整合，而非分解到每个联合动作。具体地，对于智能体`i`，不确定性集定义为：
  - 对于每个状态`(s, a_i)`，以**期望名义转移核**`P^{π_{-i}}_{h,s,a_i}`为中心（该核依赖于其他智能体策略`π_{-i}`和名义转移`P^0`），以TV距离为度量，半径为`σ_i`。
  - 这等价于将单智能体鲁棒RL中的`(s,a)-矩形性`自然推广到多智能体情境，形成“他人集成”的`(s,a_i)-矩形性`。
- **关键技术细节**：
  1. **理论奠基**：证明了一类新RMGs中鲁棒纳什均衡（NE）和粗相关均衡（CCE）的存在性，并给出了鲁棒值函数与鲁棒最优响应的贝尔曼方程。
  2. **算法设计 —— Robust-Q-FTRL**：
     - 依托生成模型（generative model），采用**自适应采样**与**在线对抗学习**框架。
     - 每时间步`h`执行`K`次迭代，每次迭代从名义转移核中抽取`N`个样本构建经验模型；利用对偶技巧（式(16)）高效计算当前策略下的鲁棒Q函数（避免直接求解维度为S的线性规划）。
     - 使用Follow-the-Regularized-Leader（FTRL）更新每个智能体的策略：`π^{k+1}_{i,h}(a_i|s) ∝ exp(η_{k+1} * Q^k_{i,h}(s,a_i))`。
     - 引入方差形式乐观奖励项`β_{i,h}(s)`，用于价值函数的置信上界估计。
     - 最终输出策略分布`ξ`，其概率权重由学习率`α_k`定义。
  3. **样本复杂度上界**：在TV距离不确定性集下，实现`ε`-鲁棒CCE所需样本数为：
     \[
     \widetilde{O}\left(\frac{S H^6 \sum_{i=1}^n A_i}{\varepsilon^4} \min\left\{H,\frac{1}{\min_i \sigma_i}\right\}\right)
     \]
     这是首次摆脱多智能体诅咒（线性依赖各智能体动作数之和而非乘积）。
- **信息论下界**：通过退化为单智能体鲁棒MDP得到下界`Ω(S H^3 \max_i A_i / (\varepsilon^2 \min\{H,1/\min_i \sigma_i\}))`，表明算法在核心参数上接近最优。

## 3. 实验设计

- **实验部分**：**论文未进行任何数值实验或模拟**。全文聚焦于理论分析（存在性证明、样本复杂度上界与下界），未涉及具体数据集、基准方法或对比实验。算法的有效性完全通过理论推导保证。

## 4. 资源与算力

- **未提及**：论文未提及任何GPU型号、数量或训练时长。这符合理论型论文的特点，不涉及实验计算开销。

## 5. 实验数量与充分性

- **不适用**：由于没有实验，无法评估实验充分性与公平性。论文通过数学证明（非数值实验）来支持结论，属于理论贡献型工作。证明过程包括：
  - 鲁棒均衡存在性（Kakutani不动点定理）；
  - 鲁棒Q函数的对偶表示（强对偶性）；
  - 算法收敛性与样本复杂度界（基于马尔可夫不等式、鞅差、自适应采样分析）。
- 这些证明在理论上是严谨的，但缺乏实际场景验证（如自动驾驶、游戏等）。因此，其充分性需读者基于理论逻辑自行判断。

## 6. 论文的主要结论与发现

1. **新一类RMGs**：提出具有“他人集成`(s,a_i)-矩形性`”的虚构不确定性集，更符合人类决策模式，且自然扩展自单智能体鲁棒RL。
2. **均衡存在性**：证明了鲁棒NE和鲁棒CCE在该类RMGs中总是存在。
3. **突破多智能体诅咒**：Robust-Q-FTRL算法实现了样本复杂度`\widetilde{O}(S H^6 \sum_i A_i / \varepsilon^4 · min\{H,1/\min_i \sigma_i\})`，首次在RMGs中打破多智能体诅咒（依赖动作数之和而非乘积）。
4. **算法可操作性**：给出鲁棒Q函数的可计算对偶形式，避免了指数爆炸的线性规划求解。
5. **信息论下界**：`Ω(S H^3 \max_i A_i / (\varepsilon^2 \min\{H,1/\min_i \sigma_i\}))`，表明算法在H和σ相关项上可能仍存在改进空间。

## 7. 优点

- **理论创新性**：首次将行为经济学观点引入RMGs不确定性集设计，解决了现有集合定义不现实的问题。
- **重大突破**：提供了第一个打破多智能体诅咒的RMGs算法，样本复杂度与智能体数量成线性关系（而非指数），极大提升可扩展性。
- **技术巧妙**：利用对偶性简化鲁棒Q函数计算，结合自适应采样和FTRL处理非线性鲁棒目标，设计方差奖励项控制统计误差。
- **完整性**：同时给出上界与信息论下界（且下界匹配核心参数），证明了方法在理论上的接近最优性。

## 8. 不足与局限

- **缺乏实验验证**：没有在标准多智能体环境（如MAMuJuCo、StarCraft II等）中测试算法实际性能，仅依赖理论样本复杂度上界，读者可能质疑其实用性。
- **生成模型假设较强**：假设能任意从名义转移核采样（即simulator），但在许多实际场景中可能无法满足。
- **TV距离局限性**：仅考虑TV距离作为不确定性度量，而其他常用度量（KL、χ²、Wasserstein等）未被分析。
- **样本复杂度阶次较高**：相比标准MARL中CCE的`\widetilde{O}(H^4 S \sum A_i / \varepsilon^2)`，本文的复杂度（`H^6 / \varepsilon^4`）在H和ε上更高，可能在实际中不够高效。
- **仅关注CCE**：未提供学习NE的算法，NE的样本复杂度可能仍需指数级样本（如现有工作所示），限制了在竞争环境中的应用。
- **场景抽象**：论文假设有限状态、离散动作、有限步长，连续场景、函数近似等情况未涉及。

（完）
