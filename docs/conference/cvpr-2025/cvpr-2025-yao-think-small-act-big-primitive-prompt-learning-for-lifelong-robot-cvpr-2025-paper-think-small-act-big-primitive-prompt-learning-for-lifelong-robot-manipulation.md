---
title: "Think Small, Act Big: Primitive Prompt Learning for Lifelong Robot Manipulation"
title_zh: 小题大做：面向终身机器人操作的原始提示学习
authors: "Yao, Yuanqi, Liu, Siao, Song, Haoming, Qu, Delin, Chen, Qizhi, Ding, Yan, Zhao, Bin, Wang, Zhigang, Li, Xuelong, Wang, Dong"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yao_Think_Small_Act_Big_Primitive_Prompt_Learning_for_Lifelong_Robot_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 基于原始提示的终身机器人操作
tldr: 终身机器人操作中技能间共享原语难以利用。PPL提出两阶段方案：先多技能预训练学习运动感知原始提示，再通过可扩展提示实现连续技能获取。在多个操作任务上展示了高效的知识复用与抗遗忘能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 777, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1709, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1703, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1761, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 845, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 203, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yao-think-small-act-big-primitive-prompt-learning-for-lifelong-robot-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 176, \"label\": \"Table\"}]"
motivation: 现有方法不能充分利用技能间的共享原语，导致遗忘。
method: 两阶段学习：预训练习得运动感知原始提示，再用于终身学习。
result: 在连续机器人操作任务中显著提升学习效率与性能。
conclusion: 可复用原始提示是实现终身技能迁移的关键。
---

## Abstract
Learning a generalist robot that can effectively leverage prior knowledge for continuous skill acquisition remains significantly challenging. Despite the success of experience replay and parameter-efficient methods in maintaining knowledge across skills, naively applying these methods causes a failure to leverage the shared primitives between skills. To tackle these issues, we propose Primitive Prompt Learning (PPL), to achieve lifelong robot manipulation via reusable and extensible primitives. Within our two stage learning scheme, we first learn a set of primitive prompts to model primitives through multi-skills pre-training stage, where motion-aware prompts are learned to capture semantic and motion shared primitives across different skills. Secondly, when acquiring new skills in lifelong span, new prompts are concatenated and optimized with frozen pretrained prompts, boosting the learning via knowledge transfer from old skills to new ones. For evaluation, we construct a large-scale skill dataset and conduct extensive experiments in both simulation and real-world tasks, demonstrating PPL's superior performance over state-of-the-art methods.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：开发能够持续学习新技能的通用机器人是机器人领域的长期目标。人类能有效利用过往经验加速新技能学习（例如使用筷子后能更快学会镊子），但现有机器人方法在终身学习场景下存在**灾难性遗忘**问题，且未能充分利用不同技能间共享的**原始运动原语（primitives）**。
- **背景**：现有方法如经验回放（experience replay）受限于内存和隐私；正则化或动态架构方法在复杂视觉操作任务中表现不佳；参数高效方法（如LoRA）虽能避免任务干扰，但无法实现跨技能知识迁移。论文指出，不同技能（如“抓取香蕉”和“放置锅”）在语义上不同，但可能共享相似的底层运动模式（如夹持、移动），这些共享原语是知识迁移的关键。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：提出**原始提示学习（Primitive Prompt Learning, PPL）**，通过两阶段框架学习**可复用、可扩展的原始提示**，实现终身机器人操作技能迁移。
- **第一阶段：多技能预训练（Multi-Skill Pre-Training）**
  - 目标：学习一组原始提示（primitive prompts）\( p \in \mathbb{R}^{L_p \times D} \)，表示不同技能间的共享原语。
  - 关键技术：**运动感知提示（Motion-Aware Prompting, MAP）**，将**光流（optical flow）** 与**任务语义嵌入（CLIP embedding）** 结合，生成查询向量，通过注意力权重加权组合提示组件，并**插入扩散Transformer策略的多头自注意力层的键和值**（前缀提示方法）。
  - 光流计算：使用RAFT迭代估计，公式 \( f_{k+1} = f_k + \Delta f_k \)，\(\Delta f_k = \text{GRU}(C(f_k), h_k)\)。
  - MAP公式：\(\text{MAP}(T, F) = f_{\text{prompt}}(E_{\text{CLIP}}(T), \Phi(F))\)，其中 \(T\) 为任务描述，\(F\) 为光流。
- **第二阶段：终身技能获取（Lifelong Skill Acquisition）**
  - 冻结预训练阶段的原始提示，为每个新技能添加新的提示组件（\(P, K, A\)），通过当前任务的MAP查询与所有提示组件的键进行余弦相似度计算，得到加权权重 \(\alpha\)，生成最终提示 \( p = \sum_m \alpha_m P_m \)。
  - 仅优化新任务的提示参数，保留旧知识，实现无重放知识的迁移。
- **算法流程**（文字描述）：初始化原始提示 → 对每个预训练技能：计算光流 → 计算MAP查询 → 应用前缀提示到扩散Transformer → 计算扩散损失更新参数 → 对每个终身技能：初始化新提示组件 → 计算MAP查询 → 计算注意力权重 α → 生成新提示 → 优化新提示 → 扩展提示集。

## 3. 实验设计：数据集、场景、基准、对比方法
- **数据集构建**：基于**MimicGen**和**LIBERO**构建大规模技能数据集，每个技能包含多个演示（如1K个），涵盖多种操作场景（抓取、放置、打开抽屉等），并附带语言指令。
- **场景**：
  - 仿真环境：MimicGen和LIBERO任务。
  - 真实世界：Franka Panda机器人臂，包含4个预训练技能和5个终身学习技能，物体随机放置评估位置泛化。
- **基准**：采用**FWT（前向迁移权重）** 和**BWT（后向迁移权重）** 作为终身学习评估指标，以及平均成功率。
- **对比方法**：
  - 基础方法：顺序学习（Sequential）、经验回放（Experience Replay）。
  - 参数高效方法：LoRA（TAIL）、MoE（Sparse Diffusion Policy）。
  - 消融实验：对比仅文本查询 vs 文本+光流查询、不同提示数量、有无预训练提示等。

## 4. 资源与算力
- 论文中**未明确说明**使用的GPU型号、数量以及训练时长。仅提到在模拟和真实场景中进行实验，未提供具体计算资源细节。因此，无法总结精确的算力消耗。

## 5. 实验数量与充分性
- **实验数量**：包含多组实验：
  - 在LIBERO-GOAL环境下的预训练性能对比（Table 2显示具体成功率）。
  - 在MimicGen上的终身学习性能对比（Table 1，7个任务序列，含FWT和BWT）。
  - 在真实世界场景中的预训练和终身学习性能（Table 2，平均成功率）。
  - 消融实验：提示数量影响、运动感知查询可视化（权重分布图）、光流作用、有无预训练提示、光照鲁棒性分析（Table 3，三种光照等级）。
  - 与LoRA和MoE的训练速度对比（定性讨论）。
- **充分性**：实验较为充分，覆盖仿真和真实场景、多任务序列、多种评估指标，并进行了消融和鲁棒性分析。但**光照鲁棒性实验仅测试了单一任务（推茶壶把手）**，且结果显示光流方法在极端动态光照下性能下降，说明存在局限性。整体公平性较好，与SOTA方法进行了量化对比。

## 6. 论文的主要结论与发现
- PPL在模拟和真实世界中均达到**最优性能**，在预训练阶段平均成功率提升至84%（LIBERO）和84%（真实），优于Diffusion-Transformer和MoE。
- 在终身学习阶段，PPL的FWT平均为0.83，高于LoRA（0.78）和顺序学习（0.65）；BWT也优于对比方法，表明**有效缓解遗忘并实现正向迁移**。
- 运动感知查询（光流+文本）相比纯文本查询能捕获不同技能间的**共享运动原语**，即使任务语义不同也能产生相似的提示权重响应。
- 提示数量存在最优值，过多或过少均降低性能。
- 预训练提示在终身阶段冻结使用是提升新技能性能的关键。

## 7. 优点
- **创新性**：首次将原始原语学习与提示学习结合，提出两阶段框架，利用光流感知运动原语，克服了传统方法忽视共享原语的缺陷。
- **高效性**：相比MoE，PPL训练速度更快（仅需与LoRA相当的训练时间），同时保持高性能，实现了效率与效果的平衡。
- **可扩展性**：终身学习阶段仅需为新任务添加少量提示参数，无需访问旧数据，适合实际部署。
- **泛化能力**：在仿真和真实场景中均验证了有效性，且跨语义不同任务（如抓取与放置）仍能实现知识迁移。

## 8. 不足与局限
- **光照鲁棒性不足**：在极端动态光照（暖→冷→暗）条件下，基于光流的PPL性能明显下降（从0.83降至0.61），而纯文本查询方法反而更稳定。论文承认这是未来需要改进的方向（如引入深度图或3D场景流）。
- **提示数量敏感**：需要手动调整提示数量，未提供自适应选择机制，可能影响泛化。
- **未涉及3D信息**：当前仅使用2D光流，未利用3D场景流或深度信息，限制了复杂三维操作场景的适用性。
- **实验覆盖有限**：真实世界任务仅9个，且未测试长任务序列（如10+任务）的累积遗忘情况。光照鲁棒性实验仅在一个任务上测试，缺乏更多多样性。
- **算力信息缺失**：未报告训练计算成本（GPU型号、时长等），不利于可重复性评估。

（完）
