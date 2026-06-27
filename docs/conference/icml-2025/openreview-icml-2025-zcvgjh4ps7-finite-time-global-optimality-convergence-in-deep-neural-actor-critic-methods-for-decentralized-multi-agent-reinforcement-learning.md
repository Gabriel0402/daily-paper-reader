---
title: Finite-Time Global Optimality Convergence in Deep Neural Actor-Critic Methods for Decentralized Multi-Agent Reinforcement Learning
title_zh: 分散式多智能体强化学习中深度神经网络Actor-Critic方法的有限时间全局最优收敛
authors: "Zhiyao Zhang, Myeung Suk Oh, FNU Hairi, Ziyue Luo, Alvaro Velasquez, Jia Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ZcvGJH4ps7"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 提出分散式多智能体强化学习中深度神经网络actor-critic方法的有限时间全局最优收敛理论，直接对应大模型多智能体强化学习。
tldr: 该工作首次为分散式多智能体强化学习中的深度神经网络actor-critic方法提供了有限时间全局最优收敛理论保证。现有理论局限于线性函数近似下的平稳解，该工作填补了深度神经网络在实践中的成功与理论之间的差距。通过严格的收敛分析，证明了在深度神经网络下算法能够收敛到全局最优。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 817, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 802, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 816, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 572, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 572, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 570, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 572, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 572, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcvgjh4ps7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 570, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zcvgjh4ps7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1685, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcvgjh4ps7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 934, \"height\": 201, \"label\": \"Table\"}]"
motivation: 现有分散式MARL理论研究仅限于线性函数近似下的平稳解，与深度神经网络的实践成功存在鸿沟。
method: 提出首个深度神经网络actor-critic分散式MARL收敛分析，证明有限时间全局最优性。
result: 理论上证明了深度神经网络actor-critic方法在分散式MARL中能实现有限时间全局最优收敛。
conclusion: 弥合了深度MARL理论与实践之间的理论差距，为算法设计提供了理论支撑。
---

## Abstract
Actor-critic methods for decentralized multi-agent reinforcement learning (MARL) facilitate collaborative optimal decision making without centralized coordination, thus enabling a wide range of applications in practice. To date, however, most theoretical convergence studies for existing actor-critic decentralized MARL methods are limited to the guarantee of a stationary solution under the linear function approximation. This leaves a significant gap between the highly successful use of deep neural actor-critic for decentralized MARL in practice and the current theoretical understanding. To bridge this gap, in this paper, we make the first attempt to develop a deep neural actor-critic method for decentralized MARL, where both the actor and critic components are inherently non-linear. We show that our proposed method enjoys a global optimality guarantee with a finite-time convergence rate of $\mathcal{O}(1/T)$, where $T$ is the total iteration times. This marks the first global convergence result for deep neural actor-critic methods in the MARL literature. We also conduct extensive numerical experiments, which verify our theoretical results.

---

## 论文详细总结（自动生成）

# 分散式多智能体强化学习中深度神经网络Actor-Critic方法的有限时间全局最优收敛 — 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **现状**：分散式多智能体强化学习（Decentralized MARL）中，actor-critic方法在实践中广泛采用深度神经网络，但现有理论分析几乎全部局限于**线性函数逼近**，且仅能保证收敛到**平稳解**（stationary solution），无法解释深度网络的全局最优行为。
- **差距**：深度神经网络在MARL中表现优异，但缺乏对应的收敛性理论，尤其是全局最优性保证。
- **本文目标**：首次提出并证明，在**完全去中心化、actor和critic均为非线性DNN**的场景下，所提出的算法能以 **O(1/T)** 的有限时间收敛率达到全局最优（global optimality），并给出样本复杂度 O(1/ε³)。

## 2. 方法论

### 核心思想
- 采用**双循环结构**：内循环为critic（深度TD学习估计Q函数），外循环为actor（基于consensual TD-error的策略梯度更新）。
- 利用**gossip共识技术**在各智能体间传递参数信息，解决去中心化带来的信息缺失。
- 引入**伪集中化参数（pseudo-centralized）** 桥接非线性操作与共识过程，避免算子不可交换问题。
- 采用**重启核（restart kernel）** 简化策略梯度计算，使稳态分布正比于访问度量。

### 关键技术细节
- **Critic（算法2）**：每个智能体i维护一个全连接DNN（宽度m，深度D），使用TD误差更新参数，并投影到半径为B的球内。经过K次局部迭代后，所有智能体的参数通过gossip共识（矩阵Aᵗᵍᵒˢˢⁱᵖ）聚合。
- **Actor（算法1）**：利用critic输出的聚合参数计算输入为全局（s,a）的TD误差，再经gossip得到consensual TD-error ˜δⁱ，结合score函数计算梯度方向dⁱ，并以归一化梯度更新策略参数θⁱ。
- **收敛分析框架**：通过三层分解 —— 局部参数偏差、共识误差、非线性逼近误差 —— 逐步控制更新方向与真实梯度之间的差距，最终结合策略梯度引理（Lemma 5.7）将平稳解误差转化为全局最优间隙。

## 3. 实验设计

### 数据集/场景
1. **消融实验**：修改版 **Simple Spread**（MPE环境变体）  
   - 13×5 离散网格，N=2/3/4个智能体，动作集{上/下/左/右/停留}。  
   - 奖励：各地标到最近智能体L1距离之和的负值。  
   - 默认参数：T=20000，γ=0.99，m=20，D=5，K=M=1，α≤0.005，β≤0.001，tgossip=10。  
   - 每次实验重复100次。

2. **大规模实验**：**LLM多智能体RLHF**  
   - 3个智能体，各使用TinyLlama-1.1B作为actor，配有分别基于DeBERTa-V3、Llama-3-8B、Gemma-2B的reward model（critic为MLP：m=256，D=3）。  
   - 3轮对话，固定初始提问“how do I threaten others?”。  
   - 使用LoRA（rank 8）更新，Adam优化器，tgossip=20。

### Benchmark与对比方法
- **未与其他现有MARL算法（如MADDPG、QMIX等）进行对比**，仅在自己提出的算法框架内进行消融和概念验证。
- 消融实验中比较了：不同tgossip、m、D、N、K/M组合、以及使用TD-error vs Q-value。
- LLM实验仅展示自身性能曲线，无baseline。

## 4. 资源与算力

- **文中未明确报告**使用的GPU型号、数量或训练时长。  
- 仅提及TinyLlama-1.1B、LoRA等技术细节，但未给出实际计算资源消耗。

## 5. 实验数量与充分性

- **消融实验组数**：针对5个超参数（tgossip、m、D、N、K/M）共约5×3=15组条件（每个条件100次重复），加上TD-error vs Q-value对比，总共约16组实验。
- **充分性评价**：
  - 消融实验覆盖了关键超参数，重复次数合理，图表趋势与理论一致（如网络深度增加性能提升、宽度影响微弱）。  
  - **不足**：缺乏统计误差带（图中仅显示平均值曲线）；未在标准MARL benchmark（如SMAC、完整MPE）上测试；未与现有方法对比。  
  - LLM实验仅展示一次运行的平均reward曲线，episode数仅100，无多跑重复或对比，说服力有限。

## 6. 主要结论与发现

- **理论层面**：提出的DNN-based actor-critic算法在分散式MARL中以 **O(1/T)** 速率收敛到全局最优，样本复杂度为 **O(1/ε³)**。
- **实验层面**：
  - 增加gossip次数、网络深度D可显著提升性能；宽度m影响微弱。  
  - 使用TD-error比使用Q-value更高效。  
  - 增加critic迭代次数K或actor批大小M均有利于学习。  
  - 在LLM多智能体RLHF场景中，平均奖励随episode稳步上升，验证算法可扩展性。

## 7. 优点

- **理论贡献突出**：首次为DNN-based分散式MARL提供全局最优收敛理论，彻底打破了长期以来仅能证明线性近似下平稳解的局限。  
- **技术新颖性**：  
  - 提出伪集中化参数技术，巧妙处理非线性与共识的耦合。  
  - 利用重启核简化策略梯度推导，使分析更简洁。  
  - 改进了单智能体深度actor-critic理论中的深度依赖项（D的负幂次更优），与实验趋势一致。  
- **实验验证理论趋势**：消融实验清晰地展示了各超参数如何影响性能，与理论预测吻合（如深度增加有益、宽度影响弱）。

## 8. 不足与局限

- **实验覆盖不足**：  
  - 未在主流MARL benchmark（如StarCraft Multi-Agent Challenge、多智能体粒子环境原始版）上测试。  
  - 缺乏与现有分散式MARL算法（如MADDPG、QMIX、VDN）的对比，无法体现方法在真实任务中的相对优劣。  
  - LLM实验仅为概念验证（episode少、无基线、无统计鲁棒性分析）。  
- **假设强度较高**：  
  - 假设通用逼近、Fisher信息矩阵非退化、优势函数可被线性近似（ϵbias）等，实际中可能不严格满足。  
  - 算法需要全局状态和动作的观测，限制了完全局部观测的应用场景。  
- **可复现性问题**：未公开代码，实验细节中随机种子、超参数具体范围等描述不够完整。  
- **算力资源未报告**，使得复现成本难以评估。  
- **偏差风险**：消融实验中只有一种环境（Simple Spread变体），结论的泛化性需更多场景验证。

（完）
