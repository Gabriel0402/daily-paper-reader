---
title: "OmniDrive: A Holistic Vision-Language Dataset for Autonomous Driving with Counterfactual Reasoning"
title_zh: OmniDrive：面向自动驾驶的全面视觉语言数据集与反事实推理
authors: "Wang, Shihao, Yu, Zhiding, Jiang, Xiaohui, Lan, Shiyi, Shi, Min, Chang, Nadine, Kautz, Jan, Li, Ying, Alvarez, Jose M."
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_OmniDrive_A_Holistic_Vision-Language_Dataset_for_Autonomous_Driving_with_Counterfactual_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 用于自驾的VLM数据集及反事实推理
tldr: 自动驾驶中VLM的3D理解能力不足。本文提出OmniDrive，一个全面的VLM数据集，通过反事实推理增强3D驾驶任务对齐。该数据集利用反事实合成数据标注，生成大规模高质量数据，为规划提供密集监督信号。实验表明，基于该数据集训练的模型在3D驾驶场景推理和规划任务上表现显著提升。该工作推动了VLM在自动驾驶决策中的应用。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1792, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1739, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1148, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1370, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1251, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1753, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1501, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-omnidrive-a-holistic-vision-language-dataset-for-autonomous-driving-with-counterfactual-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1586, \"height\": 374, \"label\": \"Table\"}]"
motivation: VLM在自动驾驶中的3D理解能力有限，缺乏高质量3D对齐数据集。
method: 构建大规模反事实合成数据，通过反事实推理对齐VLM与3D驾驶任务。
result: 训练的模型在3D驾驶推理和规划任务上取得显著提升。
conclusion: 反事实推理为VLM的3D驾驶决策提供了有效监督信号。
---

## Abstract
The advances in vision-language models (VLMs) have led to a growing interest in autonomous driving to leverage their strong reasoning capabilities. However, extending these capabilities from 2D to full 3D understanding is crucial for real-world applications. To address this challenge, we propose OmniDrive, a holistic vision-language dataset that aligns agent models with 3D driving tasks through counterfactual reasoning. This approach enhances decision-making by evaluating potential scenarios and their outcomes, similar to human drivers considering alternative actions. Our counterfactual-based synthetic data annotation process generates large-scale, high-quality datasets, providing denser supervision signals that bridge planning trajectories and language-based reasoning. Futher, we explore two advanced OmniDrive-Agent frameworks, namely Omni-L and Omni-Q, to assess the importance of vision-language alignment versus 3D perception, revealing critical insights into designing effective LLM-agents. Significant improvements on the DriveLM Q&A benchmark and nuScenes open-loop planning demonstrate the effectiveness of our dataset and methods.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：视觉-语言模型（VLM）在2D视觉理解上表现出强推理能力，但将其扩展到3D空间理解对于自动驾驶等真实应用至关重要。现有自动驾驶VLM数据集和模型在3D几何与空间推理方面存在不足，且开放循环规划评估易过拟合专家轨迹，缺乏对决策过程的反事实推理能力。
- **研究动机**：利用反事实推理（类似人类司机考虑替代方案）生成高质量3D驾驶问答数据，以桥接规划轨迹与语言推理，提供更密集的监督信号。同时探索两种VLM框架设计方向（从2D VLM迁移或整合3D感知栈），为构建有效LLM智能体提供见解。
- **整体含义**：提出OmniDrive数据集及Omni-L/Omni-Q基线模型，在DriveLM基准和nuScenes开放循环规划上取得显著提升，证明了反事实推理数据与VLM结合的有效性。

## 2. 论文提出的方法论
- **核心思想**：
  - 基于反事实推理由规则清单和GPT-4生成高质量3D驾驶问答数据。
  - 设计两种LLM智能体框架：Omni-L（基于LLaVA的MLP投影对齐多视图图像特征与语言）和Omni-Q（基于BEV感知架构StreamPETR与Q-Former设计，整合3D位置编码与感知监督）。
- **关键技术细节**：
  - **数据生成流程**：
    1. **关键帧选择**：利用CLIP嵌入对nuScenes前视图聚类，选择语义代表性帧；再根据车辆未来轨迹聚类，覆盖各种驾驶行为。
    2. **反事实清单与提示设计**：模拟各种驾驶轨迹（停止、直行、转弯等），基于3D检测、中心线等规则检查碰撞、红灯、道路边界违规；同时让GPT-4根据图像分析高层决策安全性。
    3. **问答生成**：输入场景描述（由GPT-4生成）、专家轨迹+附近物体、反事实轨迹及检查结果，生成四类问答：注意力、反事实推理、决策规划、通用对话。
    4. **质量保证**：人工循环检查清单和提示，确保覆盖所有场景后进行大规模数据迭代。
  - **模型架构**：
    - **Omni-L**：沿用LLaVA的MLP投影器，为多视图图像特征添加3D位置编码，直接送入LLM。
    - **Omni-Q**：借鉴Q-Former设计，初始化检测查询（Q_d）和载体查询（Q_c），通过自注意力+交叉注意力从多视图特征中提取信息；载体查询经MLP对齐LLM维度，检测查询用于感知任务预测。
  - **训练策略**：两阶段训练：先在2D图像任务上预训练投影器，再在3D驾驶任务（运动规划、反事实推理等）上微调。
- **公式或算法流程**：文中给出Q-Former中自注意力和交叉注意力的公式（略），核心是查询与图像特征的交互。

## 3. 实验设计
- **数据集**：
  - **OmniDrive**：基于nuScenes构建，包含场景描述、开放循环规划、反事实推理等任务，共约？未明确给出总数，但提到通过关键帧选择和聚类生成大规模数据。
  - **DriveLM**：用于评估VLM的图视觉问答基准，包含696场景、4,072样本。
  - **nuScenes**：用于开放循环规划评估。
- **Benchmark**：
  - 开放循环规划：L2误差、碰撞率、与道路边界交叉率。
  - DriveLM：语言指标（BLEU、ROUGE-L、CIDEr）、准确率、ChatGPT分数、匹配分数，最终加权得分。
  - 反事实推理：用GPT-3.5提取关键词（安全、碰撞、闯红灯、驶离可行驶区域），计算精确率和召回率。
- **对比方法**：
  - 开放循环规划：BEV-Planner、ST-P3、UniAD、VAD-Base、Ego-MLP等。
  - DriveLM：仅DriveLM训练 vs 加OmniDrive预训练 vs 加LLaVA665k预训练。
  - 反事实推理：Omni-L、Omni-Q、BEV-MLP、有无感知监督的变体。

## 4. 资源与算力
- **文中未明确说明**：未提及训练所使用的GPU型号、数量、训练时长、显存规模等具体算力信息。仅提到训练优化器为AdamW，batch size=16，学习率策略。实际应用中需根据模型（LLaMA2-7B等）和EVA-02-L视觉编码器推断资源消耗，但论文未提供细节。

## 5. 实验数量与充分性
- **主要实验组**：
  1. 开放循环规划对比（表2）：对比多种基线，包含Omni-L/Omni-Q有/无自我状态（ego status），有/无OmniDrive数据训练。
  2. DriveLM基准测试（表3）：测试Omni-L在不同预训练数据组合下的性能。
  3. 反事实推理评估（表4）：比较不同架构（Omni-L、Omni-Q、BEV-MLP）及3D感知监督的影响。
  4. 消融实验（表5）：综合对比反事实推理AP/AR、语言CIDEr、开放循环规划指标。
- **充分性与公平性**：
  - 实验设计较为全面，覆盖了规划、推理、语言能力等多维度。
  - 公平性方面：在开放循环规划中统一采用了BEV-Planner的复现结果作为基线；对比方法使用了官方或已发表的复现。使用Ego-MLP、BEV-Planner等最新方法。
  - 消融实验系统：对架构、感知监督、数据来源进行了控制变量。
  - 但缺少在闭环仿真（如CARLA）中的验证，作者在局限中也指出这一点。

## 6. 论文的主要结论与发现
- 反事实推理数据能有效提升VLM在3D驾驶任务上的推理和规划能力，提供密集监督。
- Omni-L（从2D VLM迁移至3D）在开放循环规划、反事实推理和语言能力上均优于Omni-Q（整合3D感知栈），表明视觉-语言对齐比传统3D感知堆栈更关键。
- 加入自我状态（ego status）会显著提升开放循环规划指标，但LLM对自我状态存在过拟合风险。
- 单用轨迹预测任务训练会降低语言模型分布建模能力，但加入OmniDrive问答数据可缓解。
- 在DriveLM基准上，OmniDrive预训练带来3%以上提升，即使结合LLaVA665k仍有额外增益。

## 7. 优点
- **反事实数据生成方法创新**：利用规则清单+GPT-4实现大规模、高质量3D问答数据合成，避免纯人工标注成本，且通过人工循环保证质量。
- **系统性模型对比**：同时探索两种主流VLM框架（2D迁移 vs 3D感知整合），提供了设计LLM智能体的实证指导。
- **全面评估**：不仅评估开放循环规划，还评估反事实推理和语言能力，结果具有多维度参考价值。
- **开源贡献**：数据集和代码公开（GitHub链接），便于复现和后续研究。
- **有效缓解数据稀疏问题**：通过反事实推理提供更密集的监督信号，超越专家轨迹的单一稀疏反馈。

## 8. 不足与局限
- **反事实模拟未考虑其他智能体反应**：仅检测静态规则（碰撞、红灯等），未建模其他车辆或行人的动态响应，与真实交互仍有差距。
- **开放循环规划评估的固有局限**：仅采用nuScenes开放循环评估，仍存在对自我状态的过拟合偏差，论文本身对此有讨论但未提供闭环验证。
- **算力资源不透明**：未报告训练所需的GPU型号、数量、时间，不利于复现和资源评估。
- **语言能力评估依赖GPT-3.5/4**：在反事实推理评估中使用GPT-3.5提取关键词，可能引入新误差。
- **数据集规模未明确量化**：未给出OmniDrive具体包含多少QA对、场景数，仅说明通过关键帧选择压缩并迭代。
- **仅基于nuScenes**：单一数据集，场景多样性可能受限（如缺少恶劣天气、极端场景）。

（完）
