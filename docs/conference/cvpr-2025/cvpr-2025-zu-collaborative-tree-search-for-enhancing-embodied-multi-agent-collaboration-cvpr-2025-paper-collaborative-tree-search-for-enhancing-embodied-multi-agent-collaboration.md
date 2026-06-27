---
title: Collaborative Tree Search for Enhancing Embodied Multi-Agent Collaboration
title_zh: 协作树搜索增强具身多智能体协作
authors: "Zu, Lizheng, Lin, Lin, Fu, Song, Zhao, Na, Zhou, Pan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zu_Collaborative_Tree_Search_for_Enhancing_Embodied_Multi-Agent_Collaboration_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 8.0
evidence: CoTS框架使用LLM驱动的奖励搜索实现多智能体协作
tldr: 针对基于大语言模型的具身智能体在多智能体协作中通信效率低与行动不一致的问题，本文提出协作树搜索（CoTS）框架，让多个智能体在修改的蒙特卡洛树内讨论长期策略，并借助LLM驱动的奖励函数进行搜索。实验表明该方法显著提升了多智能体任务的成功率和效率，为大模型在多智能体系统中的应用提供了新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1572, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1797, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 559, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 547, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 567, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 671, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 839, \"height\": 416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1624, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 784, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zu-collaborative-tree-search-for-enhancing-embodied-multi-agent-collaboration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 782, \"height\": 260, \"label\": \"Table\"}]"
motivation: 现有基于LLM的智能体协作存在通信模式简单导致错误累积的问题。
method: 在蒙特卡洛树中引导多智能体讨论长期计划，使用LLM驱动的奖励函数指导搜索。
result: "在多个协作任务上成功率提高20%以上，执行效率显著提升。"
conclusion: 协作树搜索有效促进了多智能体间的协调规划，是大模型应用于多智能体系统的重要进展。
---

## Abstract
Embodied agents based on large language models (LLMs) face significant challenges in collaborative tasks, requiring effective communication and reasonable division of labor to ensure efficient and correct task completion. Previous approaches with simple communication patterns carry erroneous or incoherent agent actions, which can lead to additional risks. To address these problems, we propose Cooperative Tree Search (CoTS), a framework designed to significantly improve collaborative planning and task execution efficiency among embodied agents. CoTS guides multi-agents to discuss long-term strategic plans within a modified Monte Carlo tree, searching along LLM-driven reward functions to provide a more thoughtful and promising approach to cooperation. Another key feature of our method is the introduction of a plan evaluation module, which not only prevents agent action confusion caused by frequent plan updates but also ensures plan updates when the current plan becomes unsuitable. Experimental results show that the proposed method performs excellently in planning, communication, and collaboration on embodied environments (CWAH and TDW-MAT), efficiently completing long-term, complex tasks and significantly outperforming existing methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **研究动机**：基于大语言模型（LLM）的具身智能体在执行协作任务时面临重大挑战——需要有效的通信和合理的分工。现有方法（如CoELA、RoCo）存在通信模式简单、决策独立或依赖单一推理路径等问题，容易导致错误积累、行动不协调、计划频繁更新造成混乱。
- **整体含义**：提出**协作树搜索（CoTS）** 框架，旨在通过让多智能体在修改的蒙特卡洛树（MCTS）内进行长期战略讨论，并利用LLM驱动的奖励函数进行搜索，从而显著提升协作规划与任务执行效率。

## 2. 方法论
### 核心思想
- 将多智能体协作规划转化为树搜索问题：一个智能体（如Alice）作为“规划者”提出计划，其他智能体（如Bob）作为“评审者”评估并给出奖励，通过选择、扩展、评估、反向传播四个步骤在树中搜索最优长期协作计划。
- 引入**计划评估模块**动态监控当前计划的可行性，仅在必要时更新计划，避免频繁更新导致的行动混乱。

### 关键技术细节
- **协作树搜索（基于MCTS）**：
  - **选择**：按UCT公式 `UCT(s_i)=V(s_i)+w√(ln N(p_i)/N(s_i))` 从根节点向下选择节点直至叶节点。
  - **扩展**：从选中节点采样n个新讨论路径，生成n个子节点（代表不同规划方向）。
  - **评估**：基于LLM的非模拟奖励函数，包含“分配奖励”（评估协调性与效率）和“成本奖励”（评估空间移动代价），每项1-5分，最终归一化至0-1。
  - **反向传播**：沿路径更新节点访问次数和平均奖励：`N(s_i)=N(s_{i-1})+1`，`V(s_i)=(V(s_{i-1})N(s_{i-1})+r)/N(s_i)`。
- **计划评估模块**：
  - 持续评估当前协作计划的可行性；若评分低于阈值则调用规划模块重新搜索并更新计划；否则保留原计划。
- **扩展记忆**：引入“扩展记忆”存储协作计划，属于中短期记忆，定期更新以平衡保留与适应性。
- **感知模块增强**：引入距离作为关键感知因素，利用固定空间布局提升房间级理解与规划效率。

## 3. 实验设计
### 使用的数据集/场景
- **TDW-MAT**（ThreeD World Multi-Agent Transport）：基于物理的家庭环境，包含24个任务（食物运输与杂物运输各半）。评估指标为**运输率**（成功运输目标物体的百分比），时间上限3000帧。
- **C-WAH**（Communicative Watch-And-Help）：基于VirtualHome-Social平台，包含5个常见家庭场景共10个任务。评估指标为**完成所有子任务所需的步数**（越少越好）。

### Benchmark
- 对比三类基线方法：
  - **基础智能体**：RHP（启发式规则）、MHP（MCTS+回归规划）
  - **RL智能体**：MAT（多智能体强化学习）
  - **LLM智能体**：CoELA、RoCo、CaPo

### 对比方法
- 在TDW-MAT上：与RHP、CoRHP、MAT、CoELA、RoCo、CaPo对比。
- 在C-WAH上：与MHP、CoMHP、CoELA、RoCo、CaPo对比。

## 4. 资源与算力
- 论文未明确说明训练时长或数据集规模，仅提及实验环境：**Intel Core i9-10980XE CPU + NVIDIA GeForce RTX 3090 GPU**，使用GPT-4和GPT-3.5-turbo（温度0.7，top-1采样，最大输出512 tokens）。
- 未报告具体训练/推理耗时、GPU数量或显存使用量。

## 5. 实验数量与充分性
- 主要实验组数：
  - TDW-MAT：在“有oracle感知”和“无oracle感知”两种设置下，分别报告Stuff和Food两类任务的运输率，以及平均值。
  - C-WAH：在Visual Obs和Symbolic Obs两种观察设置下报告平均步数。
  - 消融实验：移除奖励函数、MCTS规划模块、计划评估与更新模块（E&U）分别测试运输率下降。
  - 时间步分析：对比CoTS与CoELA在不同时间步的运输率。
  - 分支因子影响：测试1、2、3、4分支因子下的运输率。
- 充分性评价：实验覆盖了两个不同复杂度的环境、多种基线、消融实验和超参数分析，较为充分。但未报告多次运行的标准差或置信区间，可能影响统计显著性判断。

## 6. 主要结论与发现
- CoTS在TDW-MAT上以GPT-4驱动时，平均运输率比CoELA提升9.41%（有oracle感知）和16.90%（无oracle感知）；在C-WAH上步数减少11.96%（Visual Obs）和14.04%（Symbolic Obs）。
- 相比RoCo和CaPo，CoTS因多路径搜索和计划评估模块，避免了单一对话链的次优计划与频繁更新造成的行动冲突。
- 消融实验证实：树搜索、奖励函数、计划评估模块均对性能有显著贡献。
- 时间步分析显示：CoTS早期运输率较低（因优先收集物品），但后期（2000步后）显著超越CoELA。
- 增加分支因子（从1到4）可提升运输率，但需权衡效率。

## 7. 优点
- **创新性**：首次将MCTS与LLM驱动具身多智能体协作结合，提出非模拟奖励函数（LLM直接评估计划质量），避免高成本物理交互。
- **实用性**：计划评估模块有效平衡计划稳定性和适应性，减少不必要的LLM调用和环境交互。
- **通用性**：在两种不同环境（TDW-MAT物理仿真、C-WAH社交仿真）上均验证了有效性，且支持GPT-3.5和GPT-4。
- **解释性**：提供了丰富的定性案例（图4、图5）直观展示CoTS如何避免短视、优化分工、平滑执行。

## 8. 不足与局限
- **依赖LLM能力**：GPT-4显著优于GPT-3.5-turbo，LLM的推理质量直接影响搜索效果（如评估准确性）。
- **计算开销**：MCTS多路径搜索需要多次LLM调用，文中未定量分析额外时间与token消耗（附录A.2仅提及“成本可接受”但未给出具体数据）。
- **实验覆盖**：仅测试两个智能体协作（2-agent），未推广到更多智能体场景（如3-5个智能体）；未在真实机器人平台验证。
- **统计严谨性**：结果表格中未给出多次运行的方差或置信区间，可能掩盖随机性影响。
- **超参数敏感性**：分支因子、UCT探索系数w等参数需手动调整，文中仅测试分支因子影响，未详细分析其他参数。

（完）
