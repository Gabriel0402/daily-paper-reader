---
title: Object-Centric Prompt-Driven Vision-Language-Action Model for Robotic Manipulation
title_zh: 面向机器人操作的对象中心提示驱动视觉-语言-动作模型
authors: "Li, Xiaoqi, Xu, Jingyun, Zhang, Mingxu, Liu, Jiaming, Shen, Yan, Ponomarenko, Iaroslav, Xu, Jiahui, Heng, Liang, Huang, Siyuan, Zhang, Shanghang, Dong, Hao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_Object-Centric_Prompt-Driven_Vision-Language-Action_Model_for_Robotic_Manipulation_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 面向机器人操作的视觉-语言-动作模型
tldr: 机器人操作任务中，自然语言存在歧义，图像视频细节过多。本文提出以对象为中心的提示驱动VLA模型，通过简单2D视觉提示（如末端执行器位姿和接触后运动方向）显式表达低级动作和高级规划。训练中将视觉提示与语言图像融合，实现高效的机器人操作学习。实验表明该方法在多个操作任务上显著优于现有方法，提升了指令遵循的准确性和鲁棒性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1705, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1629, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1627, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1417, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1552, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 660, \"height\": 390, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 747, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-object-centric-prompt-driven-vision-language-action-model-for-robotic-manipulation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 263, \"label\": \"Table\"}]"
motivation: 现有方法难以通过单一模态准确传达操作目标的低级动作和高级规划。
method: 提出使用2D视觉提示作为显式多模态输入，结合VLA模型进行端到端训练。
result: 在多个机器人操作 benchmark 上取得领先性能，准确理解并执行复杂指令。
conclusion: 对象中心的视觉提示有效弥合了语言歧义与精确动作之间的鸿沟。
---

## Abstract
In robotic manipulation, task goals can be conveyed through various modalities, such as language, goal images, and goal videos. However, natural language can be ambiguous, while images or videos may offer overly detailed specifications. To address these challenges, we propose a novel approach using comprehensive multi-modal prompts that explicitly convey both low-level actions and high-level planning in a simple manner. Specifically, for each key-frame in the task sequence, our method allows for manual or automatic generation of simple and expressive 2D visual prompts overlaid on RGB images. These prompts represent the required task goals, such as the end-effector pose and the desired movement direction after contact. We develop a training strategy that enables the model to interpret these visual-language prompts and predict the corresponding contact poses and movement directions in SE(3) space. Furthermore, by sequentially executing all key-frame steps, the model can complete long-horizon tasks. This approach not only helps the model explicitly understand the task objectives but also enhances its robustness on unseen tasks by providing easily interpretable prompts. We evaluate our method in both simulated and real-world environments, demonstrating its robust manipulation capabilities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **研究动机**：在机器人操作任务中，如何准确、高效地向机器人传达任务目标是一个核心挑战。现有方法存在固有缺陷：**自然语言指令**常存在歧义（过于简略或过于冗长），**目标图像/视频**则包含大量与任务无关的背景信息，导致模型聚焦困难。
- **核心问题**：需要一种既能精确表达低级动作（如接触点、末端执行器姿态、接触后移动方向）又能承载高级规划（关键帧序列）的指令模态，并且对用户友好、易于生成。
- **整体含义**：本文提出 **CrayonRobo**，通过叠加在RGB图像上的2D“蜡笔风格”视觉提示（不同颜色代表不同语义）来显式表达动作目标，结合视觉-语言-动作（VLA）模型实现从提示到SE(3)空间操作指令的映射，从而提升任务的完成率和泛化鲁棒性。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：将任务分解为关键帧序列，每个关键帧使用2D视觉提示（如蓝色圆点表示接触点，红/绿线表示末端执行器z轴和y轴方向，黄线表示接触后移动方向）来传达子目标。模型学习解读这些提示并输出对应的SE(3)位姿和移动方向，通过依次执行各关键帧完成长时域任务。
- **关键技术细节**：
  - **输入形式**：视觉输入为带有彩色提示的RGB图像；语言输入为附带坐标数值（文本形式）的提示，用于消解视觉重叠歧义。
  - **模型架构**：基于开放VLA模型（ManipLLM的backbone），使用CLIP视觉编码器提取特征，LLaMa作为语言模型，仅微调注入的适配器（LoRA）和多模态投影模块，其余预训练参数冻结。
  - **训练策略**：设计渐进式输入对（从仅接触点、到逐步增加z轴、y轴、移动方向），引导模型理解各提示含义。预测输出为文本形式（离散化为100个bin），配合三项损失：
    - **文本监督损失 L_T**：交叉熵损失，监督方向向量的离散分类输出。
    - **正交损失 L_O**：用Gram-Schmidt损失强制预测的z轴和y轴方向正交。
    - **投影损失 L_P**：将预测的3D方向反投影到2D，与输入2D方向计算余弦相似度损失，建立2D-3D显式关联。
  - **推理方式**：支持**自动生成**（先用Grounded-DINO检测物体中心，再均匀采样候选方向，由GPT-4选择合理方向）和**手动绘制**两种方式。对于长任务，依次输入关键帧提示并执行。

## 3. 实验设计
- **模拟器环境**：使用SAPIEN平台和PartNet-Mobility数据集，包含约1500种物体形状，随机化相机视角。任务包括拉抽屉、开门、开笔记本电脑盖等需要平移和旋转的组合动作。
- **数据收集**：基于规则启发式方法模拟交互，记录成功的接触位姿和后续移动方向，并生成对应的2D提示。总计收集约10,000个训练样本，训练/测试按类别划分。
- **对比方法**：
  - Pure vision baseline：Flowbot3D
  - Language conditioned：ManipLLM
  - Vision Goal conditioned：Implicit3D (使用吸盘末端执行器)
  - Visual prompt conditioned：RT-trajectory（复现版）
  - Goal video conditioned：AVDC（生成视频质量评估）
- **评估指标**：操作成功率（成功/总测试样本数），成功标准为物体部件移动距离超过阈值。
- **实验类别**：
  - **主要对比实验**：在所有训练/测试任务上对比成功率（表1），包括seen和unseen任务。
  - **消融实验**：分析不同类型提示的影响（表2）：无方向、仅z轴、z+y轴、完整提示；以及移除视觉提示仅用语言的效果。
  - **噪声鲁棒性实验**：对2D方向提示添加10%~40%均匀噪声，观察性能变化（图5）。
  - **真实世界实验**：使用Franka Emika机械臂+Realsense 415相机，针对6种操作任务（含多步骤）进行测试，每任务5次尝试。其中还包括“无提示微调”实验：用之前成功预测的位姿作为GT，仅输入物体图像和机器人状态，微调模型使其无需后续提示即可执行。

## 4. 资源与算力
- 文中**未明确说明训练所用的GPU型号、数量和具体训练时长**。仅提及数据收集耗时约6-8小时（模拟器中）。模型微调仅更新LoRA适配器和投影模块，可推测训练相对高效，但具体算力细节缺失。

## 5. 实验数量与充分性
- **实验数量**：
  - 模拟器主要对比实验：覆盖16种任务（seen + unseen），每种方法列出单独成功率。
  - 消融实验：4种输入配置（表2） + 噪声5个水平 + 真实世界5-10次/任务 + 微调实验。
  - 整体实验总数中等偏上，但模拟器测试样本量未明确（如每个任务测试多少实例）。
- **充分性与客观性**：
  - 对比方法覆盖了不同流派（纯视觉、语言条件、视觉目标条件、视觉提示条件、视频条件），且使用相同训练/测试分割，公平性较好。
  - 消融实验系统地验证了各提示成分的贡献，以及提示噪声的容忍度。
  - 真实实验采用有限次数（5次/任务）且未提供置信区间，统计显著性较弱。
  - 未在公开标准benchmark（如RLBench、MetaWorld等）上评估，而是使用自定义任务集，可能影响泛化性评估。
  - 对比方法Flowbot3D、ManipLLM等原文使用吸盘，本文复现时一致采用吸盘，但同时展示了自己方法在手指夹爪上的结果，具有一定全面性。

## 6. 主要结论与发现
- **方法有效性**：CrayonRobo在seen任务上平均成功率0.75（吸盘）/0.73（手指夹爪），显著优于所有baseline；在unseen任务上0.79/0.72，同样领先。
- **提示类型的重要性**：逐步增加方向提示（z轴、y轴、移动方向）能持续提升性能；同时使用视觉+语言提示优于仅使用语言提示。
- **噪声鲁棒性**：在方向提示加入0%-20%噪声时性能几乎不变；30%-40%噪声时仍可完成任务但出现劣化，表明对非精准输入具有较好容忍度。
- **可迁移性**：真实世界零样本部署表现良好（如打开垃圾桶成功率9/10、打开微波炉7/10），且通过少量微调可实现无需提示的自主执行。

## 7. 优点
- **创新性**：首次系统性地将2D彩色线条/圆点作为多含义视觉提示，融合了接触点语义、位姿方向、接触后移动方向，表达力强且直观。
- **实用性**：同时支持自动生成（借助视觉检测+LLM）和手动绘制，降低用户使用门槛。
- **训练高效**：仅微调适配器和投影层，保留预训练知识，参数效率高。
- **鲁棒性**：对提示噪声和视角变化具有良好容忍度，真实世界零样本迁移成功。
- **长时域能力**：通过关键帧序列自然地分解长任务，并在真实世界多步骤任务中验证。

## 8. 不足与局限
- **未公开标准Benchmark评估**：实验基于自定义仿真任务和有限真实任务，未在RLBench、META-World或更多真实标准基准上评测，影响结果的可比较性。
- **真实实验样本量较小**：每个任务仅5-10次试次，缺乏统计显著性报告；未进行跨物体类别、光照变化等更全面的泛化测试。
- **算力细节缺失**：未提供GPU型号、数量、训练时长等关键信息，不利于复现和成本评估。
- **未端到端处理避障**：方法本身不包含碰撞避免，作者提及可结合外部运动规划器（如CUROBO）来弥补，但未在实验中验证。
- **对3D方向遮挡敏感**：若目标方向几乎垂直于相机，2D投影退化为点；作者提出添加微小噪声来增强可见性，但可能引入额外不确定性。
- **手动绘制依赖用户精度**：虽然实验显示对噪声有容忍，但极端错误输入仍会导致失败；自动生成依赖检测和LLM的可靠性。
- **无提示微调实验仅限于两个任务**，泛化性有限。

（完）
