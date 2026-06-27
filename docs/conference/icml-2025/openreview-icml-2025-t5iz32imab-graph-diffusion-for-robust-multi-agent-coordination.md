---
title: Graph Diffusion for Robust Multi-Agent Coordination
title_zh: 面向鲁棒多智能体协调的图扩散模型
authors: "Xianghua Zeng, Hang Su, Zhengyi Wang, Zhiyuan LIN"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=T5IZ32ImAB"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 图扩散模型用于多智能体协调
tldr: 针对离线多智能体强化学习中分布外估计和协调缺失问题，提出基于图扩散的MCGD框架。通过构建稀疏协调图并引入图扩散模型，有效建模多智能体协调动态，显著提升协作策略在动态环境中的鲁棒性和有效性。实验证明该方法在多个基准上优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 703, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 726, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-t5iz32imab/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 844, \"height\": 633, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1792, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 657, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 776, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1774, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-t5iz32imab/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 420, \"label\": \"Table\"}]"
motivation: 离线多智能体强化学习面临分布外状态估计和忽略协调动态的问题。
method: 提出MCGD框架，构建包含连续节点和离散边的稀疏协调图，利用图扩散模型增强协作策略。
result: 在动态环境下协作策略的有效性和鲁棒性得到显著提升。
conclusion: 图扩散模型能有效建模多智能体协调动态，提升策略鲁棒性。
---

## Abstract
Offline multi-agent reinforcement learning (MARL) struggles to estimate out-of-distribution states and actions due to the absence of real-time environmental feedback. While diffusion models show promise in addressing these challenges, their application primarily focuses on independently diffusing the historical trajectories of individual agents, neglecting crucial multi-agent coordination dynamics and reducing policy robustness in dynamic environments. In this paper, we propose MCGD, a novel Multi-agent Coordination framework based on Graph Diffusion models to improve the effectiveness and robustness of collaborative policies. Specifically, we begin by constructing a sparse coordination graph that includes continuous node attributes and discrete edge attributes to effectively identify the underlying dynamics of multi-agent interactions. Next, we derive transition probabilities between edge categories and present adaptive categorical diffusion to capture the structure diversity of multi-agent coordination. Leveraging this coordination structure, we define neighbor-dependent forward noise and develop anisotropic diffusion to enhance the action diversity of each agent. Extensive experiments across various multi-agent environments demonstrate that MCGD significantly outperforms existing state-of-the-art baselines in coordination performance and policy robustness in dynamic environments.

---

## 论文详细总结（自动生成）

# 论文《Graph Diffusion for Robust Multi-Agent Coordination》详细总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：离线多智能体强化学习（Offline MARL）由于无法与环境实时交互，面临严重的**分布外（OOD）状态与动作估计**问题。现有方法（包括基于扩散模型的MADIFF、DOM2等）通常**独立地对每个智能体的历史轨迹施加扩散过程**，忽略了智能体之间关键的**协调动态**（如协作关系变化、智能体突然失效等），导致策略在动态环境中鲁棒性不足。
- **整体含义**：如何显式建模多智能体之间的**协调结构**（包括哪些智能体需要合作、合作强度如何随环境变化），并利用图扩散模型同时捕捉**结构多样性**和**动作多样性**，是提升离线MARL策略有效性和鲁棒性的关键。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 提出**MCGD（Multi-agent Coordination via Graph Diffusion）** 框架，首次将**图扩散模型**用于离线多智能体协调。通过构建**稀疏协调图**（节点=智能体动作，边=是否协调），并分别对**离散边属性**（协调结构）和**连续节点属性**（智能体动作）设计专门的扩散过程，以同时建模协调结构的多样性和单个智能体动作的多样性。

### 关键技术细节
1. **稀疏协调图构建**  
   - 基于智能体观测的**余弦相似度**，为每个智能体选取k近邻作为边，形成k-NN图。节点属性为连续动作向量（或离散动作的one-hot），边属性为0/1（存在/不存在协调）。
2. **类别扩散（Categorical Diffusion）处理离散边**  
   - 利用观测相似性矩阵\(C\)计算**自适应转移矩阵**\(Q_t = e^{(C-D)t}\)（\(D\)为度矩阵），该矩阵满足对称性、可加性、局部性和收敛性（Theorem 4.1）。  
   - 对边属性\(E_t\)施加类别噪声：\(q(E_{t}^{k}|E_{t}^{k-1}) = \text{cat}(E_{t}^{k-1} Q_{\beta_k})\)，最终闭式形式为\(q(E_t^K|E_t) = \text{cat}(E_t Q_{\beta_K})\)。
3. **各向异性扩散（Anisotropic Diffusion）处理连续节点**  
   - 对每个智能体\(n_i\)，基于其邻居动作集合\(A_t^i\)计算**协方差矩阵**\(\Sigma_i\)，作为各向异性高斯噪声的协方差。  
   - 前向加噪：\(q(a_{i,k}|a_{i,k-1}) = \mathcal{N}(a_{i,k}; \sqrt{1-\beta_k}a_{i,k-1}, \beta_k \Sigma_i)\)，闭式形式：\(q(a_{i,K}|a_i) = \mathcal{N}(a_{i,K}; \sqrt{\alpha_K}a_i, (1-\alpha_K)\Sigma_i)\)。
4. **逆去噪过程（Reverse Denoising）**  
   - 使用**图Transformer网络**\(f_\theta\)从带噪图\(G_t^K\)预测干净的边属性\(\hat{E}_t^\theta\)和节点属性\(\hat{A}_t^\theta\)。  
   - 损失函数：  
     - 交叉熵损失\(\mathcal{L}_{ce}\)（预测边与真实边）。  
     - 各向异性扩散损失\(\mathcal{L}_{ad}\)：欧氏距离 + Q值正则（\(\lambda\)可调）。  
   - 训练时对邻居观测采用**均值池化**（避免参数暴涨），通过共享MLP处理。
5. **策略采样（Policy Sampling）**  
   - 在线执行时，每个智能体利用训练好的Q函数选择初始候选动作，构造全连接图作为扩散起点，逐步去噪得到最终动作。适用于离散/连续动作空间。

## 3. 实验设计

### 使用的基准与数据集
- **三个基准环境**：
  - **MPE**（Multi-Agent Particle Environments）：Spread、Tag、World（离线数据集来自Pan等，含Expert、Medium-Replay、Medium、Random等级）。
  - **MAMuJoCo**（Multi-Agent MuJoCo）：2halfcheetah、2ant、4ant（离线数据集来自Formanek等，含Good、Medium、Poor等级）。
  - **SMAC**（StarCraft Multi-Agent Challenge）：3m、2s3z、5m6m、8m（离线数据集同MAMuJoCo，含Good、Medium、Poor等级）。

### 对比方法
- **非扩散基线**：MA-ICQ、MA-CQL、OMAR（离线MARL方法）。
- **扩散基线**：MA-SfBC（单智能体扩散扩展）、DOM2、MADIFF（多智能体扩散方法）。

## 4. 资源与算力

- **文中明确说明**：所有实验在配置为**64核Intel Xeon Platinum 8336C CPU (2.30 GHz)** 和**NVIDIA A800-SXM4-80GB GPU**的Linux服务器上运行。
- **未明确说明的信息**：未给出**具体GPU数量、训练时长、总计算成本**（例如多少GPU小时）。附录提到使用Adam优化器、学习率2e-4、batch size 32、扩散步数K∈[50,200]，但无整体算力量化。

## 5. 实验数量与充分性

### 实验数量与覆盖
- **主实验结果**：Table 1（Expert/Good数据集，3个基准，共10个子任务），Table 2（4个环境下的动态变化实验，包括属性变化与协调结构变化）。
- **补充实验结果**：附录Table 7（MPE的Random/Medium-Replay/Medium等级）、Table 8（MAMuJoCo的Poor/Medium）、Table 9（SMAC的Poor/Medium）——覆盖了所有难度等级。
- **消融实验**：图6（Categorical Diffusion与Anisotropic Diffusion的独立消融）、表3（邻居观测处理方式对比：均值池化 vs 特征拼接）。
- **鲁棒性实验**：Table 2（在动态环境下的测试，包括属性变化与协调结构变化），图4-5（定性可视化轨迹与图结构）。
- **超参数敏感性**：图7（正则系数λ的影响）。
- **采样效率**：表6（MCGD与MADIFF不同智能体数量下的采样时间对比）。

### 充分性与公平性评价
- **充分性**：实验覆盖3个主流基准、多个难度等级、多种环境动态变化，对比了6种基线方法，并进行了消融和敏感性分析。实验设计较完整，验证了方法的有效性和鲁棒性。
- **公平性**：使用相同的数据集和评估协议（多次运行取平均值与标准差）。未发现明显偏向性设计。但未报告所有基线在相同硬件下的运行时间或收敛曲线，可能影响公平性陈述的完整性。

## 6. 主要结论与发现

- **性能提升显著**：在Expert/Good数据集的10个任务上，MCGD均取得**最高平均回报**，相比最强基线（MADIFF/DOM2）在MPE、MAMuJoCo、SMAC上分别提升**至少5.7%、6.5%、4.7%**；在动态变化环境下提升更明显（高达14.2%）。
- **鲁棒性优势突出**：在智能体属性改变或协调结构改变（如某个智能体失效）的场景下，MCGD仍能保持高性能，而基线方法大幅下降。
- **图解构适应性强**：定性可视化（图4-5）显示，MCGD能动态调整协调图结构（如孤立失效智能体、重新分配目标），验证了类别扩散的有效性。
- **消融证实模块贡献**：各向异性扩散和类别扩散均不可或缺，且均值池化优于特征拼接（性能更高、计算更优）。

## 7. 优点

- **方法创新性**：首次将**图扩散模型**引入离线多智能体协调，同时处理离散边（协调结构）和连续节点（动作），与之前独立扩散的单智能体视角不同。
- **协同建模全面**：通过**自适应转移矩阵**（基于观测相似性）和**各向异性噪声**（基于邻居动作分布），同时捕捉结构多样性与动作多样性，提升了政策灵活性和鲁棒性。
- **鲁棒性惊艳**：在动态环境（特别是协调结构突变）中的表现显著优于现有方法，体现出实用性。
- **实验扎实**：覆盖多难度、多环境、多维度评估（性能、鲁棒性、消融、敏感性、效率），证据链完整。
- **实现细节清晰**：提供算法伪代码、附录证明、超参数设置，可复现性好。

## 8. 不足与局限

- **算力资源未量化**：未报告训练所需的**GPU数量、总耗时、能耗**，不利于评估方法的实际部署成本。
- **现实验证缺失**：仅在仿真环境（MPE、MAMuJoCo、SMAC）测试，未在真实机器人或复杂物理场景中验证，声明“正在部署”但未包含定量数据。
- **图结构假设的局限性**：采用k-NN图（基于观测相似度）假设协调关系由观测相似性主导，可能不适用于某些任务（如需要非对称或层级协调的场景）。
- **扩展性讨论不足**：尽管附录表6显示采样时间与MADIFF接近，但未测试大规模智能体（如>64）下的训练稳定性与图构建开销。
- **基线对比细节缺失**：未报告各基线在相同随机种子下的**收敛曲线或方差分析**，仅给出最终平均回报，可能隐藏训练不稳定性。
- **超参数敏感性**：正则系数λ对性能影响较大（图7），但未提供自动化选择策略，需要人工调参。

---

（完）
