---
title: VLMs-Guided Representation Distillation for Efficient Vision-Based Reinforcement Learning
title_zh: VLM引导的表示蒸馏用于高效视觉强化学习
authors: "Xu, Haoran, Peng, Peixi, Tan, Guang, Chang, Yiqian, Li, Luntong, Tian, Yonghong"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Xu_VLMs-Guided_Representation_Distillation_for_Efficient_Vision-Based_Reinforcement_Learning_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 5.0
evidence: VLM引导蒸馏用于视觉强化学习，与VLA模型相关
tldr: 针对视觉强化学习中数据样本有限和缺乏语义约束的问题，提出DGC方法，利用视觉语言模型（VLM）的指导进行表示蒸馏，结合自监督学习，将VLM知识压缩到紧凑的VRL智能体中。在多个基准任务上验证了该方法能有效提升样本效率和策略性能，为VLM在机器人RL中的应用提供了轻量化方案。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 779, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 928, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 814, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 724, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 870, \"height\": 642, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 1040, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xu-vlms-guided-representation-distillation-for-efficient-vision-based-reinforcement-learning-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 738, \"height\": 401, \"label\": \"Table\"}]"
motivation: 解决视觉强化学习中数据有限和缺乏语义约束的问题。
method: 提出DGC，从VLM蒸馏指导信号结合自监督学习到紧凑VRL智能体。
result: 在多个视觉RL任务上提升了样本效率和策略性能。
conclusion: VLM引导的蒸馏可有效增强视觉RL表示质量。
---

## Abstract
Vision-based Reinforcement Learning (VRL) attempts to establish associations between visual inputs and optimal actions through interactions with the environment. Given the high-dimensional and complex nature of visual data, it becomes essential to learn policy upon high-quality state representation. To this end, existing VRL methods primarily rely on interaction-collected data, combined with self-supervised auxiliary tasks. However, two key challenges remain: limited data samples and a lack of task-relevant semantic constraints. To tackle this, we propose DGC, a method that distills guidance from Visual Language Models (VLMs) alongside self-supervised learning into a compact VRL agent. Notably, we leverage the state representation capabilities of VLMs, rather than their decision-making abilities. Within DGC, a novel prompting-reasoning pipeline is designed to convert historical observations and actions into usable supervision signals, enabling semantic understanding within the compact visual encoder. By leveraging these distilled semantic representations, the VRL agent achieves significant improvements in the sample efficiency. Extensive experiments on the Carla benchmark demonstrate our state-of-the-art performance.

---

## 论文详细总结（自动生成）

# VLMs-Guided Representation Distillation for Efficient Vision-Based Reinforcement Learning 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：视觉强化学习（VRL）从高维像素观测中学习控制策略，现有方法主要依赖智能体与环境交互收集的数据，结合自监督学习（SSL）辅助任务来学习状态表示。然而，这面临两个关键挑战：
  - **数据样本有限**：数据仅来源于智能体在特定场景中的自我探索，缺乏多样性。
  - **缺乏任务相关的语义约束**：自监督学习无法提供额外的语义信息，难以捕获对象间的有意义关系，导致表示不利于决策。
- **动机**：预训练的视觉语言模型（VLM）具有强大的视觉理解和常识推理能力，可生成丰富的、任务特定的表示。但直接使用VLM输出进行策略微调（PFT）或表示微调（RFT）在复杂任务（如Carla驾驶）中表现欠佳，可能产生不合理决策。因此，作者提出**将VLM的常识知识蒸馏到紧凑的VRL智能体的视觉编码器中**，而不是用于策略解码，从而保留VRL自主优化的能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：DGC（Distil Guidance from VLMs + SSL into Compact VRL agent）通过提示-推理管道让VLM生成语义监督信号（卷积核和特征图），引导紧凑视觉编码器的学习，再结合与任务相关的自监督任务进行精炼，最后使用TD损失进行策略学习。
- **关键技术细节**：
  - **提示-推理管道**：
    - 使用推理VLM（如QWen-VL-Chat），输入预定义提示（包括任务定义、常识规则、链式思维），以及连续三帧历史观测 `{o_t, o_{t-1}, o_{t-2}}` 和历史动作 `{a_{t-1}, a_{t-2}}`，输出语义类别 `sem_t`。
    - 使用可指代图像分割的VLM（如CLIP系列中的CRIS），将 `sem_t` 转换为两个监督信号：
      1. 语义相关的卷积核 `Φ_refer_txt(sem_t)`
      2. 对应的特征图 `Φ_refer_img(o_t) ⊗ Φ_refer_txt(sem_t)`
  - **蒸馏损失**：
    - 卷积核蒸馏损失 `L_k`：使RL智能体最终卷积层的每个输出通道的权重与VLM生成的卷积核接近。
    - 特征图蒸馏损失 `L_f`：使RL智能体的特征图与VLM生成的特征图接近。
  - **精炼过程**：使用两个自监督辅助任务（transition预测和reward预测）来减少蒸馏噪声，使表示更好地适应具体场景：
    - `L_trans = ||Φ_trans(z_t, a_t) - z_{t+1}||^2`
    - `L_rwd = ||Φ_rwd(z_t, a_t) - r_{t+1}||^2`
  - **强化学习**：在蒸馏后的表示 `z_t` 上应用SAC算法，使用TD损失更新动作-价值函数和策略：
    - `L_Q = E[Q(z_t, a_t) - (r_t + γV(z_{t+1}))]`
    - `L_π = E[α log π(a_t|z_t) - Q̃(z_t, a_t)]`
  - **测试阶段**：VLMs和SSL组件可被丢弃，仅保留紧凑的视觉编码器和策略解码器，实现高效推理。

## 3. 实验设计

- **数据集/场景**：使用Carla驾驶模拟器的三个具有挑战性的场景：
  - **Jaywalk (#JW)**：行人随机横穿马路
  - **Highbeam (#HB)**：遇对向车辆远光灯和前方骑行者
  - **Highway (#HW)**：20辆不同速度的车辆环绕
- **评估指标**：Episode Return（ER）和 Driving Distance（D，米），报告20个episode的均值和方差（3个随机种子）。
- **对比方法**：
  - VRL基线：SAC
  - 数据增强：DrQ
  - SSL for VRL：DeepMDP, CURL, DBC, MLR
  - VLM-based方法：
    - Executor：直接使用QWen-VL-Chat输出作为动作
    - RFT（表示微调）：使用CLIP图像编码器初始化SAC视觉编码器并微调
    - PFT（策略微调）：使用QWen-VL-Chat输出微调SAC的actor

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量或训练时长。仅提到计算支持来自鹏城云脑（Pengcheng Cloudbrain），未提供具体算力细节。

## 5. 实验数量与充分性

- **主要实验**（表1）：在三个场景上对比9种方法，每个方法报告平均和方差（3种子），给出最佳和第二佳标注。
- **消融实验**（图7）：在#HW场景上验证DGC各组件（移除`L_f`、移除`L_f+L_k`、仅用SAC加精炼等），共6种配置。
- **VLM-based RFT对比**（表2）：6种不同的VLM表示微调策略（冻结CLIP、冻结CRIS、加FC、全微调等），在#HW场景上比较。
- **定性分析**（图8、9）：展示视觉编码器卷积的显著性区域与推断语义类别的一致性；t-SNE可视化潜在表示分布。
- **充分性评价**：实验设计较为全面，覆盖了多种VRL和VLM方法，消融实验验证了各模块贡献，定性分析提供了直观理解。但局限性在于**仅在Carla驾驶场景**上进行，未涉及其他机器人或游戏领域，泛化性有待验证。对比方法的选择较合理，但缺少与最新VLM-RL结合方法（如使用GPT-4o进行规划）的对比。

## 6. 论文的主要结论与发现

1. **DGC在三个Carla场景上均取得最优的episode return和驾驶距离**，相比SSL方法和VLM-based RFT/PFT有显著提升。
2. **VLM蒸馏结合SSL精炼能有效提高样本效率**：训练曲线显示DGC在100K步内保持快速增长，优于其他方法。
3. **解耦表示学习和策略学习是关键**：通过将VLM知识压缩到视觉编码器而非策略解码器，避免了策略优化波动对表示学习的影响。
4. **定性结果**表明，学习到的视觉编码器能够聚焦于VLM推断的语义类别区域（如行人、骑行者、车辆），生成任务相关的鲁棒表示。

## 7. 优点

- **创新性**：提出了一种新颖的VLM蒸馏框架，不同于直接使用VLM进行微调或作为执行器，而是利用VLM的推理和指代分割能力为紧凑编码器提供像素级监督。
- **实用性**：测试时无需VLM，保持紧凑的CNN编码器结构，推理开销低，适合实际部署。
- **实验充分**：在多个复杂驾驶场景上验证，消融实验清晰显示了各损失项贡献，定性分析佐证了蒸馏效果。
- **模块化设计**：提示-推理管道可灵活替换不同的VLM（如QWen-VL-Chat + CLIP系列），具有可扩展性。

## 8. 不足与局限

- **实验域局限**：仅在Carla驾驶模拟器上测试，缺乏在更通用的VRL基准（如Atari、MetaWorld、DMControl）上的验证，泛化性存疑。
- **对VLM质量的依赖**：蒸馏质量高度依赖于推理VLM生成语义类别的准确性和指代VLM的分割能力。在罕见或模糊场景下，VLM可能产生错误或幻觉，导致劣质监督。
- **计算开销**：训练阶段需要调用两个VLM（推理+指代），尽管测试阶段可丢弃，但训练成本较高（论文未给出具体时间）。
- **超参数敏感性**：蒸馏损失权重、辅助任务权重等可能需针对不同任务调整，论文未提供详细的超参数分析。
- **未考虑多模态融合**：当前仅利用视觉和语言信息，未探索与其他传感器（如雷达、深度）的结合。

（完）
