---
title: "SOLVE: Synergy of Language-Vision and End-to-End Networks for Autonomous Driving"
title_zh: SOLVE：语言-视觉与端到端网络的协同自动驾驶
authors: "Chen, Xuesong, Huang, Linjiang, Ma, Tao, Fang, Rongyao, Shi, Shaoshuai, Li, Hongsheng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Chen_SOLVE_Synergy_of_Language-Vision_and_End-to-End_Networks_for_Autonomous_Driving_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: VLM赋能端到端自动驾驶规划
tldr: 针对VLM集成到自动驾驶中的计算效率问题，提出SOLVE框架，通过共享视觉编码器实现VLM与端到端模型在特征级知识共享，并设计轨迹思维链（T-CoT）逐步优化轨迹预测。实验表明该方法在规划准确性和实时性上取得平衡，展示了VLM在自主驾驶规划中的实际应用价值。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 893, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1754, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 835, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1764, \"height\": 1437, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1300, \"height\": 742, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-chen-solve-synergy-of-language-vision-and-end-to-end-networks-for-autonomous-driving-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 736, \"height\": 278, \"label\": \"Table\"}]"
motivation: VLM集成到自动驾驶面临计算开销和实时性挑战。
method: 提出SOLVE，通过共享编码器和轨迹思维链融合VLM与端到端规划。
result: 在规划准确性和实时性上均优于基线。
conclusion: VLM与端到端协同可提升自动驾驶规划能力。
---

## Abstract
The integration of Vision-Language Models (VLMs) into autonomous driving systems has shown promise in addressing key challenges such as learning complexity, interpretability, and common-sense reasoning. However, existing approaches often struggle with efficient integration and real-time decision-making due to computational demands. In this paper, we introduce SOLVE, an innovative framework that synergizes VLMs with end-to-end (E2E) models to enhance autonomous vehicle planning. Our approach emphasizes knowledge sharing at the feature level through a shared visual encoder, enabling comprehensive interaction between VLM and E2E components. We propose a Trajectory Chain-of-Thought (T-CoT) paradigm, which progressively refines trajectory predictions, reducing uncertainty and improving accuracy. By employing a temporal decoupling strategy, SOLVE achieves efficient asynchronous cooperation, aligning high-quality VLM outputs with E2E real-time performance. Evaluated on the nuScenes dataset, our method demonstrates significant improvements in trajectory prediction accuracy, paving the way for more robust and reliable autonomous driving systems.

---

## 论文详细总结（自动生成）

# SOLVE 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：端到端自动驾驶系统虽在数据驱动下展现了强大规划能力，但仍面临学习复杂性高、常识推理不足、可解释性差、因果混淆等挑战。视觉-语言模型（VLM）通过大规模多模态训练能提供直观的场景理解和常识知识，但直接集成到实时驾驶系统中存在计算开销大、效率低、3D感知能力弱等问题。
- **核心问题**：现有方法（如DriveVLM）仅在后处理层面进行轨迹级协作（VLM生成粗轨迹，E2E模型细化），缺乏特征级知识共享，限制了VLM的高层推理与E2E的3D感知能力互补。
- **整体含义**：提出SOLVE框架，旨在实现VLM与端到端模型在**特征级**和**轨迹级**的双重协同，兼顾精度与实时性，推动更鲁棒、可靠的自动驾驶规划。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **特征级协同**：通过共享视觉编码器（SQ-Former）同时为VLM和E2E模型提供统一、紧凑的视觉特征，实现知识共享。
- **轨迹级协同**：提出轨迹思维链（Trajectory Chain-of-Thought, T-CoT），逐步细化轨迹预测；并采用时间解耦策略异步利用VLM的高质量轨迹辅助E2E模型。

### 关键技术细节
1. **Sequential Q-Former (SQ-Former)**：
   - 将多视图图像特征分为三类：场景级静态信息（天气、时段）、动态参与者（车辆、行人）、动态地图线索（车道线）。
   - 采用Q-Former架构，先通过收集器查询（collector queries）编码静态线索，再依次与检测查询、车道查询进行交叉注意力，最终输出384个紧凑视觉token。
   - 引入记忆库（memory bank）融入时间动态（借鉴StreamPETR）。
2. **Trajectory Chain-of-Thought (T-CoT)**：
   - 构建轨迹银行（trajectory bank）：对训练集轨迹按导航命令（直行、左转、右转）聚类，每类生成36个候选轨迹。
   - 两阶段推理：
     - **轨迹选择**：VLM从候选轨迹（聚类相似轨迹+MLP预测轨迹，共kl+1条）中选出最佳轨迹。
     - **轨迹细化**：将选中轨迹的每个路径点编码为token，加入速度、加速度等状态信息，让VLM生成细化后的轨迹。
   - 轨迹适配器将候选轨迹端点/路径点映射到VLM的token空间。
3. **时间解耦协同（Time-decoupled Synergy Prediction）**：
   - VLM预测长时域轨迹（超过自身延迟和E2E所需时域），存储在记忆中。
   - E2E模型在预测当前帧轨迹时，异步获取历史帧VLM轨迹作为额外的初始化规划查询（planning query），提升精度。
4. **多阶段训练策略**：
   - 第一阶段：用OmniDrive的QA数据训练VLM（含LoRA），优化SQ-Former收集器查询。
   - 第二阶段：训练轨迹适配器，然后训练E2E规划头（冻结SQ-Former、视觉适配器、轨迹适配器）。
   - 第三阶段：联合优化VLM和E2E规划头（不冻结任何组件）。
   - 最后：只微调E2E规划器，利用历史VLM轨迹作为额外初始化。

## 3. 实验设计

- **数据集**：nuScenes（1000个驾驶场景，每个约20秒），包含多视角相机、LiDAR、3D标注、自车轨迹、道路地图。
- **基准**：使用OmniDrive-nuScenes数据集（含感知、预测、规划的QA对）进行VLM训练。
- **评估指标**：位移误差（L2距离，cm/m）和碰撞率（%），按1s、2s、3s及平均评估。
- **对比方法**：
  - 端到端方法：UniAD、VAD-Base、AD-MLP、BEV-Planner、BEV-Planner++、DriveVLM、OmniDrive、EMMA。
  - VLM方法：DriveVLM、OmniDrive、DriveVLM-Dual。
  - 自身变体：Ours-E2E、Ours-E2E (Async)、Ours-VLM。
- **主要结果**：
  - SOLVE-E2E在平均L2误差上达到0.31m（优于UniAD 0.46m、VAD 0.37m、BEV-Planner 0.35m），碰撞率0.29%（低于对比方法）。
  - SOLVE-VLM平均L2误差0.28m，碰撞率0.20%，均优于OmniDrive（0.33m/0.30%）和DriveVLM（0.40m/未提供）。
  - 异步协作（Ours-E2E Async）进一步降低L2误差至0.30m。

## 4. 资源与算力

- **明确说明**：论文在实现细节中未直接报告使用的GPU型号、数量及训练时长。仅提到：
  - 使用LLaVA v1.5（LLaMA-7B）作为VLM。
  - 图像编码器初始化为EVA-02-L。
  - 消融实验中，SQ-Former和VLM训练6个epoch以优化计算资源。
- **未明确部分**：未说明训练所需GPU数量、显存消耗、推理延迟等具体算力信息。

## 5. 实验数量与充分性

- **实验组数**：论文包含：
  - **主对比实验**：在nuScenes上与8种以上方法比较。
  - **消融实验**：
    1. SQ-Former查询数量影响（256/384/512）。
    2. 视觉信息编码顺序（多种组合）。
    3. 轨迹CoT影响（无CoT vs 不同参考轨迹数量4/6/8）。
    4. 共享SQ-Former特征对E2E和VLM的影响（有无共享）。
  - **定性结果**：展示了两个典型场景的轨迹可视化。
- **充分性评价**：
  - 消融实验覆盖了核心组件（SQ-Former、T-CoT、共享机制），但未对时间解耦策略单独消融（仅通过E2E vs E2E Async对比）。
  - 实验数据仅基于nuScenes单一数据集，缺乏在Waymo、nuPlan等其他数据集上的验证。
  - 未进行闭环（closed-loop）仿真评估，仅开放环（open-loop）规划，可能不能完全反映真实驾驶性能。
  - 整体实验设计客观，对比方法均为近期SOTA，但缺乏更详细的超参数敏感性分析。

## 6. 论文的主要结论与发现

- **主要结论**：SOLVE通过特征级共享视觉编码器和轨迹级T-CoT+时间解耦协同，显著提升了端到端自动驾驶的规划精度和安全性，在nuScenes开放环规划上达到SOTA。
- **关键发现**：
  - 共享SQ-Former特征使E2E模型L2误差降低1.5cm（31.0 vs 32.5），VLM降低0.6cm（28.4 vs 29.0），证明QA supervision有助于提取更有效的规划特征。
  - T-CoT通过轨迹银行和渐进式推理使VLM轨迹预测提升1.1cm（28.4 vs 29.5），且6条候选轨迹为最佳平衡。
  - 编码顺序“图像特征→检测→车道”优于其他顺序，表明图像级场景线索对规划有益。
  - VLM异步提供的初始轨迹可使E2E进一步受益。

## 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - 创新性地将VLM与E2E模型在**特征级**和**轨迹级**双维度协同，弥补了现有方法仅后处理协作的不足。
  - SQ-Former通过顺序编码不同感知任务，用较少的查询数（384）实现高效视觉压缩，降低VLM计算开销。
  - T-CoT避免VLM直接自回归生成细粒度轨迹的困难，通过轨迹银行和链式推理逐步细化，提升精度且仅需少量输出。
  - 时间解耦策略巧妙利用VLM的长时域预测，以异步方式增强E2E实时规划，兼顾精度与效率。
- **实验亮点**：
  - 与多种近期SOTA方法（UniAD、VAD、DriveVLM、OmniDrive等）进行全面对比。
  - 消融实验设计系统，验证了SQ-Former的查询数、编码顺序、T-CoT、共享机制等关键设计的有效性。

## 8. 不足与局限

- **实验覆盖不足**：仅在nuScenes开放环上验证，缺乏在更大规模数据集（如Waymo、nuPlan）或闭环仿真（如CARLA）上的评估，泛化性待证实。
- **偏差风险**：nuScenes场景主要集中于城市环境，对高速、乡村、极端天气等场景覆盖有限。
- **计算资源未明确**：未提供VLM推理延迟、实时性具体数据，虽提出时间解耦但未量化VLM的延迟对系统的影响。
- **消融不完整**：未消融时间解耦策略中记忆大小、异步延迟窗口等超参数；未分析E2E规划头交叉注意力设计的贡献。
- **应用限制**：VLM本身参数量大（7B），实际车载部署仍面临硬件成本挑战；T-CoT依赖预定义的轨迹银行，可能无法覆盖所有罕见驾驶情形。

（完）
