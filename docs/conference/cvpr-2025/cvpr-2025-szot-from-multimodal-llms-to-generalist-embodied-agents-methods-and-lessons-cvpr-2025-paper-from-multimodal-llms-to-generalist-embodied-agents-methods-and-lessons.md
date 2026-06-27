---
title: "From Multimodal LLMs to Generalist Embodied Agents: Methods and Lessons"
title_zh: 从多模态大语言模型到通用具身智能体：方法与经验
authors: "Szot, Andrew, Mazoure, Bogdan, Attia, Omar, Timofeev, Aleksei, Agrawal, Harsh, Hjelm, Devon, Gan, Zhe, Kira, Zsolt, Toshev, Alexander"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Szot_From_Multimodal_LLMs_to_Generalist_Embodied_Agents_Methods_and_Lessons_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 将多模态大语言模型适配为通用具身智能体，使用多体态动作分词器和强化学习
tldr: 本文提出将多模态大语言模型（MLLM）转化为通用具身智能体（GEA），通过多体态动作分词器实现跨领域动作输出，并利用监督学习和在线强化学习训练，在具身AI、游戏、UI控制等任务上展现出通用能力，为VLM到VLA的转化提供了重要经验。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1612, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 215, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 343, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1673, \"height\": 1016, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-szot-from-multimodal-llms-to-generalist-embodied-agents-methods-and-lessons-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 277, \"label\": \"Table\"}]"
motivation: MLLM在传统语言视觉任务外，有望扩展到具身智能等领域。
method: 设计多体态动作分词器，统一输出动作；使用大规模具身体验监督学习和在线RL。
result: GEA在多个具身任务中表现优异。
conclusion: 数据、动作分词和RL是构建通用具身智能体的关键。
---

## Abstract
We examine the capability of Multimodal Large Language Models (MLLMs) to tackle diverse domains that extend beyond the traditional language and vision tasks these models are typically trained on. Specifically, our focus lies in areas such as Embodied AI, Games, UI Control, and Planning. To this end, we introduce a process of adapting an MLLM to a Generalist Embodied Agent (GEA). GEA is a single unified model capable of grounding itself across these varied domains through a multi-embodiment action tokenizer. GEA is trained with supervised learning on a large dataset of embodied experiences and with online RL in interactive simulators. We explore the data and algorithmic choices necessary to develop such a model. Our findings reveal the importance of training with cross-domain data and online RL for building generalist agents. The final GEA model achieves strong generalization performance to unseen tasks across diverse benchmarks compared to other generalist models and benchmark-specific approaches.

---

## 论文详细总结（自动生成）

# 从多模态大语言模型到通用具身智能体：方法与经验

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多模态大语言模型（MLLM）在传统语言和视觉任务上表现优异，但能否扩展到更广泛的决策领域（如具身AI、游戏、UI控制、规划）是一个开放问题。现有方法通常针对特定领域设计，缺乏统一的通用智能体。
- **背景**：视觉-语言-动作模型已在机器人、网页和UI控制中成功应用，但如何将单个MLLM适配为跨多种具身形态（如机械臂、移动机器人、游戏角色、UI界面）的通用智能体仍面临挑战：任务需要物理推理、长程规划、部分可观测性，且不同领域的动作空间差异巨大。
- **核心含义**：本文提出将MLLM转化为通用具身智能体（GEA），通过统一动作分词和两阶段训练（监督微调+在线强化学习），使单一模型能够泛化到多种未见过任务和环境，为构建决策基础模型提供重要经验。

## 2. 方法论

### 2.1 核心思想
- **统一动作接口**：设计多体态动作分词器（multi-embodiment action tokenizer），将连续和离散动作空间统一映射为LLM词汇表内的token序列，使模型能输出任意环境下的动作。
- **两阶段训练**：
  - **阶段1：监督微调（SFT）**：在包含220万条轨迹的大规模具身体验数据集上微调整个MLLM，学习从观测和指令到动作的映射。
  - **阶段2：在线强化学习（RL）**：使用PPO算法在部分可交互模拟器中进行在线RL训练，同时联合SFT损失以防止遗忘。

### 2.2 关键技术细节
- **动作分词器**：采用残差向量量化-变分自编码器（Residual VQ-VAE）对连续动作进行编码，每个连续动作被表示为M个离散token（使用2个码本，每个码本512个token，token维度1024）。所有连续动作空间共享同一个分词器/解分词器，通过填充和截断适应不同维度。
- **输入表示**：模型接收环境提示、任务指令（自然语言）、以及最近c步的观测图像和动作历史（c=3）。
- **基础模型**：基于LLaVA-OneVision（支持长上下文和序列图像），并同时实验了MM1.5等模型。
- **RL细节**：
  - 值函数网络为MLP，输入来自MLLM最后层的激活和视觉嵌入的平均池化，可选输入特权状态信息（仅训练时使用）。
  - 使用PopArt归一化处理不同环境的奖励分布差异。
  - 采用约束解码确保生成的动作token属于当前环境的有效动作空间。
  - 采用LoRA微调LLM部分，冻结其他组件。
- **损失函数**：
  - SFT：交叉熵损失，最大化动作序列的对数似然。
  - 总损失：\(\mathcal{L}_{GEA} = \sum_{i} \mathcal{L}_{PPO}(\mathcal{M}_i) + \omega \sum_{i} \mathcal{L}_{SFT}(\mathcal{D}_i)\), 其中\(\omega=0.1\)。

## 3. 实验设计

### 3.1 使用的数据集与场景
| 领域 | 数据集/环境 | 动作类型 | 轨迹数 | 数据来源 |
|------|------------|----------|--------|----------|
| 静态操作 | OpenX（多机器人）、Meta-World、CALVIN、Maniskill | 连续（末端执行器、关节速度/位置） | 1.2M+45k+18k+5k | 多种机器人/脚本/人类 |
| 移动操作 | Habitat Pick、Habitat Place | 连续（关节位置+基座） | 各50k | RL专家 |
| 导航 | Habitat Nav、BabyAI | 连续/离散 | 13k/50k | 最短路径 |
| 视频游戏 | Procgen（16个游戏）、Atari | 离散 | 320k/286k | RL专家 |
| 规划 | LangR | 离散 | 150k | RL专家 |
| UI控制 | AndroidControl | 混合 | 14k | 人类 |
| 视觉语言数据 | VQAv2、OKVQA、A-OKVQA、GQA、LLaVA-Instruct-150k | - | - | 公开数据集 |

### 3.2 Benchmark与测试
- 测试所有领域的新任务泛化（如新物体位置、新场景、新指令、新背景等）。
- 对于AndroidControl，采用轨迹匹配方式评估。
- 报告指标：成功率（%），Procgen和Atari报告专家分数百分比。

### 3.3 对比方法
- **通用智能体**：Gato（基于Transformer的通用智能体）。
- **领域专家**：各领域的专用方法，如MLLM+IL（Szot等人）、3D Diffuser Actor、IL+PPO、Multi-Game DT等。
- **消融实验**：对比仅SFT（GEA-Base）、仅在线RL、迭代SFT、离线RL（IQL）等变体。
- **MLLM后端**：比较LLaVA-OneVision（0.5B/7B）和MM1.5（1.2B/6.4B）不同规模。

## 4. 资源与算力

- **SFT阶段**：使用8节点，每节点8块H100 GPU，训练75k步，约2天。全局batch size=256。
- **RL阶段**：使用8节点，每节点8块H100 GPU，其中每节点3个GPU运行Habitat Pick、3个运行Procgen、2个运行LangR。训练累计100M环境步，约1天。
- **模型大小**：最终GEA基于7B参数的LLaVA-OneVision。
- **说明**：论文明确给出了训练时长、硬件配置和并行环境数量，算力资源描述详细。

## 5. 实验数量与充分性

- **主实验**：在9个基准（Meta-World、CALVIN、Maniskill、Habitat Pick/Place、Procgen、Atari、BabyAI、Habitat Nav、AndroidControl、LangR）上评估GEA的零样本泛化，对比多种基线方法。
- **消融实验**：
  - 多领域数据 vs 单领域数据（表4）。
  - RL vs 仅SFT vs 迭代SFT vs 离线RL（图4）。
  - MLLM预训练权重的重要性（随机初始化LLM/视觉编码器/全部，表4）。
  - 不同基础MLLM和参数规模的影响（图5）。
  - RL对非RL任务的影响（表3）。
  - 附录中还讨论了不同数据集间的迁移性（附录G.4）。
- **充分性评价**：实验覆盖了多种具身领域，消融实验设计合理，对比了足够多的基线（包括通用和专用方法）。但部分对比（如Maniskill中RL专家方法）依赖于特权信息（仿真状态），标注为灰色不公平比较，体现了客观性。
- **公平性**：论文注意到基线方法可能使用额外输入（如点云、真实状态），在表中用灰色标注并说明不是公平比较，体现了实验设计的严谨性。

## 6. 主要结论与发现

- **GEA达到或接近领域专家性能**：在CALVIN、Habitat Pick、Procgen、Meta-World等基准上超越或匹配专用方法，证明了通用智能体的潜力。
- **多领域数据带来跨领域增益**：在多个领域上，使用所有领域数据训练比仅使用单领域数据性能更高（表4）。
- **在线RL至关重要**：在Habitat Pick任务中，在线RL将GEA-Base从57%提升至83%，而迭代SFT和离线RL反而下降（图4）。
- **MLLM预训练是关键**：全预训练MLLM显著优于仅初始化LLM或视觉编码器，视觉编码器尤为重要。
- **模型规模影响性能**：7B模型优于0.5B/1.2B模型，但不同MLLM类（LLaVA vs MM1）在相同规模下性能相近（图5）。
- **RL不会损害其他任务**：通过联合SFT损失，RL训练仅提升目标任务性能，对其他任务无负面影响（表3）。

## 7. 优点

- **统一动作分词器设计**：创新地使用RVQ将不同连续和离散动作空间统一到LLM词汇表，使单一模型能控制多种体态。
- **两阶段训练策略**：先SFT后RL，既利用大规模离线数据又通过在线交互修正分布偏移，效果优于纯SFT或纯RL。
- **全面的实验验证**：覆盖操作、导航、游戏、UI、规划五大领域，消融实验系统深入，对比基线考虑周到。
- **开源与可复现性**：论文提供了架构细节、训练超参数、数据来源等，便于后续研究复现和改进。
- **实证显示多领域数据增益**：通过消融实验证实了跨领域数据训练的优势，为通用智能体数据收集提供了指导。

## 8. 不足与局限

- **部分领域性能欠佳**：在Maniskill、Atari、AndroidControl等任务上表现不够理想，尤其在Maniskill中远低于RL专家（但专家使用特权信息）。
- **RL覆盖领域有限**：仅对3个环境（Habitat Pick、LangR、Procgen）进行在线RL训练，其他领域仍依赖SFT，可能限制了性能上限。
- **依赖模拟器**：RL阶段需要可交互模拟器，对于现实世界的机器人任务难以直接应用。
- **泛化能力仍有局限**：论文指出GEA还不能像语言基础模型那样零样本控制任意体态和任意环境，距离真正的“决策基础模型”尚有差距。
- **长上下文能力利用不足**：当前仅使用3步历史观测，可能限制了在高度部分可观测环境（如Habitat Nav）中的表现。
- **未进行现实世界验证**：全部实验均在仿真中进行，现实世界的噪声和分布偏移尚未测试。
- **统计显著性未报告**：实验多数报告单次性能，未提供多次重复的置信区间或标准差。

（完）
