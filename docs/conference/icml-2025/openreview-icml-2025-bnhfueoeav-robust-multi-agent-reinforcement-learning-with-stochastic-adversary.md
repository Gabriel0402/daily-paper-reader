---
title: Robust Multi-Agent Reinforcement Learning with Stochastic Adversary
title_zh: 带随机对手的鲁棒多智能体强化学习
authors: "Ziyuan Zhou, Guanjun Liu, Mengchu Zhou, Weiran Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bnhFueOeav"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 多智能体强化学习中的对抗训练
tldr: 论文针对多智能体强化学习对观测扰动敏感的问题，提出ATSA方法。ATSA包含随机指挥器和生成器，在线学习对抗扰动策略。与传统对抗训练不同，该方法能利用主体策略先验，避免过拟合。实验表明ATSA显著增强了多智能体系统在复杂环境中的鲁棒性和可靠性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 775, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bnhfueoeav/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 967, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1248, \"height\": 1005, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 1759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnhfueoeav/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 443, \"label\": \"Table\"}]"
motivation: 现有MARL模型对观测扰动敏感，且对抗训练容易过拟合，缺乏策略先验。
method: 提出随机对手（SDor和STor）与主体智能体在线联合训练，引入策略先验。
result: ATSA在多个基准环境上提升了抗干扰能力，优于现有对抗训练方法。
conclusion: 引入了策略先验的随机对手训练是提升MARL鲁棒性的有效方法。
---

## Abstract
The performance of models trained by Multi-Agent Reinforcement Learning (MARL) is sensitive to perturbations in observations, lowering their trustworthiness in complex environments. Adversarial training is a valuable approach to enhance their performance robustness. However, existing methods often overfit to adversarial perturbations of observations and fail to incorporate prior information about the policy adopted by their protagonist agent, i.e., the primary one being trained. To address this important issue, this paper introduces Adversarial Training with Stochastic Adversary (ATSA), where the proposed adversary is trained online alongside the protagonist agent. The former consists of Stochastic Director (SDor) and SDor-guided generaTor (STor). SDor performs policy perturbations by minimizing the expected team reward of protagonists and maximizing the entropy of its policy, while STor generates adversarial perturbations of observations by following SDor's guidance. We prove that SDor's soft policy converges to a global optimum according to factorized maximum-entropy MARL and leads to the optimal adversary. This paper also introduces an SDor-STor loss function to quantify the difference between a) perturbations in the agent's policy and b) those advised by SDor. We evaluate our ATSA on StarCraft II tasks and autonomous driving scenarios, demonstrating that a) it is robust against diverse perturbations of observations while maintaining outstanding performance in perturbation-free environments, and b) it outperforms the state-of-the-art methods.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：多智能体强化学习（MARL）模型对观测中的扰动非常敏感，这降低了其在复杂环境中的可信度。现有对抗训练方法虽然能提升鲁棒性，但存在两个关键缺陷：一是容易过拟合到特定对抗扰动，导致在干净环境下性能下降；二是未能利用主体智能体（protagonist agent）本身的策略先验信息。
- **研究背景**：深度强化学习依赖独立同分布假设，而现实环境往往是动态和带噪声的，导致模型在遇到不同数据分布时性能退化。在MARL中，这一鲁棒性问题更为突出，尤其在自动驾驶、推荐系统等安全关键应用中。
- **整体目标**：提出一种新的对抗训练框架ATSA，通过引入随机对手并利用主体策略先验，同时提升模型在扰动环境和干净环境下的表现，避免过拟合，增强泛化鲁棒性。

### 2. 方法论

- **核心思想**：ATSA框架包含两个关键组件：
  1. **随机指挥器（Stochastic Director, SDor）**：在线训练，负责产生策略扰动建议。其目标是**最小化主体智能体的期望团队奖励**，同时**最大化自身策略熵**，以鼓励探索并避免过拟合。
  2. **SDor引导的生成器（SDor-guided generaTor, STor）**：根据SDor的建议，生成具体的观测对抗扰动。
- **关键技术细节**：
  - **SDor的学习**：基于分解的最大熵MARL框架，将PD-POMDP（策略对抗Dec-POMDP）转化为一个带熵正则化的最优控制问题。SDor的软策略（soft policy）通过因子化软策略迭代（factorized soft policy iteration）交替评估和改进，最终收敛到全局最优。
  - **STor的生成**：给定SDor的建议策略，STor通过最小化KL散度（实际使用FGSM方法近似求解）来寻找能使主体策略最接近SDor意图的观测扰动。
  - **SDor-STor损失函数**：引入一个新的损失项（交叉熵），量化STor生成的扰动导致的主体策略变化与SDor建议的策略变化之间的差异，用于训练中调整SDor的策略，保证两者一致性。
- **公式与算法流程**（文字说明）：
  - SDor的目标函数：最大化熵正则化的累积奖励 \( J = \mathbb{E}[\sum (\hat{r} + \alpha H(h))] \)，其中 \(\hat{r}\) 是策略对抗奖励（主体奖励的负值），\(\alpha\) 控制熵权重。
  - SDor的最优软策略：\( h^*(\hat{a}|\tau) \propto \exp(\alpha^{-1} Q^*(\tau,\hat{a})) \)，其中 \(Q^*\) 是最优软Q函数。
  - STor的优化目标：最小化 \( D_{KL}(\pi_i(\cdot|\hat{o}_i,\tau) \parallel h_i(\cdot|o_i,\tau)) \)，并通过FGSM一步求解：\(\hat{o}_i = \text{clip}(o_i - \beta \text{sgn}(\nabla_{o_i} \text{Loss}))\)。
  - 联合训练：在SDor的个体策略优化中，加入SDor-STor损失项 \(L'(\phi_i) = J(\phi_i) + \kappa L(\phi_i)\)，其中 \(\kappa\) 控制一致性损失强度。

### 3. 实验设计

- **实验场景**：
  - **StarCraft Multi-Agent Challenge (SMAC)**：3个地图（3m, 3s_3z, 8m），每个地图有不同的智能体数量和对抗组合。
  - **Connected and Autonomous Vehicles (CAV)**：模拟高速公路匝道合并场景，3辆自动驾驶车与1-4辆人类驾驶车混合。
- **Benchmark方法**：
  - 基础MARL方法：VDN、QMIX（作为主体训练算法）。
  - 对比方法分为四类：
    - 无对抗训练：NoAdv（无扰动）、RN（随机噪声）。
    - 对抗训练：FGSM、ATLA（交替训练）、PAAD（策略对抗演员-导演）。
    - 鲁棒学习：PR（策略正则化）、PR-REP（重复正则化）、ERNIE（对抗正则化）。
    - 随机对手：RAP（对手种群）、ROMANCE-p/s（进化对抗生成）。
- **对抗扰动设定**：ℓ∞范数边界，SMAC中3m和3s_3z为0.25，8m为0.1；CAV中为0.05。
- **评价指标**：SMAC使用胜率（Win Rate, WR）；CAV使用累积奖励和碰撞率（Crash Rate, CR）。同时报告平均性能。

### 4. 资源与算力

- **文中未明确说明**：论文未提及所使用的GPU型号、数量、训练时间等具体算力信息。仅在附录G中简要分析了算法的时间复杂度（O(T(Dp1+Dp2+Dg1) + (T/TI)(Dg2+...+Dg6)），未给出实际硬件配置。

### 5. 实验数量与充分性

- **实验数量**：
  - SMAC：3个地图 + 2种基础算法（VDN, QMIX） ⇒ 6组主要实验。
  - CAV：1个场景 + 2种基础算法 ⇒ 2组主要实验。
  - 每个主实验中，主体模型（行）与对手（列）交叉评估，形成一个矩阵（表1和表2），每个单元格代表500个episodes的评估结果。
  - 额外进行消融实验（移除SDor-STor损失函数，图2）、攻击性能分析（图3）、不同扰动范围鲁棒性测试（图5，附录H.5）、连续动作空间初步实验（附录H.6，表5）。
- **充分性与公平性**：
  - 对比方法全面，覆盖了主流对抗训练与鲁棒学习方法。
  - 使用Wilcoxon秩和检验（p<0.05）标注统计显著性，增强了结论可靠性。
  - 消融实验验证了SDor-STor损失函数的作用，以及温度参数α的影响。
  - 扰动范围泛化测试证明了模型对不同攻击强度的鲁棒性。
  - 但连续动作空间实验仅用了MPE环境，且ATSA表现不如某些基线（如FACMAC下），说明其在该场景下仍有局限，论文也承认需进一步改进。

### 6. 主要结论与发现

- ATSA在SMAC和CAV上均取得了最高的平均胜率/奖励，且在42个统计对比中显著优于其他方法。
- ATSA在干净环境和随机噪声环境下性能几乎不降，解决了PAAD和FGSM等方法过拟合扰动的问题。
- 随机对手（随机策略）比确定性对手更有助于主体探索，从而提升鲁棒性。
- SDor-STor损失函数（κ>0）对于维持SDor与STor方向一致性至关重要，消融实验验证了其必要性。
- 理论上证明了SDor的软策略收敛到全局最优，并且最优SDor结合STor可以导出最优随机观测对手。

### 7. 优点

- **方法创新性**：首次将随机对手与主体策略先验信息结合到MARL对抗训练中，克服了以往方法过拟合和忽略策略信息的缺点。
- **理论完整性**：从最大熵框架出发，证明了SDor策略的收敛性与最优性，并建立了与最优观测对手之间的理论联系。
- **实验全面性**：覆盖了离散和连续动作空间（虽然连续场景有待加强），比较了11种基准方法，包含多个场景和评价指标，并进行了统计检验和消融分析。
- **实际应用价值**：在真实的自动驾驶模拟环境中验证了鲁棒性提升，表明方法具有部署潜力。

### 8. 不足与局限

- **算力信息缺失**：未报告训练所需的GPU资源、时间等，不利于其他研究者复现和比较资源开销。
- **连续动作空间表现有限**：在MPE的连续控制任务中，ATSA在FACMAC下并未明显优于基线，论文也承认处理连续动作和联合最优扰动存在困难，需要未来改进。
- **超参数敏感性**：κ和α需要根据环境调整，且文中未给出自动调节策略，可能影响在不同任务上的泛化使用。
- **实验场景有限**：SMAC和CAV虽具代表性，但未涵盖更多MARL标准测试（如Level-Based Foraging、物流调度等），通用性有待进一步验证。
- **计算效率**：SDor和STor两个额外网络增加了训练复杂度，文中对时间复杂度分析较粗略，未对比实际运行时间开销。

（完）
