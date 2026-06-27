---
title: "DiffusionVLA: Scaling Robot Foundation Models via Unified Diffusion and Autoregression"
title_zh: "DiffusionVLA: 通过统一扩散和自回归扩展机器人基础模型"
authors: "Junjie Wen, Yichen Zhu, Minjie Zhu, Zhibin Tang, Jinming Li, Zhongyi Zhou, Xiaoyu Liu, Chaomin Shen, Yaxin Peng, Feifei Feng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VdwdU81Uzy"
tags: ["query:vlm-rl"]
score: 9.0
evidence: DiffusionVLA将自回归推理与扩散策略结合用于VLA
tldr: 现有VLA模型自回归推理缺乏精确动作生成，而扩散策略缺少推理能力。DiffusionVLA框架将预训练VLM的推理过程融入扩散策略，通过推理注入模块紧密耦合，在机器人操纵任务中同时提升了推理准确性和动作精度。本文展示了融合两范式的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1597, \"height\": 1235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1569, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 769, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1747, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1759, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 860, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 724, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 815, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1778, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 727, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 810, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 809, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 838, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 894, \"height\": 561, \"label\": \"Table\"}]"
motivation: 自回归VLA动作生成不精确，扩散策略缺乏推理。
method: 用VLM分解任务生成推理短语，注入扩散策略指导动作生成。
result: 在模拟和真实机器人任务中性能显著优于单独方法。
conclusion: 统一推理与扩散为VLA提供了可扩展方案。
---

## Abstract
In this paper, we present DiffusionVLA, a novel framework that integrates autoregressive reasoning with diffusion policies to address the limitations of existing methods: while autoregressive Vision-Language-Action (VLA) models lack precise and robust action generation, diffusion-based policies inherently lack reasoning capabilities. Central to our approach is autoregressive reasoning — a task decomposition and explanation process enabled by a pre-trained VLM — to guide diffusion-based action policies. To tightly couple reasoning with action generation, we introduce a reasoning injection module that directly embeds self-generated reasoning phrases into the policy learning process. The framework is simple, flexible, and efficient, enabling seamless deployment across diverse robotic platforms.

We conduct extensive experiments using multiple real robots to validate the effectiveness of DiVLA. Our tests include a challenging factory sorting task, where DiVLA successfully categorizes objects, including those not seen during training. The reasoning injection module enhances interpretability, enabling explicit failure diagnosis by visualizing the model’s decision process. Additionally, we test DiVLA on a zero-shot bin-picking task, achieving \textbf{63.7\% accuracy on 102 previously unseen objects}. Our method demonstrates robustness to visual changes, such as distractors and new backgrounds, and easily adapts to new embodiments. Furthermore, DiVLA can follow novel instructions and retain conversational ability. Notably, DiVLA is data-efficient and fast at inference; our smallest DiVLA-2B runs 82Hz on a single A6000 GPU. Finally, we scale the model from 2B to 72B parameters, showcasing improved generalization capabilities with increased model size.

---

## 论文详细总结（自动生成）

# 1. 核心问题与整体含义（研究动机和背景）

现有视觉-语言-动作（VLA）模型主要分为两类：

- **自回归模型**（如RT-2、OpenVLA）：将动作预测视为下一个token预测，具备语言推理能力，但动作生成精度低、效率低，且离散化连续动作会破坏动作连贯性。
- **扩散策略模型**（如Diffusion Policy）：通过噪声-去噪过程生成动作，能更好捕捉多模态动作分布、生成速度快，但**缺乏语言推理能力**，无法处理复杂任务中的上下文理解与分解。

本文的核心动机是：**能否将自回归的推理能力与扩散策略的动作生成优势统一到一个框架中？** 作者提出DiffusionVLA（DiVLA），让机器人模型既能“思考”（推理）又能“行动”（精确、高频动作生成），从而提升泛化性、可解释性和部署效率。

# 2. 方法论：核心思想与关键技术

## 2.1 核心思想
- 使用**预训练的视觉-语言模型（VLM）** 进行自回归推理，产生任务分解和解释性文本（reasoning tokens）。
- 将这些推理短语通过**推理注入模块**嵌入到**扩散策略**的动作生成过程中，使动作生成受到显式推理引导。
- 训练损失为扩散损失与下一token预测损失的加权和：\( \mathcal{L} = \mathcal{L}_{\text{diff}} + \alpha \mathcal{L}_{\text{ntp}} \)，其中 \(\alpha=10\)（因扩散损失量级约比NTP损失大10倍）。

## 2.2 关键技术细节
- **视觉编码**：使用SigLIP将多视图图像编码为视觉token，再通过VLM的Transformer得到固定数量的视觉嵌入。
- **VLM骨干**：选用Qwen2-VL（2B/8B/72B），权重从公开检查点初始化，可替换为其他VLM。
- **动作token投影**：在VLM最后一层后生成固定数量的动作token，经两层MLP+LayerNorm投影到扩散模型。
- **扩散模型**：采用标准Diffusion Policy设计（Chi et al., 2023），随机初始化，底部附加MLP预测机器人关节空间。对于多形态机器人，仅新增MLP层而不复制整个动作解码器，保持预训练知识。
- **推理注入模块**：从推理部分的最后token嵌入中提取特征，通过**特征线性调制（FiLM）** 注入到扩散策略网络的各层，使推理信号直接参与动作生成，不增加推理计算开销（因为推理在训练时已融入动作解码器，测试时无需额外循环）。

## 2.3 训练策略
- 使用预训练数据（Droid、OXE）进行预训练，并用GPT-4o自动生成推理文本以增强语言泛化。
- 微调时使用LoRA（秩适配）冻结大部分VLM权重，学习率固定为2e-5。

# 3. 实验设计

## 3.1 数据集与场景
- **预训练数据**：Droid数据集（主要用于2B和7B模型）；对于72B模型，额外使用OXE数据集（共25倍于DiVLA预训练数据规模）。
- **微调数据**：四种真实机器人任务：
  - 工厂分拣（500条轨迹）；零样本拣选（无训练数据，纯测试）；多任务学习（580条轨迹）；桌面清理（双机械臂，400条轨迹）。

## 3.2 Benchmark与对比方法
- **对比方法**：Diffusion Policy、TinyVLA、Octo、OpenVLA。其中Octo和OpenVLA使用OXE预训练（数据量是DiVLA的25倍）。
- **任务覆盖**：
  - **多任务学习**（5个子任务：物体选择、翻转锅、立方体入盒、杯子放盘子、立方体入指定颜色盒）→ 评估分布内和视觉泛化（干扰物、新背景、彩色灯光）。
  - **工厂分拣**：四类物体（玩具车、针织手套、毛绒玩具、六角扳手），含“简单/困难”（物体数量<5或6-11）、“仅见过/混合未见”、“干净/杂乱”四种组合。
  - **零样本拣选**：对102个从未见过的物体，要求“将右侧面板上的物体移到左侧篮子”。
  - **桌面清理（双机械臂）** ：将餐具放左侧托盘，垃圾扔右侧垃圾桶，测试见过/混合未见物体。
  - **额外实验**：视角转移泛化、遵循新指令、VQA能力、模型规模缩放（2B/7B/72B）。

# 4. 资源与算力

文中未明确说明训练所需的GPU型号、数量或训练时长。仅提到：模型在单张A6000 GPU上推理时，DiVLA-2B达82Hz，DiVLA-7B达42Hz；使用vLLM框架加速。训练细节（如总步数、并行配置）未给出。

# 5. 实验数量与充分性

- **实验组数**：涵盖7个主要实验设置（多任务学习、视觉泛化、工厂分拣、零样本拣选、双机械臂桌面清理、视角泛化、新指令遵循），每个设置下都进行多次独立试次（如多任务学习77次，分拣每种场景65-80次，零样本102个物体，桌面清理48次等）。此外包含消融实验（去掉推理注入模块）、规模缩放实验（2B vs 7B vs 72B）、单/多视角对比、VQA演示。
- **充分性**：实验设计较为全面，覆盖了分布内/分布外、常见/未见物体、不同难度、不同机器人形态（单臂Franka和双臂AgileX）、不同视觉变化、以及可解释性分析。对比方法均使用一致的训练策略（如OpenVLA扩展为三视角以公平比较）。但缺乏仿真实验，完全基于真实机器人；也未报告多次试次的标准差或置信区间，可能对随机性考虑不足。

# 6. 主要结论与发现

1. **统一推理与扩散有效**：DiVLA在全部任务上显著优于纯自回归或纯扩散方法。例如，多任务学习平均成功率83.6%（分布内），而最佳对比方法OpenVLA仅39.4%；工厂分拣平均66.2%，远超OpenVLA的45.3%。
2. **零样本泛化能力强**：对102个未见物体，零样本拣选成功率达63.7%，其他方法均低于30%。
3. **视觉鲁棒性**：在干扰物、新背景、彩色灯光下，DiVLA仍保持57.8%成功率（对比OpenVLA 26.7%）。
4. **推理可解释性**：推理注入模块能可视化模型内部决策过程，如对未见物体进行语义类比（将螺丝刀归为六角扳手类），并能通过推理变化分析失败原因。
5. **形态适应快**：在双机械臂桌清任务上，DiVLA对见过物体达72.9%，对混合未见物体达70.8%，远超Diffusion Policy和OpenVLA。
6. **推理速度快**：即便最小的2B模型也能实现82Hz控制频率（远高于OpenVLA的5Hz）。
7. **可扩展性**：随着模型参数从2B增至72B，分拣任务成功率从66.2%提升至82.4%，零样本拣选从63.7%提升至75.9%，验证了缩放定律。

# 7. 优点

- **方法创新性**：首次将自回归推理与扩散策略有机结合起来，通过推理注入模块实现端到端训练，避免了传统循环递归（将推理输出再作为输入）带来的计算开销。
- **实用性强**：模型在真实机器人上高效运行，数据效率高（仅需39K预训练轨迹，远少于OpenVLA的970K），且能快速适应新形态和视觉变化。
- **可解释性好**：推理注入使得模型能“说出”其决策依据，有助于调试和信任建立。
- **实验覆盖广泛**：在多种复杂真实场景下进行了严格评估，包括零样本、视觉干扰、新指令、双机械臂等，且对比了多个强基线。

# 8. 不足与局限

- **缺乏仿真实验**：所有实验基于真实机器人，虽更有说服力，但未提供仿真benchmark（如RLBench、MetaWorld）下的结果，难以与更多学术方法直接对比。
- **统计严谨性不足**：未报告成功率的置信区间或每次试次的标准差，可能因随机放置、抓取等因素导致结果波动。
- **训练细节缺失**：未明确说明训练所需GPU数量、总训练时间、超参数搜索过程等，可复现性受限。
- **推理依赖VLM质量**：推理来自预训练VLM（Qwen2-VL），若VLM本身存在偏见或错误，可能误导动作生成。虽然实验展示其能泛化，但对某些罕见物体（如将玩具龙误认为玩具虎）仍有失败。
- **低精度推理劣化**：量化至8-bit或4-bit时性能显著下降，表明当前VLA模型对量化敏感，不利于边缘部署。
- **新指令遵循能力有限**：对于三步顺序指令，成功率仅约1/3，表明复杂指令理解仍有提升空间。
- **未涉及安全问题**：虽然方法具有可解释性，但未讨论故障安全、人机交互中的风险或对齐问题。

（完）
