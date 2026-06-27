---
title: Robotic Visual Instruction
title_zh: 机器人视觉指令
authors: "Li, Yanbang, Gong, Ziyang, Li, Haoyang, Huang, Xiaoqi, Kang, Haolan, Bai, Guangping, Ma, Xianzheng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_Robotic_Visual_Instruction_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 机器人任务的视觉指令
tldr: 本文提出机器人视觉指令（RoVI）新范式，通过手绘草图（包含箭头、圆圈等）编码时空信息指导机器人任务，并设计了VIEW流水线使机器人能够理解RoVI并生成精确动作，解决了自然语言指令缺乏空间精度的问题。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1788, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1784, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1777, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1799, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 875, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 876, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 863, \"height\": 379, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1803, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1806, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-robotic-visual-instruction-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 329, \"label\": \"Table\"}]"
motivation: 自然语言指令在机器人控制中缺乏空间精度，导致歧义。
method: 提出RoVI，使用对象中心、手绘符号表示空间时间指令；VIEW流水线将RoVI转化为策略。
result: 实验证明RoVI能有效指导机器人完成复杂操作任务。
conclusion: 视觉指令为机器人与人交互提供了更精确、直观的方式。
---

## Abstract
Recently, natural language has been the primary medium for human-robot interaction. However, its inherent lack of spatial precision for robotic control introduces challenges such as ambiguity and verbosity. To address these limitations, we introduce the ***Robotic Visual Instruction (RoVI)***, a novel paradigm to guide robotic tasks through an object-centric, hand-drawn symbolic representation. RoVI effectively encodes spatial-temporal information into human-interpretable visual instructions through 2D sketches, utilizing arrows, circles, colors, and numbers to direct 3D robotic manipulation. To enable robots to understand RoVI better and generate precise actions based on RoVI, we present ***Visual Instruction Embodied Workflow (VIEW)***, a pipeline formulated for RoVI-conditioned policies. This approach leverages Vision-Language Models (VLMs) to interpret RoVI inputs, decode spatial and temporal constraints from 2D pixel space via keypoint extraction, and then transform them into executable 3D action sequences. We additionally curate a specialized dataset of 15K instances to fine-tune small VLMs for edge deployment, enabling them to effectively learn RoVI capabilities. Our approach is rigorously validated across 11 novel tasks in both real and simulated environments, demonstrating significant generalization capability. Notably, VIEW achieves an 87.5% success rate in real-world scenarios involving unseen tasks that feature multi-step actions, with disturbances, and trajectory-following requirements. Code and Datasets in this paper will be released soon.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自然语言（NL）是当前人机交互的主要媒介，但缺乏空间精度，导致歧义和冗长，尤其难以精确描述位置、方向、距离等空间信息。此外，在图书馆、医院等公共环境中，语音交流可能不适宜。
- **整体含义**：提出一种全新的交互范式——**机器人视觉指令（RoVI）**，通过手绘草图（箭头、圆圈、颜色、数字）编码时空信息，以对象为中心的方式指导3D机器人操作，实现用户友好、可解释且空间精确的人机交互。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：用2D手绘符号语言代替自然语言，将时空信息压缩为人类可理解的视觉指令，再通过VLM+关键点提取将其转化为3D动作序列。
- **关键技术细节**：
  - **RoVI设计**：基础图元包括箭头（表示轨迹和方向）、圆圈（表示可操作点）。颜色/数字表示时间序列。将任务分解为“从A到B移动”、“旋转物体”、“拾取/选择”三种对象中心运动。
  - **VIEW流水线**：分为三个组件：
    1. **VLM（fθ）**：输入RoVI v、初始观测图X、默认提示，生成语言响应（任务定义、细粒度规划）和可执行代码函数（如move()、grasp()）。
    2. **关键点模块（fδ）**：用YOLOv8从RoVI中提取起点、路径点、终点的2D坐标，作为时空约束。
    3. **低层策略（π）**：将2D关键点通过深度图映射到3D，形成末端执行器位姿序列，通过代价函数最小化执行平移或旋转动作。代价函数：Li(t)=αi δtrans(t)+(1-αi)δrot(t)，δtrans为欧氏距离，δrot为角度差。
  - **多步任务分解**：根据颜色/数字标识将高层任务拆分为单步子任务。
- **公式/算法流程**：提出关键点条件策略，步骤：状态观测→代价最小化→关键点转移，直到所有关键点完成。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集**：自建**RoVI Book**数据集，15K图像-文本问答对，从Open X-Embodiment中选取，覆盖64%单步和36%多步任务（移动、旋转、拾取、开/关抽屉等）。包含手绘和几何两种风格，每个任务3-8种视觉变体。
- **场景**：真实环境（UFACTORY X-Arm 6和UR5机械臂，RealSense D435深度相机）8个任务；模拟环境（SAPIEN+SIMPLER）3个任务。所有任务和环境均为未见过的。
- **Benchmark**：动作成功率、时空对齐度（6点Likert量表）。
- **对比方法**：
  - 真实环境：CoPa（GPT-4o+VLM+Set-of-Mark）、VoxPoser（GPT-4o）。
  - 模拟环境：RT-1-X、Octo（语言条件/目标图像条件）。
  - RoVI理解评估：GPT-4o、Gemini-1.5 Pro、Claude 3.5-Sonnet、LLaVA-13B（RoVI Book微调）等，含大规模和小模型。

## 4. 资源与算力

- 文中明确提到：使用**NVIDIA A40 GPU**进行LLaVA-7B/13B的LoRA微调，训练1个epoch，学习率2e-4。未说明具体GPU数量、训练总时长，也未提及YOLOv8训练的资源需求。总体来说算力消耗适中，但细节不够完整。

## 5. 实验数量与充分性

- **实验数量**：
  - 真实环境：8个任务（含单步复杂场景和多步骤长程任务），每个10次试验。
  - 模拟环境：3个任务，每个10次试验。
  - RoVI理解评估：8种VLM在11个任务上评估“任务&规划”成功率。
  - 消融实验：绘图风格对比（几何 vs 松散）；关键点模块对比4种检测模型（GDINO、OWL-ViT、OWL-V2、YOLOv8）。
- **充分性**：实验覆盖了真实与模拟、单步与多步、有干扰物等多样场景，对比了多种基线（语言、目标图像、端到端VLA），消融研究充分。但受限于任务数量（11个）和每个任务仅10次试验，统计显著性可能有限。公平性方面，基线均使用相同VLM（GPT-4o）进行了公平对比。

## 6. 论文的主要结论与发现

- **RoVI效果显著**：在真实环境8个任务中，VIEW-LLaVA-13B（RoVI Book）平均成功率87.5%，远优于VoxPoser（43.8%）和CoPa（45%）。在模拟环境中也显著优于RT-1-X和Octo。
- **VLM能理解RoVI**：GPT-4o、Claude等大模型通过上下文学习即可理解RoVI，但小模型（<13B）需微调才能掌握。LLaVA-13B经RoVI Book微调后，在多步任务上表现稳定。
- **关键点模块优势**：YOLOv8在提取RoVI符号关键点方面优于开放词汇检测模型（GDINO、OWL-ViT等），误差更小、mAP更高。
- **绘图风格影响**：几何风格（结构化）比松散风格更有利于VLM理解。

## 7. 优点

- **方法创新**：首次提出用对象中心的手绘符号作为机器人指令，平衡了用户友好性、可解释性和时空对齐性，填补了视觉提示在机器人操作领域的空白。
- **完整流水线**：VIEW将2D视觉指令转化为3D动作序列，利用VLM进行高层理解+关键点模块提供精确空间约束，设计清晰且实用。
- **开源数据集**：提供15K标注数据，促进后续研究。
- **泛化能力**：在未见过任务、新物体、杂乱环境、多步骤长程任务中均表现优异。
- **消融实验全面**：评估了绘图风格、关键点检测方法、不同VLM等，结论可靠。

## 8. 不足与局限

- **任务数量有限**：仅测试11个任务，且每个任务仅10次试验，统计可靠性和泛化性有待更大规模验证。
- **数据集规模较小**：RoVI Book仅15K样本，且源自Open X-Embodiment的有限技能类型，可能无法覆盖复杂多变的真实场景。
- **资源细节缺失**：未明确说明训练YOLOv8和微调LLaVA的GPU数量、时间等，影响可复现性。
- **依赖深度相机**：关键点3D映射依赖RGB-D相机精度和校准，在远距离或反光表面可能失效。
- **仅支持特定图元**：当前RoVI仅支持箭头和圆圈，无法表达更复杂的操作（如“推”、“拉”的力度或“旋转”的角度大小）。
- **实时性未讨论**：VLM推理（尤其大模型）可能影响实时交互，本文未评估执行延迟。

（完）
