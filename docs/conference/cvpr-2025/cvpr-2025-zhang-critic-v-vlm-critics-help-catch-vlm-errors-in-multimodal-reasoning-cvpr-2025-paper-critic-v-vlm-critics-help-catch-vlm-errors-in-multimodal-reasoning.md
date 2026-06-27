---
title: "Critic-V: VLM Critics Help Catch VLM Errors in Multimodal Reasoning"
title_zh: Critic-V：VLM批评者帮助捕捉视觉语言模型在多模态推理中的错误
authors: "Zhang, Di, Lei, Jingdi, Li, Junxian, Wang, Xunzhi, Liu, Yujie, Yang, Zonglin, Li, Jiatong, Wang, Weida, Yang, Suorong, Wu, Jianbo, Ye, Peng, Ouyang, Wanli, Zhou, Dongzhan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_Critic-V_VLM_Critics_Help_Catch_VLM_Errors_in_Multimodal_Reasoning_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 基于Actor-Critic的VLM推理纠错框架
tldr: VLM在多模态推理中常出现幻觉或推理路径错误。Critic-V借鉴Actor-Critic范式，将推理与批评解耦：推理器生成初始回答，批判器提供建设性批评以迭代优化。该框架无需额外训练数据即可显著提升VLM推理准确性，并减少错误累积。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 810, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1256, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1226, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 637, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1338, \"height\": 489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1734, \"height\": 685, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1512, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-critic-v-vlm-critics-help-catch-vlm-errors-in-multimodal-reasoning-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 241, \"label\": \"Table\"}]"
motivation: VLM在多模态推理中产生不准确或无关响应，需要一种自动纠错机制。
method: 解耦推理与批评过程，集成独立推理器和批判器，批判器提供建设性反馈以迭代细化推理路径。
result: 多模态推理基准上准确率显著提升，有效减少幻觉和推理错误。
conclusion: Actor-Critic范式可有效增强VLM推理的鲁棒性。
---

## Abstract
Vision-language models (VLMs) have shown remarkable advancements in multimodal reasoning tasks. However, they still often generate inaccurate or irrelevant responses due to issues like hallucinated image understandings or unrefined reasoning paths. To address these challenges, we introduce Critic-V, a novel framework inspired by the Actor-Critic paradigm to boost the reasoning capability of VLMs. This framework decouples the reasoning process and critic process by integrating two independent components: the Reasoner, which generates reasoning paths based on visual and textual inputs, and the Critic, which provides constructive critique to refine these paths. In this approach, the Reasoner generates reasoning responses according to text prompts, which can evolve iteratively as a policy based on feedback from the Critic. This interaction process was theoretically driven by a reinforcement learning framework where the Critic offers natural language critiques instead of scalar rewards, enabling more nuanced feedback to boost the Reasoner's capability on complex reasoning tasks. The Critic model is trained using Direct Preference Optimization (DPO), leveraging a preference dataset of critiques ranked by Rule-based Reward (RBR) to enhance its critic capabilities. Evaluation results show that the Critic-V framework significantly outperforms existing methods, including GPT-4V, on 5 out of 8 benchmarks, especially regarding reasoning accuracy and efficiency. Combining a dynamic text-based policy for the Reasoner and constructive feedback from the preference-optimized Critic enables a more reliable and context-sensitive multimodal reasoning process. Our approach provides a promising solution to enhance the reliability of VLMs, improving their performance in real-world reasoning-heavy multimodal applications such as autonomous driving and embodied intelligence.

---

## 论文详细总结（自动生成）

# Critic-V: VLM Critics Help Catch VLM Errors in Multimodal Reasoning – 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉语言模型（VLM）在多模态推理任务中常出现不准确或无关的响应，主要包括：
  - 对图像内容产生“幻觉”（hallucinated image understandings）。
  - 推理路径不完善或产生级联错误（cascading errors）。
  - 过度依赖内部知识而忽略视觉上下文。
- **背景**：现有方法主要聚焦于增强 VLM 的内在推理能力（如微调、自纠正、Self-Refine 等），但这些方法大多依赖模型自身能力，缺乏高质量的外部监督反馈。
- **整体目标**：引入一个能够实时提供建设性批评的“批评者”（Critic），与“推理者”（Reasoner）协同工作，以提高 VLM 推理的可靠性和准确性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 借鉴强化学习中的 **Actor-Critic 范式**，将推理过程与批评过程解耦：
  - **Reasoner**（Actor）：根据视觉和文本输入生成推理路径。
  - **Critic**（Critic）：对 Reasoner 的输出提供自然语言反馈（而不是标量奖励），以迭代方式改进其推理策略。
- 交互过程形式化为一个强化学习框架：Critic 的反馈作为梯度信号，引导 Reasoner 更新基于文本的提示（text prompt）。

### 关键技术细节
1. **Reasoner**：
   - 使用动态文本提示 $P_{\text{reasoner}}$ 驱动推理，结合输入图像 $I$。
   - 更新规则基于 TextGrad 框架进行文本梯度的稳定计算。
   - Critic 模型学习预测最优的文本提示更新，近似于策略梯度中的价值函数。

2. **Critic 模型**：
   - 使用 **Direct Preference Optimization (DPO)** 训练，而非标量奖励优化。
   - 训练数据通过 **VEST (Vision Error Insertion Technique)** 构建：使用 GPT-4o 在真实 VQA 答案中插入 1~5 个错误，生成 “fake answer”；然后由多个 VLM（GLM-4V-9B, GPT-4o mini, MiniCPM-V）生成批评；最后用 **Rule-based Reward (RBR)** 结合 **Jaccard 指数** 和 GPT-4o 评分进行偏好排序。
   - 损失函数为 DPO 损失：$\mathcal{L}_{\text{DPO}}(\pi_\theta; \pi_{\text{ref}}) = -\mathbb{E}_{Q,I,C_w,C_l \sim D_{\text{cri}}}\left[\log \sigma\left( \beta \log \frac{\pi_\theta(C_w|Q,I)}{\pi_{\text{ref}}(C_w|Q,I)} - \beta \log \frac{\pi_\theta(C_l|Q,I)}{\pi_{\text{ref}}(C_l|Q,I)} \right)\right]$

3. **Reasoner-Critic 框架迭代流程**：
   - Reasoner 生成初始回答 → Critic 给出批评 → Reasoner 根据批评修正提示 → 重复直到达到最大迭代次数或满意为止。
   - 使用 TextGrad 实现文本提示的稳定更新。

## 3. 实验设计：数据集、Benchmark、对比方法

### Benchmark 和数据集
- **评估基准**：RealWorldQA, MMStar, MMBench, SEEDBench, ScienceQA, MMT-Bench, MathVista, MathVerse（共 8 个）。
- **训练数据**：构建了包含 29,012 个多模态问答对的 critique-VQA 数据集，每个问题附带批评和偏好标签。

### 对比方法
- **基线模型**：Llama-3.2-11B-Vision, MiniCPM-V 2.6, InternVL2-8B, GPT-4V, GeminiPro-Vision, LLaVA-v1.5-13B/7B, ShareGPT4V-7B, InternLM2-XC2, Qwen2-VL-7B, DeepSeek-VL-7B。
- **方法对比**：POVID, CSR, SIMA, SCL (Self-Correcting Learning) 以及 Self-Refine。

### 实验设置
- 使用 **Qwen2-VL-7B** 和 **DeepSeek-VL-7B** 作为主要测试的 Reasoner，Critic 模型也基于 Qwen2-VL-7B 进行 DPO 训练。
- 温度参数设为 0 或接近 0 以保证稳定性；所有实验采用两轮对话（第一轮特殊提示，第二轮利用 Critic 反馈）。

## 4. 资源与算力

- 论文中 **未明确说明具体使用的 GPU 型号、数量及训练时长**。仅提到使用了 DeepSpeed 进行训练优化（见参考文献 [44]），但未提及算力细节。
- 推理阶段：Critic-V 每次迭代仅增加少量 token 消耗（平均每个批评额外消耗几十个 token），计算开销较小。

## 5. 实验数量与充分性

- **主要实验**：在 8 个 benchmark 上对 Qwen2-VL-7B 和 DeepSeek-VL-7B 进行测试，共 16 组主要对比结果，其中 23/24 次实验表现提升。
- **消融实验**：
  - Token 消耗分析（附录 11）。
  - DPO 训练对比：Critic-V vs. Self-Refine（未训练 DPO），在 MathVista、MMT-Bench、MMBench 上显示 DPO 训练至关重要。
  - 提示消融：仅使用特殊提示而不加批评，验证提升来自框架本身。
- **充分性评估**：实验覆盖推理密集型（数学）和知识型任务，对比了 SOTA 闭源/开源模型，消融设计合理。但仅测试了 7B 规模模型，未扩展到更大尺度（如 13B/34B），且未在高资源环境下测试效率。总体实验设置客观公平。

## 6. 论文的主要结论与发现

1. **Critic-V 显著提升 VLM 推理性能**：在 5/8 基准上超越 GPT-4V，尤其在数学推理任务（MathVista +11.8% ~ +17.8%；MathVerse +7.1% ~ +10.5%）和真实世界推理（RealWorldQA +4.8% ~ +12.8%）上提升明显。
2. **DPO 训练是 Critic 有效性的关键**：未训练的 Self-Refine 提升有限，甚至可能下降；经 DPO 训练的 Critic 提供更精准的批评。
3. **自然语言反馈优于标量奖励**：批评提供细粒度错误位置和逻辑不一致描述，有利于复杂的迭代修正。
4. **外部批评可有效减少 VLM 的幻觉和级联错误**，提高对图像内容理解的可靠性。

## 7. 优点

- **创新框架**：将强化学习的 Actor-Critic 范式引入 VLM 推理，实现推理与批评的主动解耦，思路新颖。
- **高质量批评数据**：通过 VEST 自动生成带有插入错误的答案，并融合多 VLM 批评和 RBR 偏好排序，数据集可靠且可扩展。
- **即插即用**：Critic 模型可与现有 VLM 集成，无需重新训练 Reasoner，适用性广。
- **理论贡献**：形式化了基于文本提示的更新规则，并证明了 DPO 适用于批评模型训练。
- **实验充分**：多 benchmark、多基线、多消融，结果具有说服力。

## 8. 不足与局限

- **基准规模有限**：仅测试 7B 参数量的 VLM，未验证更大模型（如 13B/34B/72B）或更小参数模型上的泛化性。
- **计算开销**：虽然个例 token 消耗少，但推理需多轮迭代（每轮调用两次 VLM：一次 Reasoner + 一次 Critic），在实时应用中可能带来延迟。
- **批评质量依赖训练数据**：Critic 是否能泛化到未见过的错误类型（如外域图像）未充分验证。
- **消融实验不完整**：未对 VEST 中插入错误数量、GPT-4o 造成的偏差进行深入分析。
- **数据集局限**：critique-VQA 仅基于 VQA 数据，可能不涵盖所有多模态推理场景（如图表理解、对话历史等）。
- **偏差风险**：RBR 评分使用 GPT-4o，可能引入自身偏见；Jaccard 指数对长批评惩罚较大，可能偏向简短反馈。

（完）
