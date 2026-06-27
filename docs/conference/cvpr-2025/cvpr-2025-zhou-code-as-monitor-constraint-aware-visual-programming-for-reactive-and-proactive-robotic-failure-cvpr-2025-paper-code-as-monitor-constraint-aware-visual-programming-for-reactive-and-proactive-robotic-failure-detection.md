---
title: "Code-as-Monitor: Constraint-aware Visual Programming for Reactive and Proactive Robotic Failure Detection"
title_zh: 代码即监控器：用于机器人主动与被动故障检测的约束感知视觉编程
authors: "Zhou, Enshen, Su, Qi, Chi, Cheng, Zhang, Zhizheng, Wang, Zhongyuan, Huang, Tiejun, Sheng, Lu, Wang, He"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhou_Code-as-Monitor_Constraint-aware_Visual_Programming_for_Reactive_and_Proactive_Robotic_Failure_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: VLM用于机器人故障检测中的时空约束满足
tldr: 机器人系统中同时检测和预防开放性故障具有挑战性。本文提出Code-as-Monitor (CaM)，将故障检测统一为时空约束满足问题，利用VLM生成代码实时评估约束。实验证明CaM在多种机器人场景下有效检测预期和非预期故障，为VLM在机器人安全监控中的应用提供了新范式。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1791, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1811, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1800, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1802, \"height\": 644, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1802, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 795, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 808, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-code-as-monitor-constraint-aware-visual-programming-for-reactive-and-proactive-robotic-failure-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 208, \"label\": \"Table\"}]"
motivation: 现有方法难以同时实现反应式故障检测和主动预防。
method: 提出CaM范式，将故障检测转化为时空约束满足问题，利用VLM生成代码进行实时监控。
result: 在多种机器人任务上实现有效的开放集故障检测，优于基线方法。
conclusion: CaM为机器人安全监控提供了VLM驱动的新解决方案。
---

## Abstract
Automatic detection and prevention of open-set failures are crucial in closed-loop robotic systems. Recent studies often struggle to simultaneously identify unexpected failures reactively after they occur and prevent foreseeable ones proactively. To this end, we propose Code-as-Monitor (CaM), a novel paradigm leveraging the vision-language model (VLM) for both open-set reactive and proactive failure detection. The core of our method is to formulate both tasks as a unified set of spatio-temporal constraint satisfaction problems and use VLM-generated code to evaluate them for real-time monitoring. To enhance the accuracy and efficiency of monitoring, we further introduce constraint elements that abstract constraint-related entities or their parts into compact geometric elements. This approach offers greater generality, simplifies tracking, and facilitates constraint-aware visual programming by leveraging these elements as visual prompts. Experiments show that CaM achieves a 28.7% higher success rate and reduces execution time by 31.8% under severe disturbances compared to baselines across three simulators and a real-world setting. Moreover, CaM can be integrated with open-loop control policies to form closed-loop systems, enabling long-horizon tasks in cluttered scenes with dynamic environments.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：Code-as-Monitor

## 1. 论文的核心问题与整体含义
**研究动机与背景**：  
机器人执行长时域任务时，故障不可避免。现有方法难以同时实现两种故障检测模式：  
- **反应式检测**（reactive）：在故障发生后识别（如龙虾跳出平底锅）。  
- **主动式检测**（proactive）：在故障发生前预防（如平底锅倾斜导致龙虾滑落）。  
开放集场景（open-set）下故障类型未定义，传统基于VQA的VLM方法（如DoReMi）存在执行速度慢、3D时空感知不足、无法实现主动检测等问题。  
**整体含义**：提出CaM，统一两种检测模式为时空约束满足问题，利用VLM生成代码实时评估约束，实现高精度、实时的开放集故障检测。

## 2. 论文提出的方法论
**核心思想**：  
将故障检测转化为**时空约束满足问题**，通过VLM（GPT-4o）生成**监控代码**（monitor code），对约束元素（constraint elements）的3D位置进行算术运算，实时判断约束是否被违反。  
**关键技术细节**：  
- **约束生成器**（Constraint Generator）：基于多视角RGB-D观测、任务指令、上一子目标及反馈，利用VLM生成下一子目标和文本约束（C_d：执行中需保持的约束；C_u：完成后需满足的约束）。  
- **约束画师**（Constraint Painter）：  
  - 提出**约束元素**（constraint elements）：将约束相关的实体/部件抽象为紧凑几何元素（点、线、面）。  
  - 训练**ConSeg**模型（基于LISA+LoRA）：进行约束感知的实例级和部件级分割，输出元素类型描述和掩码。  
  - 多视图投影、体素化、聚类、连接，形成最终3D约束元素集E。  
- **约束监控器**（Constraint Monitor）：  
  - 将带标注的多视图图像（OE）作为视觉提示，由VLM生成Python代码（监控代码）。  
  - 代码接收约束元素的3D位置，执行NumPy运算（如计算法向量与z轴夹角），返回布尔值和失败原因。  
  - 使用CoTracker进行实时跟踪，避免频繁调用VLM。  

**算法流程（文字说明）**：  
1. 输入任务指令L_global、多视图观测O、上一子目标l_pre、失败反馈f_pre。  
2. 约束生成器输出下一子目标l_next和约束集C。  
3. 约束画师为每个约束c生成约束元素e，并标注到图像上得到OE。  
4. 监控器生成监控代码，实时跟踪元素位置，执行代码判断失败。  
5. 若失败则反馈并重新规划；若成功则继续下一子目标。

## 3. 实验设计
**数据集/场景**：  
- 三个模拟器：CLIPort（UR5+吸盘）、Omnigibson（Fetch+夹爪）、RLBench（Franka+夹爪）。  
- 一个真实场景：UR5+Leap Hand灵巧手，控制策略为DexGraspNet 2.0。  
- 数据集：基于BridgeData V2构建，10,181条轨迹、219,356张图像，含帧级子目标和约束标注，用于训练ConSeg。  
**Benchmark**：  
- 任务：堆叠方块、扫半方块、插笔、放书、倒茶、简单抓取、推理抓取等。  
- 引入扰动：点级、线级、面级（如物体移动、掉落、旋转、倾斜）。  
**对比方法**：  
- 基线：DoReMi（DRM）[15]、Inner Monologue [20]、CLIPort [54]、ReKep [21]。  
- 分割对比：PixelLM [50]、LISA-13B [28]、基础模型组合（FMC：GPT-4o + Grounded SAM + Semantic SAM）。

## 4. 资源与算力
**未明确说明GPU型号、数量、训练时长**。  
仅提及：ConSeg基于LISA（LLaVA + SAM）训练，使用LoRA微调，保持VLM和视觉编码器冻结；训练数据结合BridgeData V2和LISA原有数据。具体算力消耗未在论文中列出。

## 5. 实验数量与充分性
**实验数量**：  
- 模拟器：CLIPort 2任务 × 6种扰动设置 × 5种子×12试次；Omnigibson 3任务 × 3种扰动 × 10试次；RLBench 1任务（补充材料）。  
- 真实世界：简单抓取4种物体类型 × 每种3例 × 10试次；推理抓取2个长程任务 × 10试次。  
- 分割评估：ReasonSeg + 自主构建的ConstraintSeg基准（gIoU/cIoU）。  
- 消融实验：多视图、约束分割、元素连接、训练数据成分（语义/参考/VQA/实例/部件）等。  
**充分性与公平性**：  
- 环境多样性较高（3个模拟器+真实世界，不同机器人/末端执行器/干扰类型）。  
- 与多个强基线对比（含VLM方法ReKep+DRM、纯策略方法CLIPort等），结果具有竞争力。  
- 消融实验覆盖关键设计（多视图、分割模型、元素形成、训练数据），验证了各模块贡献。  
- 但部分任务（RLBench）结果仅在补充材料中，主文实验规模不够大。另外，真实场景仅两个任务，未覆盖更复杂操作（如装配）。

## 6. 论文的主要结论与发现
- CaM同时实现反应式和主动式故障检测，在严重扰动下成功率平均提升28.7%，执行时间减少31.8%。  
- 约束元素有效抽象相关实体/部件，提升监控精度、效率和泛化性。  
- ConSeg在约束感知分割上远超现有方法（部件级gIoU提升近40%）。  
- 结合开放环策略可形成闭环系统，处理动态环境和人类干扰下的长时域任务。  
- 代码评估比频繁VLM查询更精确、更高效（Omnigibson中token减少52.2%）。

## 7. 优点
- **统一框架**：首次将反应式和主动式故障检测整合为同一约束满足问题。  
- **高效实时**：监控代码仅生成一次，后续通过跟踪元素执行，避免重复调用VLM。  
- **强泛化性**：约束元素抽象化，适用于未见物体、场景和任务（如不同末端执行器、灵巧手）。  
- **精确性**：基于3D位置的算术运算（如角度、距离）优于VLM对单张图像的3D理解。  
- **分割能力**：ConSeg在推理分割基础上增加了约束感知的部件级分割，精度显著优于通用分割模型。  
- **完整实验**：在多个模拟器和真实世界验证，消融实验证明各模块有效性。

## 8. 不足与局限
- **算力未说明**：未提供训练ConSeg的GPU型号、数量、时长，可复现性受限。  
- **实验覆盖不全面**：主文仅展示CLIPort和Omnigibson结果，RLBench结果在补充材料；真实任务仅两个，未涵盖更复杂交互（如装配、多步骤精细操作）。  
- **数据集规模较小**：ConSeg训练数据来自BridgeData V2子集（10k条轨迹），可能不足以覆盖所有开放集场景。  
- **依赖预训练模型**：VLM（GPT-4o）、追踪器（CoTracker）为黑盒，性能受其限制；GPT-4o需要API调用，存在延迟和成本。  
- **约束元素生成依赖精度**：深度图质量、多视图对齐误差会影响元素3D位置的准确性。  
- **主动检测能力有限**：文中主动检测主要针对可预见的几何约束（如倾斜、距离），对更复杂因果关系（如物理属性变化）可能无效。  
- **偏差风险**：任务设定和扰动是人工设计的，可能未覆盖真实环境中所有故障类型。

（完）
