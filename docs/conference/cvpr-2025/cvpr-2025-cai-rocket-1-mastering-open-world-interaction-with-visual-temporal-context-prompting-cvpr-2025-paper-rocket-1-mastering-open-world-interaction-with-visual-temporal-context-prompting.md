---
title: "ROCKET-1: Mastering Open-World Interaction with Visual-Temporal Context Prompting"
title_zh: ROCKET-1：基于视觉-时序上下文提示的开放世界交互掌握
authors: "Cai, Shaofei, Wang, Zihao, Lian, Kewei, Mu, Zhancun, Ma, Xiaojian, Liu, Anji, Liang, Yitao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Cai_ROCKET-1_Mastering_Open-World_Interaction_with_Visual-Temporal_Context_Prompting_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 用于具身决策的VLM，结合视觉-时序提示
tldr: 该论文提出ROCKET-1框架，针对VLM在开放世界具身决策中的挑战，设计了一种新颖的视觉-时序上下文提示协议，作为VLM与策略模型之间的通信桥梁。该协议利用过去观察中的物体分割来传递空间信息，弥补了语言无法表达详细空间信息的缺陷。实验证明ROCKET-1在复杂开放世界任务中显著提升了分层智能体的决策性能，为VLM在具身AI中的应用提供了有效范式。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1724, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1690, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1796, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1731, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1643, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1803, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1789, \"height\": 409, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 876, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1816, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1814, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 878, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-cai-rocket-1-mastering-open-world-interaction-with-visual-temporal-context-prompting-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 876, \"height\": 378, \"label\": \"Table\"}]"
motivation: VLM在具身决策中难以将低级观察与高级抽象概念桥接，语言无法传达空间细节。
method: 提出视觉-时序上下文提示协议，利用历史分割传递空间信息，连接VLM与策略模型。
result: 在开放世界任务中显著提升分层智能体的交互与规划能力。
conclusion: 视觉-时序上下文提示有效弥合了VLM与具身策略之间的信息鸿沟。
---

## Abstract
Vision-language models (VLMs) have excelled in multimodal tasks, but adapting them to embodied decision-making in open-world environments presents challenges. One critical issue is bridging the gap between discrete entities in low-level observations and the abstract concepts required for effective planning. A common solution is building hierarchical agents, where VLMs serve as high-level reasoners that break down tasks into executable sub-tasks, typically specified using language. However, language suffers from the inability to communicate detailed spatial information. We propose visual-temporal context prompting, a novel communication protocol between VLMs and policy models. This protocol leverages object segmentation from past observations to guide policy-environment interactions. Using this approach, we train ROCKET-2, a low-level policy that predicts actions based on concatenated visual observations and segmentation masks, supported by real-time object tracking from SAM2. Our method unlocks the potential of VLMs, enabling them to tackle complex tasks that demand spatial reasoning. Experiments in Minecraft show that our approach enables agents to achieve previously unattainable tasks, with a 76% absolute improvement in open-world interaction performance. Codes are available at https://craftjarvis.github.io/ROCKET-1.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：Vision-Language Models（VLMs）在开放世界具身决策任务中面临“语义鸿沟”挑战——低级视觉观测中的离散实体难以与高级规划所需的抽象概念对齐。现有分层智能体架构通常使用语言作为高层推理器（VLM）与低层策略之间的通信协议，但语言无法有效传达详细的空间信息（例如在多个同类物体中指定特定一个）。
- **整体背景**：Minecraft 作为高度开放的沙盒环境，是测试通用人工智能（AGI）适应性和长期规划能力的理想平台。已有研究如 VPT、STEVE-1、GROOT-1 等，但均存在空间信息表达不足或依赖未来图像预测（易幻觉）等局限。
- **研究动机**：受人类任务执行方式启发（人类不预想结果，而是持续关注目标物体并利用记忆连接过去与当前视觉场景），作者提出一种全新的通信协议——**视觉-时序上下文提示**（Visual-Temporal Context Prompting），旨在弥合 VLM 与策略模型之间的空间信息鸿沟。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将“过去观察中的物体分割掩码”作为任务提示，结合交互类型（如使用、靠近、切换、挖掘）引导低层策略与环境交互，从而替代语言指令。
- **关键技术细节**：
  - **通信协议**：视觉-时序上下文提示由高层推理器（VLM）生成：对当前观测中的兴趣区域进行物体分割，并输出一组交互类型（skill primitives）；低层策略 ROCKET-1 接收这些分割掩码和交互类型，预测下一步动作。
  - **ROCKET-1 架构**（图 3）：
    - 输入：当前观测图像 \(o_t\)、物体分割掩码 \(m_t\)、交互类型 \(c_t\)。
    - 将 \(o_t\) 与 \(m_t\) 像素级拼接为 4 通道图像，送入视觉骨干网络（EfficientNet-B0，第一层从 3 通道扩展为 4 通道，新增参数初始化为 0）进行深度融合。
    - 使用 Self-Attention Pooling 提取特征。
    - 通过 TransformerXL 建模时序依赖，并结合交互类型 \(c_t\) 预测动作 \(\hat{a}_t\)。
    - 训练时采用随机丢弃策略（以概率 \(p=0.75\) 随机丢弃分割掩码和交互类型），迫使模型从过去上下文（视觉-时序上下文）推断意图。
  - **向后轨迹重标注方法**（Backward Trajectory Relabeling）：
    - 从已有轨迹数据（仅含观测和动作）中自动生成分割掩码和交互类型。
    - 利用 OpenAI 提供的人类游戏数据（1.6B 帧），其元信息已包含交互事件（如 kill entity, mine block, use item 等）。
    - 对于每个交互事件，在事件前一帧使用固定位置边界框和中心点作为提示，调用 SAM-2（或在 Minecraft 中使用 Grounded SAM）逆向追踪，获取过去若干帧的物体分割。
    - 额外定义了“导航”交互类型：若玩家移动超过阈值，则将该段最后面对的目标物体作为导航目标，同样用 SAM-2 逆向标记。
  - **分层智能体集成**（图 5）：
    - 高层：GPT-4o 根据观测分解任务并描述交互目标；Molmo 72B 生成目标物体的 (x,y) 坐标；SAM-2 根据坐标生成初始分割并在后续帧中跟踪；ROCKET-1 根据分割和交互类型执行动作。
    - GPT-4o 和 Molmo 以低频运行（节省算力），SAM-2 和 ROCKET-1 以环境频率（20 FPS）运行。

## 3. 实验设计：数据集、Benchmark 与对比方法

- **环境**：未修改的 Minecraft 1.16.5，动作空间为鼠标+键盘，观测为 640×360 RGB 图像。
- **训练数据**：OpenAI 提供的人类游戏数据集（1.6B 帧），包含元信息（交互事件）。ROCKET-1 训练时从该数据中通过向后轨迹重标注生成分割和交互类型标签。
- **提出的 Benchmark**：**Minecraft Interaction Benchmark**，包含 6 大类共 12 个任务：
  - Hunt（猎杀指定栅栏内的羊）、Mine（挖掘特定位置的矿石）、Interact（与特定物体交互）、Navigate（导航到特定位置）、Tool（使用工具）、Place（在指定方块旁放置物品，如 oak door on diamond block）。
  - 强调空间定位和零样本泛化（部分任务从未出现在训练集中）。
- **对比方法**：
  - VPT-bc（行为克隆微调版）
  - STEVE-1（文本条件版本）
  - GROOT-1（参考视频条件策略）
  - 对于分层架构实验，还比较了 DEPS（语言协议）、MineDreamer（未来图像协议）、OmniJarvis（隐编码协议）。
- **评估配置**：每个任务测试 32 次，报告平均成功率。高层推理器提供两种方式：人工（Oracle）和 Molmo 72B。

## 4. 资源与算力

- **论文未明确说明**训练 GPU 型号、数量、总时长等具体算力信息。仅提及大部分训练参数遵循先前工作（如 VPT、GROOT），但未给出详细硬件配置。这一点需要在总结中明确指出。

## 5. 实验数量与充分性

- **主要实验**（表1）：在 12 个交互任务上与 3 个基线对比（VPT、STEVE-1、GROOT-1），每个任务 32 次，统计成功率。
- **长时任务实验**（表3）：在 7 个长时任务上（如获得木镐、钻石、黑曜石等）与 3 种分层架构对比，每个任务运行 20-100 次。
- **消融实验**（表4、表5）：探究条件融合位置（在 Transformer 层 vs 视觉骨干中融合交互类型）、不同 SAM-2 模型大小对性能和速度的影响。
- **充分性评价**：实验覆盖了基本交互能力、长时规划、零样本泛化、以及设计选择消融，对比基线全面（包括 VPT、STEVE-1、GROOT-1 以及三种分层通信协议）。结果充分且具有说服力。所有实验在 Minecraft 同一环境中进行，评估公正（使用相同 Prompt、未泄露测试数据）。但未在其他开放世界环境（如机器人操控）中验证泛化性。

## 6. 论文的主要结论与发现

- **主要结论**：视觉-时序上下文提示协议有效解决了 VLM 在具身决策中空间信息表达不足的问题。ROCKET-1 在 Minecraft Interaction Benchmark 上取得了 **82%**（MOLMO 推理器）和 **95%**（人工推理器）的平均成功率，显著优于所有基线（STEVE-1 19%、GROOT-1 9%、VPT 7%）。绝对提升达 76% 以上。
- **长时任务**：在需要复杂规划的任务（如获得黑曜石、粉红羊毛）上，先前基线全部失败（0%），而 ROCKET-1 分别达到 50% 和 70% 的成功率。
- **关键发现**：
  - 交互类型在 Transformer 层融合优于在视觉骨干中融合（表4：Hunt 91% vs 72%，Mine 78% vs 69%）。
  - SAM-2 的跟踪能力对性能至关重要（表5：无 SAM-2 时低频率 Prompt 导致任务完全失败，加入 SAM-2 后恢复至 82-91%）。

## 7. 优点

- **创新性**：提出视觉-时序上下文提示作为新的通信协议，直接利用历史分割传递空间信息，避免了语言歧义和未来图像预测的幻觉问题。
- **自动化标注**：向后轨迹重标注方法无需人工标注分割和交互类型，利用 SAM-2 和现成的动作元信息自动生成训练数据，可扩展性强。
- **模块化分层设计**：VLM 仅需低频运行，SAM-2 和 ROCKET-1 实时响应，兼顾推理质量和效率。
- **零样本泛化**：在从未见过的任务（如“在钻石块旁放置橡木门”）上仍能完成 91%（人工）或 72%（Molmo），表明策略学到了空间定位能力。
- **消融实验充分**：验证了融合位置、SAM-2 大小等设计选择，为后续研究提供了实用指导。

## 8. 不足与局限

- **环境局限性**：所有实验仅在 Minecraft 中进行，未在物理机器人或其他开放世界环境（如 Habitat、MetaWorld）中验证，泛化性存疑。
- **对预训练模型依赖强**：高层推理依赖于 GPT-4o 和 Molmo，这些模型并非免费开源，且计算成本高；SAM-2 也需要大量 GPU 推理。低层策略 ROCKET-1 本身也需要 1.6B 帧训练数据。
- **隐式假设**：假设交互物体在事件前一帧通常位于图像中央（用于固定边界框），可能不适用于所有场景（如目标物体在画面边缘被遮挡）。
- **未讨论失败案例分析**：论文未深入分析 ROCEKT-1 失败的场景（例如 SAM-2 跟踪丢失、Molmo 识别错误等），缺乏对错误模式的定性分析。
- **长期记忆不足**：TransformerXL 仅支持 128 帧历史，对于极长 horizon 任务（如建筑）可能需要更大的上下文窗口。
- **泛化到不同动作空间**：目前仅针对 Minecraft 的鼠标+键盘界面，未讨论如何迁移到连续动作控制的机器人场景。

（完）
