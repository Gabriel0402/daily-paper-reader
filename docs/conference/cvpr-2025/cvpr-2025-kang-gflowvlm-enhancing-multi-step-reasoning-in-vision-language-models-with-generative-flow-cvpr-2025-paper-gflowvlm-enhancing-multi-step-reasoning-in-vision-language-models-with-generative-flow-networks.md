---
title: "GFlowVLM: Enhancing Multi-step Reasoning in Vision-Language Models with Generative Flow Networks"
title_zh: GFlowVLM：利用生成流网络增强视觉语言模型的多步推理能力
authors: "Kang, Haoqiang, Sachdeva, Enna, Gupta, Piyush, Bae, Sangjae, Lee, Kwonjoon"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Kang_GFlowVLM_Enhancing_Multi-step_Reasoning_in_Vision-Language_Models_with_Generative_Flow_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 利用GFlowNets微调VLM以增强多步推理，连接VLM与强化学习
tldr: VLM在多步推理任务中微调存在SFT对独立同分布假设的依赖和PPO对累积奖励最大化的限制，导致解多样性不足。GFlowVLM引入生成流网络，通过鼓励探索多种合理推理路径来提升泛化能力。实验表明其在不同推理任务上优于SFT和PPO，产生更丰富的解。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 527, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1328, \"height\": 907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1601, \"height\": 462, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 772, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 902, \"height\": 818, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1294, \"height\": 818, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-kang-gflowvlm-enhancing-multi-step-reasoning-in-vision-language-models-with-generative-flow-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1607, \"height\": 341, \"label\": \"Table\"}]"
motivation: VLM微调方法SFT和PPO分别受限于数据独立同分布假设和奖励最大化，限制了推理多样性。
method: 采用生成流网络（GFlowNets）作为微调框架，以促进多步推理中多样化解的生成。
result: 在多步推理基准上相比SFT和PPO获得更优性能，且解多样性显著增加。
conclusion: GFlowNet为VLM推理微调提供了一种高效多样化的替代方案。
---

## Abstract
Vision-Language Models (VLMs) have recently shown promising advancements in sequential decision-making tasks through task-specific fine-tuning. However, common fine-tuning methods, such as Supervised Fine-Tuning (SFT) and Reinforcement Learning (RL) techniques like Proximal Policy Optimization (PPO), present notable limitations: SFT assumes Independent and Identically Distributed (IID) data, while PPO focuses on maximizing cumulative rewards. These limitations often restrict solution diversity and hinder generalization in multi-step reasoning tasks. To address these challenges, we introduce a novel framework, GFlowVLM, a framework that fine-tune VLMs using Generative Flow Networks (GFlowNets) to promote generation of diverse solutions for complex reasoning tasks. GFlowVLM models the environment as a non-Markovian decision process, allowing it to capture long-term dependencies essential for real-world applications. It takes observations and task descriptions as inputs to prompt chain-of-thought (CoT) reasoning which subsequently guides action selection. We use task based rewards to fine-tune VLM with GFlowNets. This approach enables VLMs to outperform prior fine-tuning methods, including SFT and RL. Empirical results demonstrate the effectiveness of GFlowVLM on complex tasks such as card games (NumberLine, BlackJack) and embodied planning tasks (ALFWorld), showing enhanced training efficiency, solution diversity, and stronger generalization capabilities across both in-distribution and out-of-distribution scenarios. Project page is available at \href https://mk322.github.io/gflowvlm/ https://mk322.github.io/gflowvlm/ .

---

## 论文详细总结（自动生成）

# 中文论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉语言模型（VLM）在多步推理和序列决策任务中表现出潜力，但现有微调方法（SFT 和 PPO）存在明显局限：SFT 假设训练数据独立同分布（IID），限制了泛化能力；PPO 优化累积奖励，倾向于收敛到单一最优策略，缺乏解多样性。两者都难以在复杂推理任务中充分探索多种合理路径。
- **核心问题**：如何让 VLM 在复杂多步推理任务中生成多样化、高奖励的解，并提升在分布外（OOD）场景下的泛化能力。
- **整体含义**：本文提出利用生成流网络（GFlowNets）微调 VLM，使生成的解分布与奖励函数成正比，从而在探索多样性和高效学习之间取得平衡。这是首次将 GFlowNets 与 VLM 端到端融合的工作。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将预训练 VLM（LLaVA-1.6-Mistral-7B）作为前向策略 \(P_F\)，通过 GFlowNets 的轨迹平衡、子轨迹平衡、细节平衡等目标函数进行微调，使 VLM 生成的推理路径（包括 CoT 和动作）的分布与任务奖励函数成正比。
- **关键技术细节**：
  - 采用**非马尔可夫决策过程**：输入中包含历史状态、历史动作和链式推理（CoT），使模型能捕捉长程依赖。
  - **提示设计**：输入包含目标描述、历史状态/动作、当前可行动作空间、以及当前的视觉观察（仅最新一帧）。输出为 JSON 格式，包含“thoughts”（CoT）和“action”。
  - **动作选择**：先生成 CoT 推理（描述图像和思考过程），再基于 CoT 选择动作。前向策略的对数概率为动作概率与 CoT 概率的加权和（权重 λ=0.4）。
  - **训练目标**：使用三种 GFlowNets 损失函数：
    - **轨迹平衡（TB）**：确保整条轨迹的流与奖励成比例，采用方差 TB 损失。
    - **子轨迹平衡（SubTB）**：在子轨迹上平衡局部流，需估计终止概率 \(P_F(\top|\cdot)\)。
    - **细节平衡（DB）**：在每一步转移上平衡前向和后向流，需要密集奖励。
  - 为了处理非负奖励要求，对 NumberLine 和 Blackjack 任务进行了奖励塑形（reward shaping），使其非负。
  - 引入新标记 `[DONE]` 显式建模终止状态，并用 SFT 预训练帮助模型估计终止概率。
  - 支持**离线策略学习**：可复用历史轨迹进行更新，提升样本效率。

## 3. 实验设计

- **数据集/场景**：
  - **NumberLine**：数字序列推理，目标是将当前数字移动到目标数字。分布内（ID）范围 0~5，OOD 范围 10~50。
  - **Blackjack**：21 点纸牌游戏，含视觉信息和随机性。分布内标准规则，OOD 未明确区分（但实验中有 OOD 泛化测试？实际文中未特别提 Blackjack OOD）。
  - **ALFWorld**：具身 AI 规划任务，结合文本和视觉，有 6 个子任务（Pick、Look、Clean、Heat、Cool、Pick2）。OOD 基于未见场景。
- **Benchmark**：任务成功率（SR）和多样性指标 Div@N（N=16）。
- **对比方法**：
  - **SFT**：两种版本（有/无 `[DONE]` 标记），基于 GPT-4o 生成的数据集。
  - **RL4VLM**：PPO 微调方法，包括马尔可夫和非马尔可夫设置，以及不同奖励函数。
  - **GFlowVLM**：分别用 Var-TB、SubTB、DB 三种损失，以及在线/离线策略、有无 SFT 初始化的消融。
- **实验公平性**：使用相同基座模型（LLaVA-1.6-Mistral-7B），相同提示格式（对 RL4VLM 也做了非马尔可夫适配）。独立 4 次运行报告均值和标准差。

## 4. 资源与算力

- **文中明确说明**：“Limited computational resources led us to use small-sized VLMs”（第 7 章结论）。但**未具体说明 GPU 型号、数量、训练时长**等算力细节。只提到训练效率上，GFlowVLM 比 RL4VLM 少约 10,000 个环境步骤即收敛。

## 5. 实验数量与充分性

- **实验组数**：在 NumberLine（ID 和 OOD）、Blackjack、ALFWorld 三个主要场景上测试，对比了 4 种基线（多种变体），并进行了以下消融：
  - 不同损失函数（TB、SubTB、DB）
  - 在线 vs. 离线策略
  - 有无 SFT 初始化（对 SubTB 和 DB）
  - 有无 `[DONE]` 标记（SFT）
  - 温度参数（α=1 vs 1.2）的多样性测试（在动机实验中）
- **充分性评估**：
  - 实验覆盖了三种不同类型的多步推理（算术推理、随机游戏、具身规划），ID 和 OOD 泛化均有测试。
  - 消融实验展示了各组件（SFT 初始化、离线数据、非马尔可夫假设）的贡献。
  - 训练曲线对比了收敛速度。
  - 但缺少与更多 VLM 基模型的对比（如更大规模 LLaVA、GPT-4V 等），也未涉及多智能体或更复杂场景。
  - **公平性较好**：调整了 RL4VLM 的提示和奖励以对齐比较，但原始 RL4VLM 使用不同奖励，可能略有优势偏移。

## 6. 论文的主要结论与发现

- GFlowVLM 在所有任务上显著优于 SFT 和 PPO 基线：
  - 在 NumberLine ID 上达到 100% 成功率，比 RL4VLM 高约 12%。
  - 在 Blackjack 上提升约 8%。
  - 在 ALFWorld 上平均成功率高约 29%，OOD 泛化提升 156%。
- 解多样性大幅提升：ALFWorld 上 Div@16 比 RL4VLM 高 25-33%，比 SFT 高约 37%。
- 离线策略训练可进一步提升性能（尤其在 OOD 任务上），平均提升约 36%。
- 非马尔可夫建模显著优于马尔可夫：GFlowVLM 在 ALFWorld 上 OOD 成功率提升 100%。
- SFT 初始化对 SubTB 和 DB 损失至关重要（否则性能极低）。
- 三种损失函数中，DB 在需要密集奖励的任务上泛化最好，SubTB 和 TB 在大部分任务上相当。

## 7. 优点

- **方法新颖性**：首次将 GFlowNets 与 VLM 端到端融合，直接用于多模态多步推理微调。
- **多样化与泛化能力强**：通过学习奖励比例分布而非只最大化奖励，能生成多种高质量解，对 OOD 场景鲁棒性更强。
- **样本效率高**：支持离线策略，可复用历史轨迹，收敛速度快于 PPO。
- **非马尔可夫建模**：引入历史状态和动作，更适合长程依赖任务。
- **实验设计全面**：覆盖多种任务类型，消融实验完整，对比基线经过公平调整。

## 8. 不足与局限

- **计算资源有限**：仅使用了 7B 参数的 LLaVA-1.6，未探索更大模型，结论的普适性待验证。
- **仅限单智能体**：未扩展到多智能体协作或竞争场景。
- **DB 损失需要密集奖励**：在 ALFWorld 中无法使用（无密集奖励），限制了其适用范围。
- **奖励塑形可能引入偏差**：对 NumberLine 和 Blackjack 做了非负奖励塑形，可能偏离原始奖励含义，影响对比公平性。
- **OOD 测试范围有限**：NumberLine OOD 仅为数值范围外推，ALFWorld OOD 为未见场景，但缺乏更复杂的分布偏移测试。
- **未与最新 CoT 提示方法（如 Tree-of-Thought）比较**：仅对比了 PPO 和 SFT，未考虑其他推理增强技术。
- **终止概率估计需要 SFT 预训练**：增加了训练步骤和依赖，且 SFT 数据可能引入偏差。

（完）
