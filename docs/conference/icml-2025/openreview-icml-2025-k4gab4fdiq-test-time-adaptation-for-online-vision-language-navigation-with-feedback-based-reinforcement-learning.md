---
title: Test-Time Adaptation for Online Vision-Language Navigation with Feedback-based Reinforcement Learning
title_zh: 基于反馈强化学习的在线视觉语言导航测试时自适应
authors: "Sungjune Kim, Gyeongrok Oh, Heeju Ko, Daehyun Ji, Dongwook Lee, Byung-Jun Lee, Sujin Jang, Sangpil Kim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=K4GaB4fdIq"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 基于反馈强化学习的视觉语言导航
tldr: 该论文提出FeedTTA框架，用于在线视觉语言导航的测试时自适应。方法利用反馈强化学习最大化二元情节反馈，使智能体能够在部署时适应陌生环境。实验表明，该方法在灵活性、交互性和稳定性方面显著优于基线，推进了机器人导航中的测试时自适应研究。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 880, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1741, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 755, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1724, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 865, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1539, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 724, \"height\": 109, \"label\": \"Table\"}]"
motivation: 视觉语言导航智能体在部署时面临陌生环境，需要有效的测试时自适应方法。
method: 提出FeedTTA框架，利用反馈强化学习最大化二元情节反馈来实现自适应。
result: 在多个VLN基准上，FeedTTA显著提升了导航成功率与适应性。
conclusion: 该工作为机器人导航中的在线测试时自适应提供了有效方案。
---

## Abstract
Navigating in an unfamiliar environment during deployment poses a critical challenge for a vision-language navigation (VLN) agent. Yet, test-time adaptation (TTA) remains relatively underexplored in robotic navigation, leading us to the fundamental question: what are the key properties of TTA for online VLN? In our view, effective adaptation requires three qualities: 1) flexibility in handling different navigation outcomes, 2) interactivity with external environment, and 3) maintaining a harmony between plasticity and stability. To address this, we introduce FeedTTA, a novel TTA framework for online VLN utilizing feedback-based reinforcement learning. Specifically, FeedTTA learns by maximizing binary episodic feedback, a practical setup in which the agent receives a binary scalar after each episode that indicates the success or failure of the navigation. Additionally, we propose a gradient regularization technique that leverages the binary structure of FeedTTA to achieve a balance between plasticity and stability during adaptation. Our extensive experiments on challenging VLN benchmarks demonstrate the superior adaptability of FeedTTA, even outperforming the state-of-the-art offline training methods in REVERIE benchmark with a single stream of learning.

---

## 论文详细总结（自动生成）

# 基于反馈强化学习的在线视觉语言导航测试时自适应

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：视觉语言导航（VLN）智能体在部署时面临训练环境与测试环境的分布偏移，导致性能下降。现有测试时自适应（TTA）方法（如熵最小化）存在三个关键缺陷：
  - **灵活性不足**：适应过程无法根据导航结果（成功/失败）动态调整，易在失败路径上过拟合。
  - **缺乏交互性**：未利用外部反馈信号（如用户或AI系统的简单判断），限制了自适应能力。
  - **可塑性与稳定性失衡**：适应新信息时容易灾难性遗忘先前知识。
- **整体含义**：本文旨在设计一种满足灵活性、交互性、可塑性与稳定性三者平衡的在线TTA方法，使VLN智能体能够低成本、高效地适应陌生环境，提升实际部署的可靠性。

## 2. 方法论

### 2.1 核心思想：反馈强化学习（Feedback-based RL）

- 采用**二元情节反馈**：在每个导航情节结束后，Oracle（人类或AI系统）提供一个二元标量（+1表示成功，-1表示失败）。
- 基于REINFORCE算法优化策略参数 \(\theta\)，最大化累积反馈的期望：
  \[
  J(\theta) = \mathbb{E}_{\tau \sim \pi_\theta}\left[\sum_{t=0}^{T-1} \gamma^{T-t-1} F\right]
  \]
  其中 \(F \in \{+1, -1\}\) 为情节反馈，\(\gamma\) 为折扣因子。
- 策略梯度近似公式：
  \[
  \nabla_\theta J(\theta) \approx \mathbb{E}_{a_t,s_t\sim\tau}\left[\sum_{t=0}^{T-1} \nabla_\theta \log \pi_\theta(a_t|s_t) \gamma^{T-t-1} F\right]
  \]

### 2.2 关键技术：随机梯度反转（Stochastic Gradient Reversion, SGR）

- **动机**：二元反馈导致梯度指向极端方向（+1或-1），引入非平稳性，损害可塑性与稳定性。
- **算法流程**：  
  1. 计算完整策略梯度 \(\nabla_\theta J(\theta)\)。  
  2. 以概率 \(p\)（伯努利采样）随机选择参数子集 \(G \subseteq \nabla_\theta J(\theta)\)。  
  3. 对选中维度乘以**负系数** \(\alpha < 0\) 实现反转，未选中维度按比例缩放以保持期望不变：  
     \[
     g'_{\theta_m} = 
     \begin{cases}
     \alpha g_{\theta_m}, & \text{if } g_{\theta_m} \in G \\
     \frac{1}{\alpha p + (1-p)} g_{\theta_m}, & \text{if } g_{\theta_m} \notin G
     \end{cases}
     \]
  4. 使用修正梯度进行参数更新：\(\theta_{n+1} \leftarrow \theta_n + \eta \nabla J(\theta)'\)。
- **作用**：模拟反事实场景，平滑梯度分布，降低期望绝对梯度值，从而平衡可塑性与稳定性，缓解灾难性遗忘。

## 3. 实验设计

### 3.1 数据集与基准

- **REVERIE**：目标导向任务，需远程定位物体并选择正确边界框。
- **R2R**：细粒度导航指令任务，要求停止在目标点3米内。
- **R2R-CE**：R2R的连续环境变体。

### 3.2 对比方法

- **离线训练基线**：HAMT、DUET、BEVBert、EPTNav、VLN⟳BERT、HOP+、KERM、NaviLLM、VLN-VER等。
- **TTA基线**：Tent（熵最小化）、FSTTA（专门为VLN设计的TTA方法），均进行复现（标记†）。
- **自身变体**：FeedTTA w/o reg.、w/ GD（梯度丢弃，α=0）、w/ GS（梯度缩放，α>0）、w/ SGR（本文方法，α<0）。

### 3.3 评估指标

- **经典指标**：轨迹长度（TL）、导航误差（NE）、成功率（SR）、Oracle成功率（OSR）、成功路径加权长度（SPL）、远程定位成功率（RGS）、远程定位成功路径加权长度（RGSPL）。
- **新指标**：自适应成功率（ASR）——同时衡量保持成功率（PSR，原有成功样本保持成功）和转换成功率（CSR，原有失败样本转为成功），综合评估可塑性与稳定性。

## 4. 资源与算力

- **GPU**：所有实验在单个 NVIDIA Tesla A100 GPU 上运行。
- **效率**：论文指出FeedTTA不要求高端服务器级GPU，可在GTX 1080等实际硬件上高效部署。
- **推理时间**：DUET + FeedTTA 每4个情节平均推理时间384.2ms（略高于基线DUET的85.4ms，但显著低于FSTTA的460.1ms），表明额外计算开销可接受。

## 5. 实验数量与充分性

- **主要结果实验**：在REVERIE、R2R、R2R-CE三个数据集上，比较FeedTTA与多种离线/在线方法，涵盖了Val Seen、Val Unseen、Test Unseen三个数据划分。
- **消融与敏感性实验**：
  - SGR不同α值对比（GD/GS/SGR）。  
  - 反馈精度（50%~100%）、反馈数量（前K%样本）、更新间隔（1~100次迭代）。  
  - LLM作为Oracle的可行性（GPT-4o vs GPT-4o-mini）。  
  - 序列顺序影响（通用TTA、连续TTA、逐场景TTA）。  
  - 跨任务TTA（REVERIE→R2R和R2R→REVERIE）。  
  - 轨迹长度分析（按真实TL分箱）。  
  - 权重幅度与塑性分析。  
  - 灾难性遗忘测试（在Val Seen上验证TTA后性能）。  
- **充分性评价**：实验设计全面，覆盖性能、鲁棒性、可塑性、稳定性、跨任务泛化等维度，且多次运行报告均值和标准差（如表8-10），结果客观可靠。

## 6. 主要结论与发现

- **核心结论**：FeedTTA通过二元情节反馈强化学习，显著提升了在线VLN的自适应能力，在REVERIE上甚至超越了当时最先进的离线训练方法。
- **关键发现**：
  - SGR通过梯度反转有效缓解非平稳性，优于梯度丢弃或简单缩放；在ASR指标上表现出最佳的平衡（CSR提升14%以上）。
  - 反馈精度不低于50%时，FeedTTA即可超越基线，对噪声具有鲁棒性；仅需约20%的反馈样本即可显著提升性能。
  - LLM作为Oracle（GPT-4o）可达到72%的反馈准确率，是人工反馈的可行替代方案。
  - FeedTTA在细粒度指令（R2R）上提升幅度小于目标导向任务（REVERIE），源于二元反馈相对于密集指导的稀疏性。
  - 轨迹长度增加主要来自“失败→成功”的转换样例，表明是必要的探索而非低效。

## 7. 优点

- **方法简洁实用**：仅需情节末的二元反馈（成功/失败），交互成本极低，适合真实部署。
- **创新性技术**：SGR针对二元反馈的非平稳性设计，利用反事实推理调节梯度分布，概念新颖且有效。
- **实验全面**：覆盖多个基准、多种评估指标、大量消融和敏感性分析，并设计了ASR指标专门衡量样本级转换能力。
- **公平对比**：对基线方法复现（标记†），保证比较的公平性。
- **计算效率**：推理开销可控，且支持低端GPU。

## 8. 不足与局限

- **LLM Oracle可靠性**：虽然LLM可行，但准确率（72%）仍低于人工，且存在推理成本与延迟，安全应用需谨慎。
- **跨任务适应性有限**：在R2R上的提升小于REVERIE，且跨任务（如R2R→REVERIE）时RGSPL几乎无改善，表明二元反馈对密集指令任务的适应效果有限。
- **轨迹长度增加**：部分成功案例的轨迹更长，可能不适合对路径效率有严格要求的场景。
- **实验覆盖**：未在更多样化的场景（如动态障碍物、开放世界）或真实机器人平台上验证；未讨论多智能体协作或更复杂反馈形式。
- **超参数敏感性**：SGR的 \(p\) 和 \(\alpha\) 需针对不同任务调优（如REVERIE用 \(p=0.05, \alpha=-0.2\)；R2R用 \(p=0.05, \alpha=0.1\)），泛化性需进一步验证。

（完）
