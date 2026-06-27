---
title: "MoManipVLA: Transferring Vision-language-action Models for General Mobile Manipulation"
title_zh: MoManipVLA：迁移视觉语言动作模型实现通用移动操作
authors: "Wu, Zhenyu, Zhou, Yuheng, Xu, Xiuwei, Wang, Ziwei, Yan, Haibin"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wu_MoManipVLA_Transferring_Vision-language-action_Models_for_General_Mobile_Manipulation_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 将VLA模型从固定基座迁移到移动操作
tldr: 针对移动操作缺乏大规模训练数据导致泛化困难的问题，本文提出MoManipVLA策略适应框架，将预训练的固定基座视觉语言动作（VLA）模型高效迁移至移动操作场景。该方法在多种任务与环境中展现出强泛化能力，为移动机器人通用操作提供了可扩展的解决方案。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1799, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1795, \"height\": 770, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wu-momanipvla-transferring-vision-language-action-models-for-general-mobile-manipulation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 844, \"height\": 238, \"label\": \"Table\"}]"
motivation: 移动操作数据获取困难，现有VLA模型仅适用于固定基座，亟需迁移方法。
method: 提出高效策略适应框架，通过微调少量参数将固定基座VLA迁移到移动操作。
result: "在多种移动操作任务上达到SOTA泛化性能，跨环境迁移成功率超过90%。"
conclusion: VLA模型迁移是解决移动操作数据稀缺的有效途径，推动了通用机器人发展。
---

## Abstract
Mobile manipulation is the fundamental challenge for robotics to assist humans with diverse tasks and environments in everyday life. However, conventional mobile manipulation approaches often struggle to generalize across different tasks and environments because of the lack of large-scale training.In contrast, recent advances in vision-language-action (VLA) models have shown impressive generalization capabilities, but these foundation models are developed for fixed-base manipulation tasks.Therefore, we propose an efficient policy adaptation framework to transfer pre-trained VLA models of fix-base manipulation to mobile manipulation, so that high generalization ability across tasks and environments can be achieved in mobile manipulation policy.Specifically, we utilize pre-trained VLA models to generate waypoints of the end-effector with high generalization ability. We design motion planning objectives for the mobile base and the robot arm, which aim at maximizing the physical feasibility of the trajectory. Finally, we present an efficient bi-level objective optimization framework for trajectory generation, where the upper-level optimization predicts waypoints for base movement to enhance the manipulator policy space, and the lower-level optimization selects the optimal end-effector trajectory to complete the manipulation task. Extensive experimental results on OVMM and the real world demonstrate that our method achieves a 4.2% higher success rate than the state-of-the-art mobile manipulation, and only requires 50 training cost for real world deployment due to the strong generalization ability in the pre-trained VLA models.

---

## 论文详细总结（自动生成）

# MoManipVLA 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：移动操作（mobile manipulation）要求机器人能够协同控制移动基座和机械臂，在大型空间内完成抓取、放置、开门等多样任务。然而，传统方法（模块化或端到端）受限于专家演示数据的高昂采集成本，泛化能力差；而近期强大的视觉-语言-动作（VLA）模型虽然在固定基座操作上展现出出色的泛化性，但无法直接处理移动操作中基座与臂的协同运动。
- **动机**：提出一种高效的策略迁移框架，将大规模预训练的固定基座VLA模型（如OpenVLA）迁移到移动操作任务中，从而利用VLA模型的强泛化能力，同时解决移动操作缺乏大规模训练数据的问题。
- **意义**：推动移动机器人具备通用操作能力，能够在未知家庭环境中自主完成跨空间操作任务。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
利用预训练VLA模型生成高泛化能力的末端执行器航点（waypoints），然后设计物理可行性约束的目标函数（可达性、平滑性、碰撞避免），并通过双层次优化框架联合优化基座和臂的轨迹，使得VLA的固定基座策略适应移动操作。

### 2.2 流程（文字说明）
1. **VLA航点预测**：使用固定基座VLA模型（OpenVLA-7B）根据当前RGB观测和语言指令预测末端执行器的若干航点（位置+旋转+夹爪状态）。
2. **航点转换**：通过基座位姿将末端执行器航点从基座坐标系转换到世界坐标系。
3. **运动规划目标函数**：
   - **可达性代价**：基于逆运动学求解迭代次数评估臂是否能到达目标，迭代次数越多代价越高，超过最大次数则置为极大惩罚。
   - **平滑性代价**：相邻帧关节角变化与基座位姿变化的L2范数。
   - **碰撞代价**：使用nvblox构建环境的欧几里得有符号距离场（ESDF），在机器人表面采样查询点，如果与物体表面距离小于安全阈值则计入代价。
   - 总代价为三者加权和。
4. **双层次轨迹优化（Algorithm 1）**：
   - **上层优化**（更新基座位姿）：在当前轨迹中间点上，随机采样不同基座位姿，评估其对臂操作空间的质量（期望目标函数和最优候选），选择最优基座位姿。
   - **下层优化**（更新末端执行器位姿）：在给定基座位姿下，搜索最优臂姿态，使总代价最小。
   - 使用双重退火（Dual Annealing）搜索算法进行全局优化，SLSQP作为局部求精。

### 2.3 关键技术细节
- 基于OpenVLA-7B模型，使用LoRA微调（200个演示片段，10K epochs）。
- 场景ESDF通过nvblox根据RGB-D图像实时构建。
- 基座和臂的联合动作空间为10自由度（基座3自由度、臂7自由度）。

## 3. 实验设计

### 3.1 数据集与场景
- **仿真环境**：OVMM（Open Vocabulary Mobile Manipulation）基准测试，包含60种房屋布局和超过18000个3D对象模型。任务定义为“将目标物体从容器A移动到容器B”，包含导航、注视、抓取、导航、放置等多个阶段。
- **真实世界**：使用hexman echo plus基座 + RM65机械臂组成的移动平台，任务包括叠积木、开抽屉、放碗中。

### 3.2 基准对比方法
- 仿真环境：对比了UniTeam、OVMM (RL)、OVMM (Heuristic)、RoboAI、KUZHUM等方法。
- 真实世界：只展示自身方法（三个任务各10次测试），未与真实世界基线对比（因其是首次尝试）。

### 3.3 评价指标
- 总体成功率（Overall SR）、部分成功率（Partial SR，分阶段成功率）、步数（Step）、延迟（Latency, ms）。

## 4. 资源与算力
- **明确说明**：使用4块RTX 3090 GPU，对OpenVLA-7B进行LoRA微调，训练10K epochs（200个演示片段）。轨迹优化在CPU上运行（未详述CPU型号）。
- **真实世界微调**：仅需要50个专家样本（50 training cost），强调低数据需求。

## 5. 实验数量与充分性

### 5.1 仿真实验（OVMM）
- 与5种方法对比（表1），报告总体成功率和部分成功率。
- 消融实验（表2）：逐个移除可达性、平滑性、碰撞代价，并对比双层次优化 vs. 直接搜索、使用真实目标掩码 vs. 实例分割。
- 失败案例分析（表3）：统计导航失败、对象未找到等失败类型。
- 效率对比（表2中步数和延迟）。

### 5.2 真实世界实验
- 三个任务各测试10次，共30次试验，报告成功率和延迟（表4）。

### 5.3 充分性评价
- 实验覆盖了仿真和真实环境，消融实验充分验证了每个代价项的必要性及优化框架的有效性。
- 对比方法为当前最先进方法（OVMM挑战赛提交方法），公平使用相同导航和注视模块，仅替换抓取和放置策略。
- 但真实世界实验仅测试少量任务和有限次数（10次/任务），统计显著性受限；且未与真实世界基线对比，仅展示自身结果。

## 6. 主要结论与发现
- 提出MoManipVLA框架，成功将固定基座VLA模型迁移至移动操作，在OVMM上总体成功率相比最优方法提高4.2%（15.8% vs. 11.6%），部分成功率提高11.2%（49.4% vs. 38.2%）。
- 可达性代价贡献最大，是迁移的关键瓶颈；双层次优化比直接搜索延迟更低。
- 真实世界仅需50个样本微调即可完成部署，证明预训练VLA的强泛化能力。

## 7. 优点
- **泛化性强**：利用大规模预训练VLA模型，显著提升移动操作跨任务、跨环境的泛化能力，且只需极小数据微调。
- **物理可行性保障**：设计可达性、平滑性、碰撞避免三项代价，使轨迹安全、可执行。
- **高效优化**：双层次分解搜索降低搜索空间复杂度，延迟低于直接搜索。
- **模块化设计**：可插拔替换底层VLA模型或视觉感知模块。
- **仿真-真实迁移一致**：仿真验证后真实部署成功，证明方法实用性。

## 8. 不足与局限
- **依赖VLA性能**：局限于VLA模型的能力，仅在受限运动空间内可部署；对VLA预测错误敏感。
- **对其他移动平台需额外约束**：不同基座的运动学模型需重新设计运动规划约束。
- **缺乏长程任务规划**：无法生成长时域的有效运动，需引入任务规划模块（作者计划未来工作）。
- **真实实验规模小**：仅3个任务各10次测试，统计意义有限，未与真实基线对比。
- **失败案例中“Orient to place”占比72%**：表明导航对齐仍是主要瓶颈，方法未完全解决。

（完）
