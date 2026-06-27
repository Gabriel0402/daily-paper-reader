---
title: "PhysVLM: Enabling Visual Language Models to Understand Robotic Physical Reachability"
title_zh: PhysVLM：使视觉语言模型理解机器人物理可达性
authors: "Zhou, Weijie, Tao, Manli, Zhao, Chaoyang, Guo, Haiyun, Dong, Honghui, Tang, Ming, Wang, Jinqiao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhou_PhysVLM_Enabling_Visual_Language_Models_to_Understand_Robotic_Physical_Reachability_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 8.0
evidence: VLM理解机器人物理可达性
tldr: 该论文提出PhysVLM，针对VLM在具身视觉推理中因缺乏物理可达性理解而产生不准确响应的问题，构建了统一的空间-物理可达性图（S-P Map）并集成到VLM中。S-P Map将不同机器人的物理可达性抽象为通用空间表示，从而使VLM能够生成更实际的操作建议。实验表明PhysVLM在多个机器人平台上显著提升了任务成功率，为VLM在机器人领域的应用提供了物理感知新维度。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1801, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1698, \"height\": 661, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1754, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 888, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 781, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 758, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 755, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 702, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-physvlm-enabling-visual-language-models-to-understand-robotic-physical-reachability-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 784, \"height\": 265, \"label\": \"Table\"}]"
motivation: 现有VLM缺乏对机器人物理可达性的理解，导致在具身推理中给出不切实际的建议。
method: 提出空间-物理可达性图（S-P Map）统一表示不同机器人的可达性，并集成入VLM。
result: 在多种机器人平台上提升了视觉推理任务的准确性和实用性。
conclusion: 集成物理可达性知识可以显著增强VLM在机器人任务中的可靠性。
---

## Abstract
Understanding the environment and a robot's physical reachability is crucial for task execution. While state-of-the-art vision-language models (VLMs) excel in environmental perception, they often generate inaccurate or impractical responses in embodied visual reasoning tasks due to a lack of understanding of robotic physical reachability. To address this issue, we propose a unified representation of physical reachability across diverse robots, i.e., Space-Physical Reachability Map (S-P Map), and PhysVLM, a vision-language model that integrates this reachability information into visual reasoning. Specifically, the S-P Map abstracts a robot's physical reachability into a generalized spatial representation, independent of specific robot configurations, allowing the model to focus on reachability features rather than robot-specific parameters. Subsequently, PhysVLM extends traditional VLM architectures by incorporating an additional feature encoder to process the S-P Map, enabling the model to reason about physical reachability without compromising its general vision-language capabilities. To train and evaluate PhysVLM, we constructed a large-scale multi-robot dataset, Phys100K, and a challenging benchmark, EQA-phys, which includes tasks for six different robots in both simulated and real-world environments. Experimental results demonstrate that PhysVLM outperforms existing models, achieving a 14% improvement over GPT-4o on EQA-phys and surpassing advanced embodied VLMs such as RoboMamba and SpatialVLM on the RoboVQA-val and OpenEQA benchmarks. Additionally, the S-P Map shows strong compatibility with various VLMs, and its integration into GPT-4o-mini yields a 7.1% performance improvement.

---

## 论文详细总结（自动生成）

# PhysVLM: 使视觉语言模型理解机器人物理可达性 —— 论文详细总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：现有的视觉语言模型（VLM）在机器人具身推理任务中，虽然具备强大的环境感知能力，但缺乏对机器人自身物理可达性的理解。这导致模型往往做出不准确或不切实际的回答（例如，建议机器人去抓取实际不可及的物体），从而影响任务执行的成功率和安全性。
- **背景**：机器人的物理可达性因机械臂构型（关节范围、连杆长度等）而异，现有VLM在训练中未包含此类约束信息，无法直接推理“某个物体是否在机器人工作空间内”。此外，不同机器人的参数差异大，难以统一建模。
- **整体意义**：通过引入一种与机器人构型无关的、统一的可达性表示（S-P Map），并设计能够融合该信息的VLM架构（PhysVLM），从而在保持通用视觉语言能力的同时，赋予VLM对物理可达性的理解，提升具身任务推理的可靠性和实用性。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将机器人的物理可达性抽象为一种统一的空间表示（S-P Map），然后通过一个额外的特征编码器将S-P Map与视觉、文本信息融合，使模型能够同时利用视觉上下文和物理约束进行推理。
- **关键技术细节**：
  - **S-P Map生成**：
    1. 离线阶段：利用机器人DH参数和关节角度范围，通过正向运动学采样生成可达工作空间的体素网格（voxel grid）并存储。
    2. 在线阶段：将机器人自顶向下视角的深度图转换为点云，利用相机与机器人的外参将其变换到机器人坐标系，再通过体素网格查找判断每个点是否在可达工作空间内，只保留可达点。
    3. 将可达点投影回图像平面，在原深度图上标记不可达区域为灰色并勾勒边界，最终得到S-P Map。该图将物理可达性抽象为空间区域，不暴露机器人具体参数。
  - **PhysVLM架构**：
    - 双分支设计：视觉分支（SigLip-400M ViT）提取RGB图像特征；约束分支（相同ViT）提取S-P Map特征。
    - 两个分支经过Max Pooling下采样和MLP映射后，通过融合层合并，再与语言指令（Qwen-2.5-Instruct-3B LLM解码器）一起输入LLM生成响应。
    - 这种设计避免了直接用共享视觉编码器处理S-P Map带来的干扰，确保通用视觉能力不受影响。
  - **训练过程**：
    - 两阶段训练：第一阶段仅训练投影层，对齐多模态特征（使用LLaVA-Pretrain和OpenX-Embodiment数据）；第二阶段全参数微调（使用Phys100K、ShareGPT4V、RoboVQA）。
    - 数据构造：Phys100K包含来自RoboVQA、ScanNet、OpenX-Embodiment和PyBullet的约10万样本，并利用DepthAnything-v2生成缺失的深度图，Grounding DINO+SAM2获取物体分割标签，自动或半自动生成涉及可达性的问答对。

## 3. 实验设计
- **数据集与场景**：
  - **Phys100K**：大规模多机器人数据集，含20K（RoboVQA）+10K（ScanNet）+60K（OpenX-Embodiment）+10K（PyBullet模拟），覆盖UR5、FR5、CR5、FRANKA四种机械臂。
  - **EQA-phys基准**：针对物理可达性的具身QA基准，包含模拟环境（200样本，1000问题）和真实环境（UR3、XArm6机器人，60样本，300问题），所有真实问题由专家手工标注。
- **对比方法**：
  - API-based VLM：GPT-4o、GPT-4o-mini、Claude-3.5，以及这些模型+S-P Map的变体。
  - Embodied VLM：SpatialVLM、SpatialBot、3D-VLA、RoboMamba。
- **评估指标**：
  - EQA-phys：LLM评分（1–5分，转为百分比）。
  - RoboVQA-val：BLEU-1/2/3/4。
  - OpenEQA：EM-EQA（精确匹配）得分。
  - 任务规划：每个任务类型执行10次，平均成功率。

## 4. 资源与算力
- 文中明确说明：使用**八块A800 GPU**，训练总时长**48小时**，分两阶段各训练一个epoch。第一阶段批次大小128、学习率1e-3；第二阶段批次大小64、学习率1e-5。最终模型为PhysVLM-3B（参数量约3B）。

## 5. 实验数量与充分性
- **主要实验组**：
  - EQA-phys基准上：对比8种基线（含S-P Map注入的变体），涵盖4种模拟机械臂+2种真实机械臂。
  - RoboVQA-val：对比4种已有方法，以BLEU分数比较。
  - OpenEQA基准：对比5种方法（含GPT-4V和GPT-4o）。
  - 真实任务规划实验：对比5种基线，分“全部物体可达”和“部分物体可达”两种场景。
  - 消融实验：
    1. S-P Map有效性（替换为深度图或移除输入）（Table 5）。
    2. 额外特征编码器 vs. 共享编码器（Table 6）。
    3. 训练数据贡献（移除PyBullet或其他数据集）（Table 7）。
  - 定性分析（图4）：展示与GPT-4o、SpatialBot的视觉比较。
- **充分性评估**：实验覆盖了模拟与真实环境、多种机器人型号、多种VLM基线（包括API和自有模型）、多个消融变量，验证了各组件贡献。评估指标多样，结果客观。整体实验设计较为充分和公平。

## 6. 主要结论与发现
- PhysVLM在EQA-phys上平均得分71%，比GPT-4o高14%，显著优于所有对比的VLM。
- 在RoboVQA-val和OpenEQA基准上，PhysVLM在BLEU-4和EM-EQA上分别超越或接近GPT-4o，且优于其他具身VLM（如RoboMamba、SpatialVLM）。
- S-P Map具有跨模型兼容性：将S-P Map注入GPT-4o-mini可带来7.1%性能提升，注入Claude-3.5或GPT-4o同样有效。
- 消融实验证明：S-P Map比纯深度图更有效；独立约束编码器优于共享编码器；完整数据集（Phys100K）对性能至关重要。
- 零样本真实机器人测试表明模型能泛化到未见过的机器人（UR3、XArm6）和环境，但模拟到真实的域差距仍然存在。

## 7. 优点
- **创新性**：首次提出将机器人物理可达性抽象为统一的S-P Map，并设计独立的约束编码器进行融合，解决了VLM缺乏物理约束理解的核心问题。
- **通用性**：S-P Map与具体机器人参数解耦，可适用于任意机械臂；双分支架构保证了通用视觉语言能力不受损害。
- **数据贡献**：构建了大规模多机器人数据集Phys100K和专门的可达性基准EQA-phys，填补了该领域的空白。
- **实验全面**：涵盖多机器人（6种）、多环境（模拟+真实）、多任务（QA、规划、零样本泛化），并与多种先进模型（GPT-4o、Claude等）公平对比。

## 8. 不足与局限
- **零样本真实性能下降**：在真实机器人（UR3、XArm6）上的得分（约63–64%）低于模拟环境（约71–78%），说明存在模拟到真实的域差距，主要由于传感器噪声、深度图精度、环境纹理差异等。
- **任务规划依赖外部控制**：论文仅输出自然语言规划，未实际控制机器人执行，因此无法验证规划在执行层面的可行性。
- **S-P Map生成依赖相机外参和DH参数**：在完全未知或非标定机器人场景下无法直接使用。
- **实验规模**：真实机器人实验样本仅60个（300问答），相对较少，可能影响统计显著性。
- **计算开销**：S-P Map的离线体素生成和在线投影需要一定计算资源，但在论文中未详细讨论实时性要求。
- **潜在风险**：模型可能过度依赖S-P Map而忽略视觉上下文中的细微信息；此外，对于动态障碍或移动物体，S-P Map基于静态深度图，可能过时。

（完）
