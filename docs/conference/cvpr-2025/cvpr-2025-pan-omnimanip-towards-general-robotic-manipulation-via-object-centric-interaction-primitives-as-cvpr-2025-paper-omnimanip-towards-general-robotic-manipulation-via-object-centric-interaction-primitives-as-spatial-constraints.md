---
title: "OmniManip: Towards General Robotic Manipulation via Object-Centric Interaction Primitives as Spatial Constraints"
title_zh: OmniManip：通过物体中心交互原语实现通用机器人操作
authors: "Pan, Mingjie, Zhang, Jiyao, Wu, Tianshu, Zhao, Yinghao, Gao, Wenlong, Dong, Hao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Pan_OmniManip_Towards_General_Robotic_Manipulation_via_Object-Centric_Interaction_Primitives_as_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 通过物体中心原语桥接VLM高层推理与底层操作
tldr: 针对视觉语言模型（VLM）缺乏精细3D空间理解而微调为视觉语言动作模型（VLA）成本高昂的问题，本文提出OmniManip，通过物体中心交互原语将VLM的高层常识推理与机器人精确操作相结合。该方法无需大量机器人数据集微调，即可在多种操作任务中实现高泛化性，为通用机器人操作提供了高效新途径。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1795, \"height\": 1217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 847, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 854, \"height\": 492, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 871, \"height\": 817, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1737, \"height\": 819, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-pan-omnimanip-towards-general-robotic-manipulation-via-object-centric-interaction-primitives-as-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 835, \"height\": 246, \"label\": \"Table\"}]"
motivation: VLM擅长高层推理但缺乏3D空间精度，VLA微调数据采集成本高且泛化差。
method: 提出物体中心交互原语，将物体规范空间作为空间约束，连接VLM推理与底层控制。
result: 在多个操作任务上达到SOTA，无需大量机器人数据即可泛化到新场景。
conclusion: 物体中心原语有效弥合了VLM与精细操作之间的鸿沟，为通用机器人提供了可扩展方案。
---

## Abstract
The development of general robotic systems capable of manipulating in unstructured environments is a significant challenge. While Vision-Language Models(VLM) excel in high-level commonsense reasoning, they lack the fine-grained 3D spatial understanding required for precise manipulation tasks. Fine-tuning VLM on robotic datasets to create Vision-Language-Action Models(VLA) is a potential solution, but it is hindered by high data collection costs and generalization issues. To address these challenges, we propose a novel object-centric representation that bridges the gap between VLM's high-level reasoning and the low-level precision required for manipulation. Our key insight is that an object's canonical space, defined by its functional affordances, provides a structured and semantically meaningful way to describe interaction primitives, such as points and directions. These primitives act as a bridge, translating VLM's commonsense reasoning into actionable 3D spatial constraints. In this context, we introduce a dual closed-loop, open-vocabulary robotic manipulation system: one loop for high-level planning through primitive resampling, interaction rendering and VLM checking, and another for low-level execution via 6D pose tracking. This design ensures robust, real-time control without requiring VLM fine-tuning. Extensive experiments demonstrate strong zero-shot generalization across diverse robotic manipulation tasks, highlighting the potential of this approach for automating large-scale data generation.

---

## 论文详细总结（自动生成）

# 论文结构化总结：OmniManip

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：视觉语言模型（VLM）擅长高层常识推理，但缺乏精细的3D空间理解能力，难以直接用于精确机器人操作任务。
- **现有解法局限**：微调VLM为视觉语言动作模型（VLA）需要大量高质量机器人数据，成本高且泛化性差；抽象操作原语的方法（如关键点、值图）存在任务无关、不稳定、依赖人工规则等问题。
- **整体含义**：本文提出一种物体中心（object-centric）的交互原语表示，将VLM的高层推理转化为可执行的3D空间约束，无需VLM微调即可实现开放词汇的通用机器人操作，并设计了双闭环系统（规划闭环+执行闭环）提升鲁棒性。

## 2. 方法论
### 核心思想
- 在物体的**规范空间（canonical space）**中，利用其功能可供性（functional affordances）定义交互原语（交互点 + 交互方向），作为VLM推理与底层控制的桥梁。
- 交互原语以空间约束（位置对齐+方向对齐）的形式描述主动物体与被动物体之间的几何关系。

### 关键技术细节
1. **任务分解**：使用SAM和GroundingDINO标记场景物体，VLM筛选相关物体并将任务拆分为多个阶段（Stage），每个阶段包含动作、主动物体、被动物体。
2. **物体规范空间获取**：通过单视角3D生成网络（如TripoSR）获得物体网格，用通用6D姿态估计模型（Omni6DPose）进行规范化。
3. **交互原语提取**：
   - **交互点**：利用SCAFFOLD视觉提示机制（在图像上叠加笛卡尔网格），VLM定位可见点，不可见点通过多视角推理确定。
   - **交互方向**：在规范空间中沿物体主轴采样候选方向，由VLM生成语义描述，再由LLM评分排序。
4. **空间约束定义**：每个阶段定义距离约束（两点距离）和角度约束（两方向夹角），通过优化求解末端执行器位姿。
5. **双闭环系统**：
   - **规划闭环（RRC）**：VLM对渲染的交互图像进行自检，触发重采样、渲染、检查，纠正幻觉。
   - **执行闭环**：通过6D位姿跟踪实时更新主动/被动物体位姿，用于优化末端位姿，处理动态变化和抓取偏差。

### 算法流程（文字说明）
- 输入：自然语言指令 + RGB-D观测。
- 输出：机器人轨迹。
- 简要步骤：
  1. 场景物体分割与任务相关物体过滤。
  2. 任务分解为阶段。
  3. 对每个阶段，在规范空间中提取交互原语并生成候选约束列表。
  4. RRC自校正循环挑选有效约束。
  5. 约束优化计算目标末端位姿。
  6. 6D位姿跟踪闭环执行。

## 3. 实验设计
- **平台**：Franka Emika Panda机械臂 + UMI手指 + 两个Intel RealSense D415深度相机（一腕部一外部）。
- **任务与场景**：12个真实世界操作任务，包括6个刚体操作（倒茶、插花、插笔、回收电池、拿杯、盖壶盖）和6个铰接物体操作（开抽屉、关抽屉、锤按钮、按红色按钮、关笔记本电脑盖、开罐子）。
- **基准方法**：
  - VoxPoser（3D值图 + LLM/VLM）
  - CoPa（物体部分空间约束 + VLM）
  - ReKep（关系关键点约束 + 分层优化）
- **评估指标**：每个任务10次试验的成功率，每次试验后重新配置物体布局。

## 4. 资源与算力
- 论文中**未明确说明**训练使用的GPU型号、数量或训练时长。
- 方法本身无需VLM微调，使用预训练模型（GPT-4o、SAM、GroundingDINO、TripoSR、Omni6DPose、AnyGrasp等），推理时多次调用VLM（需考虑计算成本）。
- 文中提到“多个VLM调用存在计算挑战”，但未给出具体硬件配置。

## 5. 实验数量与充分性
- **实验数量**：12个任务×10次/任务 = 120次试验（每个方法），对比三个基线（部分基线不包括铰接任务，故总试验数略有差异）。
- **消融实验**：
  - 关闭闭环规划 vs 开启闭环规划（表1中Ours vs OmniManip无闭环规划），验证闭环规划提升超15%。
  - 采样效率对比（表3）：均匀采样 vs OmniManip采样，在回收电池和倒茶任务上比较成功率和迭代次数。
  - 视角稳定性实验（表2 & 图6）：不同视角下ReKep与OmniManip的规划结果和成功率对比。
- **充分性**：实验覆盖了多种操作类型（pick-and-place、交互式操作、铰接操作），对比了主流方法，消融实验合理，但未包含仿真实验或多机器人平台验证。总体充分，但对象类别和场景多样性尚可进一步提升。

## 6. 主要结论与发现
- OmniManip在12个真实任务上取得了优于所有基线的零样本性能（刚体68.3% vs ReKep 45.0%，铰接61.7% vs CoPa 26.7%），且无需微调VLM。
- 物体中心的规范空间交互原语比基于表面关键点的方法更稳定、更视角不变。
- 双闭环系统（特别是规划闭环的RRC自校正）显著减少了VLM幻觉导致的规划错误，提升成功率超15%。
- 沿物体主轴采样比均匀采样更高效（迭代次数少、成功率高）。
- 6D位姿跟踪闭环执行对处理抓取偏差和动态物体更鲁棒，优于ReKep的点跟踪（后者有47%遮挡失败率）。

## 7. 优点
- **创新性**：首次提出利用物体规范空间中的交互原语作为VLM与机器人控制的桥梁，无需VLM微调。
- **系统性**：双闭环设计（规划自校正 + 执行跟踪）有效弥补了大型模型的幻觉和动态环境干扰。
- **泛化性**：零样本跨任务、跨场景表现突出。
- **可解释性**：交互原语和空间约束具有清晰的几何意义，规划结果可通过渲染检查。
- **效率**：沿主轴采样减少了搜索空间，提升了推理效率。

## 8. 不足与局限
- **可变形物体**：因基于6D位姿表示，无法建模绳子、布料等可变形物体的操作。
- **依赖3D生成质量**：单视图3D网格重建的质量（如TripoSR）直接影响原语提取的准确性，而当前AIGC对透明、高反光等物体仍存在挑战。
- **计算开销**：多次调用VLM（任务分解、原语提取、RRC循环、渲染检查）导致延时较高，即使支持并行也面临计算资源压力。
- **实验覆盖面**：仅在一个机械臂平台和有限物体类别上测试，未在多种机器人或真实家庭环境中验证；任务数量有限（12个），可能存在选择偏差。
- **可重复性细节**：未开源完整代码或提供训练配置，部分提示词和参数仅供附录，可能影响复现。
- **安全性**：优化过程中碰撞损失基于简单的距离阈值，未考虑复杂障碍物或人机协作场景的安全性。

（完）
