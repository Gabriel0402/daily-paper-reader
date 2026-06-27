---
title: "GROVE: A Generalized Reward for Learning Open-Vocabulary Physical Skill"
title_zh: GROVE：一种用于学习开放词汇物理技能的通用奖励框架
authors: "Cui, Jieming, Liu, Tengyu, Meng, Ziyu, Yu, Jiale, Song, Ran, Zhang, Wei, Zhu, Yixin, Huang, Siyuan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Cui_GROVE_A_Generalized_Reward_for_Learning_Open-Vocabulary_Physical_Skill_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 基于VLM的通用奖励函数用于物理技能学习
tldr: 强化学习在开放词汇物理技能学习中面临奖励设计耗时、示范泛化差的问题。GROVE提出利用大语言模型生成精确物理约束、视觉语言模型评估运动语义和自然性，自动构建通用奖励函数。实验证明该方法无需手工设计或示范即可学习多样化技能，显著提升泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1806, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 845, \"height\": 804, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1796, \"height\": 1543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 864, \"height\": 1128, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 448, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 791, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 875, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 698, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cui-grove-a-generalized-reward-for-learning-open-vocabulary-physical-skill-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 871, \"height\": 338, \"label\": \"Table\"}]"
motivation: 现有强化学习奖励设计依赖手工或示范，难以扩展到开放词汇物理技能学习任务。
method: 利用LLM和VLM的互补优势，LLM生成物理约束，VLM评估运动语义，自动构建通用奖励函数。
result: 无需手动工程或任务特定示范即可有效学习多样物理技能，泛化性能显著提升。
conclusion: GROVE框架为开放词汇物理技能学习提供了可扩展的奖励自动生成方案。
---

## Abstract
Learning open-vocabulary physical skills for simulated agents presents a significant challenge in artificial intelligence. Current reinforcement learning approaches face critical limitations: manually designed rewards lack scalability across diverse tasks, while demonstration-based methods struggle to generalize beyond their training distribution. We introduce GROVE, a generalized reward framework that enables open-vocabulary physical skill learning without manual engineering or task-specific demonstrations. Our key insight is that Large Language Models (LLMs) and Vision Language Models (VLMs) provide complementary guidance---LLMs generate precise physical constraints capturing task requirements, while VLMs evaluate motion semantics and naturalness. Through an iterative design process, VLM-based feedback continuously refines LLM-generated constraints, creating a self-improving reward system. To bridge the domain gap between simulation and natural images, we develop Pose2CLIP, a lightweight mapper that efficiently projects agent poses directly into semantic feature space without computationally expensive rendering. Extensive experiments across diverse embodiments and learning paradigms demonstrate GROVE's effectiveness, achieving 22.2% higher motion naturalness and 25.7% better task completion scores while training 8.4x faster than previous methods. These results establish a new foundation for scalable physical skill acquisition in simulated environments.

---

## 论文详细总结（自动生成）

# GROVE 论文深度总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：让仿真智能体从自然语言指令中学习开放词汇的物理技能，面临两大困境：传统强化学习依赖手工设计的奖励函数，难以扩展到多样任务；基于演示的方法泛化能力差，受限于训练数据分布。
- **研究动机**：当前LLM（大语言模型）和VLM（视觉语言模型）各有优劣——LLM擅长生成精确的物理约束（如关节位置、速度），但缺乏对运动整体自然性的评估；VLM擅长评估运动语义和自然性，但无法施加精确的物理约束。两者互补。
- **整体含义**：提出GROVE框架，融合LLM和VLM的互补优势，自动构建通用奖励函数，无需手工工程或任务特定演示，实现开放词汇物理技能的高效学习，推动可扩展的物理技能获取。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将LLM生成的精确物理约束与VLM提供的语义评估结合，形成正交的奖励信号：LLM约束缩小搜索空间到合理物理区域，VLM筛选出语义正确且自然的运动。
- **关键技术细节**：
    - **奖励函数组成**：`R_GROVE = ω_V * R_V + ω_L * R_L`，其中R_V为VLM语义评估奖励，R_L为LLM生成约束奖励。
    - **LLM奖励生成**：使用GPT-o1-preview，在提示中注入详细智能体描述（关节命名和索引），并引导模型聚焦任务本质，避免过度复杂化。
    - **VLM奖励**：采用冻结CLIP模型，但通过Pose2CLIP轻量映射器，将智能体姿态直接投影到CLIP特征空间，避免渲染开销并弥合仿真-真实域差距。
    - **Pose2CLIP**：两层MLP，训练数据来自AMASS和Motion-X的170万帧SMPL姿态，经Blender高质量渲染和五视角（前、侧、斜、后侧、后）渲染，提取CLIP-ViT-B/32图像特征，再通过平衡采样策略（k-means++聚类后分层均匀采样）训练。
    - **自适应拒绝采样策略（RDP）**：以VLM奖励作为适应度函数，当检测到连续8步R_V下降且平均值低于阈值0.1时，触发LLM奖励重生成，防止优化偏离语义正确方向。
    - **算法流程**：初始化策略和LLM奖励，训练中每步计算GROVE奖励，通过PPO更新策略；若适应度持续下降则重生成LLM奖励。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **数据集/场景**：
    - 开放词汇人形技能合成：使用CALM预训练的低层控制器，高层策略优化GROVE奖励；评估5种代表性指令（如“奔跑中跳栏”、“指挥交响乐”、“身体摆成C形”等）。
    - 标准RL基准：包括Cartpole平衡、Ant前向跑、ANYmal侧向走、ANYmal跳跃、Humanoid弯腰（指定角度），在IsaacGym中训练。
- **benchmark**：
    - 人形技能：计算指标包括平滑度、CLIP相似度；用户研究（30人）评估任务完成度、运动自然度、物理真实性（0-10分）。
    - 标准RL：使用奖励距离衡量学习效率，并有人工评估任务完成度。
- **对比方法**：
    - 人形技能：AvatarCLIP、TMR（运动检索）、MoMask、MotionGPT（数据驱动生成）、AnySkill（仅VLM奖励）。
    - 标准RL：与直接优化专家奖励的基线、VLM-RM（改进纹理的VLM奖励）对比。
    - 消融实验：VLM Only、LLM Only w/o RDP、LLM Only with RDP、VLM+LLM、Pose2CLIP Only、Pose2CLIP+LLM w/o RDP、全模型Pose2CLIP+LLM，共7种配置。

## 4. 资源与算力
- 文中未明确说明使用的GPU型号、数量或具体训练时长。仅提及：
    - Pose2CLIP训练使用170万帧数据。
    - 训练时间对比：全模型仅需7分钟，而VLM-only基线需59分钟，VLM-RM需411分钟。
    - 训练平台为IsaacGym，未给出硬件细节。

## 5. 实验数量与充分性
- **实验数量**：两组主要实验（人形技能合成+标准RL基准），每组有多个任务（人形5个指令，标准RL 5个智能体7个任务）。消融实验覆盖7种配置，并展示奖励收敛曲线（3个任务）。
- **充分性**：实验设计较全面，涵盖了不同复杂度、不同智能体（人形、四足、倒立摆）、不同学习范式（预训练控制器+高层学习 vs 从零学习）。用户研究采用30人评估，具有统计意义。消融实验验证了各组件的互补性。
- **客观公平性**：对比了多种代表性方法（检索、生成、零样本），指标包括人工评估和计算指标，对比条件合理。但部分基线（如AnySkill）未能完全复现其原论文设置（可能有差异）；CLIP相似度指标可能存在对自身方法的偏好（因为Pose2CLIP直接优化CLIP特征）。总体上实验设计较为严谨。

## 6. 论文的主要结论与发现
- GROVE框架在开放词汇人形技能合成中，任务完成度比最好基线高25.7%，运动自然度高22.2%，且训练速度比VLM-RM快8.4倍（从411分钟降至47分钟）。
- 在标准RL基准上，GROVE在4个任务中的3个（Ant、Cartpole、ANYmal侧向走）优于直接优化专家奖励，仅跳跃任务略逊（因基线直接优化了评估指标本身）。
- 消融实验证实：LLM和VLM奖励互补，Pose2CLIP显著提升效率（无需渲染），自适应重采样（RDP）防止奖励退化；全模型在所有指标上最优。
- 奖励收敛曲线显示，多模态奖励加速了两类奖励的收敛，证明了互补指导的有效性。

## 7. 优点：方法或实验设计上的亮点
- **方法亮点**：
    - 巧妙结合LLM和VLM的互补优势，形成正交约束，解决单一模型各自的局限。
    - Pose2CLIP轻量设计（2层MLP），直接映射姿态到CLIP特征，避免渲染开销且弥合域差距，是实用创新。
    - 自适应RDP机制利用VLM作为适应度函数动态重生成LLM奖励，增强鲁棒性。
    - 无需手动设计奖励或任务特定演示，真正实现零样本开放词汇技能学习。
- **实验设计亮点**：
    - 涵盖多种智能体（人形、四足、倒立摆）、多种学习范式（预训练+高层、从零学习）。
    - 消融实验全面，7种配置系统验证每个组件贡献。
    - 用户研究使用30人、三维度评分，减少主观偏差。
    - 对比方法涵盖主流范式（检索、生成、RL基线），具有代表性。

## 8. 不足与局限
- **实验覆盖**：
    - 仅使用了5种开放式指令和标准RL基准任务，未在更多复杂任务（如物体操作、多智能体协作）上验证。
    - 未在真实机器人上进行sim-to-real实验，仅在仿真中验证。
- **偏差风险**：
    - CLIP相似度指标可能对Pose2CLIP有利（因为其直接优化CLIP特征），但论文也同时采用了人工评估和多个计算指标，一定程度上抵消了该偏差。
    - 用户研究中参与者可能对“自然性”判断标准不一，尽管有校准示例，但仍存在主观性。
- **应用限制**：
    - Pose2CLIP目前仅针对人形智能体（基于SMPL），对其他固定状态空间的智能体需重新训练；文中虽声称可泛化，但未给出实例验证。
    - LLM奖励生成依赖GPT-o1-preview，可能受API随机性影响；RDP虽然能缓解，但极端情况下可能仍会产生不符合预期的奖励。
    - 训练效率虽高，但Pose2CLIP需要离线收集1.7万帧渲染数据，对于新智能体有一定前期成本。
    - 未讨论失败案例或失效模式，例如对非常抽象或矛盾指令的处理能力未知。

（完）
