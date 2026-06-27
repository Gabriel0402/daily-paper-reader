---
title: "UP-VLA:  A Unified Understanding and Prediction Model for Embodied Agent"
title_zh: "UP-VLA: 具身智能体的统一理解与预测模型"
authors: "Jianke Zhang, Yanjiang Guo, Yucheng Hu, Xiaoyu Chen, Xiang Zhu, Jianyu Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=V7JPraxi5j"
tags: ["query:vlm-rl"]
score: 8.0
evidence: UP-VLA通过统一理解和预测改进VLA
tldr: 现有VLM用于VLA时忽略低级特征，限制了空间和理解物理动力学的能力。UP-VLA提出统一训练范式，联合优化视觉语言理解和未来状态预测，使模型同时捕捉高语义和低层细节。在具身操控任务中表现优越，验证了该训练思路的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1718, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1734, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1753, \"height\": 635, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1763, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1628, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 348, \"label\": \"Table\"}]"
motivation: VLM过度关注高层语义，忽视低级特征如空间细节。
method: 设计理解和预测联合训练目标，在预训练中引入物理动力学预测。
result: 在多个机器人操控基准上实现更精确的控制。
conclusion: 统一预训练范式可弥补VLM在具身任务中的不足。
---

## Abstract
Recent advancements in Vision-Language-Action (VLA) models have leveraged pre-trained Vision-Language Models (VLMs) to improve the generalization capabilities.
VLMs, typically pre-trained on vision-language understanding tasks, provide rich semantic knowledge and reasoning abilities. 
However, prior research has shown that VLMs often focus on
high-level semantic content and neglect low-level features, 
limiting their ability to capture detailed spatial information and understand physical dynamics.
These aspects, which are crucial for embodied control tasks, remain underexplored in existing pre-training paradigms.
In this paper, we investigate the training paradigm for VLAs, and 
introduce \textbf{UP-VLA}, a \textbf{U}nified VLA model training with both multi-modal \textbf{U}nderstanding and future \textbf{P}rediction objectives, enhancing both high-level semantic comprehension and low-level spatial understanding. Experimental results show that UP-VLA achieves a 33\% improvement on the Calvin ABC-D benchmark compared to the previous state-of-the-art method. Additionally, UP-VLA demonstrates improved success rates in real-world manipulation tasks, particularly those requiring precise spatial information.

---

## 论文详细总结（自动生成）

# UP-VLA: 具身智能体的统一理解与预测模型——论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的 Vision-Language-Action (VLA) 模型通常基于预训练的 Vision-Language Model (VLM) 进行微调。然而，VLM 在预训练时主要聚焦于高层的语义理解（如视觉问答），这导致其**忽略低层视觉特征**（如空间位置、物体大小、物理动态等），而这些能力对于机器人精确操控至关重要。
- **整体含义**：本文旨在设计一种新的 VLA 训练范式，在保留 VLM 高层语义推理能力的同时，**显式地引入未来预测目标**，使模型能够同时捕捉高层的语义信息和低层的空间/动态细节，从而提升具身智能体的决策与操控性能。

## 2. 论文提出的方法论

### 核心思想
构建一个统一的自回归模型，通过灵活注意力掩码和特殊 token 区分任务类型，联合训练三种数据：**多模态理解数据**（图像-文本对）、**未来图像预测数据**（机器人视频序列）、**机器人动作数据**。使模型同时具备以下能力：
- 多模态理解（VQA 等）
- 未来视觉预测（预测下一帧图像）
- 动作生成（输出机器人末端位姿和夹爪状态）

### 关键技术细节
- **模型架构**：以 Phi-1.5 作为 LLM 骨干；使用 CLIP-ViT 作为连续视觉编码器（用于理解任务），使用 VQ-GAN (MagVIT) 作为离散图像 tokenizer（用于预测任务）。
- **统一输入格式**：通过特殊 token（如 `SOI`, `EOI`, `SOT`, `EOT`, `SOA`, `EOA`）区分不同任务。理解任务中图像 token 放在文本之前；预测任务中图像 token 放在文本之后；动作学习任务同时包含理解 token 和预测 token。
- **两阶段训练**：
  1. **预训练阶段**：联合优化多模态理解损失（来自 LLaVA-tuning-665k 数据集）和未来预测损失（来自 Bridge 数据集 25k 演示），使模型同时具备理解和预测能力。
  2. **微调阶段**：在机器人下游任务上联合优化未来预测损失和动作损失，同时继续混合理解数据以保持语义能力。此外，将场景描述（由模型自身生成）作为语言提示的一部分输入，增强语义引导。
- **损失函数**：
  - 多模态理解：交叉熵损失（语言 token 预测）
  - 未来预测：交叉熵损失（离散图像 token 预测）
  - 动作学习：MSE 损失（连续位置）+ 二元交叉熵损失（夹爪开关状态）
  - 总损失：`L = λ1·L_MMU + λ2·L_PRE + λ3·L_ACT`

### 公式/算法流程（文字说明）
- 输入当前观察图像和语言指令，模型先通过连续编码器（CLIP-ViT）将当前图像映射为连续 token，并生成场景描述（通过多模态理解能力）。
- 然后，将场景描述、语言指令、当前图像离散 token（通过 VQ-GAN）拼接，输入 LLM，自回归地生成未来图像 token 和动作 token。
- 未来图像 token 经 VQ-GAN 解码器重建为未来帧；动作 token 通过一个小型 policy head（单层注意力 + 线性层）映射为连续动作序列。

## 3. 实验设计

### 使用数据集与场景
- **模拟环境**：CALVIN 基准（4 个场景 A/B/C/D），包含长时域语言条件操控任务。任务设置包括：
  - `ABCD→D`：在训练场景 A/B/C/D 上训练，在场景 D 上测试（同分布）
  - `ABC→D`：在场景 A/B/C 上训练，在场景 D 上测试（零样本泛化，更困难）
- **真实世界环境**：Franka Emika Panda 机器人，6 种技能（抓取、放置、拉抽屉、布线、按按钮、抓取小球/笔等），共收集 2000+ 演示。测试分三类：
  - **seen**：训练过的物体和场景
  - **unseen**：新物体（如新形状的蔬菜、箭头纸等），验证语义泛化
  - **precise**：要求精确空间操作的任务（如布线的路径、抓取小球/笔）

### 对比方法
- **VLM-based VLA 方法**：RT-2、RoboFlamingo、3D-VLA、UP-VLA-RT-2（自己复现的 RT-2 版本）
- **预测-based 方法**：GR-1、Uni-Pi、Susie、UP-VLA-phi-w/o-mmu（消融变体，仅使用预测和动作，不使用多模态理解）
- **其他**：RT-1、Diffusion Policy、3D Diffuser Actor

### Benchmark 指标
- 模拟：5 个连续子任务的成功完成长度（Avg. Len），以及各子任务完成率。
- 真实：每个任务 20 次尝试的成功率（Success Rate）。

## 4. 资源与算力

- 论文正文及附录中**未明确说明**使用的 GPU 型号、数量、训练时长等具体算力信息。
- 附录 A 仅提到：预训练阶段训练 20k 步，batch size 64；微调阶段 batch size 64。但未提及硬件配置。因此无法总结具体算力。

## 5. 实验数量与充分性

### 实验数量
- **模拟实验**：2 个 benchmark（ABC→D 和 ABCD→D），各列出 9-10 种方法对比。
- **真实世界实验**：3 类任务（seen/unseen/precise），每类包含 2-4 个子任务，共约 8 个子任务，每个子任务 20 次 roll-out。
- **消融实验**：4 种变体（w/o MMU、w/o Bridge-Pretrain、w/o Prediction、w/o MMU-Condition），在模拟和真实任务上均进行了比较。
- **定性可视化**：展示 VQA 回答和未来预测图。

### 充分性与公平性
- 对比方法覆盖了主流的 VLA 方法和预测方法，且尽量在同一 backbone（Phi-1.5）下复现了关键基线（如 UP-VLA-RT-2、UP-VLA-phi-w/o-mmu），保证了对比公平。
- 消融实验设计全面，分别验证了多模态理解、未来预测、Bridge 预训练、MMU condition 四个组件的贡献。
- 但**真实世界实验仅在单一机器人平台（Panda）上执行**，且数据集规模较小（2000+ 演示），可能限制了结论的泛化性。此外，论文未报告实验的标准差或置信区间，统计显著性不足。

## 6. 论文的主要结论与发现

1. **未来预测显著提升 VLA 表现**：在 Calvin ABC→D 基准上，UP-VLA 比最先进的 GR-1 提升了 33%（平均完成长度从 3.06 到 4.08）。相比于纯 VLM 方法的 UP-VLA-RT-2（1.44），加入预测后提升近 2.8 倍。
2. **多模态理解增强语义泛化**：特别是在真实世界 unseen 任务中，UP-VLA 成功率（0.58）高于不含 MMU 的变体（0.20），说明理解知识有助于对新物体的 zero-shot 泛化。
3. **联合训练达到最佳平衡**：UP-VLA 同时在高语义任务和低层精确任务上均表现最优，说明理解和预测可以互补而非冲突。
4. **可视化分析**：模型能准确预测手臂和物体的未来位置，但在预测背景颜色时存在泛化缺陷（倾向于训练集背景）。

## 7. 优点

- **方法创新**：首次将视觉预测与多模态理解在同一个自回归 VLA 框架中统一训练，直接针对 VLM 的弱点进行补充，思路清晰且实用。
- **框架简洁统一**：通过特殊的注意力掩码和 token 设计，将三种任务（理解、预测、动作）在单一模型内处理，无需额外组件。
- **实验全面**：覆盖模拟和真实世界，包含同分布、分布外、语义泛化、精确操控等多种场景，消融实验验证了每个模块的必要性。
- **公平对比**：在相同骨干下复现了基线（UP-VLA-RT-2、UP-VLA-phi-w/o-mmu），使结论具有说服力。

## 8. 不足与局限

- **计算资源未披露**：未提供训练的具体 GPU 型号、数量、耗时，不利于可重复性和成本评估。
- **真实实验规模有限**：只有 2000+ 演示，单一机器人平台，任务多样性有限，结果可能存在偶然性。
- **缺乏置信区间**：所有结果均为点估计（成功率/平均长度），未报告标准差或多次实验的误差，统计可靠性存疑。
- **预测质量不足**：可视化显示模型在预测背景颜色时出现偏差（将 D 场景背景误预测为 A/B/C 风格），说明未来预测的泛化能力仍待提升。
- **多模态理解精度仍有提升空间**：VQA 回答有时不准确，说明在有限数据下模型的理解能力不够鲁棒。
- **未讨论与更大模型/数据规模的扩展性**：论文基于 1.3B 的 Show-o，未测试更大模型或更多数据的效果，限制了其适用性结论的普适性。
- **动作表示简单**：仅使用离散 action token + 小网络回归，未探索更复杂的动作表示（如扩散策略），可能限制了对精细动作的建模。

（完）
