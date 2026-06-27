---
title: Enhancing Cooperative Multi-Agent Reinforcement Learning with State Modelling and Adversarial Exploration
title_zh: 通过状态建模与对抗性探索增强合作多智能体强化学习
authors: "Andreas Kontogiannis, Konstantinos Papathanasiou, Yi Shen, Giorgos Stamou, Michael M. Zavlanos, George Vouros"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TCsdlqzZNL"
tags: ["query:vlm-rl"]
score: 4.0
evidence: 合作多智能体强化学习中的状态建模
tldr: 该文提出一种面向合作多智能体强化学习的状态建模框架，智能体从局部观测推断信念表示，过滤冗余信息并增强探索与协作，实验表明该方法在部分可观察环境中显著提升合作效果。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1411, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1047, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1258, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 710, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 463, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 485, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 752, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 947, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1459, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 734, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1567, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1765, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 580, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 569, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 567, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1728, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 682, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 691, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tcsdlqzznl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1457, \"height\": 890, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 568, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1653, \"height\": 1026, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 532, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 1143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 744, \"height\": 1012, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tcsdlqzznl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 537, \"height\": 795, \"label\": \"Table\"}]"
motivation: 在分布式部分可观察无通信环境中，智能体难以推断全局状态并协同探索。
method: 提出状态建模框架，智能体从局部观测学习信念表示，并引入对抗性探索机制。
result: 在多个合作任务中取得更优的协作策略和探索效率。
conclusion: 有效的状态建模能显著提升部分可观察环境下的多智能体协作。
---

## Abstract
Learning to cooperate in distributed partially observable environments with no communication abilities poses significant challenges for multi-agent deep reinforcement learning (MARL). This paper addresses key concerns in this domain, focusing on inferring state representations from individual agent observations and leveraging these representations to enhance agents' exploration and collaborative task execution policies. To this end, we propose a novel state modelling framework for cooperative MARL, where agents infer meaningful belief representations of the non-observable state, with respect to optimizing their own policies, while filtering redundant and less informative joint state information. Building upon this framework, we propose the MARL SMPE$^2$ algorithm. In SMPE$^2$, agents enhance their own policy's discriminative abilities under partial observability, explicitly by incorporating their beliefs into the policy network, and implicitly by adopting an adversarial type of exploration policies which encourages agents to discover novel, high-value states while improving the discriminative abilities of others. Experimentally, we show that SMPE$^2$ outperforms a plethora of state-of-the-art MARL algorithms in complex fully cooperative tasks from the MPE, LBF, and RWARE benchmarks.

---

## 论文详细总结（自动生成）

# 论文总结：Enhancing Cooperative Multi-Agent Reinforcement Learning with State Modelling and Adversarial Exploration

## 1. 核心问题与整体含义

- **研究动机与背景**：在分布式、部分可观察且无通信能力的多智能体系统中，合作强化学习面临两大挑战：一是智能体无法直接观测全局状态，难以有效协调；二是在稀疏奖励环境下，智能体难以探索到高价值状态。现有方法（如对手建模）存在三个不足：(a) 推断的信念表示未针对优化策略进行学习；(b) 未过滤冗余的联合状态信息；(c) 未利用信念表示改进随机探索策略。本文旨在解决如何从局部观测推断有意义的全局状态表示，并利用这些表示提升探索与协作能力。
- **整体含义**：提出状态建模（State Modelling）框架，使智能体能学习到与自身策略优化相关的全局状态信念，并设计对抗性探索机制，在无通信条件下显著提升合作MARL的性能。

## 2. 方法论

- **核心思想**：
  - 构建状态建模优化框架，每个智能体根据自身观测$o_i$推断潜在信念$z_i$，该信念包含对非可观察状态的丰富信息，并过滤冗余特征。信念$z_i$用于增强策略网络的判别能力，即$\pi_{\psi_i}(a_i^t | h_i^t, z_i^t)$。
  - 提出SMPE$^2$算法，包含两个并发部分：
    1. **自监督状态建模**：使用变分自编码器（Encoder-Decoder）从$o_i$重建其他智能体的观测$\hat{o}_{-i}$，并通过可学习的AM过滤器$w_i$（对每个其他智能体的特征赋予重要性权重）过滤非信息性特征，引导$z_i$聚焦于有价值信息。损失函数包含重建损失、KL散度、$L_2$正则化和一个额外的批评网络（用于学习$w_i$与策略优化的关联）。
    2. **对抗式基于计数的内在探索**：对$z_i$使用SimHash函数进行计数，生成内在奖励$\hat{r}_i = 1 / \sqrt{n(\text{SH}(z_i))}$，激励智能体探索新颖观测（从而产生新颖$z_i$），同时这些新颖观测会“对抗性”地增加其他智能体重建模型的损失，帮助它们形成更好的信念。最终奖励为$\tilde{r}_i = r_i + \beta \hat{r}_i$。
- **关键技术细节**：
  - 使用MAA2C作为基础Actor-Critic算法，维护两个批评网络：标准批评$V_\xi$和基于过滤状态的批评$V_k$。
  - AM过滤器$w_i$通过sigmoid输出在[0,1]之间，并与目标批评配合学习。
  - 周期性硬更新编码器-解码器参数，稳定内在奖励。
- **算法流程**：每个时间步，智能体采样$z_i$，执行动作，存储转移；在并行回合结束后更新actor、两个critic；每隔$N_{ED}$步从回放缓冲区采样更新编码器-解码器和AM过滤器。

## 3. 实验设计

- **数据集/场景**：
  - **MPE**（Multiagent Particle Environment）：Spread（3,4,5,8智能体）和Double Speaker-Listener（2智能体）——密集奖励任务。
  - **LBF**（Level-Based Foraging）：6个稀疏奖励任务（如2s-9x9-3p-2f, 4s-11x11-3p-2f, 7s-20x20-5p-3f等），其中2s-11x11-3p-2f和4s-11x11-3p-2f被先前工作标记为“开放挑战”。
  - **RWARE**（Multi-Robot Warehouse）：3个硬任务（tiny-2ag-hard, tiny-4ag-hard, small-4ag-hard）——稀疏奖励、高部分可观察性。
- **对比方法**：
  - MPE：MAA2C, COMA, MAPPO, ATM（基于Transformer的工作记忆）。
  - LBF/RWARE：额外对比基于内在动机的SOTA方法：EOI（多样性探索）、EMC（好奇心驱动）、MASER（子目标生成），以及QMIX、SIDE、MLIAM（多智能体LIAM扩展）。
- **评价指标**：未归一化的平均回合奖励，报告6个随机种子的25-75%置信区间。总步数：MPE/LBF 10M，RWARE 40M。

## 4. 资源与算力

- 文中未明确说明使用的GPU型号、数量或总训练时长。仅附录表2提供了在LBF 2s-12x12-2p-2f任务上各方法的运行时间比较（CPU和GPU规格：RTX 3080ti, i9-11900, 64GB RAM），其中SMPE$^2$运行时间为1h13m，快于EOI（17h）、EMC（1d5h）、MASER（1d1h），与MAA2C（37m）和COMA（54m）相比稍慢但可接受。其他任务的详细算力消耗未报告。

## 5. 实验数量与充分性

- **实验数量**：在3个基准（MPE, LBF, RWARE）上共评估了约10余个具体任务（包括不同规模），每个任务使用6个随机种子。进行了大量消融实验（图5、图6、附录多个小节），包括：移除内在奖励、移除AM过滤器、移除$L_{KL}$、移除$L_{norm}$、替换为标准SimHash、移除第二个批评网络、调节超参数$\lambda_{rec}$、$\lambda_{norm}$等。还测试了将SMPE$^2$与MAPPO结合（SMPE PPO）以验证灵活性。
- **充分性**：实验充分且设计公平。对比方法包括多样化SOTA（基于值分解、Actor-Critic、内在动机、Transformer等），覆盖了密集和稀疏奖励场景。消融实验系统地验证了各组件的必要性。但未在更大规模或随机性更强的环境中测试，且未提供统计显著性检验（如t检验）。部分LBF任务中对比方法（如EMC、MASER）表现极差，但作者解释了其原因（对初始策略依赖等），总体可信。

## 6. 主要结论与发现

- SMPE$^2$在MPE的Spread（尤其大规模）和Double Speaker-Listener上显著优于所有对比方法，证明状态建模能提升部分可观察性下的判别能力。
- 在LBF和RWARE的稀疏奖励任务中，SMPE$^2$大幅超越SOTA方法，成功解决了多个先前被标记为“开放挑战”的任务，得益于对抗性探索机制与状态建模的协同。
- 消融实验表明：AM过滤器、$L_{KL}$、$L_{norm}$、基于$z_i$的内在奖励、第二个批评网络（针对策略优化学习$w_i$）均不可或缺；直接使用观测哈希（标准SimHash）替换内在奖励会严重退化性能。
- t-SNE可视化显示，加入$L_{KL}$后智能体的信念表示更紧凑且具有一致性，定量分析（逻辑回归准确率57.5% vs 无KL时99.3%）证实了该观点。
- SMPE$^2$可灵活适配不同骨干算法（如MAPPO），进一步提升骨干性能。

## 7. 优点

- **方法论创新**：提出状态建模优化框架，将信念学习与策略优化直接关联（第二个批评网络），避免传统对手建模的分布不匹配问题；AM过滤器有效过滤冗余信息；对抗性探索机制将个体探索与改善他智能体信念相耦合。
- **实验扎实**：在3个广泛使用的基准上包含多种任务规模和难度，消融实验完整，对比方法全面且包括近年SOTA（如EOI、EMC、MASER、ATM）。
- **可复现性**：代码开源（GitHub链接），超参数在附录中列出。
- **可扩展性**：能够与不同AC算法结合，展现出较好灵活性。

## 8. 不足与局限

- **实验覆盖**：未在随机动态更强（如噪声观测、随机转移）的环境中测试，也未在更大规模（如>10智能体）或连续动作空间场景中验证。仅使用离散动作环境。
- **资源报告不完整**：未明确说明训练所用的GPU型号、数量、总GPU小时等关键算力信息，影响复现难度。
- **统计验证**：未提供统计显著性检验（如置信区间重叠或p值），尽管6个种子提供一定可靠性，但部分对比中置信区间较大（如RWARE small-4ag-hard）。
- **潜在偏差风险**：内在奖励$\beta$在LBF和RWARE中使用不同值（0.1 vs 0.001），可能对结果有敏感影响，但作者仅在一个任务上进行了消融。
- **应用限制**：假设无通信通道且部分可观察，但训练时使用CTDE（集中式批评）需要全局状态，这在某些实际系统中可能不可行（如隐私限制）。此外，AM过滤器的训练依赖于其他智能体的观测，在训练时需要共享这些信息，可能违背某些去中心化训练要求。
- **方法复杂度**：相较于基础MAA2C，增加了编码器-解码器、AM过滤器、第二个批评网络和SimHash，参数更多，调参较复杂。

（完）
