---
title: Enhancing Rating-Based Reinforcement Learning to Effectively Leverage Feedback from Large Vision-Language Models
title_zh: 增强基于评分的强化学习以有效利用大视觉语言模型的反馈
authors: "Tung Minh Luu, Younghwan Lee, Donghoon Lee, Sunho Kim, Min Jun Kim, Chang D. Yoo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=k77bq8AJVy"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 利用大视觉语言模型反馈进行强化学习奖励学习
tldr: 论文提出ERL-VLM方法，利用大视觉语言模型提供的评分反馈来学习奖励函数，避免人工标注。与依赖成对比较的方法不同，ERL-VLM通过评分直接拟合奖励，实验表明在多个任务上有效提升强化学习性能，为自动化奖励设计提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1769, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1679, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1680, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1087, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1754, \"height\": 156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1277, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1282, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1281, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1626, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1777, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1477, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1479, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 200, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 200, \"height\": 202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 199, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 199, \"height\": 197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 199, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 199, \"height\": 204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 200, \"height\": 199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1663, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1666, \"height\": 152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1036, \"height\": 164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1670, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1658, \"height\": 213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1219, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1546, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1545, \"height\": 123, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1130, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1783, \"height\": 2019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k77bq8ajvy/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1615, \"height\": 2285, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 1012, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 780, \"height\": 756, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 957, \"height\": 887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 797, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1748, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1749, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1750, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1749, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k77bq8ajvy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1749, \"height\": 268, \"label\": \"Table\"}]"
motivation: 人工设计奖励函数困难且昂贵，需要利用大模型自动生成反馈。
method: 引入基于评分的强化学习方法，直接从VLM评分中学习奖励函数。
result: ERL-VLM在多个环境中成功学习到有效奖励，性能超越基线。
conclusion: 利用VLM评分的RL方法可显著降低人工成本，拓展应用范围。
---

## Abstract
Designing effective reward functions remains a fundamental challenge in reinforcement learning (RL), as it often requires extensive human effort and domain expertise. While RL from human feedback has been successful in aligning agents with human intent, acquiring high-quality feedback is costly and labor-intensive, limiting its scalability. Recent advancements in foundation models present a promising alternative--leveraging AI-generated feedback to reduce reliance on human supervision in reward learning. Building on this paradigm, we introduce ERL-VLM, an enhanced rating-based RL method that effectively learns reward functions from AI feedback. Unlike prior methods that rely on pairwise comparisons, ERL-VLM queries large vision-language models (VLMs) for absolute ratings of individual trajectories, enabling more expressive feedback and improved sample efficiency. Additionally, we propose key enhancements to rating-based RL, addressing instability issues caused by data imbalance and noisy labels. Through extensive experiments across both low-level and high-level control tasks, we demonstrate that ERL-VLM significantly outperforms existing VLM-based reward generation methods. Our results demonstrate the potential of AI feedback for scaling RL with minimal human intervention, paving the way for more autonomous and efficient reward learning.

---

## 论文详细总结（自动生成）

# 论文总结：Enhancing Rating-Based Reinforcement Learning to Effectively Leverage Feedback from Large Vision-Language Models

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在强化学习（RL）中，奖励函数的设计通常需要大量人工努力和领域专业知识，这是RL应用扩展的主要瓶颈。虽然基于人类反馈的RL（RLHF）在将智能体行为与人类意图对齐方面取得了成功，但获取高质量的人类反馈成本高昂且劳动密集，难以规模化。
- **背景动机**：近年来的视觉-语言模型（VLMs）展现出强大的视觉理解与推理能力，能够替代人类提供反馈。已有工作（如RL-VLM-F）利用VLM进行成对轨迹偏好比较来学习奖励，但存在以下缺点：
  - 单次偏好信息量少，导致样本效率低；
  - 输入两个轨迹的token数加倍，计算成本高；
  - 当轨迹质量相近时，VLM容易产生无效偏好或幻觉。
- **整体含义**：论文旨在提出一种更高效、更鲁棒的方法，利用VLM提供的绝对评分（rating）而非成对比较来学习奖励函数，从而减少对人类反馈的依赖，实现更自主的奖励学习。

## 2. 方法论

- **核心思想**：ERL-VLM（Enhanced Rating-based RL from VLMs）通过查询大型VLM（如Gemini）对单个轨迹段进行绝对评分（如Likert量表：“very bad”, “bad”, “ok”, “good”, “very good”），并将这些评分作为监督信号训练奖励模型ˆr_ψ，再基于学到的奖励函数进行策略优化。
- **关键技术细节**：
  1. **VLM评分生成**：采用两阶段提示：（1）分析阶段：要求VLM分析轨迹段中的图像序列和动作（如有），理解智能体行为；（2）评分阶段：基于分析结果在离散评分类别中打分。对于复杂任务，使用多帧轨迹段以提供更丰富的上下文。
  2. **奖励学习**：基于Rating-based RL框架（White et al., 2024），将轨迹段的累积回报映射到评分类别概率分布。使用一个概率模型计算每个评分类别的概率，然后最小化损失函数。
  3. **关键改进**：
     - **分层采样（Stratified Sampling）**：确保每个训练批次包含所有评分类别的样本，缓解数据不平衡（早期“bad”占多数）。
     - **加权损失**：根据各类别样本频率分配权重，进一步平衡分布。
     - **平均绝对误差损失（MAE）**：替代原始的交叉熵损失，因为MAE对噪声标签更鲁棒，可有效应对VLM评分中的标签噪声。
  4. **算法流程**（文字说明）：
     - 初始化策略π_θ、奖励模型ˆr_ψ、经验回放缓冲B、评分数据集D。
     - 在每个迭代中：
       - 数据收集：智能体与环境交互T步，将经验(s,a,s',ˆr)存入B。
       - 每隔K步：从B中随机采样N个轨迹段，查询VLM获取评分˜y，存入D。
       - 奖励学习：使用分层采样从D中取小批量，通过MAE损失更新ˆr_ψ。
       - 使用更新后的ˆr_ψ重新标注B中所有经验。
       - 策略学习：从B中采样，使用任意off-policy RL算法（本文使用SAC或IQL）更新π_θ。
- **公式说明**：论文使用概率模型P_σ(i) = exp(-(R̃(σ)-R̄_i)(R̃(σ)-R̄_{i+1})) / Σ...，其中R̃是归一化累积回报，R̄_i是评分类边界。损失为L_MAE = E_{σ,˜y}[ Σ_i |μ_σ(i)-P_σ(i)| ]，其中μ_σ(i)为指示函数。

## 3. 实验设计

- **数据集/场景**：
  - **MetaWorld（低层连续控制）**：三个任务：Sweep Into（扫绿球入洞）、Drawer Open（拉抽屉）、Soccer（踢球入球门）。
  - **ALFRED（高层视觉-语言导航）**：20个任务，来自10个厨房场景，包含4种类型：PickupObject、PutObject、CoolObject、CleanObject。使用众包语言指令。
  - **真实机器人**：7-DOF Rethink Sawyer机器人，三个桌面任务：Sweep Bowl、Drawer Open、Pickup Banana。
- **Benchmark**：任务成功率（success rate）。MetaWorld每10个episode评估一次，ALFRED每100个episode。
- **对比方法**：
  - CLIP Score：在CLIP嵌入空间中计算当前图像与任务描述之间的余弦相似度作为奖励。
  - RoboCLIP Score：基于S3D嵌入的视频-文本相似度。
  - RL-VLM-F：利用VLM进行成对偏好比较学习奖励（原方法）。
  - Environment Reward：使用环境提供的真实奖励（MetaWorld中稠密，ALFRED中稀疏）。
  - 对于真实机器人，额外对比Behavior Cloning（BC）和Sparse Rewards。

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。仅在超参数表中列出了批大小、学习率、迭代步数等，但未提及硬件配置。作者提到代码已开源，但未量化计算开销。

## 5. 实验数量与充分性

- **实验数量**：涵盖三大类环境（模拟的MetaWorld和ALFRED，以及真实机器人），共7个模拟环境任务 + 3个真实任务。每种方法重复3次独立实验，报告均值和标准差。
- **消融实验**：
  - 对MetaWorld的三个任务进行了消融，分别移除MAE损失、移除分层采样、以及使用原始的Vanilla RbRL（无任何增强）。
  - 研究了不同评分等级数n（2, 3, 4）的影响。
  - 对比了MAE与标签平滑（label smoothing）处理噪声的效果。
  - 额外在RL-VLM-F中尝试加入MAE损失，以分析噪声处理对偏好方法的贡献。
- **公平性**：所有方法使用相同的策略训练超参数，唯一的区别是奖励函数。VLM查询预算一致（MetaWorld 10000个，ALFRED 1500个）。对于RL-VLM-F，使用相同VLM（Gemini-1.5-Pro）进行偏好比较，确保对比公平。
- **充分性**：实验较为充分，既包含低层连续控制也包含高层离散控制，还有真实机器人验证。消融实验覆盖了关键设计选择。但缺失对大规模任务或不同VLM型号的泛化性测试，也未分析计算开销的定量比较。

## 6. 主要结论与发现

- ERL-VLM在6/7的模拟任务上优于所有基线，尤其在ALFRED的复杂语言导航任务上表现突出，显著超过RL-VLM-F和CLIP/ RoboCLIP。
- 绝对评分比成对偏好在每个查询中提供更多信息，样本效率更高：在有限查询预算下（ALFRED每任务仅75个样本），ERL-VLM仍能学出有效奖励，而RL-VLM-F几乎失败。
- 对于PickupObject和PutObject，ERL-VLM甚至超过了稀疏环境奖励，说明学到的奖励能提供更好的塑造信号（shaping signal）。
- 提出的三项增强（分层采样、加权损失、MAE损失）均在消融中显示正贡献，其中MAE损失提升最大。
- 真实机器人实验表明ERL-VLM能够有效将VLM评分迁移到离线策略学习，优于BC和稀疏奖励。
- 评分等级数n的选择需要根据任务特性调整：二分类适合二元判断任务（如Sweep Into），三分类更适合主观性强任务（如Drawer Open）。

## 7. 优点

- **创新性**：提出了基于绝对评分的VLM反馈框架，相比偏好比较更高效、信息更丰富，并设计了针对数据不平衡和标签噪声的增强机制。
- **实用性**：仅需语言任务描述和图像观测，无需特权状态信息或环境代码，适用于多种真实场景。
- **鲁棒性**：MAE损失和分层采样有效缓解了VLM评分中的噪声问题，实验显示模型训练更稳定。
- **实验完整性**：覆盖模拟和真实环境，包含低层和高层控制，消融实验全面，对比方法合理。
- **开源**：代码公开，促进可复现性。

## 8. 不足与局限

- **依赖VLM的固有偏见**：VLM可能继承训练数据中的偏见，导致奖励函数存在偏差，影响智能体行为的安全性。
- **评分等级选择需手动调整**：不同任务需要尝试不同n值（2/3/4），缺乏自适应机制，可能增加应用成本。
- **提示工程依赖**：评分质量高度依赖提示设计中的分析阶段，对复杂或长时任务需要精心设计轨迹段长度和动作描述。
- **计算成本未量化**：虽然论文声称绝对评分更高效，但未具体对比两种方法的API调用次数、token消耗和实际时间成本，缺乏量化证据。
- **泛化性局限**：实验仅在机器人操作和导航任务上验证，未涉及其他领域（如游戏、自动驾驶等）。VLM仅使用了Gemini，未测试其他模型（如GPT-4V、LLaVA）的表现。
- **标签噪声假设**：论文假设VLM噪声大致均匀，但实际噪声分布可能更复杂，MAE的鲁棒性在非对称噪声下未验证。
- **未研究在线查询频率的影响**：查询频率K固定为5000 step（MetaWorld）或50 epoch（ALFRED），未分析不同频率对性能的影响。

（完）
